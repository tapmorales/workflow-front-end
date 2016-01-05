# Avaliando o histórico

Se tudo correu bem, já temos algumas versões de nosso arquivo. Vamos verificar digitando no terminal:

```$ git log```

Com esse comando, podemos ver o histório de commits já efetuados. Poderíamos também ver uma versão resumida, passando mais uma flag ```--oneline```

```$ git log --oneline```

Também poderíamos ver somente os últimos comites. Se nosso projeto já existisse há bastante tempo, contendo vários comites, o comando acima nos traria uma lista enorme. Podemos passar mais uma flag, informando quando comites queremos ver. Até o momento só temos dois comites em nosso repositório, portanto, para ver isso funcionando, digite em seu terminal:

```$ git log -n 1```
 
Esse comando nos traz apenas o último commite. Se quisermos, por exemplo ver os últimos três, basta digitar:

```$ git log -n 3```

E também dá para unir as duas flags. Experimente:

```$ git --oneline -n 1```

Dica: Se você tiver vários comites, é provavel que veja um sinal de dois-pontos na última linha do terminal ao digitar ```$ git log```. Esse sinal é um indicativo que há mais linhas para mostrar no output. Para vê-las uma a uma, basta apertar o ENTER do teclado. Para sair dessa visualização, basta digitar a letra "q". 

Fácil, não? Vimos o básico sobre o Git. Daria pra falar muito mais sobre ele, como por exemplo criar branchs, criar releases, fazer merge entre branchs, resolver possíveis conflitos entre arquivos. Mas vamos ter que parar por aqui. Espero que com essa base você possa continuar seus estudos sem se assustar com o terminal e podendo dar os primeiros comandos do Git.

No próximo capítulo vou falar um pouco sobre o GitHub. Vamos criar um repositório na nuvem e mandar nossos arquivos pra lá, deixando nossos arquivos visíveis para o mundo inteiro. O clound é o limite. 
