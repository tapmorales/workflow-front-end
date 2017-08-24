##Aninhamento de seletores


[![Torne-se front-end com este curso 100% prático](../cta_livro.png "Torne-se front-end com este curso 100% prático")](https://www.udemy.com/ferramentas-front-end-git-npm-script-gulp-e-sass/?couponCode=PROMOLIVRO20 "12 horas de video. Apenas R$ 20,00. Acesso vitalício e sem mensalidades")

Entender como funciona o aninhamento de seletores no Sass é algo que não exige maiores explicações por ser bastante auto-explicativo. Veja um exemplo:

O .scss ...

```scss
#menu{
    ul{
        margin: 0px;
        padding: 0;
        li{
           list-style-type: none;
            a{
                text-decoration: none;
           }
        }
    }
}


```

… gera o.css:
```css
#menu {
  background: #ddd; 
}
  #menu ul {
    margin: 0px;
    padding: 0;
  }
    #menu ul li {
      list-style-type: none; 
    }
      #menu ul li a {
        text-decoration: none;
      }

```

O problema do aninhamento é a sua facilidade. É tão fácil que se não tomarmos cuidado, podemos acabar com seletores do tipo:

```css
main #mainContent #header #menu ul li a span.icon
```
Nós dois sabemos que seletores desse tipo são péssimos em termos de performance na renderização, os arquivos ficam mais pesados, ficam deselegantes e denigrem sua imagem como desenvolvedor. Nunca faça seletores desse tipo. (Para mim, isso é pior que usar o Dreamweaver ;)

Mas nós podemos usar o aninhamento para gerar o efeito hover em um link, juntamente com a referência ao seletor pai ‘&’. Veja:

o arquivo .scss ...
```scss
a{
    text-decoration: none;
    &:hover{
        text-decoration: underline;
    }
}

```

… gera o seguinte .css:

```css

a{
     text-decoration: none;
}
a:hover{
     text-decoration: underline;
}

```