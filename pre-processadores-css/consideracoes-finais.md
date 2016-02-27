#Considerações Finais

A abordagem apresentada até este ponto não é a única possível, mas o meu intuito não é te apresentar tudo que está disponível no Sass, mas sim te mostrar os primeiros passos para que você consiga desenvolver os seus estudos. [Nesse site](http://sass-lang.com/guide) há mais alguns exemplos básicos sobre a utilização do Sass, em especial, veja com atenção sobre @extend  e operadores.

Todo esse conhecimento passado até aqui foi bem básico, mas se você quiser conhecer o Sass pra valer, vá até a [documentação](http://sass-lang.com/documentation/file.SASS_REFERENCE.html). 

Antes de finalizarmos, devemos remover as referencias aos arquivos .map. 


##Removendo o sourceMap de produção

Lembra que eu falei que não devemos colocar em produção os arquivos .map e que devemos remover as referências à estes arquivos? Pois então, para fazer isso, basta incluir uma opção nas configurações do Sass em nosso Gruntfile.js. Veja:

```javascript

sass: {
    options: {
        sourceMap: false
    },          
    dist: {
       files: {
              'deploy/css/main.css': 'source/sass/main.scss',
       },
    },
}



```

##automatização da automatização

Para compilar seus arquivos, você pode digitar no terminal o nome da sua tarefa ou fazer com que, toda vez que um arquivo .scss seja alterado e salvo, o GruntJS rode automaticamente e tarefa necessária. 
Para isso você precisará instalar o [watch do grunt](https://github.com/gruntjs/grunt-contrib-watch). Este wrapper é responsável por monitorar alterações nos seus arquivos (.scss, por exemplo) e rodar determinadas tarefas quando estes arquivos forem salvos. Dessa forma, configurando corretamente, você consegue fazer com que o grunt rode a sua tarefa sass toda vez que um arquivo .scss for salvo, sem que você tenha digitar o tempo todo comandos no terminal para esta tarefa.


##Fallback com o Modernizr

No componente buttonsContainer, você pode utilizar o sinal de & para criar um fallback de css para quando o browser não tiver suporte à todas as features utilizadas em nossa folha de estilo. 

##Uma palavra sobre o BEM.

Nesse ponto nosso arquivo está funcionando perfeitamente. Vimos como trabalhar com variáveis, @mixins/@include,seletor & e aninhamento de seletores. Dei uma rápida passada sobre as @function/@return e pedi para que você visse por conta própria sobre @extend e os operadores. Isso cobre uma parte de qualquer pré-processador, mas fique ciente que ainda há muito que não foi discutido.

Para encerrar, gostaria de sugerir que você use com cautela o aninhamento de seletores. O meu exemplo foi para uso didático, mas creio que possa ser melhorado. 

Se olharmos com atenção para a metodologia BEM, vemos que não faz muito sentido termos seletores desse tipos:

```css
.buttonsContainer .buttonsContainer__button
```

O seletor acima poderia ser facilmente substituído por:
```css
.buttonsContainer__button
```
Concorda? 

Se achar válido, altere seus arquivos .scss para deixar os seletores do arquivo compilado  mais simples, quando possível.