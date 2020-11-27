# Zania Website

## System Preparation
To use this project, you'll need the following things installed on your machine.
1. [Jekyll] (http://jekyllrb.com/) - $ gem install jekyll bundler
2. [NodeJS] (http://nodejs.org) - use the installer.
3. [GulpJS] (https://github.com/gulpjs/gulp) - $ npm install -g gulp (mac users may need sudo)

## Installation
Local Instalation
1. Inside the directory, run npm install .
2. Enjoy

Development Mode
This will give you file watching, browser synchronisation, auto-rebuild, CSS injecting etc etc.
$ gulp

Deploy with Gulp
1. You can easily deploy your site build to a gh-pages branch.
2. First, follow the instructions at [gulp-gh-pages](https://github.com/rowoot/gulp-gh-pages) to get your branch prepared for the deployment and to install the module.
Then, in gulpfile.js you'll want to include something like the code below.
gulp.src() needs to be the path to your final site folder, which by default will be _site. If you change the destination in your _config.yml file, be sure to reflect that in your gulpfile.
var deploy = require("gulp-gh-pages");
gulp.task("deploy", ["jekyll-build"], function () {
    return gulp.src("./_site/**/*")
        .pipe(deploy());
})
