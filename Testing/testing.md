# intro
 While our full project is ostensibly the creation and deployment of a fully-featured organizational messaging, scheduling and contact application, the discussions with the sponsor have made it clear that the first priority is the completion of a working contact information section of the app. In this section, users should be able to see information about other users such as name, email and phone number, so that the sponsor organization has a central contact information platform that can be easily and readily updated in a unified manner. As a result, our testing approach has primarily focused around this functionality, and the broader needs of app development and deployment, while the more fully featured tests are roadmapped, but reserved for when those features become a development priority.

 Because of the intermittent development capability in our group, we have structured semi-weekly meetings where we have necessary discussions as well as active development work on the project. Many of these meetings center around the prototyped implementation of a given feature or integration, as well as manual testing of these works. The next step is generally a discussion about the plan for more rigorous manual and automated testing, including unit tests, and work on implementation of those in parallel with further development of the feature. Generally, the person working on the feature is also responsible for guiding the tests for it as they have the most intimate knowledge of the possibilities, but all team members continue to provide input, action and perspectives on tests in particular.

# unit tests

- objective, describe the importance of a unit test

## current tests

- uses go's build in framework
- just shy of 40% code coverage
- tests are run inside of a docker image
- tests focus on config and models
- details on what models are, and how they are covered

## future directions

- discuss what sections not covered, and what are plans are for those sections
- completing unit tests over areas that do not have them yet
- not all files are covered/completely covered

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
