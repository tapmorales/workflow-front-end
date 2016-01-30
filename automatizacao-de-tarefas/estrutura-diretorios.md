#Criando a estrutura de diretórios

A partir desse momento vamos trabalhar com uma estrutura de diretórios um pouco diferente de como estávamos trabalhando até o tópico anterior. A ideia é termos uma estrutura que lembre um pouco um projeto real. Para isso, vou pedir que você execute algumas tarefas:

* Crie um novo diretório chamado "projetoWorkflow" no seu diretório home. (fora da pasta que estávamos trabalhando, a "PrimeirosPassosWorkflow".
* Nesse diretório recém-criado, acrescente mais dois diretórios: "source" e "deploy". Os arquivos de "source" serão os arquivos fontes (arquivos de edição). Os arquivos que estivem em "deploy" serão os arquivos que irão para produção. Estes arquivos serão gerados pelo nosso GruntJS.
* Dentro da pasta "source" crie mais três diretórios, a saber: "javascript", "sass" e "vendor". Crie também um index.html com a estrutura inicial de qualquer arquivo html.
* Na raiz do projeto, crie um arquivo chamado .gitignore (mantenha o ‘ponto’ inicial no nome do arquivo).
* Crie um aquivo package.json através de um comando no npm. Lembra qual é o comando? ``` $ npm init ```. Responda as perguntas feitas pelo assistente e vá dando ENTER.
* Transforme o diretório raiz (PrimeirosPassosWorkflow) num repositório Git. Lembra-se do comando que faz isso? Não poderei contar que é o ``` $ git init ``` ;)
* Crie um novo repositório na sua conta do GitHub e mande tudo para lá. Se você não se lembra como faz isso, é uma boa hora para revisar [Fundamentos do GitHub](https://tapmorales.gitbooks.io/workflow-front-end/content/fundamentos-do-github.html). Essa etapa não é obrigatória, mas é um bom momento para revisarmos.

No final das etapas descritas acima, você terá a seguinte estrutura:

<pre>
projetoWorkflow
    |-> .git
    |-> deploy
    |-> source
        |-> javascript
        |-> vendor
        |-> sass
        |- index.html
    |- .gitignore
    |- package.json
</pre>


Faça uma pequena edição no seu arquivo package.json para ficar semelhante à:

```javascript

{
  "name": "projetoWorkflow",
  "version": "1.0.0",
  "description": "Exemplo de um projeto",  
  "author": "Daniel Tapias Morales"
}


```

##Explicação sobre o processo de build

O build, ou deploy, nada mais é do que preparar os arquivos para serem enviados para produção (subir no servidor e torná-lo disponível na internet). Esse processo pode envolver uma série de tarefas, e pode variar de projeto para projeto. Os exemplos mais comuns e simples de entender são:

* autoprefixer nos arquivos css, ou seja, incluir os prefixos dos browsers, quando necessário.
* concatenar arquivos javascript.
* minificar arquivos, aumentando a performance do site/aplicação.
* Copiar arquivos estáticos (como midias ou fontes) no diretório de deploy.

Há muitos outros processos legais que poderíamos ver nesse guia, mas focarei no mais fundamental para seu entendimento.

Dito isto, quero detalhar alguns pontos sobre a estrutura de diretórios criada acima:

* O arquivo package.json, como sabemos, é onde listamos as nossas dependências do projeto.
* O arquivo .gitignore é usado para dizer ao Git quais arquivos não devem ser versionados.
* Não deveremos mexer dentro da pasta "deploy". Os arquivos desta pasta serão criados pelo nosso *builder*, no nosso caso, será o GruntJS.
* A pasta source/javascript terá mais de um arquivo .js. Porém, esses arquivos serão concatenados num único arquivo e minificados no momento do build.
* Por enquanto, a pasta source/sass conterá um arquivo css simples. Este arquivo será autoprefixado apenas. Nos próximos tópicos faremos as alterações necessárias para podermos trabalhar com o pre-processador SASS.
* A pasta source/vendor conterá, para exemplificar, um arquivo de terceiro, o modernizr. Se este arquivo estiver minificado (normalmente está) ele simplesmente será copiado para o devido lugar dentro de "deploy". Esse mesmo processo poderia ser criado para uma pasta "images", por exemplo. Não criarei imagens em nosso projeto para manter as coisas simples. 
* Antes de cada build, iremos apagar (automaticamente, claro) todos os arquivos que estiverem dentro de "deploy". Esse processo é importante para evitarmos "sujeiras" de builds anteriores.


Já temos o entendimento necessário para instalarmos o GruntJS, mas isso é assunto para o próximo tópico.