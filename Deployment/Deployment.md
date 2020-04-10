# Deployment
## Database Setup
In the command line, navigate to the directory containing the setup-db.sh file.
Use the command './setup-db.sh --perform-install' using the optional commands --host and --port to specify the hostname and the port
EX: ./setup-db.sh --perform-install --host hostname --port portnumber

## Server Setup
**NOTE: Serverside code is not included in this repo, as it is not freely distributable**
1. Install RHEL 8 onto an AWS EC2 T2.Micro instance
2. Give the EC2 instance's security group access to the DB instance's network.
2. Install PostgreSQL, Git, and Golang inside the AWS instance
    - sudo yum install postgres git go-toolset
3. Setup a deployment key on GitLab
4. Use the deployment key to clone the source code to the EC2 instance
5. Generate an SSL certificate that is read-only to your user on the EC2 instance
6. Navigate into the `src` folder inside the code
1. Install go dependencies:
   - `go get github.com/gorilla/mux`
   - `go get github.com/lib/pq`
   - `go get golang.org/x/crypto/bcrypt`
   - `go get github.com/aws/aws-sdk-go/...`
1. Run `go build .` to build the executable
7. Configure config.json to point to the correct database and certificates
    - aes_key must be a KMS encrypted key valid for use in sealed-box cryptography. The name is a bit of a misnomer from an older implementation.
    - Ensure domain and ports for the server itself are correct!
8. Configure AWS Shared Config Credentials in `$HOME/.aws`. This can be done using Amazon's command line tools if you install those. The account logged in must have permission to decrypt using the same CMK as the one used to encrypt the `aes_key`
9. Execute the `tmux` command to attach to a new tmux session
10. Inside tmux, in the `src/` folder, run `./src`
11. Disconnect from tmux using `Control-b, d` if needed. You may reattach with `tmux a`
12. You may now logout and the server will continue to run.

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
