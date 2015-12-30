# Versionamento e GIT

Tanto no desenvolvimento de sistemas para web quanto na criação de websites, é muito importante que você saiba versionar os seus arquivos. Mesmo que você seja uma pessoa regrada e que faça backup do seu sistema/site todos os dias em Pendrivers ou deixe-os na nuvem, como o DropBox, o gerenciamento dessas versões é impraticável. Você nunca se lembra o que foi feito na semana passada e se algo quebrar, você precisa comparar os arquivos manualmente para descobrir o código que gerou o bug. 

Versionar arquivos é uma tarefa básica e trivial que todos nós devemos ser capazes de executar sem pestanejar.

Se você usa Windows, eu tenho uma notícia boa e uma má para você. A boa: há uma ferramenta que faz o versionamento através de uma interface gráfica muito elegante. É bem simples mexer e você adoraria trabalhar com ela. A má: nós não vamos nem chegar perto dessa ferramenta. Motivo: no começo, eu também me senti atraído por poder versionar meus arquivos sem a necessidade de digitar linhas de comandos. O problema é que com o tempo você percebe que precisa ter um maior controle sobre esse versionamento, e esta ferramenta que deveria facilitar a tua vida acaba se tornando um problema. Além do mais, trabalhar com o Git por linha de comando é moleza, você vai ver.

Dito isto, quero explicar a base sobre os sistemas de versão. 

Um sistema de versionamento que se preze precisa efetuar bem duas tarefas:
1. Armazenar registros temporais da evolução de seu sistema. É como se você conseguisse tirar uma fotografia do seu projeto num determinado instante e inserir uma legenda nessa fotografia. Essa ‘legenda’ é chamada de commit. Cada commit é um registro do seu projeto numa linha de tempo.
2. Gerenciar conflitos em um mesmo arquivo se este for editado por mais de uma pessoa ao mesmo tempo. Muitas vezes o Git é capaz de lidar com esses conflitos de maneira espetacular. Outras vezes o Git não sabe qual é a versão correta, e então os desenvolvedores envolvidos devem decidir qual é a versão que deve ficar para a história do projeto. 



## Instalando

Para instalar o Git para windows, acesse [https://git-for-windows.github.io/](https://git-for-windows.github.io/) e faça do download do executável. No momento da escrita deste texto, o Git para windows estava na versão 2.6.2.

Siga as imagens abaixo para terminar sua instalação

4-Nesta tela eu prefiro a primeira opção. Pois, a segunda diz que o Git usará o prompt padrão do Windows, mas não os comandos Unix. A terceira, diz que alguns comandos Windows serão substituidos por comandos Unix. E a primeira permite usar comandos Git e outros comandos Unix apenas no Git Bash.

5- A próxima tela, é sobre quebra-linhas. Como sabemos os OS possuem formatos diferentes de quebra-linhas em aquivos de texto.O objetivo dessa opção é normalizar isso. A primeira opção converte para o padrão Windows quando os arquivos chega para você. E quando você comita ele converte para o formato Unix.  A segunda não faz nenhuma conversão quando o arquivo chega, apenas converte para Unix quando comitamos e a terceira, não faz nenhum tipo de conversão.Eu prefiro a segunda

E nesta última tela deixe marcada a primeira opção, indicando que queremos que as quebras de linha sejam consideradas da mesma maneira, independente do sistema operacional. - See more at: http://web-mister.blogspot.com.br/2012/04/instalando-e-configurando-o-git-no.html#sthash.aoKDwnps.dpuf
E por último mais não menos importante, a configuração de quebra de linha. Como você deve saber, o ambiente windows utiliza CRLF como quebra de linha, e o ambiente unix utiliza apenas LF. Na opção default para windows, as quebras de linhas são convertidas automaticamente no checkout e commit, então, deixe marcada a opção "Checkout Windows-style, commit Unix-Style line endings".




Agora que temos o git instalado e configurado, na próxima seção vamos dar uma olhada rapidamente em alguns comandos Unix para manipulação de arquivos.
