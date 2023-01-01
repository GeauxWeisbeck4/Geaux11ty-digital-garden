- # Intro
    - ## CLI
        - Angular CI
            - Builds and serves app
            - generates code
            - runs tests
            - Adds 3rd party projects
            - 
        - ```javascript
// Getting Started
npm install -g @angular/cli

ng --version
ng help

ng generate component --help

ng new my-app
code my-app```
    - ## Anatomy
        - tslint.json 
            - enforces rules that run code quality
        - tsconfig.json
            - Tells how the browser can use typescript
        - Shouldn't moddify these files
        - package.json
            - Where we manage all our dependencies and scripts
        - karma.conf.js
            - A config file for testing
        - browserlist
            - js and css settings based on browser
        - angular.json 
            - determines the commands of the CLI
        - dist 
            - Where our code gets written during build
        - src
            - Only pace we should regularly edit code
            - main.ts
    - ## Components
        - Binding to events
        - Interpolation
            - Decalre angular component in HTML to call it
        - Directives
            - Like a component except without css 
                - *ngif
                    - ex - when clicked do this 
                - *ngFor
                - Build custom directives with ng g d "directivename"
            - Pipes
                - async pipe - 
            - The DOM
                - Never touch the DOM
            - Component lifecycle
                - Only add dependencies in constructors
                - ngoninit
            - Change detection
        - ```javascript
```
    - Dependency Injection
        - Share data between components 
        - inject in constructor
    - Modules
        - Mainly need to know:
            - Declarations: Define in modules
            - Exports:: share with other modules
            - Import: Want to bring into modules
            - Providers:
- 
- # Firestarter App
    - https://github.com/codediodeio/angular-firestarter
    - ## Angular Material
        - One of the most powerful tools in angular ecosystem
        - other libraries - ionic nebular and bootstrap, CDK (component dev kit)
        - Theming your colors: http://mcg.mbitson.com/
            - Copy and paste into your `scss` style sheet
    - ## Schematics
        - Generate components and include all the Material stuff already
        - ```javascript
ng generate @angular/material:nav shared/shell```
    - ## Shared Module
        - ![](local-asset://Geaux-Notes/8UfCPiXgJf.png)
        - Way easier to import in and stuff
        - 
