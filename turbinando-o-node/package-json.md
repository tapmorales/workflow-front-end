#Package.json

Ora, há uma série de módulos prontos para serem utilizados em [https://www.npmjs.com/](https://www.npmjs.com/). Tem módulo para tudo que você imaginar. Mas você não pode sair instalando tudo globalmente no seu sistema como se não houvesse o amanhã. Você irá primeiramente trabalhar com esse módulo localmente, e além disso, como dito no tópico anterior, você pode querer trabalhar com este módulo apenas num projeto específico e depois excluí-lo da sua máquina. Ou seja, para que você não tenha problemas em manutenções futuras, você deverá anotar os módulos utilizados em algum lugar, para que no futuro você mesmo ou qualquer outra pessoa possa instalar corretamente todos estes módulos e continuar trabalhando no projeto. Talvez você tenha pensado num LEIAME.txt, mas não, não faça isso. Uma melhor maneira de resolver esse problema é criar um arquivo chamado package.json contendo, entre outras coisas, os módulos necessários para que o projeto continue funcionando. Além de informar o nome do módulo você também pode incluir informação sobre a versão utilizada, o que pode ser muito útil no futuro.


---


Os projetos baseados em NodeJS usam um arquivo de configuração (manifest) chamado package.json 


---



[![Torne-se front-end com este curso 100% prático](../cta_livro.png "Torne-se front-end com este curso 100% prático")](https://www.udemy.com/ferramentas-front-end-git-npm-script-gulp-e-sass/?couponCode=PROMOLIVRO20 "12 horas de video. Apenas R$ 20,00. Acesso vitalício e sem mensalidades")




Um outro cenário é quando trabalhamos em equipe. Se eu estou desenvolvendo um projeto node, posso versionar o arquivo de configuração package.json, ignorando toda a pasta node_modules (que, como vimos, são os módulos instalados localmente). Se uma pessoa do meu time precisar desenvolver uma funcionalidade nova ou continuar o meu trabalho, ele deverá puxar do Git/GitHub (```$ pull origin```, lembra?) somente o package.json, não se importando com os módulos que instalei localmente. Pois estes módulos serão instalados automaticamente na sua máquina com apenas um comando na linha de comando:

```$ npm install```

Esse comando irá ler o arquivo package.json e instalar todas as dependências locais do projeto. Isso não é lindo?

Esse arquivo possui a seguinte aparência:

```
{
  "name": "PrimeirosPassos",
  "version": "0.0.1",
  "description": "Uma descrição do seu projeto",
  "main": "main.js",
  "repository": {
    "type": "git",
    "url": "http://github.com/tapmorales/meu_repositorio"
  },
  "keywords": [
    "array", "palavras chaves"
  ],
  "author" : {
    "name" : "Daniel Tapias Morales",
    "email" : "daniel@email",
    "url" : "http://www.meudominio.com/"
  },
  "homepage": "http://www.meu-projeto.org"
  "license": "ISC",
  "private" : true,
  "dependencies" : {
    "nome_do_modulo" : "x.x.x"
  }
}
```

Acredito que a maior parte desse arquivo seja autoexplicativo, portanto, não entrarei em maiores detalhes.

O que merece maior atenção é com relação à última propriedade chamada "dependencies", que é um objeto cuja chave é o nome do módulo dependência e o valor é a versão utilizada em sem projeto. Ao digitar em seu terminal ```$ npm install``` esse objeto será lido pelo npm e todos os módulos listados serão instalados automaticamente. Eu já falei que isso é lindo?

Mas aqui eu preciso chamar a sua atenção para um detalhe importante. Os projetos instalados globalmente não são listados como dependência. Essa é uma grande desvantagem da instalação global. Dito isso, vamos criar o nosso arquivo package.json.


##Mas como criar esse arquivo? É na unha?

Não precisa ser. Há um comando do npm que te ajuda a criar esse arquivo por meio de um assistente maroto. Tudo o que você precisa fazer é responder algumas perguntas e o arquivo de configuração será criado. Para abrir este assistente, digite no seu terminal:
```
$ npm init
```

Feito isso, a primeira informação que você precisará fornecer é o nome do seu projeto. Vá digitando e confirmando com o ENTER. Quando você não tiver certeza, pode apertar o ENTER mesmo sem preencher nada. Há qualquer momento, CTRL + C para sair do assistente.

No final, você verá como o seu arquivo json será criado. Aperte Enter para confirmar.

A partir de agora, sempre que você quiser instalar um novo módulo para utilizar em seu projeto e quiser mencioná-lo como dependencia no arquivo package.json, basta você passar uma flag no momento da instalação: ```--save```.



---


A flag ``` --save ```acrescenta uma nova configuração no package.json, informando qual o módulo e versão está sendo utilizado no projeto.


---



Mas antes de entrar em maiores detalhes, quero explicar para você que há dois tipos de dependências: as de produção e as de desenvolvimento. 

Mas isso é assunto para a próxima seção.



