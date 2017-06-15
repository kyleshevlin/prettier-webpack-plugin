# Prettier Webpack Plugin
[![All Contributors](https://img.shields.io/badge/all_contributors-3-orange.svg?style=flat-square)](#contributors)

Automatically process your source files with [Prettier](https://github.com/jlongster/prettier) when bundling via Webpack.

## How it works

This plugin reads all file dependencies in your dependency graph.
If a file is found with a matching extension (`.js` and `.jsx` by default), the file is processed by Prettier and overwritten.

You can provide options Prettier by specifying them when creating the plugin.

## Installation

Simply run `npm install --save-dev prettier-webpack-plugin` or `yarn add --dev prettier-webpack-plugin` to install.

Then, in your Webpack config files, add the lines:

```JavaScript
var PrettierPlugin = require("prettier-webpack-plugin");

module.exports = {
  // ... config settings here ...
  plugins: [
    new PrettierPlugin()
  ],
};

```

### Why?

Keeping style consistent between programmers new to collaboration can be tricky.
Prettier tackles this problem by formatting your code to fit its preferred style, which is admittedly very pretty.
Now, your code is automatically formatted when you bundle with Webpack.

Perfect for group projects bundling code on save!

### Usage

The API is very simple.
The constructor accepts one argument, `options`, a JavaScript object which you can leverage to override any default behaviors.
You can specify any of [Prettier's options](https://github.com/jlongster/prettier#api) to override any of the defaults.

For the most basic example, simple add this in your `webpack.config.js`:

```JavaScript
plugins: [
  new PrettierPlugin()
],
```

**This is equivalent to**:

```JavaScript
plugins: [
  new PrettierPlugin({
    // Specify the length of line that the printer will wrap on.
    printWidth: 80, // int

    // Specify the number of spaces per indentation-level.
    tabWidth: 2, // int

    // Indent lines with tabs instead of spaces.
    useTabs: false, // bool

    // Print semicolons at the ends of statements.
    semi: true, // bool

    // Use single quotes instead of double quotes.
    singleQuote: false, // bool

    // Print trailing commas wherever possible.
    trailingComma: 'none', // string (none|es5|all)

    // Print spaces between brackets in object literals.
    bracketSpacing: true, // bool

    // Put the > of a multi-line JSX element at the end of the last line instead of being alone on the next line
    jsxBracketSameLine: false, // bool

    // Which parser to use. Valid options are 'flow' and 'babylon'
    parser: 'babylon', // string (flow|babylon)

    // Which encoding scheme to use on files
    encoding: 'utf-8', // string

    // Which file extensions to process
    extensions: [ ".js", ".jsx" ] // Array<string>
  })
],
```

### Testing

`npm run test` or `yarn run test` will show you how tests are going currently.

These tests can also serve as primitive examples for configuring Prettier Webpack Plugin.

## Contributors

Thanks goes to these wonderful people ([emoji key](https://github.com/kentcdodds/all-contributors#emoji-key)):

<!-- ALL-CONTRIBUTORS-LIST:START - Do not remove or modify this section -->
| [<img src="https://avatars3.githubusercontent.com/u/9123458?v=3" width="100px;"/><br /><sub>Josh Hawkins</sub>](http://hawkins.github.io/)<br />[💻](https://github.com/hawkins/prettier-webpack-plugin/commits?author=hawkins "Code") [📖](https://github.com/hawkins/prettier-webpack-plugin/commits?author=hawkins "Documentation") [💡](#example-hawkins "Examples") [⚠️](https://github.com/hawkins/prettier-webpack-plugin/commits?author=hawkins "Tests") | [<img src="https://avatars0.githubusercontent.com/u/655838?v=3" width="100px;"/><br /><sub>Erwann Mest</sub>](http://kud.io)<br />[📖](https://github.com/hawkins/prettier-webpack-plugin/commits?author=kud "Documentation") | [<img src="https://avatars2.githubusercontent.com/u/15572427?v=3" width="100px;"/><br /><sub>Eduardo Sganzerla</sub>](http://esganzerla.com.br)<br />[💻](https://github.com/hawkins/prettier-webpack-plugin/commits?author=esganzerla "Code") [📖](https://github.com/hawkins/prettier-webpack-plugin/commits?author=esganzerla "Documentation") [⚠️](https://github.com/hawkins/prettier-webpack-plugin/commits?author=esganzerla "Tests") |
| :---: | :---: | :---: |
<!-- ALL-CONTRIBUTORS-LIST:END -->


This project follows the [all-contributors](https://github.com/kentcdodds/all-contributors) specification. Contributions of any kind welcome!
