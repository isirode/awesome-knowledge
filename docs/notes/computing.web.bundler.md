---
id: ytfs18osddd01wh6njq1p2v
title: Bundler
desc: ''
updated: 1681660356040
created: 1676214054147
---
# Bundler

Bundling is the action of packaging the code and assets of an application.

## Tools

### webpack

Very used bundling tool.

Review: very complicated

### parcel

Very used bundling tool.

It is supposed to be easy to use.

It is supposed to not require a configuration.

It works with Typescript natively, relatively well.

Url: https://parceljs.org/

Review: not as easy to use as declared

### Bugs encountered

Not all of them are Parcel responsability, some were caused by Typescript.

They are not exhaustive, I've also encountered a bug where I had to put "--no-scope-hoist" to the command, for instance.

#### When building a library

I've encountered the error:

```
Error: Failed to install @parcel/transformer-typescript-tsc: process.chdir() is not supported in workers
```

When building a library, to fix it, I've run:

> npm i --save-dev  @parcel/transformer-typescript-tsc

#### Export issue

I've encountered the error: 

```
@parcel/core: my-path/my-class.ts does not export 'MyClass'
```

It was an interface, I've exported it as a type :

```
export type { MyInterface } from 'my-path/MyInterface.ts
```

I think it was inside an index.ts file.

#### Import issue

```
Uncaught TypeError: (0 , _myLib.MyClass) is not a constructor
```

I am not sure what I've done to fix this one.

#### dependency reload

Be aware that it will not reload the cache if the dependency is a link.

See this [issue](https://github.com/parcel-bundler/parcel/issues/4332).

I've added the argument '--no-cache':
- It still require to reload the page
- I think it need to restart the watch also 

#### Targetting web app + library

It did not work very well, on a Typescript project.

You are not allowed to specify a main, module or types.

I did some work and solved some issues.

I was left with this error:

```
@parcel/packager-js: External modules are not supported when building for browser
```

Adding this solved the build issue:

```json
"engines": {
  "node": ">= 16"
},
```

No types were exported though, and it was not importable.

I stopped looking how to fix there, and made another project, and a common library.

#### tsc interop

I've encoutered this error:

```
TypeError: Class constructor Command cannot be invoked without 'new'
```

I was working on a parcel project with tsc enabled.

I tried to setup esModuleInterop in tsconfig.json, without results.

This did not work either, setting "target": "ES6" in tsconfig.json.

Removing https://parceljs.org/languages/typescript/#tsc solved the issue.

### rollup.js

Url: https://rollupjs.org/

Review: not tested

### brunch.io

Url: https://brunch.io/

Review: not tested

### gulpjs

I'ved used it, I can't recall wether it was good or not.

Url: https://gulpjs.com/

Review: same as not tested
