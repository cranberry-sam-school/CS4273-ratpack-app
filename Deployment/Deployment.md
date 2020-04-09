# Deployment
## Database Setup
In the command line, navigate to the directory containing the setup-db.sh file.
Use the command './setup-db.sh --perform-install' using the optional commands --host and --port to specify the hostname and the port
EX: ./setup-db.sh --perform-install --host hostname --port portnumber

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

6. Select build
A new browser window will be opened after the builds are complete. The page will give you the option to start the application on an Android device/emulator, run on an iOS simulator, or run in the web browser. You can select your preferred option. 
