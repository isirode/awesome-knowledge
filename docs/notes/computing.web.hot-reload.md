---
id: eq70ln13eqi7r5dpy11otvf
title: Hot Reload
desc: ''
updated: 1681659387385
created: 1676213478943
---

# Hot reload

Hot reload consist at reloading without rebuilding a code resource, usually code.

## Tools

### live-server

It can reload JS, HTML and CSS.

Url: https://github.com/tapio/live-server

Review: not tested

### nodemon

Restart a NodeJS application when files are changed.

It watches a directory.

Url: https://www.npmjs.com/package/nodemon

Review: not tested

### node-dev

Restart a NodeJS application when files are changed.

It watches the require calls, it do not restart if an unused file is changed.

Urm: https://github.com/fgnass/node-dev

Review: not tested

### ts-node-dev

Optimization of node-dev

It uses [ts-node](https://github.com/TypeStrong/ts-node), a JIT typescript.

It do not recompile everything when a used script file is changed.

Url: https://github.com/wclr/ts-node-dev

Review: not tested

### tsc

This is the official Typescript command.

To do a watch, the command is "tsc --watch".

### webpack

You can use:
- the command "webpack --watch"
- webpack-dev-server

There is a typescript plugin as well.
