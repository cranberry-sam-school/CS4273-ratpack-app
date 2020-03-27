# intro - Britt

- basic project requirements
	- full messaging app
	- priority on contacts
	
- general approach to testing
	- bi-weekly meetings
	- general approach to writing tests, etc.

# unit tests - Gregory

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

# system tests - Ross

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

# acceptance tests - Sam

- does the application meets the specifications of the client
Acceptance tests are used to verify that our application meets the specifications given to us by the client. At first, these specifications were to create a full featured application with messaging, scheduling, contacts, and calendar features. Later in the project, our client asked us to focus more on creating a contacts app. Since this is the last contact we have had with our sponsor, we have continued to work under that specification; however vague it might be.

## current tests

- have bi-weekly on-going discussions about features that are being implemented, verifying that those features meet the requirements given

An acceptance test involves looking at our application, and verifying it performs all of the requirements accurately. Acceptance tests could also be called quality assurance tests. Given this, many of our acceptance tests cannot be properly performed until the application is complete. That being said, we have been assuring the quality of our application through bi-weekly group meetings. During these group meetings, we discuss the current state of the app, and any new features that have been implemented. When discussing these new features, we take time to ensure that our implementation meets the specifications given by our project manager. For example, during the design phase of our application, after the design document was created, each member of the group reviewed the design, and verified commented on sections that were missing, unnecessary, or otherwise not a part of the specifications.

## future directions

- communication with the client has been halted and in flux, so requirements are not clear. We are basing our requirements off of the last contact we had with Hock

- Military and Regular users can perform the outlined actions as expected