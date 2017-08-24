##@mixin



[![Torne-se front-end com este curso 100% prático](../cta_livro.png "Torne-se front-end com este curso 100% prático")](https://www.udemy.com/ferramentas-front-end-git-npm-script-gulp-e-sass/?couponCode=PROMOLIVRO20 "12 horas de video. Apenas R$ 20,00. Acesso vitalício e sem mensalidades")

Para resolver o problema de reutilização de código comentado no tópico anterior, criarei um @mixin que gere todo o código do botão e que receba por parâmetro a cor base. Farei isso da seguinte maneira:

```scss

@mixin gerarBotao($cor){
    background-image: linear-gradient(to top, darken($cor, 15), $cor);
    border: none;
    padding: 1em;
    margin: 1em 0;
    cursor: pointer;
    outline: none; 

    &:hover{
        background-image: linear-gradient(to top, $cor, darken($cor, 15));
    }
    &:active{
        background-image: linear-gradient(to top, darken($cor, 14), darken($cor, 34));
    }
}


```

O @mixin é o responsável por criar dinamicamente todo o código do botão, incluindo o hover e o active. Há no sass a opção de criarmos uma @function, porém, em nosso exemplo, uma @function não nos ajudaria, uma vez que esta retorna apenas um valor, enquanto um @mixin retorna diversos valores. 

Tenha em mente que, ao criarmos um @mixin, precisamos utilizá-lo usando a palavra @include. Se usarmos uma @function, temos que retornar o valor com a palavra @return e chamar a função do local que queremos usar aquele valor.

Apenas para exemplificar o uso de uma @function, vou criar uma função que recebe dois valores e calcula a porcentagem:

```scss
@function calc-percent($target, $container) {
  @return ($target / $container) * 100%;
}
```

Quando precisarmos utilizar essa função, teremos que chamá-la de dentro da regra css.

```scss
.modulo {
  width: calc-percent(500px, 1000px);
}
```

Voltando ao nosso exemplo, para utilizar o @mixin criado, precisamos da palavra @include. Veja como deve ficar:

```scss

@mixin gerarBotao($cor){
    background-image: linear-gradient(to top, darken($cor, 15), $cor);
    border: none;
    padding: 1em;
    margin: 1em 0;
    cursor: pointer;
    outline: none; 

    &:hover{
        background-image: linear-gradient(to top, $cor, darken($cor, 15));
    }
    &:active{
        background-image: linear-gradient(to top, darken($cor, 14), darken($cor, 34));
    }
}

.buttonsContainer{

    border-top: 2px solid #A5A5A5;

    .buttonsContainer__button{
        @include gerarBotao(#AFAFAF)
    }

    .buttonsContainer__result--number{
        font-weight: bold;
    }

}


```

E se no futuro precisarmos de uma variação desse mesmo botão, poderemos simplesmente passar uma nova cor como parâmetro:

```scss

.buttonsContainer__button{
     @include gerarBotao(#AFAFAF)
}

.buttonsContainer__button--hightlight{
     @include gerarBotao(red)
}


```