# intro

- basic project requirements
	- full messaging app
	- priority on contacts
- general approach to testing
	- bi-weekly meetings
	- general approach to writing tests, etc.

# unit tests

There are two main areas of our project that need to have extensive testing: the config and models modules. These two areas represent the vast majority of the project's functionality. 

Unit testing will allow us to test the individual functions inside each of these modules, and give us statistics on how much of our code is covered by the test.

## current tests

We currently use Go's built-in system for testing: a name_test.go file accompanies every file of code for which tests exist. Our CI/CD environment runs these tests inside a custom docker image containing all of the project's dependencies. Simulataneously, Go's vet tool is also run on the code to check for common coding mistakes that may have severe impact on functionality.

At present slighly less than 40% of our code is covered by the existing tests in the config and models modules. The config module handles loading in the configuration file, and validating that all of the private files needed to run have sufficiently strict file permissions as to be unreadable by other users of the system. The models module provides structures for information in the database, allowing the handling of these data to be abstracted signficantly.

## future directions

Currently not every module is covered by tests, and not all covered modules have complete coverage of every file. Our plan is to get the test coverage to as close to 100% as possible prior to deployment.

One of the major blockers on this is that we have not yet selected a mocking framework, which is required for some tests. A mocking framework, such as golang/mock, will allow us to fake the response of some functions. This will be helpful for testing some of the AWS integration, as we can mock a valid response for the KMS requests without actually using AWS resources - allowing us to validate that our code's behavior is correct for valid responses.

# system tests

- describe our interpretation of a system test
- discuss our implementation

## current tests

- login testing
- manually focused (case-by-case basis as features are expanded)
- integrating different parts of the applications

## future directions

- discuss what definitely would have been testing
- how do we plan to handle deployment
- discuss a more rigorous
- final testing is not feasible without more discussion with the client

# acceptance tests

- does the application meets the specifications of the client

## current tests

- have bi-weekly on-going discussions about features that are being implemented, verifying that those features meet the requirements given

## future directions

- communication with the client has been halted and in flux, so requirements are not clear. We are basing our requirements off of the last contact we had with Hock

- Military and Regular users can perform the outlined actions as expected
