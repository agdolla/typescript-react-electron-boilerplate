# Typescript - React - Redux - Electron Boilerplate

Boilerplate project for building an electron app using React, Redux, Electron and Typescript.

[![Build status](https://ci.appveyor.com/api/projects/status/o5rekt4awy1k8xj5?svg=true)](https://ci.appveyor.com/project/xwvvvvwx/typescript-boilerplate)
[![Build status](https://travis-ci.org/xwvvvvwx/typescript-react-electron-boilerplate.svg?branch=master)](https://travis-ci.org/xwvvvvwx/typescript-react-electron-boilerplate)

## Contents
* [Features](#features)
* [Install](#install)
* [Run](#run)
* [Code Organization](#code-organization)
* [Adding Type Definitions](#adding-type-definitions)
* [Testing](#testing)
* [Packaging](#packaging)
* [Linting](#linting)

## Features

- Hot module reloading
- Packaging
- CI integration with `travis` and `appveyor`
- Unit testing with `mocha` / `expect`
- React / Redux devtools
- linting with `tslint`

## Install

- Clone the repo

```
$ git clone https://github.com/xwvvvvwx/typescript-react-electron-boilerplate.git your-project-name
```

- Install dependencies

```
$ cd your-project-name && npm install
```

## Run

Run these two commands simultaneously in separate console tabs.
```
$ npm run server
$ npm start
```

**Notes**
- Uses [webpack](https://webpack.github.io/)
- Hot Module Replacement with vanilla HMR (see [Hot Reloading In React](https://medium.com/@dan_abramov/hot-reloading-in-react-1140438583bf#.389tj16hj) for details on trade offs)
- Typescript code is processed with `ts-loader`
- Redux / React devtools are automatically installed with [electron-devtools-installer](https://github.com/GPMDP/electron-devtools-installer)
- Electron devtools (devtron) automatically installed with [electron-debug](https://github.com/sindresorhus/electron-debug)
- Notifications of failed builds using [webpack-notifier](https://www.npmjs.com/package/webpack-notifier)

## Code organization

- Application entry point is `main.js`
- This loads `build/index.html` (generated by webpack)
- This calls `src/index.tsx` (generates store / handles HMR wrapping)
- This loads `src/components/App.tsx` (root component)
- Store is built from `src/reducers/main.ts`

## Adding type definitions

- Uses typescript 2
- Type definitions are installed with npm (see [The Future of Type Definition Files](https://blogs.msdn.microsoft.com/typescript/2016/06/15/the-future-of-declaration-files/))

To add a new type definition file run:
```
$ npm i -D @types/<PACKAGE_NAME>
```

## Testing

**Run tests**:<br>
```
$ npm run test
$ npm run test:watch
```

**Writing Tests**
- any file under `src` of the form `*.spec.ts` will be executed
- Tests are run using [mocha](https://mochajs.org/) running on [ts-node](https://github.com/TypeStrong/ts-node).
- Assertions can be written using [chai](http://chaijs.com/).
- React components can be tested using [enzyme](http://airbnb.io/enzyme/index.html).
- See [actionCreators.spec.ts](https://github.com/xwvvvvwx/typescript-boilerplate/blob/master/src/actions/test/actionCreators.spec.ts) for examples of pure TS tests.
- See [Todo.spec.tsx](https://github.com/xwvvvvwx/typescript-react-electron-boilerplate/tree/master/src/components/test/Todo.spec.tsx) for examples of react component testing.

## Packaging

**Package App**
```
$ npm run build-mac
$ npm run build-linux
$ npm run build-win
$ npm run build-all
```

**Notes**
- Packages are output to the `package` directory
- uses [electron-packager](https://github.com/electron-userland/electron-packager)

## Linting

**Lint Code**
```
$ npm run lint
```

**Notes**
- Uses [tslint](http://palantir.github.io/tslint/)