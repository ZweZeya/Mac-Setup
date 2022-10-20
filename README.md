# Mac-Setup
Setting up a new macbook for development

----Install Homebrew----
https://brew.sh/

## Check is brew is installed properly
which brew
brew help

----Install Browser of Choice----
Chrome
Mozilla Firefox
Microsoft Edge

----Install VSCode----
https://code.visualstudio.com/

----Install Node----
## Run the following commands
brew update
brew install nvm

## Create NVM's working directory and zshrc file
mkdir ~/.nvm
touch ~/.zshrc

## Add the following configurations to the zshrc file

export NVM_DIR="$HOME/.nvm"

# This loads nvm
[ -s "/opt/homebrew/opt/nvm/nvm.sh" ] && \. "/opt/homebrew/opt/nvm/nvm.sh"

# This loads nvm bash_completion
[ -s "/opt/homebrew/opt/nvm/etc/bash_completion.d/nvm" ] && \. "/opt/homebrew/opt/nvm/etc/bash_completion.d/nvm" 

## Check if nvm is installed properly
nvm help

## Install Node
nvm install node

----Install Mongodb Community----
## Run the following commands
brew update
brew tap mongodb/brew

## Install the version of choice (5.0 used as an example)
brew install mongodb-community@5.0

## Add the following configuration to zshrc file
export PATH="/opt/homebrew/opt/mongodb-community@5.0/bin:$PATH"

## Install Rosetta for Apple M1 Silicon Chip
softwareupdate --install-rosetta

## Check if mongodb is installed properly
mongo --version
mongod --version
mongos --version
mongosh --version
which mongo

## Starting and stopping mongodb server
brew services start mongodb/brew/mongodb-community@5.0
brew services stop mongodb/brew/mongodb-community@5.0

## Add configurations to mongod 
mongod --config /opt/homebrew/etc/mongod.conf --fork

## Start server
mongosh
