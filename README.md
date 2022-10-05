Forked from https://github.com/tverdohleb/webpack-electron-reload. This package adds the ability to pass in arguments to electron. For example: `electron ./dist/main.js some-arg`

# webpack-electron-reload

[Webpack](https://webpack.js.org/) plugin that restarts [Electron](https://electronjs.org/) main process automatically on webpack build. Inspired by [electron-reload-webpack-plugin](https://github.com/O4epegb/electron-reload-webpack-plugin).

## Installation

```
npm install --save-dev webpack-electron-reload
```

## Usage

### Add plugin to webpack config

```
const path = require('path');
const ElectronReloadPlugin = require('webpack-electron-reload')({
  path: path.join(__dirname, './dist/main.js'),
  args: ['some', 'args'],
});

module.exports = {
    // ...

    target: 'electron-main',

    plugins: [
        // ...
        ElectronReloadPlugin()
    ],

    // ...
};
```

### Start webpack with 'watch' option

```
webpack --watch
```

Plugin will start/restart electron app when webpack rebuilds sources.
