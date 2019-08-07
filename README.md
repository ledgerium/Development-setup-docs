## Development-setup-docs
A documentation on how to setup

## GitHub Repositories ##
[GithHub Repo](https://github.com/ledgerium/Development-setup-docs)

### __Generate a new SSH Key__

1) Within your CLI, type in the following code replacing with your own github email : 
   
    `ssh-keygen -t rsa -b 4096 -C "your_email@example.com"`
2) When prompted to : "Enter a file in which to save the key," press Enter. 
3) Then, at the prompt, type a secure passphrase. 
   
### __Adding a new SSH Key__

1) Within your CLI, type :
   
    `eval "$(ssh-agent -s)"`
2) Then, type : 
 
    `ssh-add -K ~/.ssh/id_rsa`
3) In your github, navigate to settings, and then press SSH and GPG keys on your left
4) Click 'New SSH key' on your top right
5) Add your ssh key that begins with 'ssh-rsa'

### __Cloning a repo__

1) Within your CLI, type : 
   
   `git clone git@github.com:ledgerium/Development-setup-docs.git`
   
2) To switch to another branch, do the following eg : 
 
   `git checkout -b feat/myob origin/feat/myob`
   
### __Install Docker(Desktop && VScode)__

 __Desktop__
1) Go to https://www.docker.com/get-started, follow the instructions and download Docker.
2) Within your CLI, type in : docker run hello-world to test whether Docker is installed succesfully.

__VScode__
1) Search for Docker in extensions, install the first extension.

### __Build Using Docker__

__Locally__
1) run `npm install` to install the dependencies\
**Important**\
If on Mac, and `npm i` doesn't work, try downgrading node to 8.16.0, and if it still doesn't work,
type the following code to remove the websocket file :

    `rm -rf node_modules/web3-providers/node_modules/websocket/.git/` 

   

2) run `docker build .` to build images\
**Important**\
If Docker shows error MSB3202: The project file was not found,\
In the Dockerfile : `COPY. .` should be above `RUN dotnet restore`
3) start debugger \
**Important**\
If docker extension shows error, create a .vscode folder and add a launch.json file inside it.
Add the following code :

    ```javascript
    {
    "type": "node",
    "request": "launch",
    "name": "debug service.js",
    "program": "${workspaceFolder}/repo-name/service.js"
    };
    ```
__DockerContainer__
1) Create a 'Dockerfile'
2) run 
   
   `docker build -t file/filename`
3) run 
   
   `docker run -it --rm file/filename`


### __Important Note__
**Xero-events-ingest-svc**


If you find this error :  

`throw new MongooseError('The `uri` parameter to `openUri()` must be a ' +
    ^
MongooseError: The `uri` parameter to `openUri()` must be a string, got "undefined". Make sure the first parameter to `mongoose.connect()` or `mongoose.createConnection()` is a string.`

This means you're missing the 'environments' file and you need to create a  .env file and copy the secret code to proceed at your local machine.

