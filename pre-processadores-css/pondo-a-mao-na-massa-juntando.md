O próximo passo é criarmos o nosso componente buttonsContainer. Abra esse arquivo e edite-o incluindo os aninhamentos necessários. Lembre-se que ele está em _modules/. 

.scss
```css

.buttonsContainer{
    border-top: 2px solid #A5A5A5;


    .buttonsContainer .buttonsContainer__button{
        background-image: linear-gradient(to top, #848484, #AFAFAF);
        border: none;
        padding: 1em;
        margin: 1em 0;
        cursor: pointer;
        outline: none;
    

        &:hover{
            background-image: linear-gradient(to top, #AFAFAF, #848484);
        }
        &:active{
            background-image: linear-gradient(to top, #868686, #565656);
        }
    }

    .buttonsContainer .buttonsContainer__result--number{
        font-weight: bold;
    }

}



```

Se você olhar bem, verá que há cores que se repetem. Parece interessante criarmos variáveis, não acha? Um detalhe importante é que o sass também possui escopo de variáveis. Veja um exemplo:

```css

.main{
    $cor: red;
    h1{
         color: $cor;
   }
}
div {
    background: $cor;
}

```

O código acima irá gerar um erro pois a variável $cor não existe no contexto da div.

Sabendo disso, vamos editar nosso componente

```css

.buttonsContainer{
    $cor1: #848484;
    $cor2: #AFAFAF;
    border-top: 2px solid #A5A5A5;


    .buttonsContainer__button{
        background-image: linear-gradient(to top, $cor1, $cor2);
        border: none;
        padding: 1em;
        margin: 1em 0;
        cursor: pointer;
        outline: none;
    

        &:hover{
            background-image: linear-gradient(to top, $cor2, $cor1);
        }
        &:active{
            background-image: linear-gradient(to top, #868686, #565656);
        }
    }

    .buttonsContainer__result--number{
        font-weight: bold;
    }

}


``` 

Não há nada de errado com o código acima. Mas ele ainda pode ser melhorado. Se prestarmos atenção, todas as cores são variações de cinza. E se tivéssemos uma função que consiga clarear ou escurecer um cor? Ah! sim. [Nós temos esse tipo de coisa no sass](http://sass-lang.com/documentation/Sass/Script/Functions.html).