# intro
 While our full project is ostensibly the creation and deployment of a fully-featured organizational messaging, scheduling and contact application, the discussions with the sponsor have made it clear that the first priority is the completion of a working contact information section of the app. In this section, users should be able to see information about other users such as name, email and phone number, so that the sponsor organization has a central contact information platform that can be easily and readily updated in a unified manner. As a result, our testing approach has primarily focused around this functionality, and the broader needs of app development and deployment, while the more fully featured tests are roadmapped, but reserved for when those features become a development priority.

 Because of the intermittent development capability in our group, we have structured semi-weekly meetings where we have necessary discussions as well as active development work on the project. Many of these meetings center around the prototyped implementation of a given feature or integration, as well as manual testing of these works. The next step is generally a discussion about the plan for more rigorous manual and automated testing, including unit tests, and work on implementation of those in parallel with further development of the feature. Generally, the person working on the feature is also responsible for guiding the tests for it as they have the most intimate knowledge of the possibilities, but all team members continue to provide input, action and perspectives on tests in particular.

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

System tests are a simple but effective mode of testing in which the developers use, populate, and exam the software in a simulated environment similar to that in which it will be used

This stage of testing has consisted primarily of running setup-db, as well as each of the other setup programs, then pinging the server to ensure that the user was created properly. Then the database is filled with dummy data to check the structure of the database. The next step will be to run all the setup programs then access the app to see that the filled database shows the proper contacts and information, as well as checking for any frontend bugs. All tests should be done with proper and accurate data/input, as well as data it is not designed to handle. The latter is to make sure the software doesn't break upon improper usage.


# acceptance tests

Acceptance tests are used to verify that our application meets the specifications given to us by the client. At first, these specifications were to create a full featured application with messaging, scheduling, contacts, and calendar features. Later in the project, our client asked us to focus more on creating a contacts app. Since this is the last contact we have had with our sponsor, we have continued to work under that specification and developed a contacts application. Therefore, our acceptance tests will be based on what is necessary for a contact application.

## current tests

An acceptance test involves looking at our application, and verifying it performs all of the requirements accurately to the project specification. Given this, many of our acceptance tests cannot be properly performed until the application is complete. We have, nonetheless, been assuring the quality of our application through bi-weekly group meetings. During these group meetings, we discuss the current state of the app, and any new features that have been implemented. When discussing these new features, we take time to ensure that our implementation meets the specifications given by our project manager. For example, during the design phase of our application, each member of the group reviewed the design document, and gave feedback on sections that were missing, unnecessary, or otherwise did not meet the specifications.

## future directions

When the application is complete, acceptance testing can begin in earnest. We will start by verifying that our application meets the specifications given to us. Since those specifications are sparse, we can use common sense for what is necessary for a contacts app: can you creat a new contact, can you edit a contact, can you view your own contact card, etc.. Once we have verified that the application meets the basic specifications, we can start testing for edge cases: can you create two contacts with the same information, what happens if you exit the application while editing a contact, can you delete your own contact card, etc.. Once we have reached a point that we believe all, or most, of the edge cases have been handled, we are able to move on to deployment.

