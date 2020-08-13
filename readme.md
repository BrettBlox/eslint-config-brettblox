# Eslint and Prettier Setup
My settings for linting and formatting my code using prettier and eslint.

## What it does

- Lints JavaScript based on the latest standards
- Fixes issues and formatting errors with Prettier
- Lints + Fixes inside of html script tags
- Lints + Fixes React via eslint-config-airbnb
- You can see all the [rules here](https://github.com/brettblox/eslint-config-brettblox/blob/master/.eslintrc.js)

## Local /  Project Installation

```
npx install-peerdeps --dev eslint-config-brettblox
```

Create a `.eslintrc` file in the root of your project's directory (it should live where package.json does). Your
`.eslintrc` file should look like this:

```json
{
  "extends": ["brettblox"]
}
```

## Global Installation

```
npx install-peerdeps --global eslint-config-brettblox
```

Create a global `.eslintrc` file:

ESLint will look for one in your home directory

* `~/.eslintrc` for mac
* `C:\Users\username\.eslintrc` for windows

In your `.eslintrc` file, it should look like this:

```json
{
  "extends": ["brettblox"]
}
```

## Instructions for VS Code

Once you have done the above install. You probably want your editor to lint and fix for you. Here are the instructions
for VS Code:

1. Install the [ESLint package](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)
2. Now we need to setup some VS Code settings via `Code/File` → `Preferences` → `Settings`. It's easier to enter these
   settings while editing the `settings.json` file. Add the following to the bottom of your `settings.json` file

```js
// These are all my auto-save configs
"editor.formatOnSave": true,
// turn it off for JS and JSX, this is done via eslint
"[javascript]": {
  "editor.formatOnSave": false,
},
"[javascriptreact]": {
  "editor.formatOnSave": false
},
// tell the ESLint plugin to run on save
"editor.codeActionsOnSave": {
  "source.fixAll.eslint": true
},
// Optional BUT IMPORTANT: If you have the prettier extension enabled for other languages like CSS and HTML, turn it off for JS since we are doing it through Eslint already
"prettier.disableLanguages": [
  "javascript",
  "javascriptreact",
]
```

## Remove Install

```
npm remove --global eslint-config-brettblox babel-eslint eslint eslint-config-prettier eslint-config-airbnb eslint-plugin-html eslint-plugin-prettier eslint-plugin-import eslint-plugin-jsx-a11y eslint-plugin-react prettier eslint-plugin-react-hooks
```

To do the above for local, omit the `--global` flag.

Then if you are using a local install, remove your package-lock.json file and delete the node_modules/ directory.
