## ESLint and Prettier config for React + TypeScript

To use in a project add it by using the following steps:

```
npx install-peerdeps --dev eslint-config-lucas-silbernagel
```

Use `yarn` instead of `npm` if prompted to do so.

Then, create a `.eslintrc.js` file in the root of your project's directory and add the configuration.

```js
module.exports = {
  extends: ['eslint-config-lucas-silbernagel'],
}

```

Finally add these two scripts to `package.json`

```json
{
    "scripts": {
        "lint": "eslint --ext \".js,.jsx,.ts,.tsx\" --ignore-path .gitignore .",
        "lint:fix": "eslint --fix --ext \".js,.jsx,.ts,.tsx\" --ignore-path .gitignore ."
    }
}
```

Depending on which project the package is being installed in, you may encounter dependency conflicts. To resolve, delete `node_modules`, `yarn.lock`, and `package-lock.json`. Also delete "`eslint`" from `package.json` if it exists. Then run `yarn` or `npm install`. If the project is dockerized, rebuild the Docker container. Depending on the project, further dependency conflict resolution may be necessary.

In VSCode, make sure you are not running the [Prettier extension](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode). The [ESLint extension](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint) should be used instead, as this package bundles Prettier with ESLint, and can cause conflicts with the Prettier extension.

To lint all files at once, use the above scripts. Otherwise, linting issues can be resolved file by file.

To disable linting in any file add the following comment at the top:

```
/* eslint-disable */
```

