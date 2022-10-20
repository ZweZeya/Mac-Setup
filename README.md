# Mac-Setup-Guide
Setting up a macbook for development! <br />
Note: The following set of instructions were carried out on a fresh MacBook M1 Pro 14 with MacOS Monterey v12.5

# Install Homebrew
https://brew.sh/

## Check is brew is installed properly
which brew <br />
brew help

# Install Browser of Choice
Chrome <br />
Mozilla Firefox <br />
Microsoft Edge

# Install VSCode
https://code.visualstudio.com/

# Install NVM

## Run the following commands
brew update <br />
brew install nvm

## Create NVM's working directory and zshrc file
mkdir ~/.nvm <br />
touch ~/.zshrc

## Add the following configurations to the zshrc file
export NVM_DIR="$HOME/.nvm" <br />
#This loads nvm <br />
[ -s "/opt/homebrew/opt/nvm/nvm.sh" ] && \. "/opt/homebrew/opt/nvm/nvm.sh" <br />
#This loads nvm bash_completion <br />
[ -s "/opt/homebrew/opt/nvm/etc/bash_completion.d/nvm" ] && \. "/opt/homebrew/opt/nvm/etc/bash_completion.d/nvm"

## Check if nvm is installed properly
nvm help

# Install Node (using NVM)
nvm install node

# Install Mongodb Community
## Run the following commands
brew update <br />
brew tap mongodb/brew

## Install the version of choice (5.0 used as an example)
brew install mongodb-community@5.0

## Add the following configuration to zshrc file
export PATH="/opt/homebrew/opt/mongodb-community@5.0/bin:$PATH"

## Install Rosetta for Apple M1 Silicon Chip
softwareupdate --install-rosetta

## Check if mongodb is installed properly
mongo --version <br />
mongod --version <br />
mongos --version <br />
mongosh --version <br />
which mongo

## Starting and stopping mongodb server
brew services start mongodb/brew/mongodb-community@5.0 <br />
brew services stop mongodb/brew/mongodb-community@5.0

## Add configurations to mongod 
mongod --config /opt/homebrew/etc/mongod.conf --fork

## Start server
mongosh
