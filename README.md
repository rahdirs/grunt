# Grunt Automation:

Install Grunt's command line interface(CLI) globally,
~~~
npm install -g grunt-cli
~~~

Check the grunt version
~~~
grunt --version
~~~

## Configure package.json and Gruntfile.js
Running grunt need a package.json and Gruntfile.js files. Keep the file package.json and Gruntfile in the root directory of the project.

### package.json
Install the grunt dependency files,

npm install grunt-contrib-nodeunit --save-dev
npm install grunt-contrib-jshint --save-dev


### Gruntfile

#### Base Configuration code:

```javascript
'use strict';

module.exports = function (grunt) {

  // Project configuration
  grunt.initConfig({
    jshint: {
      server: {
        src: ['service/cof.js']
      }
	}
  });

 // Loading the plugins
  grunt.loadNpmTasks('grunt-contrib-nodeunit');
  grunt.loadNpmTasks('grunt-contrib-jshint');

  // Tasks
  grunt.registerTask('default', ['jshint']);
};
```

### Run the grunt:
~~~
grunt --force
~~~
