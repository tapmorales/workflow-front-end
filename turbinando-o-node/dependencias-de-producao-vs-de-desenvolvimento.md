#Dependências de produção vs. de desenvolvimento

Há dois tipos de dependências em projetos NodeJS. Vamos estudá-las.

##Dependências de produção
São aquelas dependências que precisam estar em produção para que seu projeto funcione. Por exemplo: jquery, angular, bootstrap etc. 
Se você deseja instalar um módulo de produção, basta digitar em seu terminal:

```$ npm install <pacote> --save ```


Espero que você entenda porque não faz sentido digitar o seguinte:

```$ npm install <pacote> -g --save ```



##Dependencias de desenvolvimento
São as dependencias que não precisam ser levadas para produção. Estes módulos são usados apenas em ambiente de desenvolvimento. Alguns exemplos são os módulos que você instala para minificar, concatenar arquivos e até mesmo rodar alguns pré-processadores de css.

Para incluir no package.json uma depdendencia de desenvolvimento, basta digitar a flag --save-dev, como no exemplo:


```$ npm install <pacote> --save-dev```


Três informações importantes:


---


1. Na prática, os comandos acima criam duas novas propriedades no arquivo package.json, cada uma contendo um objeto, são elas: dependencies e devDependencies, usadas para listar as dependencias de produção e de desenvolvimento, respectivamente.

2. Alguns devs gostam de diferenciar o gerenciador de pacotes de produção e desenvolvimento. Eles utilizam um gerenciador de dependencias exclusivo para o ambiente de produção chamado bower. Eu acho isso uma boa prática. Mas como não vou incluir nenhum arquivo de terceiro, não vou me preocupar com as dependencias de produção. Contudo, tenha em mente que projetos na vida real utilizar o bower pode ser uma boa estratégia. 

3. Se você instalou todas as dependências de seu projeto usando a flag --save, estas estão listadas no seu arquivo package.json. Isso significa que você não precisa versionar seu diretório node_modules, o que é uma boa prática. Se você ou outra pessoa precisar rodar seu projeto em outra máquina, basta digitar no terminal ```$ npm install``` que todas as dependências serão instaladas de uma única vez. É possível dizer ao Git que você não quer versionar seu diretório de módulos criando um arquivo .gitignore contendo simplesmente o nome da pasta "node_modules". Lembre-se de incluir esse arquivo .gitignore no versionamento com o ```$ git add .gitignore``` ou ```$ git add .```



---



Pois bem. Até o momento aprendemos a diferenciar os pacotes de desenvolvimento/produção e instalações globais/locais. A sua lição de casa é dar uma olhada no [bower](http://bower.io/). Você verá que com o conteúdo que aprendeu até aqui, será capaz de instalar e utilizar essa ferramenta para gerenciar suas dependências de produção.

<!--Esse guia ainda está em desenvolvimento. E ainda há muito o que eu falar.

Se quiser saber quando um novo tópico estiver disponível, [siga-me](http://twitter.com/tapmorales). Eu te aviso por lá.-->