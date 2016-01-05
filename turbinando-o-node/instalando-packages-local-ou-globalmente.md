# Maneiras de instalar pacotes do npm

Sabemos que para instalar um novo pacote através do npm, devemos digitar em nosso terminal o seguinte comando:

```$ npm instal <package>```, para instalações locais em cada diretório do projeto

ou:

```$ npm instal <package> -g``` , para instalações globais no sistema.

Contudo, falta-nos entender, de fato, quais as principais diferenças entre essas duas abordagens:

A vantagem mais obvia de uma instalação global é com relação à utilização do espaço físico na sua HD. Os pacotes instalados globalmente precisam ser instalados apenas uma vez e podem ser utilizados em quantos projetos forem necessários. Se você usa com frequência um determinado módulo do NodeJS, vale a pena pensar em instalá-lo globalmente. A próposito, o caminho físico dessa instalação em seu sistema Windows é: 
C:\Users\<user>\AppData\Roaming\npm\node_modules

Se você instalar um módulo localmente na sua pasta do projeto os arquivos e todas as suas dependências ficarão dentro de um diretório chamado "node_modules" pentencente ao projeto. Os módulos do npm são conhecidos por serem, algumas vezes, um tanto pesados. Portanto, o espaço físico disponível na sua HD deve ser levado em consideração.

Dito isto, você deve estar se perguntando por qual motivo alguém deveria instalar um módulo localmente no diretório do projeto. Eu creio que este não seja o momento de explicar isso, mas eu quero que você tome nota do paragráfo abaixo e leia-o no futuro (eu anotaria no evernote):



---


 Se você quiser usar o módulo no seu projeto, através do terminal (linha de comando, ou CLI, como preferir), você poderá instalar um módulo globalmente. Entretanto, se você estiver desenvolvendo um módulo para servir de dependência de outro módulo - usando require("seu_modulo") -, você terá que instalá-lo localmente, na raiz do seu projeto.



---



Na prática, eu instalo os módulos que utilizo com mais frequência globalmente. Contudo, instalo os módulos usados em projetos específicos apenas localmente. Estes pacotes serão descartados da minha máquina quando o projeto estiver entregue em produção, liberando espaço físico da minha HD. Não há problema algum em apagar um módulo, desde que você consiga nova instalação rapidamente, sem esforço algum, caso necessário na manutenção do projeto. E isso é tema do próximo tópico.