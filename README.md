## Development-setup-docs
A documentation on how to setup 

## GitHub Repositories ##
[GithHub Repo](https://github.com/ledgerium/Development-setup-docs)

### __Generate a new SSH Key__

1) Within your CLI, type in the following code replacing with your own github email : ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
2) When prompted to : "Enter a file in which to save the key," press Enter. 
3) Then, at the prompt, type a secure passphrase. 
   
### __Adding a new SSH Key__

1) Within your CLI, type : eval "$(ssh-agent -s)"
2) Then, type: ssh-add -K ~/.ssh/id_rsa
3) In your github, navigate to settings, and then press SSH and GPG keys on your left
4) Click 'New SSH key' on your top right
5) Add your ssh key that begins with 'ssh-rsa'

### __Cloning a repo__

1) Within your CLI, type : git clone git@github.com:ledgerium/Development-setup-docs.git


