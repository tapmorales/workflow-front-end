# Fundamentos do GitHub

Ainda me lembro como se você ontem. Foi no final de 2012 que desenvolvi meu primeiro plugin jQuery.
O plugin era muito simples e resolvia um problema que frequentemente eu enfrentava: igualava as alturas de vários elementos flutuantes de acordo com a altura do maior elemento na mesma linha. Hoje há formas de resolver este problema apenas com o CSS, mas naquela época, me facilitou muito a vida e resolvi compartilhar o meu feito com o mundo inteiro. 

E onde deveria "hospedar" o meu código? Já havia usado o GitHub para "baixar" javascripts de terceiros, portanto, "subir" meu próprio código não deveria ser difícil.

Depois de me cadastrar no site, procurei imediatamente um botão para upload, sem sucesso. Não havia (e não há um botão upload de arquivos no GitHub). Tudo bem, talvez eu tenha sido o único idiota que tenha procurado esse botão no GitHub, mas naquele momento, a minha vida teria sido mais fácil se alguém mais experiente tivesse me explicado:

"O GitHub não é um lugar para você hospedar seus arquivos lá. Ele é um serviço que possibilita você deixar o seu repositório GIT na nuvem."

##Assim no Git como no GitHub.

Até o capítulo passado, todo o versionamento (```git init```, ```git add```, ```git commit``` etc) era efetuado na sua máquina. Isso resolve um problema: se algo der errado, é fácil voltar uma versão ou até mesmo comparar arquivos antes e depois de cada commit. Mas isso ainda não resolve alguns problemas:
* Se você trabalhar em equipe, cada desenvolvedor terá a sua própria versão. O que não é o ideal.
* Mesmo trabalhando sozinho, o ideal é que você não mantenha o seu versionamento de seu sistema somente na sua máquina. Assim, mesmo que a sua máquina pegue fogo, você poderá continuar trabalhando de qualquer outro lugar.

O GitHub não é a única solução para estes problemas. Você poderia, por exemplo, manter um repositório central no seu servidor e fazer todos os colaboradores clonarem os projetos de lá. É uma solução válida, contudo, pela facilidade, mostrarei aqui como manter seu repositório no GitHub. Entretanto, vale alertar que o GitHub é gratuíto para contas com projetos públicos. Se você precisar de um projeto privado, precisará de uma conta paga.

