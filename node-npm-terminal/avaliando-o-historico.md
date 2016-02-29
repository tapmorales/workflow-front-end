# Avaliando o histórico

Se tudo correu bem, já temos algumas versões de nosso arquivo. Vamos verificar digitando no terminal:

```$ git log```

Com esse comando, podemos ver o histório de commits já efetuados. Poderíamos também ver uma versão resumida, passando mais uma flag ```--oneline```

```$ git log --oneline```

Se nosso projeto tivesse muitos comites efetuados, o comando acima nos traria uma lista enorme. Uma opção seria limitar o número de itens mostrado pelo comando ```$ git log ```. Para isso, basta passar mais uma flag, informando quantos comites queremos ver. Até o momento temos apenas dois comites em nosso repositório, portanto, para ver isso funcionando, digite em seu terminal:

```$ git log -n 1```
 
Esse comando nos traz apenas o último commite. Se quisermos, por exemplo ver os últimos três, basta digitar:

```$ git log -n 3```

E também dá para unir as duas flags. Experimente:

```$ git log --oneline -n 1```

Dica: Se você tiver vários comites, é provavel que veja um sinal de dois-pontos na última linha do terminal ao digitar ```$ git log```. Esse sinal é um indicativo que há mais linhas para mostrar no output. Para vê-las uma a uma, basta apertar o ENTER do teclado. Para sair dessa visualização, basta digitar a letra "q". 

Fácil, não? Vimos o básico sobre o Git. Daria pra falar muito mais sobre ele, como por exemplo criar branchs, criar releases, fazer merge entre branchs, resolver possíveis conflitos entre arquivos. Mas vamos ter que parar por aqui. Espero que com essa base você possa continuar seus estudos sem se assustar com o terminal e podendo dar os primeiros comandos do Git.

---

Há várias maneiras de comparar as modificações de um arquivo usando o Git. A que mais me agrada é utilizar uma interface gráfica para isso. Para abrir esse programa, digite no terminal ```$ gitk ```. O Gitk é um programa a parte específico para visualizar as alterações nos arquivos. Dê uma fuçada nele. É bem tranquilo.

---


No próximo tópico vou falar um pouco sobre o GitHub. Vamos criar um repositório na nuvem e mandar nossos arquivos pra lá, deixando nossos arquivos visíveis para o mundo inteiro. O cloud é o limite. 




