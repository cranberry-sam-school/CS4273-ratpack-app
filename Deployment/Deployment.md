# Deployment

## Database Setup

1. In the command line, navigate to the directory containing the setup-db.sh file.
2. Use the command `./setup-db.sh --perform-install` using the optional commands `--host` and `--port` to specify the hostname and the port, respectivly.

EX: `./setup-db.sh --perform-install --host hostname --port portnumber`

## Client Setup

1. Download file
2. Move to proper location and Unzip
3. `cd ./[directory location]/ratpack-client/ratpackClient`

4.  Install programs required to start the application

```
brew install node
brew install watchman
sudo gem install cocoapods # optional
```

5. Prepare the application

```
yarn install
npm start
```

This command will also install expo, when asked if you would like to continue with the expo instillation, press ‘y’.

6. A new browser window will be opened after the builds are complete. The page will give you the option to start the application on an Android device/emulator, run on an iOS simulator, or run in the web browser. You can select your preferred option. 

# Future Directions

This section of the document will outline aspects of deployment that will be addressed if there is time, as well as those that would be addressed if we were to continue working on this project.

## Docker Images

While our final project will certainly have this implemented, we not currently created a dockerfile for the client. The docker image will allow for a more steamlined deployment process. When this is implemented, the readme document will be updated with steps for deployment using a Dockerfile.

## Update to Current UI

While not explicetly part of deployment, our team felt it worth mentioning the UI of the project. We were unable to access the existing client code. We worked under the assumption that the client code was non-existent or inaccessable, and so created a new UI design for the application. If we were to continue working on this project, we would invest time into updating the user interface to match this new design. 

## Deploy to the App Store and Play Store

The scope of this project has been limited significantly since our sponsor ended contact with us. If we were to continue working on this project after graduation, the application would reach a point when our sponsor is ready to start adoption of the new application. At this point, the client applicaiton will need to be compiled into native binaries for both iOS and Android, and we would use the developer accounts provided by our sponsor, to ship the application.
