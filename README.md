# Apps #

## Neo4j Browser is the general purpose user interface for working with Neo4j. Query, visualize, administrate and monitor the database with modern and easy-to-use tools. ##

<img width="1179" alt="neo4j-browser-screenshot" src="https://user-images.githubusercontent.com/39738292/70858694-c679ea00-1ed4-11ea-8034-7236f084aba6.png">

1- Development setup
a -Clone this repo
b- Install yarn globally (not required but recommended): # npm install -g yarn #
c- Install project dependencies: yarn

2- Development server yarn start and point your web browser to http://localhost:8080.

Testing yarn test to run a single test run. A linter will run first.

yarn dev to have continuous testing on every file change.

# E2E Suite #


To run on an existing server (with a password already set), you can use any of these (the default password is set to "newpassword", pass in --env browser-password=your-password):
yarn e2e-local --env server=3.4
yarn e2e-local-open --env server=3.4
The latter just opens Cypress runner so you can see the tests being executed and run only some of them. Very useful when writing tests.

There are also e2e tests that covers import from CSV files. To run thise, copy the e2e_tests/files/import.csv to the import/ directory of the database you want to run the tests on and then start the e2e tests with the --env include-import-tests=true flag. Example: yarn e2e-local-open --env server=3.4,include-import-tests=true

Here are the available options / env variables:

server=3.2|3.3|3.4|3.5|4.0 (default 3.5)
edition=enterprise|community (default enterprise)
browser-password=<your-pw> (default 'newpassword')
include-import-tests=true|false (default false)
bolt-url=<bolt url excluding the protocol> (default localhost:7687)
Test environment options (cannot be set using the --env flag as the ones above). These needs to be set before the test command is run.

CYPRESS_E2E_TEST_ENV=local|null (if the initial set of pw should run or not) (default undefined)
CYPRESS_BASE_URL=<url to reach the browser to test> (default http://localhost:8080)
Example: CYPRESS_E2E_TEST_ENV="local" CYPRESS_BASE_URL=http://localhost:8081 cypress open --env server=3.5

Devtools
Download these two chrome extensions:

Redux devtools
React devtools
