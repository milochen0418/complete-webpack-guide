

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

## Execute web by http-server
$ http-server


# A new package.json for managmenet your project
## package.json  
$ vim package.json   
$ cat package.json    
...   
  "scripts": {   
    "test": "echo \"Error: no test specified\" && exit 1",   
    "node:clean": "rm -rf ./ndoe_modules && rm -f ./package-lock.json",   
    "node:install": "npm install",   
    "node:reboot": "npm run node:clean && npm run node:install ",   
    "web:clean": "rm -rf ./dist",   
    "web:build": "webpack",   
    "web:exec": "http-server",   
    "web:reboot": "npm run web:clean && npm run web:build && npm run web:exec",   
    "reboot": "npm run node:reboot && npm run web:reboot",   
    "help": "cat ./package.json | jq '.scripts'"    
  },   
...   
## management for what node javascript package
$ npm run node:clean  
$ npm run node:install   
$ npm run node:reboot  

## management when web developing 
$ npm run web:clean    
$ npm run web:build     
$ npm run web:exec    
$ npm run web:reboot   

## Reboot All 
$ npm run reboot  
Reset all information of node package and web built result and reset and rebuild again. then exec web in the final.

## query more commands  
$ npm run help  
