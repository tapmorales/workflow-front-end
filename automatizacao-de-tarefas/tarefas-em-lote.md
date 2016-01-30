#Executando tarefas em lote

Estamos quase lá.

O que nos resta agora é fazer com que apenas com um comando no nosso terminal sejamos capazes de executar todas as tarefas de uma única vez. Para isso, nós iremos criar um alias, ou seja, um atalho para mais de uma tarefa criada no Gruntfile.

Veja um exemplo abaixo:

```

grunt.registerTask(minhaTarefa, [tarefa1, tarefa2, tarefa3])

```

Dessa forma, se você digitar no terminal

```

$ grunt minhaTerefa

```

As tarefas tarefa1, tarefa2 e tarefa3 serão executadas nessa mesma ordem.

Um detalhe importante é que você pode registrar uma tarefa chamada ‘default’. Nesse caso, lá no terminal basta digitar ``` $ grunt ``` que esse "default" será chamado.


Para esse exercício, vamos criar uma tarefa chamada "deploy", que conterá todas as tarefas criadas até o momento:

```

grunt.registerTask("deploy", ["clean", "autoprefixer", "cssmin", "uglify", "copy"])

```

Agora basta digitarmos no terminal ``` $ grunt deploy ``` que as cinco tarefas serão executadas, uma a uma.

Isso não é demais!?

Para referência, segue meu Gruntfile.js final:

```javascript

module.exports = function(grunt) {
	'use strict';

	grunt.initConfig({
		autoprefixer: {		    
		    dist: {
		       files: {
		             'deploy/css/main.css': 'source/sass/main.css',
		       },
		    },
		},

	    copy: {
		  dist: {
		  	files: [
			  	{
			  		expand: true, //habilita o cwd
			  		cwd: 'source/',	//relativo à source, mas não a inclui na cópia	  	
			  		src: 'vendor/*', 
			  		dest: 'deploy/'
			  	},
			  	{
			  		expand: true, //habilita o cwd
			  		cwd: 'source/',
			  		src: 'index.html', 
			  		dest: 'deploy/'}
			]        
		  }
		},

	    clean: {
  			dist: {
    			src: ["deploy"]
  			}
		},

	    cssmin: {
		    dist: {
			 files: {
		          'deploy/css/main.css': 'deploy/css/main.css'
		       }
		    }
		},

	    uglify: {
		    options: {
		      mangle: true
		    },

		    dist: {
		      files: {
		        'deploy/javascript/app.min.js': [
		        'source/javascript/incrementButton.js', 
		        'source/javascript/date.js'
		        ]
		      }
		    },
		}


	});

    
    grunt.loadNpmTasks('grunt-autoprefixer');
    grunt.loadNpmTasks('grunt-contrib-cssmin');
    grunt.loadNpmTasks('grunt-contrib-uglify');
    grunt.loadNpmTasks('grunt-contrib-copy');
    grunt.loadNpmTasks('grunt-contrib-clean');

    grunt.registerTask('deploy', ['clean', 'autoprefixer', 'cssmin', 'uglify', 'copy'])


}


```