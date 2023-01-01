- ## Ember Tutorial
    - Run ember init --name=geaux-ember to get:
        - ```javascript
  create .editorconfig
  create .ember-cli
  create .eslintignore
  create .eslintrc.js
  create .github\workflows\ci.yml
  create .prettierignore
  create .prettierrc.js
  create .template-lintrc.js
  create .watchmanconfig
  create README.md
  create app\app.js
  create app\components\.gitkeep
  create app\controllers\.gitkeep
  create app\helpers\.gitkeep
  create app\index.html
  create app\models\.gitkeep
  create app\router.js
  create app\routes\.gitkeep
  create app\styles\app.css
  create app\templates\application.hbs
  create config\ember-cli-update.json
  create config\environment.js
  create config\optional-features.json
  create config\targets.js
  create ember-cli-build.js
  create .gitignore
  create package.json
  create public\robots.txt
  create testem.js
  create tests\helpers\index.js
  create tests\index.html
  create tests\integration\.gitkeep
  create tests\test-helper.js
  create tests\unit\.gitkeep

Installing packages... This might take a couple of minutes.
npm: Installed dependencies

Successfully created project geaux-ember.
Get started by typing:

  $ cd geaux-ember
  $ npm start

Happy coding!
Done
```
    - `cd` into your directory and run `npm start` or `ember serve`
        - ```javascript
$ npm start

> geaux-ember@0.0.0 start
> ember serve


Running without permission to symlink will degrade build performance.
See https://cli.emberjs.com/release/appendix/windows/ for details.


Build successful (51640ms) – Serving on http://localhost:4200/

Slowest Nodes (totalTime >= 5%)                                                                        | Total (avg)
-------------------------------------------------------------------------------------------------------+-----------------------------
Babel: @ember/test-helpers (1)                                                                         | 19493ms
Babel: @ember-data/adapter (2)                                                                         | 4530ms (2265 ms)
ember-auto-import-webpack (1)                                                                          | 4358ms
Babel: ember-qunit (1)                                                                                 | 3082ms
BroccoliRollup (6)                                                                                     | 3059ms (509 ms)
Funnel (57)                                                                                            | 2807ms (49 ms)

```
- ## Non-Webstorm way to create an Ember Application
    - https://guides.emberjs.com/v4.9.0/tutorial/part-1/orientation/
- ## Project Directory
    - ```javascript
super-rentals
├── .github
│   └── workflows
│       └── ci.yml
├── app
│   ├── components
│   │   └── .gitkeep
│   ├── controllers
│   │   └── .gitkeep
│   ├── helpers
│   │   └── .gitkeep
│   ├── models
│   │   └── .gitkeep
│   ├── routes
│   │   └── .gitkeep
│   ├── styles
│   │   └── app.css
│   ├── templates
│   │   └── application.hbs
│   ├── app.js
│   ├── index.html
│   └── router.js
├── config
│   ├── ember-cli-update.json
│   ├── environment.js
│   ├── optional-features.json
│   └── targets.js
├── public
│   └── robots.txt
├── tests
│   ├── helpers
│   │   └── index.js
│   ├── integration
│   │   └── .gitkeep
│   ├── unit
│   │   └── .gitkeep
│   ├── index.html
│   └── test-helper.js
├── vendor
│   └── .gitkeep
├── .editorconfig
├── .ember-cli
├── .eslintcache
├── .eslintignore
├── .eslintrc.js
├── .gitignore
├── .prettierignore
├── .prettierrc.js
├── .template-lintrc.js
├── .watchmanconfig
├── README.md
├── ember-cli-build.js
├── package.json
├── package-lock.json
└── testem.js

17 directories, 36 files
```
- 
- 
