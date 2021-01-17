# npm
> By: Alan Nguyen

- [npm](#npm)
  - [nmp Basics - Treehouse](#nmp-basics---treehouse)
    - [1. What is npm?](#1-what-is-npm)
    - [2. Installing Packages with npm](#2-installing-packages-with-npm)
    - [3. Updating & Uninstalling Packages with npm](#3-updating--uninstalling-packages-with-npm)

## nmp Basics - Treehouse

### 1. What is npm?
**#Intro npm**
- JavaScript packages managing

**#Package?**
- are bundles of software
- are mainly JS code
- npm packages for Node.js projects are called modules

**#How to find & choose Packages**

- Popularity on npm – the number of downloads
- Release Date – the more recent the better
- Number of Releases – the more frequent the better
- Passing Tests - if there's tests passing
- Number of Open Issues – the less the better
- Popularity on GitHub – The more Stars, Forks and Watches the better
- Number of Contributors on GitHub – more eyes on the code the better

### 2. Installing Packages with npm

**#Install Local Packages**

**npm Command Line Usage**
- See list of commands `npm` 
- Get help for a command
  
  `npm <command> -h`

  e.g. `npm install -h`
- Installing a package

  `npm install <package_name>`
  
  e.g. `npm install bcrypt`
  
  e.g. with a flag 
  `npm install bcrypt --python=mySpecialPythonExecutable`

**#Install Global Packages**
- Installing a global package

  `npm install <package_name> -g`
  
  e.g. `npm install http-server -g`

**#Managing dependencies**
- Initializing a package.json file

  `npm init`
  `npm help json` - for what each of the fields in the `package.json` does

- Installing an npm Package as a dependency

  `npm install packageName --save`

- Installing an npm Package and save as a development dependency
  
  `npm install packageName --save-dev`

- Running npm in a production environment
  
  `NODE_ENV=production npm install`

- `.gitignore` file

  ```
  node_modules/
  .DS_Store
  config/database.yml
  ```

### 3. Updating & Uninstalling Packages with npm
**#Updating Packages**

**#Semantic Versioning**
- MAJOR.MINOR.PATCH
  - `^` before a version number means install up to the latest MINOR release.
    
    e.g. ^1.1 can install 1.3 if available but not 2.0
  - `~` before a version number means install up to the latest PATCH release.
  
  e.g. ~2.0.1 can install 2.0.9 if available but not 2.1.0


**#npm Command Line Usage**

- Check for outdated packages

  `npm outdated`

- Update packages in your project

  - For *local* packages `npm update`
  - For *global* packages `npm update <package name> -g`
    
    e.g. `npm update http-server -g`


**#Uninstalling Packages**

- Uninstall a *local* dependency: `npm uninstall <package name>`
  
  e.g. `npm uninstall colors`

- Uninstall a *local* dependency and remove from `package json`:   
    
    `npm uninstall <package name> --save`
    
    e.g. `npm uninstall colors --save`

- Uninstall a *local development dependency* and remove from `package.json`: 
  
  `npm uninstall <package name> --save-dev`

  e.g. `npm uninstall mocha --save-dev`

- Uninstall a *global* dependency: 
  
  `npm uninstall <package name> -g`
 
  e.g. `npm uninstall http-server -g`