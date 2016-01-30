#Pensando fora do Browser

O NodeJS é um programa escrito em C++ e baseado na engine V8 cuja principal função é poder ler e interpretar códigos javascripts fora do browser. 

A princípio, o NodeJS foi pensado para poder criar servidores web baseados em eventos javascripts. E isso ainda é perfeitamente possível.
Mas o fato é que você pode instalar e utilizar o node sem nunca necessariamente criar ou rodar um servidor baseado nele. Um exemplo: há um módulo do nodejs chamado uglify. (Um módulo é um arquivo javascript que você instala através do npm. Veremos isso detalhadamente em instantes). Uma vez instalado o uglify, você ganha de presente um novo comando no seu terminal. Esse comando faz com que o NodeJS seja capaz de ler um arquivo js e minificá-lo, automaticamente. Lindo né?

Uma coisa que devemos ter em mente é que um módulo do node pode ser instalado globalmente (no sistema, podendo ser usado em qualquer projeto) ou localmente (apenas no projeto atual).

## Instalando módulos no NodeJS

Assim que instalamos o node já temos o nosso primeiro módulo disponível para uso, que é o próprio node package management, ou seja, ganhamos um comando novo no terminal: ```npm```. Há uma flag que mostra um texto de ajuda sobre determinado comando: ```-h```. Então, digite no seu terminal:
```$ npm install -h```


Esse comando irá mostrar o texto de ajuda do comando install.

Sempre que você tiver dúvida sobre algum comando, habitue-se a sempre ver o texto de ajuda antes de procurar no stackoverflow. É uma excelente maneira de evoluir seus conhecimentos sobre determinada ferramenta.

Voltando: repare que no começo da ajuda há a seguinte linha: ```npm install <pkg>```, onde ```<pkg>``` é o pacote a ser instalado. 

Queremos instalar em nosso sistema o uglify, portanto, digite no terminal:
```$ npm install uglify-js -g```

a flag ```-g``` informa que você está instalando o pacote globalmente no seu sistema.

Você deve estar ser perguntando de onde o npm baixou os arquivos necessários para a instalação. A resposta: [https://www.npmjs.com/package/uglify-js](https://www.npmjs.com/package/uglify-js). O site [npmjs.com](https://www.npmjs.com/) é um repositório de pacotes desenvolvidos pela comunidade prontos para uso. Se o pacote estiver neste repositório, basta digitar seu nome logo após o comando ```install``` que o npm já sabe o que fazer. 
 
Se a instalação ocorreu com sucesso, você deverá ver no terminal, o local onde o módulo foi instalado (lembre-se que o instalamos globalmente no sistema com a flag ```-g```) e as dependências necessárias para este módulo funcionar.

Agora que temos um comando novo na linha de comando, vamos experimentar o seguinte comando:
```$ uglifyjs -h```

Eu confesso que a ajuda do uglify é um pouco extensa, mas não se preocupe, por hora, vamos simplesmente ver o uglify em ação.

A ideia é minificarmos o nosso arquivo app.js. Mas para isso, vamos editá-lo um pouco, como a seguir:

```javascript
	var body = document.body;
	var cor = 'red';

	var mudaCor = function(alvo, cor){
		alvo.style.color = cor;
	}

	mudaCor(body, cor);
```

Tudo deve continuar funcionando, entretanto, vamos minificar esse arquivo. Para isso, tenha certeza de que está na pasta PrimeirosPassosWorflow e digite no terminal:
```
$ uglifyjs js/app.js --output js/app.min.js
```

Se tudo correu bem, um novo arquivo foi criado. O NodeJS leu o se arquivo app.js e deu saída (```--output```) em outro arquivo, mas desta vez minificado. Abra-o no seu editor e veja o que aconteceu. Podemos ver que a minificação não foi lá essas coisas. Vamos corrigir isso. Digite no seu terminal: 

```
$ uglifyjs js/app.js --output js/app.min.js --mangle
```

A flag ```--mangle``` irá analizar o seu arquivo e irá substituir, onde possível, alguns nomes de variáveis para deixar o arquivo mais enxuto, reduzindo assim alguns kbytes de transferência de dados.

Se você olhar o arquivo minificado, verá que os nomes dos parâmetros da função ```mudaCor``` foram alterados para um caracter apenas. Bem melhor, não?
Há outras opções disponíveis no uglify. E há também uma infinidade de outros pacotes disponíveis no [npmjs.org](https://www.npmjs.com/). Mas o mais importante aqui é perceber que usamos o NodeJS e o npm para instalar um pacote globalmente e utilizamos esse pacote sem necessariamente termos configurado um servidor.

Precisamos entender agora a diferença entre instalar um pacote global (com a flag ```-g```) e um pacote local em nosso projeto. 


<script>
  (function(i,s,o,g,r,a,m){i['GoogleAnalyticsObject']=r;i[r]=i[r]||function(){
  (i[r].q=i[r].q||[]).push(arguments)},i[r].l=1*new Date();a=s.createElement(o),
  m=s.getElementsByTagName(o)[0];a.async=1;a.src=g;m.parentNode.insertBefore(a,m)
  })(window,document,'script','//www.google-analytics.com/analytics.js','ga');

  ga('create', 'UA-73075491-1', 'auto');
  ga('send', 'pageview');

</script>