# intro

- basic project requirements
	- full messaging app
	- priority on contacts
- general approach to testing
	- bi-weekly meetings
	- general approach to writing tests, etc.

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