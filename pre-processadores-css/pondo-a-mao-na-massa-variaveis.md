##Variáveis



[![Torne-se front-end com este curso 100% prático](../cta_livro.png "Torne-se front-end com este curso 100% prático")](https://www.udemy.com/ferramentas-front-end-git-npm-script-gulp-e-sass/?couponCode=PROMOLIVRO20 "12 horas de video. Apenas R$ 20,00. Acesso vitalício e sem mensalidades")

Sabemos que o arquivo _base/_variables.scss deve conter as principais configurações visuais de todo o site/aplicativo. Portanto, vamos editá-lo com o seguinte código:

```scss

$bg-color: #ccc;
$font: arial, sans-serif;

```

Repare que as variáveis em sass começam com um sinal de '$'.

Agora, em _base/_base.scss, digite o seguinte código:

```scss

body{
    background: $bg-color;    
    font-family: $font;
}

```
Muito simples! A varíável $bg-color armazena o valor #ccc e esta é usada na declaração CSS background: $bg-color;  Ou seja, no arquivo compilado teremos o resultado: 

```css

 background: #ccc; 

 ``` 

Pode parecer bem bobinho neste exemplo, mas num código extenso, saber utilizar bem as variáveis pode te poupar muito retrabalho.

Se você se adiantou e rodou o comando no seu terminal para compilar os seus arquivos, você deve ter percebido que o main.css ficou sem nenhuma regra visual. Isso ocorre porque a tarefa do grunt compila o arquivo main.scss em main.css. Ou seja, para vermos o sass trabalhando precisamos importar nossos arquivos recém criados.