Dito isto, o primeiro passo é criar sua conta em [https://github.com/join](https://github.com/join).

Preencha o formulário com seus dados e depois escolha um dos planos. Pode criar uma conta gratuita para testarmos.

Depois da conta criada, você precisará criar um repositório de teste. Do lado direito, procure uma caixa "Your repositories" e clique no botão "upload". Brincadeira!. Clique em "new repository".  Dê um nome bonito para o seu repositório e lembre-se de deixá-lo como público. As demais configurações você pode deixar como está. Clique em "create repository". 

Prontinho. Você tem seu primeiro repositório (ainda vazio) criado. Agora vamos fazer a ligação entre o seu repositório local e o remoto.

O primeiro passo é configurar o repositório corretamente usando o terminal.

Acesse a pasta do nosso exemplo digitando no Git Bash:

```$ cd ~/Projects/PrimeirosPassosWorflow``` 

Lembre-se que o "~" é um atalho para a sua pasta pessoal.

Estando na pasta correta, digite o seguinte comando no seu terminal:

```$ git remote add origin https://Seu_usuario/seu_repositorio.git```

Repare que você precisa trocar o seu usuário e o nome do seu repositório no endereço acima. Se você não tiver certeza de ter escrito corretamente, procure na página inicial do seu repositório o lado direito onde está escrito: HTTPS clone URL

É essa URL que você precisa escrever no seu terminal (comando ```$ git remote```)

Com o comando anterior, você criou um vínculo do nome "origin" para o seu repositório que está lá no GitHub.

##Git Push e Pull

Uma vez criado o nosso apontamento do "origin" para o GitHub, o próximo passo é "subir" seus arquivos para a nuvem. Tendo certeza que você está na pasta correta, digite no terminal:

```$ git push origin master```

Na verdade, nós não estamos "subindo" nossos arquivos. Nós estamos enviando todo o histórico do versionamento. Explicando o comando acima:
```push``` é o comando que submete o versionamento para o seu repositório na nuvem.
```origin``` é o seu repositório remoto que, como dito antes, aponta lá para o GitHub.
```master``` é a sua branch principal. Não cabe aqui explicar em detalhes o que é uma branch, mas saiba que o nome "master" é um nome padrão criado pelo próprio Git. Recomendo deixar esse nome por enquanto.

Digite seu usuário e senha do GitHub e tecle ENTER. Se tudo correu bem, você já consegue ser sua versão na internet. https://github.com/Seu_usuario/seu_repositorio

Digamos agora que a sua máquina subiu no telhado e você precisa continuar o desenvolvimento da sua página exemplo01.html. Se você fez tudo certinho (```git commit``` e ```git push``` nos momentos adequados) basta você "baixar" seus arquivos de outra máquina (pode até ser emprestada) que contenha o Git instalado.

Para isso, crie uma pasta nesse novo computador que será o seu repositório local de todos os projetos (similar à nossa pasta "Projects") e a acesse no terminal com o comando ```cd```. Depois, digite:

```$ git clone https://Seu_usuario/seu_repositorio.git```

Esse comando fará uma cópia dos arquivos que estão no seu repositório lá no GitHub num diretorio com o mesmo nome de seu repositório (veja com o comando ```ls```). Agora não tem mais desculpa. Pode continuar o desenvolvimento do projeto. Quando tudo tiver feito (ou no final do dia de trabalho), faça um ```commit``` e suba tudo novamente no GitHub (```$ git push origin master```). Assim você garante que não haverá problema de perda de arquivos (e horas de trabalho) se a sua nova máquina resolver subir no teclado também.

Maravilha. Você continuou o trabalho usando uma máquina emprestada sem prejuízo algum. Mas a sua outra máquina foi para o concerto e ficou pronta. Tudo funcionando perfeitamente. Então você agradece e devolve a máquina emprestada e volta para a sua própria máquina. Como continuar com o desenvolvimento? Será preciso clonar novamente o repositório? Não. Se este ainda estiver configurado no computador, basta solicitar ao Git para atualizar os arquivos locais de acordo com o último ```commit``` que foi feito no GitHub. Para isso, digite no terminal (depois de acessar a sua pasta com o comando ```cd```).

```$ git pull origin master```.

Prontinho, não só os arquivos na sua máquina estão todos atualizados como você ainda mantém todo o histórico. Faça um teste digitando ```$ git log```.

Por hora é isso. Ainda há muito o que aprender sobre o Git mas o que eu apresentei aqui é o básico necessário para você continuar seus estudos.

Atualmente, saber manusear bem os comandos do Git (ou outro sistema de controle de versão) é requisito obrigatório em qualquer área de desenvolvimento (web, app, mobile, front-end, back-end etc). 

Se você não conhecia nada sobre o assunto, eu espero que tenha conseguido te dar uma luz. Se já conhecia, espero que tenha acrescentado algo novo.

No próximo capítulo vou mudar um pouco de assunto e falar sobre npm e automatização de tarefas. Espero que continue a leituira. Até lá!

<script>
  (function(i,s,o,g,r,a,m){i['GoogleAnalyticsObject']=r;i[r]=i[r]||function(){
  (i[r].q=i[r].q||[]).push(arguments)},i[r].l=1*new Date();a=s.createElement(o),
  m=s.getElementsByTagName(o)[0];a.async=1;a.src=g;m.parentNode.insertBefore(a,m)
  })(window,document,'script','//www.google-analytics.com/analytics.js','ga');

  ga('create', 'UA-73075491-1', 'auto');
  ga('send', 'pageview');

</script>