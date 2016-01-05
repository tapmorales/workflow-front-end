# Iniciand um repositório local

Estando no diretório Projects, vamos criar mais um diretório chamado “PrimeirosPassosWorflow” e acessá-lo em seguida. (importante: nunca coloque espaços ou caracteres especiais, como acentos ou cedilhas em nomes de arquivos ou pastas)

```$ mkdir PrimeirosPassosWorflow ```

```$ cd primeirosP (TAB + ENTER)```

Agora, nós precisamos pedir ao Git para tomar conta dessa pasta pra gente, e ele gentilmente cuida para que nenhum arquivo ou versão se perca no decorrer do tempo. A não ser que a sua máquina pegue fogo ou o seu HD resolva fritar. Mas ainda assim há serviços que permitem você colocar suas versões na nuvem. Tem um serviço desses que um dia ficará famosinho. É um tal de GitHub. conhece? :-P

Voltando à nossa realidade, precisamos dizer ao Git que cuide no nosso diretório corrente (```$ pwd```, ok?). 

Estando no diretório que queremos versionar, vamos digitar:

```$ git init```

Ao fazermos isso, aparece uma mensagem no terminal  informando que um repositório vazio foi criado. Isso significa que agora uma pasta .git foi criada no diretório PrimeirosPassosWorflow.

Ao digitarmos ```$ ls``` esperaríamos ver o diretório mencionado acima. Mas isso não acontece. Por quê? O motivo é que o diretorio .git é oculto (esse "." inicial significa que é um arquivo ou diretório oculto).

Porém, ao digitarmos $ ls, podemos perceber que os arquivos ocultos não estão listados, mas eu garanto que ele está lá. Quer ver? Então digite:
```$ ls -a```

Com isso aparece no terminal algo como:
```. .. .git```

O primeiro "." significa o diretório corrente. O ".." significa diretório acima (nível acima, diretório pai, como você preferir). Nós já sabemos do que se trata o último ".git".

Dica 1: o nome correto para esse símbolo "-a" que digitamos acima é flag a. As flags servem para passar informações adicionais ao comandos via terminal.

Dica 2: não altere nada dentro da pasta ".git". Dizem que ao fazer isso um urso coala morre.