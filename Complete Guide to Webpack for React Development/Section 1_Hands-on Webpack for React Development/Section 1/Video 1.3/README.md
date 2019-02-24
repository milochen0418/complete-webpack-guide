

# development note
## init
npm init

## add .gitignore for webpack project
$ vim .gitignore  
$ cat .gitignore  
package-lock.json  
node_modules  
dist   

### package-lock.json 
When you use npm install to install package, the package-lock.json will save information about where you download and lock it's version    
### node_modules
When you do npm install, all libraries will download into node_modules   
### dist
When you do webpack command to build bundle.js, all result will show in ./dist folder   

## Install webpack  
$ npm install webpack  --save-dev  

## First time to use webpack to build bundle.js in ./dist
$ ./node_modules/.bin/webpack
Do you want to install 'webpack-cli' (yes/no): yes

## Install http-server to run front-end web page
$ npm install --save-dev http-server  

## fixed the bug of index.html to change bundle.js to dist/bundle.js for index.html
$ vim index.html

