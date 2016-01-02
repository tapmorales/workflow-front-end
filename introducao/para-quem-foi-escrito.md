# Para quem foi escrito


Com este material pretendo ajudar a galera que está começando agora e que já conhece e consegue se virar com Javascript, HTML e CSS. Se você se identificar com alguns dos aspectos abaixo, esse material é pra você:

* Manjo de javascript mas gostaria de saber mais sobre o novo workflow front-end para desenvolvimento de sites ou sistemas.
* Quando abro um tutorial na internet que começa com uma frase parecida com “Para começar, digite sudo npm install …”, ou - pior ainda - “Basta você digitar npm install …”, fecho-o imediatamente antes que me contamine.
* Sei da importância da performance de um site ou sistema, mas continuo entregando os mesmos javascripts de desenvolvimento em produção. 
* Versionamento? Claro! Sempre copio e colo a pasta de projetos colocando a data no nome da pasta. Além disso, nunca apago um trecho de código javascript. Sempre comento código velho que não está sendo mais necessário. Vai que eu precise dele no futuro. Nunca se sabe!
* Eu ainda uso o bom e velho FTP para subir meus arquivos no servidor. Nunca falha.


Se você se identificou com alguns pontos descritos acima, espero que este material seja útil para você.


## Se resolver continuar a leitura, você:


* Irá perder o medo do terminal.
* Irá conhecer um dos pré-processadores mais famosinhos do momento: o Sass.
* Concatenará e minificará seus javascripts e css. Acredite: é moleza e vale a pena.
* Nunca mais irá comentar códigos velhos com medo de precisar deles no futuro.
* Nunca mais irá colocar seus arquivos de desenvolvimento em produção.
* Não se assustará se abrir um tutorial na net que começa pedindo para você digitar algo começando com npm install. Você saberá o que isso significa e onde deverá digitar esse código maluco.


Ou seja, No final deste livro (se é que posso chamá-lo assim), você terá uma base sólida para iniciar o desenvolvimento de aplicativos para a web. Hoje em dia, saber HTML, CSS e Javascript não é suficiente. Você precisa conhecer versionamento (Git e Github). Você precisa instalar uma ferramenta de build (Grunt ou Gulp). Você precisa saber manipular um gerenciador de dependencias (NPM ou NPM + Bower), e se souber também um pouco sobre pre-processadores CSS, terá uma maior produtividade e acrescentará no teu currículo.


## O que você não verá aqui


* Detalhes sobre javascript, jquery, css e html. Espero que você já possua esses pré-requisitos.
* Não vou desenvolver nenhum sistema do zero, e você não será um ‘ninja’ em Node.js. Meu intuito é fazer com que você saiba o básico, que eu adoraria que alguém tivesse me contado quando comecei a desenvolver aplicativos para a web.
* Não vou explorar nenhum framework em particular. Pelo menos não por enquanto. 
* Mesmo sobre os assuntos que me proponho a explicar, por vezes não serei 100% fidedigno. Me proponho a explicar de um jeito fácil de entender. Provavelmente, se alguém tivesse feito isso comigo quando eu estava começando a entrar nesse terreno, algumas pedras sairiam do caminho antes de eu tropeçar. Pense assim: Se você tivesse que explicar javascript para alguém que está começando, provavelmente você não se preocuparia em explicar sobre escopo de variáveis.  Estou quase certo que as suas variáveis estariam todas no escopo global. E sabemos que isso não é uma boa prática. Contudo, se entrar muito nesse nível de detalhe talvez você assuste o iniciante e o faça desistir antes mesmo de tentar. Nesse caso, não importa que o seu código se pareça com: <br>
``` var texto=”Olá mundo”; ```<br>
```alert(texto);```<br>
Mesmo que isso não seja uma boa prática é fácil de entender. Lembre-se: os meus exemplos não têm a intensão de serem escritos como na vida real, contudo, espero te mostra a base para que, depois, você possa avançar com os seus estudos.






## Softwares utilizados:




### Sistema Operacional:


Eu sei que há na comunidade um certo estrelismo por quem usa o mac ou linux. Não quero entrar nesse mérito. Sei também que há um certo preconceito com o windows. Também não quero discutir isso. Mas o fato é que eu, desde o começo da minha carreira, trabalhei com windows. Portanto, não vou escrever nada que eu não tenha proficiência. Tudo que você verá aqui é voltado para o windows. Muitas coisas irão servir mesmo que você use o mac ou linux, mas não me comprometo com isso, uma vez que não tenho know-how nesses sistemas. Combinado?


### Editor de código:


Há vários editores de código disponíveis no mercado e você provavelmente utiliza o Sublime Text com o package manager instalado e, no mínimo, o emmet. Isso não é primordial, mas sugiro que dê uma olhada no Sublime, se ainda não o conhece. 
Não faz diferença, nesse momento, se você usa o Notepad++, o Text Edit, o Brackets ou o Dreamweaver. Antes que chova pedra na minha cabeça, quero me explicar: já ví códigos muito mais semânticos e corretos escritos no Dreamweaver do que códigos escritos por pessoas que se achavam cools só porque usavam o Notepad ou Sublime. A ferramenta não é importante. O que importa é o desenvolvedor. É claro que com o tempo os devs com mais experiência tendem a abandonar o Dreamweaver e começar a utilizar um editor de código melhor. Mas isso não importa realmente. Se você usa o Dreamwevaer, pense em ao menos experimentar algo diferente. E por falar nisso, eu comecei a escrever HTML usando o programa até então da Macromedia. Foi de lá que vieram os meus primeiros ```<h1>```’s. E não há nada de errado nisso.



No próximo capítulo iremos entender de uma vez por todas o que é o nodejs, o NPM e o que é um programa do tipo terminal. 
