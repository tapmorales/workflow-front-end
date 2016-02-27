##Declaração @import

Uma coisa bem legal no sass é que podemos separar os nossos códigos em vários arquivos e importá-los num arquivo ‘pai’. Apesar da semelhança de escrita de um import do css, a importação do scss é totalmente diferente. Se em css puro o import não é bem visto por ter problemas com o cache e com múltiplas requisições http, em sass ele é quase que obrigatório. O import do sass faz com que os blocos de códigos sejam inseridos num único arquivo. Logo, o resultado será um arquivo contendo todos os blocos, um a um, na ordem em que foram inseridos.

Abra o seu main.scss e digite o seguinte:

```css
@import "base/variables",
        "base/base";

```
Repare que não precisamos incluir o underline nem a extensão. O Sass já sabe do que se trata. Se você incluir o underline ou a extensão, tudo continuará funcionando da mesma forma.

Agora sim, rode o seu grunt sass no terminal e veja o resultado.