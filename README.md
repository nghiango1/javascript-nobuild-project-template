# Javascript-nobuild-project-template template

This is Javascript-nobuild-project-template, which mean the project in module format can be serve as is on browser and node without any build step.

## Why

Javascript support module natively, let go to the future and delete build step from an interprester language

## Tech stack

[JavaScript modules](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules) as the core module engine for the project. Can check for compability directly in the ref pages. While using `jsdoc` as type safety module.

This project have setup all environment config file needed, following recomended in my personal [install guide](https://github.com/nghiango1/hello/tree/main/javascript/install) notes to a single javascript project, allow LSP tool to work and help the development process:
- `jsconfig.json` file: The project use `typescript-language-server` for type check and intelligent code completion support
    > I just can't get LSP to properly suggest import module path - which required by spec we have trailling extension `.js`. LSP alway skip that on the first line of the file, so it is that it is
- `.eslintrc.json` file: The project use `eslint` for auto styling add support adding jsdoc template with `eslint-plugin-jsdoc` plugin

More:
- `esbuild`: We still want to bundle to a single js file for production web serve, ain't no way we serve milion round trip moduler js files and kill our production server
- `http-server`: Tool to setup a http server, used to check how the project run in browser environment

## How to use

> I still recommended using `npm` here, but anything else is fine. Also, all node module used in the template is dev dependancy and can be setup globally

- Install dev dependency
    ```
    npm install
    ```
- Run project with node environment
    ```
    npm run start
    ```
- Start a file server to run project in browser environment. Default will listen on `:8080`
    ```
    npm run serve
    ```
- Bundle for production use, I also add `npm run serve-release` for anyone that want to check final bundle output file.
    ```
    npm run bundle
    ```
