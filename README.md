# cypress-tiket
Installation
Install the plugin by running:

npm install --save-dev cypress-cucumber-preprocessor
Cypress Configuration
Add it to your plugins:

cypress/plugins/index.js

const cucumber = require('cypress-cucumber-preprocessor').default

module.exports = (on, config) => {
  on('file:preprocessor', cucumber())
}
Add support for feature files to your Cypress configuration

cypress.json

{
  "testFiles": "**/*.feature"
}
Configuration
Please make use of cosmiconfig to create a configuration for the plugin, for example, by adding this section to your package.json:

"cypress-cucumber-preprocessor": {
  "nonGlobalStepDefinitions": true
}
This will become the default option in a future version

Configuration option
Option	Default value	Description
commonPath	cypress/integration/common when nonGlobalStepDefinitions is true
cypress/support/step_definitions when nonGlobalStepDefinitions is false
${nonGlobalStepBaseDir}/common when nonGlobalStepBaseDir is defined	Define the path to a folder containing all common step definitions of your tests. When nonGlobalStepBaseDir is defined this path is defined from that base location. e.g ${nonGlobalStepBaseDir}/${commonPath}.
nonGlobalStepDefinitions	false	If true use the Cypress Cucumber Preprocessor Style pattern for placing step definitions files. If false, we will use the "oldschool" (everything is global) Cucumber style.
nonGlobalStepBaseDir	undefined	If defined and nonGlobalStepDefinitions is also true then step definition searches for folders with the features name will start from the directory provided here. The cwd is already taken into account. e.g test/step_definitions.
stepDefinitions	cypress/integration when nonGlobalStepDefinitions is true
cypress/support/step_definitions when nonGlobalStepDefinitions is false	Path to the folder containing our step definitions.
