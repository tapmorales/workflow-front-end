# Versionando nosso primeiro arquivo

Nesse ponto já temos o Git cuidando do nosso diretório, ou seja, versionando nossos arquivos. 

Vamos então criar nosso html simples com um ‘Olá mundo git’.

Para isso, vou abrir a minha pasta diretamente no Sublime para que eu consiga visualizar meus arquivos diretamente no painel lateral deste editor.

Vou criar um novo arquivo nesse diretório clicando com o botão direito do mouse e salvar como exemplo01.html. Segue o código:

```html
<!doctype html>
<html lang="pt-br">
	<head>
		<meta charset="utf-8">
		<title>exemplo 01</title>
	</head>
	<body>
		<h1>Primeiro exemplo com o Git</h1>
	</body>
</html>```


Agora vamos pensar. Eu tenho um diretório que está sendo monitorado pelo Git chamado PrimeirosPassosWorflow . Eu incluí um arquivo dentro desse diretório, logo, o Git começou a versioná-lo. Certo? Errado. Essa é a primeira pegadinha do Git. O fato de termos um repositório git, ou seja, um diretório sendo monitorado, não versiona arquivos criados automaticamente. É preciso que para cada arquivo incluído seja informado ao git para monitorar também esse arquivo. Mais para frente vamos ver uma maneira de incluir vários arquivos de uma vez, mas por hora, vamos provar isso que eu acabei de dizer. Digite no seu terminal:

```$ git status.```

Você verá uma mensagem informando que há um arquivo "untracked", ou seja, este arquivo está num repositório do git, mas não está sendo "rastreado". Vamos corrigir isso incluindo esse arquivo numa área especial dentro do git responsável por "fotografar" seus arquivos a cada commit. A essa área especial chamamos de "stage". Digite:

```$ git add exemplo01.html``` e tecle ENTER

Novamente, digite ```$ git status``` para entendermos o que aconteceu.

Agora podemos ver que esse arquivo está pronto para ser fotografado, isto é, comitado (O verbo comitar, assim como googlar ou twittar, não existem de fato, mas é muito comum no nosso meio).

Legal! Temos uma pasta que transformamos num repositório git (```git init```), informamos que queremos rastrear as mudanças feitas no nosso primeiro arquivo, colocando-o na área de stage (```git add```), mas até agora este arquivo não foi comitado de fato. Para resolver isso, digite no seu terminal:

```$ git commit -m "primeiro comite lindo"```

a flag -m é usada para informar uma mensagem de commit. É muito importante que as mensagens de seus commits sejam descritivas e específicas das tarefas executadas naquele momento. Por exemplo, "alteração de endereço na página de contato", "inclusão da funcionalidade buscar cep" ou "alterar banner da home - campanha natal 2016" são bons nomes de commits pois permitem facilmente identificar o momento em que as alterações foram efetuadas. Ao passo que: "correção de bugs diversos", "nova funcionalidade na página de compras" ou "incluir banner" são poucos específicos e de pouco valor. Fique atento às suas mensagens de commits. 
 
Prontinho. Nosso primeiro commit foi feito. Vamos verificar: 

```$ git status``` 
(dica: você pode executar comandos escritos recentemente no terminal apertando as teclas para cima e para baixo do teclado).

Na saída do terminal, a última linha é a que nos interessa. "nothing to commit, working directory clean". Ou seja, tudo está atualizado.

Vamos agora voltar ao Sublime, criar um paragrafo qualquer no nosso arquivo html e salvar. 

```html
<!doctype html>
<html lang="pt-br">
	<head>
		<meta charset="utf-8">
		<title>exemplo 01</title>
	</head>
	<body>
		<h1>Primeiro exemplo com o Git</h1>

		<p>um texto qualquer</p>
	</body>
</html>
```


Vamos investigar como está o nosso repositório git nesse momento (depois de alterar e salvar, não se esqueça, salvar é muito importante).

```$ git status```

