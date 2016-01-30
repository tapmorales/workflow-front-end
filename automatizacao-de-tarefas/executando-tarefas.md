#Executando Tarefas

## Autoprefixer.

A nossa primeira tarefa será incluir, automaticamente, os vendors prefixers no nosso arquivo css. Vale saber que este plugin utiliza as informações disponíveis no [caniuse](http://caniuse.com/) para decidir qual vendor incluir no arquivo css. Para isso, o autoprefixer se baseia sempre nas duas últimas versões de cada browser (mas isso é configurável).

Abra o seu Gruntfile no editor de código e substitua:

```javascript

autoprefixer: {

},

```

por:

```javascript

autoprefixer: {         
    dist: {
       files: {
             'deploy/css/main.css': 'source/sass/main.css',
       },
    },
},


```

 A configuração desse arquivo é tão simples que acredito ser auto-explicativo.

Você pode verificar outras opções de configurações na própria página do plugin. [https://www.npmjs.com/package/grunt-autoprefixer](https://www.npmjs.com/package/grunt-autoprefixer)


Você pode testar se o autoprefixer está funcionando digitando no terminal:

```javascript

 $ grunt autoprefixer 

```

Você deverá ver uma mensagem "Done, without errors", indicando que correu tudo bem.

Abra o seu css gerado na pasta de deploy e veja os prefixos do linear gradiente. Veja que eu os escrevi como manda a especificação (to top) e o autoprefixer incluiu o gradiente como fazíamos antes da especificação (bottom).

Repare também que nada mudou com o text-shadow, isso porque o autoprefixer não cria fallbacks. Ele simplesmente acidionar os prefixos, se estes existirem.


## Minificando o CSS
Depois que o CSS foi gerado, nós podemos reduzir um pouco o tamanho desse arquivo minificando-o. Na prática, nesse exemplo simples o resultado será praticamente imperceptível (alguns bytes), mas se você estiver trabalhando num projeto maior, mesmo que consiga reduzir alguns kbytes valerá a pena devido à simplicidade desse processo.

Para esta tarefa, usaremos o plugin [cssmin](https://www.npmjs.com/package/grunt-contrib-cssmin).


Substitua no lugar adequado no seu Gruntfile

```javascript

cssmin: {
    dist: {
     files: {
          'deploy/css/main.css': 'deploy/css/main.css'
       }
    }
},
    


```

Repare que nós estamos minificando o arquivo que foi prefixado, já na pasta deploy. OK!

Rode no terminal ``` $ grunt cssmin ``` e veja o que acontece


##Minificando e concatenando seus javascripts

A nossa próxima tarefa é minificarmos e concatenarmos nossos arquivos javascript. Para isso, vamos usar o [uglify](https://www.npmjs.com/package/grunt-contrib-uglify).

Da mesma forma que fizemos anteriormente, altere o seu Gruntfile, incluindo no lugar adequado o seguinte código:

```javascript

uglify: {
    options: {
      mangle: true
    },

    dist: {
      files: {
        'deploy/javascript/app.min.js': [
        'source/javascript/incrementButton.js', 
        'source/javascript/date.js'
        ]
      }
    },
}


```
 
Moleza. A propriedade do objeto files é o arquivo que será gerado. O valor dessa propriedade é um array de arquivos, ou seja, o uglify irá concatenar cada um dos arquivos descritos na array num único arquivo.

O opção true para o mangle faz com que a minificação seja mais pesada, alterando, quando possível, o nome de algumas variáveis para reduzir ainda mais o tamanho do arquivo.

Para ver o uglify em ação, você pode digitar no terminal:

```$ grunt uglify```

Sempre abra o arquivo gerado no seu editor de código para ver o resultado.

Um detalhe importante: boa prática não minificar arquivos já minificados, como bibliotecas de terceiros.

 

## Copiando arquivos estáticos

Uma tarefa bastante trivial é ter que copiar alguns arquivos estáticos para a pasta de deploy, como por exemplo: arquivos de imagens, arquivos de fontes, javascripts de terceiros, etc. Para essa tarefa, não usaremos o CTRL+C e CTRL+V, mas sim o plugin [copy](https://www.npmjs.com/package/grunt-contrib-copy). 

Da mesma forma que os plugins anteriores, substitua no lugar apropriado de seu Gruntfile.js

```javascript

copy: {
    dist: {
         files: [
            {src: 'source/vendor/*', dest: 'deploy/vendor/'}
        ]
    }
},


```

A diferença é que agora a propriedade files não é mais uma string, mas sim um array de objetos. 

Na verdade, o exemplo anterior funcionaria sem precisarmos de um array, ou seja, se fizéssemos dessa forma:

```javascript

copy: {
  dist: {
   src: 'source/vendor/*', 
   dest: 'deploy/'
  },
},

```


Mas a questão é que dificilmente temos que copiar somente um diretório, ou seja, escrevendo com array você poderá copiar mais de um diretório sem grandes problemas. 

Por exemplo:




```javascript

copy: {
  dist: {
     files: [
          {src: 'source/vendor/*', dest: deploy/vendor/'},
          {src: 'source/images/*', dest: deploy/images/'},
          {src: 'source/fonts/*', dest: deploy/fonts/'},
     ]    
  }
}

```


É hora de verificarmos se o que fizemos deu certo. Abra o seu diretório deploy e veja como ficou. Os arquivos foram copiados? A estrutura de pasta está certa? Ficou como esperávamos? Eu acho que não.

A questão é que o Grunt copiou os arquivos, mas não da maneira como estávamos imaginando. Quando configuramos o Grunt dessa forma: ``` {src: 'source/vendor/*', dest: 'deploy/'} ``` o que esperávamos era que todos os arquivos inseridos na pasta vendor fossem copiados para deploy/vendor. Mas na prática, o que o Grunt fez foi copiar o caminho completo, desde source, para dentro de deploy. O resultado foi o seguinte caminho: deploy\vendor\source\vendor. Bem estranho, não é mesmo?

Para resolver, precisamos dizer ao Grunt para para, no momento da cópia, se basear relativamente ao diretório source, mas não incluí-lo na cópia. Para isso:

```javascript

expand: true, //habilita o cwd
cwd: 'source/', //relativo ao diretório source, mas não o inclui na cópia   


```


A configuração final de nosso copy ficou assim:

```javascript

copy: {
  dist: {
    expand: true, //habilita o cwd
    cwd: 'source/', //relativo ao source, mas não o inclui na cópia      
    src: 'vendor/*', 
    dest: 'deploy/',                
  }
},

```


Para finalizar, falta configurarmos a cópia da nossa index.html. Veja como deve ficar. 

```javascript

copy: {
  dist: {
    files: [
        {
            expand: true, //habilita o cwd
            cwd: 'source/', //relativo à source, mas não a inclui na cópia      
            src: 'vendor/*', 
            dest: 'deploy/'
        },
        {
            expand: true, //habilita o cwd
            cwd: 'source/',
            src: 'index.html', 
            dest: 'deploy/'}
    ]        
  }
},


```


Tudo copiado conforme esperávamos, mas ainda resta alguns problemas: O arquivo index.html faz as chamadas às folhas de estilo e ao javascript da seguinte forma:

```html

<link rel="stylesheet" href="sass/main.css">

<script src="javascript/date.js"></script>
<script src="javascript/incrementButton.js"></script>

```


Precisamos atualizar a inclusão do javascript apontando para o arquivo concatenado e minificado e também arrumar o caminho do css, apontando para a pasta correta (nós trocamos o nome do diretório de "sass" para "css", e isso causou um problema de referência)


Eu já trabalhei com dois plugins do GruntJS para resolver esse tipo de problema:
*[https://www.npmjs.com/package/grunt-useref](https://www.npmjs.com/package/grunt-useref)
*[https://github.com/yeoman/grunt-usemin](https://github.com/yeoman/grunt-usemin)

Para o nosso guia, eu simplesmente vou pedir que você altere a chamada do main.css e app.min.js em "souce" e execute o copy novamente.

Se você quiser deixar mais profissional, tente por conta própria usar um dos plugins descritos acima. Senão, basta alterar o caminho do css e do javascript.


## Limpando o diretório antes do deploy

A cereja do bolo é fazer com que, antes de cada deploy, o grunt apague todos os arquivos da pasta de destino. Isso garante que não sobre arquivos indevidos no nosso diretório de deploy, como por exemplo imagens ou fontes que não são mais utilizadas.

Para isso, vamos usar o [grunt-contrib-clean](https://www.npmjs.com/package/grunt-contrib-clean).


```javascript

clean: {
  dist: {
    src: ["deploy"]
  }
}


```

Esse comando irá limpar deletar o nosso diretório deploy. Não é difícil perceber que o comando ``` $ grunt clean ``` deve ser executado antes de qualquer outro comando.


Ou seja, no nosso terminal, devemos executar os seguintes comandos, nessa ordem:

```javascript

$ grunt clean
$ grunt autoprefixer
$ grunt cssmin
$ grunt uglify
$ grunt copy

```

Eu acho que seria interessante se tivéssemos como executar apenas um comando no terminal e o próprio grunt executássemos quantas tarefas fossem necessárias. E advinha: isso é possível. É o que veremos a seguir. 