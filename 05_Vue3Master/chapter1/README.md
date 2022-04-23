# Chapter1 -Setup Vue.js Developing Environment-

## 1-1

Recommend IDEs.

- Editors
  - VS Code
- Terminals
  - Hyper
- Browser
  - Google Chrome
- Vue Devtools
  - Vue.js Devtools(Chrome Extensions)

## 1-2

Vue-CLI

- before installed
  - npm(or yarn)
  - node
  - git

- [Vue-CLI](https://cli.vuejs.org/guide/installation.html)

```
npm install -g @vue/cli
```

## 1-3

Vue-CLI Scaffold

- [vue create](https://cli.vuejs.org/guide/creating-a-project.html)

```[vue create]
$ vue create vueschool-master
```

```[interactive settings]
- Please pick a preset: (Use arrow keys)
  - Default ([Vue 3] babel, eslint)
- Pick the package manager to use when installing dependencies: (Use arrow keys)
  - Use Yarn
```

```[result]
success Saved lockfile.
Done in 14.93s.
⚓  Running completion hooks...

📄  Generating README.md...

🎉  Successfully created project vueschool-master.
👉  Get started with the following commands:

 $ cd vueschool-master
 $ yarn serve
```

```[start vue hello-world]
 $ cd vueschool-master
 $ yarn serve
```

## 1-4

Directory Structure of Scaffold

- node_modules
  - contains the downloaded modules projecyt uses
- public
  - contains static files
  - also includes an important file(index.html)
    - this is the page template.
- src
  - contains application's code
  - components
    - where components will live
  - assets
    - intended for storing various static files
    - images and stylesheets
- App.vue
  - so-called root component(all the other component in it)
- main.js
  - application's entry file
  - initialize Vue application(e.g. routing, state management ...etc)
- configuration files
  - package.json
    - holdss general information about the project
    - scripts -> aliases for the command
    - dependencies -> a list of the libraries for project
    - devDependencies -> packages while developing
  - babel configuration
  - gitignore

## 1-5

ESLint

- Linter
  - Utility software that programmatically reviews an application
  - reports suspicious code to the author
    -> reduces bugs, icreases the quority and consistency our code

- ESLint version
  - use ECMA6(2015)

- Easy way to use ESLint
  - integrate eslint with the vue-cli(install by default)
    -> there are ESLint in package.json
  - eslintConfig
    - extends -> array of the active presets
    - rules -> includes a list of rules I want to adjust(overwrite the preset's rules)
      - if production, rule's value to be error
      - if development. rule's value can use warn.

```[package.json - eslintConfig - rules]
"rules": {
  "no-unused-vars": 1
  // json CANNOT use this code(change env settings)
  "no-unused-vars": process.ENV.NODE_ENV === "production" ? "error" : "warn"
}

* 0=off, 1=warn, 2=error
```

↓

- `.eslintrc.js`
  - create this file in the root directory of this project
  - we can separate eslintConfig from package.json to .eslintrc,js

## 1-6

ESLint preset

*Airbnb is better*

```[easy way to lint]
npm run lint --fix
```