O git nos dá duas informações muito importantes. A primeira é que há mudanças que não estão na área de stage, portanto, ainda não estão prontas para o próximo commit. A segunda é uma consequência da primeira, ou seja, não há mudanças para serem comitadas.

Essa é a segunda pegadinha do Git. Ao alterarmos um arquivo que foi comitado previamente, precisamos incluí-lo novamente na área de stage e só depois podemos comitá-lo. Então vamos lá:

```$ git add exemplo01.html```

```$ git commit -m "inclusao de paragrafo".```


Agora que nós temos o nosso primeiro html versionado, quero que você execute algumas tarefas:

1. criar um arquivo de estilo css/estilo.css
2. criar uma arquivo de javascript: js/app.js
3. criar um conteúdo qualquer dentro desses arquivos
4. vincular os dois arquivos à sua página html.

Para referência, segue um exemplo bem bobinho que fiz apenas para mostrar:


estilo.css:
```css
body{
	background: #ccc;
}
```


app.js
```javascript
var body = document.body;
body.style.color = 'red';
```

Nesse ponto vale uma dica: com o comando ```ls``` é muito difícil identificar o que é arquivo e o que é diretório. Faça um experimento, digite no terminal ```$ ls --color``` e veja o que acontece.


Depois de vinculá-los à sua página, digite ```$ git status``` e analise o output no terminal. Se tudo estiver bem, você deverá ver que um arquivo já comitado anteriormente foi modificado, porém, os dois arquivos criados não estão sendo rastreados pelo Git, ou seja, não estão sendo versionados. Como são apenas dois arquivos, você poderia incluí-los um a um com o comando ```$ git add```. Porém, pense no caso de termos muitos arquivos, como fontes, imagens, audios, vídeos etc. Nesse caso, incluí-los um a um faria você desistir do versionamento nos primeiros dez arquivos. 

Para incluir todos os arquivos de uma vez, você poderia digitar o seguinte comando:
```$ git add .```

Observe o ponto no final. Esse sinal é o mesmo que dizer "todos os arquivos".

Faça o teste: digite o comando acima e em seguida veja o que acontece quando você verifica o status novamente.

Com tudo adicionado à área do stage, que informa que os arquivos estão preparados para serem comitados, basta você efetuar o comite normalmente

```$ git commit -m "Inclusão de javascript e css"```

Fácil, né? Incluímos todos os arquivos que não estavam na área de stage de uma única vez e depois comitamos normalmente. Contudo, digamos que depois do comite efetuado, o cliente pediu algumas alterações que precisam ser efetuadas tanto no arquivo de estilo quanto no arquivo de javascript. Como queremos manter o histórico, vamos alterar esses arquivos e efetuar um novo comite. Então vai lá. Altere os seus arquivos (pode ser qualquer alteração mesmo, ok).

Pronto? agora digite ```$ git status``` novamente. Repare que Git nos mostra no output do terminal que dois arquivos (previamente adicionados à área do stage) foram modificados. E também nos dá uma dica do que podemos fazer: podemos digitar ```git add``` ou ```git commit -a``` para resolver a questão.

O comando ```git commit -a``` mata dois coelhos com uma cajadada: acrescenta as modificações à área de stage e comita de uma só vez, porém, o jeito certo de usar esse comando é um pouco diferente. As três linhas de comando abaixo são equivalentes. Fica a seu gosto

```
$ git commit -a -m "mensagem do comite".
```
(a flag -a siginica "todos os arquivos" e -m significa que você quer digitar uma mensagem no comite).

```
$ git commit -am "mensagem do comite".
``` 
(é uma abreviação da linha acima, juntando as duas flags)

```
$ git commit -all -m "mensagem do comite".
``` 
(um pouco mais verboso, mas é exatamente a mesma coisa que as duas linhas acima).

Mas atenção: a flag -a, ou uma das variações, só funciona se os arquivos alterados foram versionados previamente (com o ```$ git add``` ou ```$ git add .```). Se você nunca adicionou os arquivos à área de stage, a flag -a não produzirá resultado algum.

