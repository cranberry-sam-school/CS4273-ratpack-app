# Intro - Britt
  As our project sponsor has asked us to keep code and database contents undisclosed, we will be describing the approaches used for implementation. The overarching project objective of a contact information, chat and calender application entails the usage of three major components: the processing server, a database to store and update information and the client application that end-users will interface with. The latter of these will have both webapp and phone application versions, with a priority placed on the phone version for initial usage.
   In addition to these three components, we also have in place automated and manual testing processes that ensure we are delivering a vetted and secure product to the sponsor at all stages of the implementation. 
# Server

# Database

# Client

# Testing - Britt
  In addition to the implementation of the key components for the application functionality, we additionally have ensured that we have a robust and automated testing process. This testing is done through the usage of unit test scripts that are then automatically triggered against a prepared docker image through the usage of a continuous integreation pipeline in the source control repositories.
  
  ## Continuous Integration
    In order to ensure that our automated testing processes are capable of running effectively and do so as frequently as needed, we make use of a continuous integration (CI) configuration. This strategy means that for every pushed and merged portion of code, automated tests are run against the new version of code, with code analysis and testing coverage published for each. This broadly enables our development process to be alleviated of running the testing suites manually, while also ensuring that bad code is never entered unchecked into the working implementation.
    This CI pipeline is implemented in our project through the use of a .yml ci configuration, which describes the services, stages and variables necessary for operation, and then scripts the creation of necessary components such as a database, users and environments for usage by the automated testing scripts. The CI .yml then triggers the testing functions and reports the code coverage of all tests on the latest version.
  
  ## Custom Docker Images
    As part of the CI process, and our general implementation, we make use of custom Docker images of the application. These images enable our testing and CI pipelines to create the appropriate starting image of the application to run tests against, without the potential for interruption of functioning versions. These images are created as part of the continuous integration process, with the help of a dockerfile that instructs the image on what resources to ensure are in place such as necessary "go get" commands. It is then against these images that our tests are run against.
    
  ## Code Coverage
    The key output of the CI pipeline is the total code coverage addressed by the tests. This outputs a percentage of the code that has been successfully tested, allowing the development team to track changes in testing success rate, as well as observe which areas of the implementation do not have thorough testing and therefore demand attention to the matter.

# Conclusion - Britt
