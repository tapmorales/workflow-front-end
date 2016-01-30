# Comandos básicos Unix para manipulação de arquivos

Você já efetuou várias tarefas de manipulação de arquivos usando um interface gráfica. Já criou, deletou, renomeou arquivos e pastas e já moveu arquivos dentro do seu HD. Você está tão acostumado a fazer isso com o mouse que parece uma idiotice ter que aprender a fazer isso via linha de comando. A primeira impressão é que você perderá muito mais tempo digitando comandos extensos do que simplesmente dando alguns cliques no mouse e/ou alguns atalhos do teclado. Talvez você esteja certo. Mas talvez não. Mesmo que se no final deste capítulo você continuar usando a interface gráfica para efetuar estas tarefas, é bom conhecer outras possibilidades. O fato é que saber operar o terminal é primordial se você quiser evoluir na área de desenvolvimento front-end, e conhecer o mínimo de manipulação de arquivos é um excelente ponto de partida.

Uma vez que você instalou o Git for Windows na sua máquina da maneira como eu descrevi na seção anterior, você ganhou de presente o “Git Bash”, que é um programa do tipo CLI (command line interface) que simula um terminal do Unix no Windows, além de permitir que você digite os comandos do Git. 

Abra o Git Bash de maneira trivial, procurando-o no menu iniciar ou em algum atalho criado na instalação.

A primeira observação importante é que, para cada usuario presente na máquina há uma pasta chamada “pasta pessoal” (também conhecida como pasta "Home"). No Windows, essa pasta fica em c:/Users/Seu_usuario. Ao abrir o Git Bash pela primeira vez você estará "visualizando" essa pasta, muito provavelmente. 

Uma outra maneira de abrir o Git Bash a partir do Windows é clicar com o botão direito do mouse dentro de um diretório qualquer e selecionar a opção "Git Bash Here". Nesse caso você não estará visualizando a sua pasta pessoal, mas sim a pasta a partir da qual você abriu o Git Bash.

A segunda observação importante é que você provavelmente está vendo algo parecido com:

seu_usuario@host MINGW64 ~
$

Vamos entender o que é cada informação acima.

* Antes do arroba é o seu usuário logado no sistema. 
* Depois do arroba significa o nome da sua máquina, ou host. 
* MINGW64 é uma variável de sistema. Não se preocupe com ela. 
* ~ é um atalho para sua pasta "Home". (é o mesmo que sua pasta pessoal, mas o nome "Home" é mais correto, pois é assim que é chamado em ambientes Linux). Se você não estiver vendo esse sinal de til, provavelmente você abriu o terminal com o botão direito do mouse sobre um diretório qualquer. Para acessar sua pasta Home, digite ```$ cd ~``` e aperte o enter. 
* O sinal de cifrão significa que você é um usuário padrão da máquina.

Para ter certeza de qual diretório está sendo visualizado, digite no terminal (A partir desse ponto, sempre que eu me referir ao terminal, ou linha de comando, estarei falando do Git Bash, ok?):


```$ pwd```

Esse comando significa “print working directory” e serve para visualizar a pasta corrente

Se você quiser visualizar os arquivos e pastas não ocultas no diretório corrente, basta digitar:

```$ ls```

Esse comando é parecido com o comando ‘dir’ do MSDOS, porém, estamos simulando um ambiente Unix e o comando dir não existe nesse ambiente.

Se você quiser entrar em alguma pasta, basta digitar o comando ```cd``` (change directory). Por exemplo:

```$ cd Desktop```

A partir desse ponto você está visualizando a sua área de trabalho, experimente efetuar novamente os comandos ```ls``` e ```pwd``` nessa pasta.

Se você quiser voltar um nível, basta digitar

```$ cd ..```

O sinal ".." significa "um nível acima". Nesse ponto estamos novamente acessando a pasta pessoal. Tente voltar dois níveis de uma vez:

```$ cd ../.. ```

Agora estamos visualizando o C:. Para voltar para a sua pasta pessoal, você poderia digitar cd Users/seu nome ou simplesmente usar um atalho, como a seguir:

```$ cd ~ ```

o sinal "til" é um atalho que aponta para o seu diretório Home, lembra?

Se você quiser descobrir a pasta pessoal de qualquer diretório ou partição no seu computador, basta digitar :

$ echo ~

Esse comando te mostrará qual é a pasta pessoal mas não "navega" até ela


## Criar um diretório onde salvaremos todos os exemplos desse livro.

Eu recomendo que para os exemplos desse livro, você salve seus arquivos no seu diretório Home. No futuro, nos projetos da vida real, fique a vontade para trabalhar na estrutura de arquivos que você preferir. O motivo é que ao trabalharmos no diretório Home, nós temos a mesma estrutura de pastas e arquivos, sendo assim ficará mais fácil e mais didático acompanhar a leitura deste guia.

Antes de criarmos o diretório principal, tenha certeza que você está lugar certo, digite
```$ cd ~```

Como vimos, esse comando fará você acessar a sua pasta pessoal, independente de qual diretório estiver sendo acessado anteriormente.

Confirme isso digitando 
```$ pwd```

Nesse ponto, vamos criar um diretório que conterá todos os exemplos deste livro. Digite:
```$ mkdir Projects```

Esse comando criará um diretório chamado Projects. Para ter certeza que foi criado corretamente.
```$ ls```

Você deverá visualizar a pasta “Projects” na lista que aparecer no terminal. Criamos o diretório, mas ainda não estamos “dentro” dele. Como fazemos mesmo para trocar o diretório corrente? ```$ cd Projects```. Isso mesmo. Mas nesse ponto eu quero te dar uma dica. O Git bash possui um autocomplete que facilita muito a nossa vida. Para vê-lo em ação, tente digitar:
```$ cd Pro``` (se sem continuar a palavra, aperte TAB do teclado. Faça uns testes com ```$ cd P``` (TAB), ```$ cd Pr``` (TAB). Veja o que acontece. Muito útil.

Será que está tudo certo? Se estiver no diretório Projects, digite ```$ pwd``` para vermos o diretório corrente. Observe que, como este diretório está vazio, digitar ```$ ls``` não produzirá nenhum resultado.

Já temos o básico necessário para começarmos a versionar nossos arquivos com o Git. Mas é claro que há muito mais comandos Unix para aprender. Se você quiser estudar por conta própria, sugiro alguns comandos iniciais: cp, mv, rm e rmdir. Com esses comandos você consegue fazer tudo o que fazia com o mouse e o Windows, só que agora via terminal. Não é só uma questão de se sentir cool. Mais cedo ou mais tarde você precisará editar um arquivo diretamente no servidor, e para fazer isso, você precisará de um editor de código do tipo terminal, como o VIM ou o Emacs (dê tchauzinho ao seu Sublime Text nessas situações).  

