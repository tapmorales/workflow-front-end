##Funções relacionadas a cores

Para facilitar minha vida, criarei uma variável para a cor cinza mais clara dentro do contexto de nosso componente.

Onde eu precisar escurecer minha cor, chamarei uma função do Sass chamada darken($color, $amount). O segundo parâmetro é referente à porcentagem de escurecimento.

```scss

.buttonsContainer{

    $cor: #AFAFAF;

    border-top: 2px solid #A5A5A5;
    .buttonsContainer__button{
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

    .buttonsContainer__result--number{
        font-weight: bold;
    }

}



```

Eu usei [este site](http://sassme.arc90.com/) para me ajudar a escolher o valor do segundo parâmetro da função darken().

Está ficando bom, mas ainda pode ser melhorado. Você deve ter percebido que incluir a variável da cor dentro do contexto do container não é uma boa ideia. Se no futuro aparecer no layout um botão com destaque, por exemplo, teríamos que duplicar código (e é justamente para não ter que fazer isso que estamos usando o Sass). 