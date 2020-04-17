# Intro

  As our project sponsor has asked us to keep code and database contents undisclosed, we will be describing the approaches used for implementation. The overarching project objective of a contact information, chat and calender application entails the usage of three major components: the processing server, a database to store and update information and the client application that end-users will interface with. The latter of these will have both webapp and phone application versions, with a priority placed on the phone version for initial usage.
   In addition to these three components, we also have in place automated and manual testing processes that ensure we are delivering a vetted and secure product to the sponsor at all stages of the implementation. 

# Server

# Database

# Client

The client user interface is was written using JavaScript and React Native. This decision was made by the previous group so less code has to be rewritten for the android, iOS, and web versions of the application. The client application is made up of an app container, which contains three main navigation stacks: the app drawer navigator, the authorization navigator, and the contact navigator. The app drawer is a custom navigation drawer that allows the user to navigate between the three main screens of the application: user profile, chat, and contacts. Our sponsor has decided to focus more on the contact list feature of the application, but we opted to keep this navigation drawer in place, since it has already been created, and we cannot contact our sponsor for clarification. 

The authorization navigator is what allows the user to log into the application. On launched, the login screen is displayed before the user is allowed access to the application. The login screen has two fields, one for the username and one for the password. The user enters text into these fields, and submits. Submitting these text fields checks if the user's credentials are correct. First, username and password are encrypted, and then a call is made to the server API using that value. The response is returned, and determines if the user has access to the application. If they do not or if the API call failed, an error message is displayed; otherwise, the user is sent to the application.

After logging in, the user profile screen is shown by default. The user can access the contacts list through the navigation drawer. Once the contact list screen is displayed, we check if the contact list data has been loaded into local storage. If there is currently no data for the contact list,  the list for user is loaded from an call to the server. Each contact in the contact list contains an id number, a list of phone numbers, a first name, a last name, a username, an email, and an profile image url. When displaying the contact list, only the user's first name, last name, phone number, and profile image are shown. This information is displayed for each contact in a list, and when the user presses one of the contacts in the list, the contact profile screen is displayed. The contact profile screen is populated by sending the selected contact information through a parameter in the navigation method. The contact's profile card is then generated based off of that contact information.

Finally, the user is able to log out of the application through the 'log out' button in the navigation drawer. Pressing this button brings up an alert that prompts the user to confirm their choice. Once the user confirms their choice, async local storage is cleared, and the user is navigated back to the login screen. 

# Testing
  In addition to the implementation of the key components for the application functionality, we additionally have ensured that we have a robust and automated testing process. This testing is done through the usage of unit test scripts that are then automatically triggered against a prepared docker image through the usage of a continuous integreation pipeline in the source control repositories.
  
  ## Continuous Integration
  In order to ensure that our automated testing processes are capable of running effectively and do so as frequently as needed, we make use of a continuous integration (CI) configuration. This strategy means that for every pushed and merged portion of code, automated tests are run against the new version of code, with code analysis and testing coverage published for each. This broadly enables our development process to be alleviated of running the testing suites manually, while also ensuring that bad code is never entered unchecked into the working implementation.
  This CI pipeline is implemented in our project through the use of a .yml ci configuration, which describes the services, stages and variables necessary for operation, and then scripts the creation of necessary components such as a database, users and environments for usage by the automated testing scripts. The CI .yml then triggers the testing functions and reports the code coverage of all tests on the latest version.
  
  ## Custom Docker Images
  As part of the CI process, and our general implementation, we make use of custom Docker images of the application. These images enable our testing and CI pipelines to create the appropriate starting image of the application to run tests against, without the potential for interruption of functioning versions. These images are created as part of the continuous integration process, with the help of a dockerfile that instructs the image on what resources to ensure are in place such as necessary "go get" commands. It is then against these images that our tests are run against.
    
  ## Code Coverage
  The key output of the CI pipeline is the total code coverage addressed by the tests. This outputs a percentage of the code that has been successfully tested, allowing the development team to track changes in testing success rate, as well as observe which areas of the implementation do not have thorough testing and therefore demand attention to the matter.

# Conclusion

  All three major components of our project have been implemented with carefully assessed priorities and in keeping with the track that was laid by previous teams on this project. Due to a lack of communication availability with the sponsor, we have taken approaches agreed upon internally for the implementation and testing steps, and we feel that these methodologies are in keeping with both the needs and constraints of the project.
