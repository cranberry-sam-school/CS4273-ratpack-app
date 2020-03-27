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

- System tests are a simple but effective mode of testing in which the developers use, populate, and exam the software in a simulated environment similar to that in which it will be used
- This stage of testing has consisted primarily of running setup-db, as well as each of the other setup programs, then pinging the server to ensure that the user was created properly. Then the database is filled with dummy data to check the structure of the database. The next step will be to run all the setup programs then access the app to see that the filled database shows the proper contacts and information, as well as checking for any frontend bugs. All tests should be done with proper and accurate data/input, as well as data it is not designed to handle. The latter is to make sure the software doesn't break upon improper usage.

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
