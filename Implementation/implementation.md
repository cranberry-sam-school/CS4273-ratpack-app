# Intro - Britt

# Server

The server is written in Golang, a decision made by our previous group. Golang has a highly developed set of extensions for web applications and is fairly intuitive for programmers already familiar with C and similar languages - making it a good choice for the development of the serverside.

The server is implemented through two parts: First a router using Gorilla/mux allows our client app's requests to be directed to the actual functions that implement the API's expected behavior. Then the remainder of the server serves as an abstraction to the underlying database - using a model-driven approach. Useful tables and views in the database are abstracted into *models*, Golang structures that represent the necessary information and behavior of the objects that the database tables represent. By interacting with these models our application is able to retrieve or update information in the database while most of the actual database implementation is hidden from the client programs.

Server-side authentication is handled through the use of Amazon Web Services' Key Management Service. At present a XSalsa20 key has been encrypted using KMS. At application startup the encrypted copy of this key is communicated to AWS over a secure connection - which then returns the actual key over the same secure encryption. The use of KMS has been validated to meet Federal Information Processing Standard 140-2. The key is then used in Golang's native sealed-box cryptography to encrypt messages to/from the client. Given the obvious flaw with this method we are in the process of converting to asymmetric encryption, where the client will posses a public key while the server posses an unknown private key. Implementation here is slow as the asymmetric key types (Curve25519) that play well with sealed-box cryptography are not on the approved list of cryptography implementations for our sponsor.

# Database

# Client

The client user interface is was written using JavaScript and React Native. This decision was made by the previous group so less code has to be rewritten for the android, iOS, and web versions of the application. The client application is made up of an app container, which contains three main navigation stacks: the app drawer navigator, the authorization navigator, and the contact navigator. The app drawer is a custom navigation drawer that allows the user to navigate between the three main screens of the application: user profile, chat, and contacts. Our sponsor has decided to focus more on the contact list feature of the application, but we opted to keep this navigation drawer in place, since it has already been created, and we cannot contact our sponsor for clarification. 

The authorization navigator is what allows the user to log into the application. On launched, the login screen is displayed before the user is allowed access to the application. The login screen has two fields, one for the username and one for the password. The user enters text into these fields, and submits. Submitting these text fields checks if the user's credentials are correct. First, username and password are encrypted, and then a call is made to the server API using that value. The response is returned, and determines if the user has access to the application. If they do not or if the API call failed, an error message is displayed; otherwise, the user is sent to the application.

After logging in, the user profile screen is shown by default. The user can access the contacts list through the navigation drawer. Once the contact list screen is displayed, we check if the contact list data has been loaded into local storage. If there is currently no data for the contact list,  the list for user is loaded from an call to the server. Each contact in the contact list contains an id number, a list of phone numbers, a first name, a last name, a username, an email, and an profile image url. When displaying the contact list, only the user's first name, last name, phone number, and profile image are shown. This information is displayed for each contact in a list, and when the user presses one of the contacts in the list, the contact profile screen is displayed. The contact profile screen is populated by sending the selected contact information through a parameter in the navigation method. The contact's profile card is then generated based off of that contact information.

Finally, the user is able to log out of the application through the 'log out' button in the navigation drawer. Pressing this button brings up an alert that prompts the user to confirm their choice. Once the user confirms their choice, async local storage is cleared, and the user is navigated back to the login screen. 

# Testing - Britt

gitlab-ci.yml in server
Custom docker images
Checks code coverage

# Conclusion - Britt
