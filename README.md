# Installation
Install the plugin by running:

```sh
npm install --save-dev cypress-cucumber-preprocessor
```
# Cypress Configuration
Add it to your plugins:
For production environments...

```sh
cypress/plugins/index.js
```
```sh
const cucumber = require('cypress-cucumber-preprocessor').default

module.exports = (on, config) => {
  on('file:preprocessor', cucumber())
}
```
Add support for feature files to your Cypress configuration
```sh
cypress.json
```
```sh
{
  "testFiles": "**/*.feature"
}
```

### Configuration
Please make use of cosmiconfig to create a configuration for the plugin, for example, by adding this section to your package.json:
```sh
"cypress-cucumber-preprocessor": {
  "nonGlobalStepDefinitions": true
}
```
### How to run the tests
Run your Cypress Launcher the way you would usually do, for example:
```sh
./node_modules/.bin/cypress open
```
click on a .feature file on the list of specs, and see the magic happening!
