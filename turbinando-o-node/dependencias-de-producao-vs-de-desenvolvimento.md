#Dependências de produção vs. de desenvolvimento

Há dois tipos de dependências em projetos NodeJS. Vamos estudá-las.

##Dependências de produção
São aquelas dependências que precisam estar em produção para que seu projeto funcione. Por exemplo: jquery, angular, bootstrap etc. 
Se você deseja instalar um módulo de produção, basta digitar em seu terminal:

```$ npm install <pacote> --save ```


Espero que você entenda porque não faz sentido digitar o seguinte:

```$ npm install <pacote> -g --save ```



##Dependencias de desenvolvimento
São as dependencias que não precisam ser levadas para produção. Estes módulos são usados apenas em ambiente de desenvolvimento. Alguns exemplos são os módulos que você instala para minificar, concatenar arquivos e até mesmo alguns pré-processadores de css.

Para incluir no package.json uma depdendencia de desenvolvimento, basta digitar a flag --save-dev, como no exemplo

``` $ npm install <pacote> -g --save-dev``` (globalmente)

ou:

```$ npm install <pacote> --save``` (localmente)


Duas informações importantes:
--
1 - Na prática, os comandos acima criam duas novas propriedades no arquivo package.json, cada uma contendo um objeto, são elas: dependencies e devDependencies, usadas para listar as dependencias de produção e de desenvolvimento, respectivamente.

2 - Alguns devs gostam de diferenciar o gerenciador de pacotes de produção e desenvolvimento. Eles utilizam um gerenciador de dependencias exclusivo para o ambiente de produção chamado bower. Eu acho isso uma boa prática. Mas como não vou incluir nenhum arquivo de terceiro, não vou me preocupar com as dependencias de produção. Contudo, tenha em mente que projetos na vida real utilizar o bower pode ser uma boa estratégia. 

--

Pois bem. Até o momento aprendemos a diferenciar os pacotes de desenvolvimento/produção e instalações globais/locais. A sua lição de casa é dar uma olhada no [bower](http://bower.io/). Você verá que com o conteúdo que aprendeu até aqui, será capaz de instalar e utilizar essa ferramenta para gerenciar suas dependências de produção. Assim eu espero.

Esse guia ainda está em desenvolvimento. E ainda há muito o que eu falar.

Se quiser saber quando um novo tópico estiver disponível, [siga-me](http://twitter.com/tapmorales). Eu te aviso por lá.