  
  >Note: This generator is supporting a very early stage app,things gonna change very frequently,so please do not fork it or do any pull request.
  
Readme
=================
webappstarter generator will give you a Simple Mobile Web App Boilerplate and Structure!

  >The App will automatically adjusts according to a device’s screen size without any extra work. 

Install
========
```shell
npm install -g generator-webappstarter
```

Prereqs and installation requirements
=====================================
1.install [node](https://nodejs.org/) and [Python](https://www.python.org/).

2.install [yeoman](http://yeoman.io/).
```shell
npm install -g yo
```
3.[optional]Clone this git repo to your local,and from the root of the repo,run
```shell
npm link
```
to developing the generator locally.

Generator commands
==================
1.generate a new project,run

```shell
mkdir myProject
cd myProject
yo webappstarter
```
or run with `--skip-install` option to skip install dependencies

```shell
mkdir myProject
cd myProject
yo webappstarter --skip-install
```
install dependencies manually with `npm install` or just copy `node_modules` folder from another project which was generated by webappstarter.

2.generate a new module,run

```shell
//this command will do:
//add "html/site/include/view-modulename.html" and inlude it to "html/site/include/views.html"
//add "scss/_debug-view-modulename.scss" and import it to "scss/_debug-view.scss"
//add "src/app/view/ModuleNameView.js"
//add "src/app/controller/ModuleNameController.js" and require it in src/app/App.js

yo webappstarter:module ModuleName
```
3.update your project's boilerplate and structure

```shell
//this command will update
//"./src/core" directory
//"./src/lib" directory
//"./src/util" directory
//"./src/widget" directory
//reqirejs files
//some files in "./src/app/" directory
//some files in "./scss/" directory
//some files in "./html/" directory

yo webappstarter:update
```
 > Warning: When you are asked before an overwrite can occur,please be careful.Default "Y" is overwrite,"n" is skip.
 

More configurations,please take a look at "project" property of "package.json" file after the generator is done.
Run ```gulp``` to re-build project is required after change the "package.json" file.

Project commands
=================
run this command before you get started.

```shell
npm install -g gulp
```

1.build project,watch change and start browserSync,run

```shell
gulp
```
or run with forever
```shell
forever ./node_modules/.bin/gulp
```
2.deploy to test server,run

```shell
gulp deploytest
```
Please update your ftp auth name and password in ".ftppass".
View the page on test server [http://office.mozat.com:8083/PROJECTNAME/](http://office.mozat.com:8083/PROJECTNAME/).
This command require [openssl](https://www.openssl.org/).
For windows,you might needd to add openssl path to classpath.


3.deploy to offical server,run

```shell
gulp deploy
```
View the page on offical server [http://m.deja.me/PROJECTNAME/](http://m.deja.me/PROJECTNAME/).
This command require [rsync](https://rsync.samba.org/).
For windows,unzip  /tools/rsync.zip to a local path and add the path to classpath.

4.run this command to copy source images to project's `resources/images/` path,then generate `scss/_dubug-sprites.csss` and `resources/images/sprites.png` for sourceSprites in `package.json`.

```shell
gulp copy
``` 

5.run this command to start jshint.

```shell
gulp jshint
```

6.run this command to start browserSync,Change browserSync options in `package.json`.

```shell
gulp serve
``` 

7.run this command to start pagespeed,Change pagespeed options in `package.json`.

```shell
gulp pagespeed
``` 

Structure
================
The structure is modular design,follow the DOOR-KEY rule you only take minutes to understand it:
  * The DOOR for javascript is in ```/src/app/App.js```,and the KEY is ```require```,see [requirejs](http://requirejs.org/)
  * The DOOR for stylesheets is in ```/scss/styles.scss```,and the KEY is ```@import```,see [SASS](http://sass-lang.com/)
  * The DOOR for HTML is in ```/html/site/debug/index.html```,and the KEY is ```@@include```,see [gulp-file-include](https://www.npmjs.com/package/gulp-file-include)
  

Git
==========
Random git commit message

```shell
 git commit -m"`curl -s http://whatthecommit.com/index.txt`"
 ```
