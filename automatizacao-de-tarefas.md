#Automatização de tarefas

Se você chegou até aqui, meus parabéns! Até esse ponto, você já deve ter conhecimento para:

* Criar um repositório no Git e no GitHub contendo os arquivos de seu projeto versionados.
* Utilizar o terminal e o npm para instalar pacotes do NodeJS para facilitar o desenvolvimento de seu site/aplicação.
* Usar o npm para criar o package.json e listar, nesse mesmo arquivo, as dependências do seu projeto no momento da instalação.

Nós vimos o básico do NodeJS e do npm instalando o pacote [uglify-js](https://www.npmjs.com/package/uglify-js). Quando fizemos isso, ganhamos de presente um comando novo de linha de comando que podemos usar para minificar nossos arquivos javascript. Por favor, nunca mais entregue em produção seus arquivos javascripts de desenvolvimento.

Além do uglify, há uma série de outros pacotes super úteis no desenvolvimento front-end. Listarei alguns:

* [Autoprefixer](https://www.npmjs.com/package/autoprefixer). Com este módulo instalado  você escreve seus arquivos css sem se preocupar com os prefixos dos vendors (-webkit, -moz, -o, -ms). Ou seja, você escreve seu CSS normalmente e o autoprefizer escrfeve os prefixos pra você. 
* [Clean CSS](https://www.npmjs.com/package/clean-css). É um minificador para arquivos css.
* [Usemin](https://www.npmjs.com/package/usemin-cli). Procura no arquivo  html as chamadas para arquivos externos (javascript e css) e as substitui por uma única chamada a um arquivo concatenado.
* [Imagemin](https://github.com/imagemin/imagemin-cli). Reponsável por minificar suas imagens.


Há uma série de outros módulos úteis disponíveis no [https://www.npmjs.com](https://www.npmjs.com). Mas o fato é que, mesmo sendo uma mão na roda, executar estes comandos, um a um, no terminal, não me parece uma boa prática. Imagine que toda vez que você efetuar uma alteração no seu arquivo fonte (arquivo de edição), você tenha que executar uma série de comandos no terminal. Um comando para concatenar os seus javascritps num arquivo só. Outro comando para minificá-lo. Outro ainda para minificar as suas imagens e outro para substituir as chamadas aos seus arquivos externos no seu html. Não seria produtivo e esse workflow seria abandonado muito rapidamente. E é aí que entram os automatizadores de tarefas.

Há dois principais automatizadores de tarefas, o [grunt](http://gruntjs.com/) e o [gulp](http://gulpjs.com/). Vou focar somente no primeiro pois, quando eu comecei meus estudos, tinha muito mais plugins disponíveis para a instalação.

O Grunt funciona da seguinte forma: você escreve uma lista de tarefas e atribui à essa lista um nome, por exemplo, 'deploy'. Toda vez que você chamar no terminal esse 'deploy', uma série de comandos será executada, ou seja, você poderá, de uma única vez, executar as seguintes tarefas:
1. Autoprefixar os seus arquivos CSS.
2. Minificar o seu arquivo CSS autoprefixado.
3. Concatenar todos os seus arquivos javascripts num arquivo só.
4. Minificar esse arquivo, removendo quebras-de-linha, reduzindo nomes de variáveis e removendo os comentários.
5. Copiar alguns arquivos estáticos (como arquivos de vendors e imagens) para a sua pasta de deploy (que não é a mesma pasta de desenvolvimento).
6. Atualizar as chamadas nos arquivos htmls aos arquivos externos. 

Existem outras possibilidades ao trabalharmos com o Grunt, mas por hora, vamos focar no workflow descrito acima.

Te vejo no próximo tópico (ainda em desenvolvimento).



Esse guia ainda está em desenvolvimento. E ainda há muito o que eu falar.

Se quiser saber quando um novo tópico estiver disponível, [siga-me](http://twitter.com/tapmorales). Eu te aviso por lá.