Modus Create test - Iuliana Popa

Ensure that Node.js and npm are installed on your computer and run the following commands: 
npm install testcafe
npm install typescript
npm install chai

Check in package.json these dev dependencies:
    "chai": "^4.2.0",
    "gulp-sass": "^4.0.0",
    "node-sass": "4.12.0",
    "testcafe": "^1.8.2",
    "core-js": "^3.6.4"

If gulp-sass and node-sass are not installed, run the following commands:
npm install node-sass 
npm install gulp-sass

In order to run a test go to the test's location and from command line, run this command:
 testcafe <browser> <test name>
 e.g.  /d/Modus Create/budgeting/e2e/_tests_ (Iuliana-Popa-Test)
$ testcafe chrome index-test.js

In order to run tests on different browsers, check available browsers by running this command:
testcafe --list-browsers

Test Scenarios:

1. Open app on different browsers: Chrome, Firefox, Internet Explorer, etc
- check that page is rendered correctly: both budget and reports pages
2. Remove all existing data entries on Budget page and check:
- listing page
- total inflow, total outflow and working balance on Budget page
- reports: inflow vs outflow, spending by category charts
3. Add a category on Budget page with an outflow value and add a description (e.g Taxes – 100000) and check:
- if added category is displayed with the correct information in the list: category name, description and value
-  total inflow, total outflow and working balance
- reports: inflow vs outflow, spending by category charts
NOTE: When there are only outflow values entered, working balance is displayed as a positive value, instead of a negative one. (e.g. Total Inflow 0, Total Outflow -30000, Working Balance 30000) 
4. Add a category on Budget page with an inflow value and add a description (e.g. Income – 300000) and check:
- if added category is displayed with the correct information in the list: category name, description and value
-  total inflow, total outflow and working balance
- reports: inflow vs outflow, spending by category charts
5. Add a category on Budget page with an invalid value (e.g. - value) and check:
- if ‘Add’ button becomes enabled when the user enters an invalid value
- if a warning message is displayed
- if the category can be added to the list by entering an invalid value
6. Remove an inflow value from the list and check:
- if the corresponding category is not displayed on the list anymore
- total inflow, total outflow and working balance are updated
- charts are updated on Reports page
7. Enter a description containing a large no of characters and a large value:
- check if these values are displayed correctly on their fields
8. Click on an added category from the listing page:
- check all actions are available for each category: Update, Cancel and Delete
9. Click on an added category from the listing page:
- click on Cancel: this action should hide the action buttons (Update, Cancel and Delete)
10. Click on an added category from the listing page:
- enter a new value and click on Update
- value should be updated on the listing page
- total inflow, total outflow and working balance values should be updated
- Reports charts should be updated
11. Click on an added category from the listing page:
- click on Delete
- category with its corresponding value should not be displayed on the listing page anymore
- total inflow, total outflow, working balance values should be updated
- Reports charts should be updated
12. Delete all entries from the listing page in order to have an empty list:
- add a new entry: Income category and a valid value
- click on the category from the listing page and check if all buttons are displayed (this seems to be a bug, Update, Cancel and Delete buttons are not displayed, instead we have a “Add” button displayed)
13. Add a new category with a valid value:
- check if this entry remains displayed on the listing page when the page is refreshed
