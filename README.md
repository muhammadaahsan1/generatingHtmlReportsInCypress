# generatingHtmlReportsInCypress

### Installation and Configuration Steps

1. Install cypress-mochawesome-reporter
   ```bash
   npm i --save-dev cypress-mochawesome-reporter


2. Change cypress reporter & setup hooks
Edit config file (cypress.config.js by default)

const { defineConfig } = require("cypress");
module.exports = defineConfig({
    reporter: 'cypress-mochawesome-reporter',
    e2e: {


setupNodeEvents(on, config) {
    // implement node event listeners here for reports
    require('cypress-mochawesome-reporter/plugin')(on); // for reports
}
    }

});

3. Add to cypress/support/e2e.js

import 'cypress-mochawesome-reporter/register';


4. Run Cypress

npx cypress run --spec cypress\e2e\mambaTest.cy.js
