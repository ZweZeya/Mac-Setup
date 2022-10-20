# Mac-Setup
Setting up a new macbook for development

# Install Homebrew
https://brew.sh/

## Check is brew is installed properly
which brew__
brew help__

# Install Browser of Choice
Chrome__
Mozilla Firefox__
Microsoft Edge__

# Install VSCode
https://code.visualstudio.com/

# Install NVM

## Run the following commands
brew update__
brew install nvm__

## Create NVM's working directory and zshrc file
mkdir ~/.nvm__
touch ~/.zshrc__

## Add the following configurations to the zshrc file
export NVM_DIR="$HOME/.nvm"__
#This loads nvm__
[ -s "/opt/homebrew/opt/nvm/nvm.sh" ] && \. "/opt/homebrew/opt/nvm/nvm.sh"__
#This loads nvm bash_completion__
[ -s "/opt/homebrew/opt/nvm/etc/bash_completion.d/nvm" ] && \. "/opt/homebrew/opt/nvm/etc/bash_completion.d/nvm"__

## Check if nvm is installed properly
nvm help__

# Install Node (using NVM)
nvm install node__

# Install Mongodb Community
## Run the following commands
brew update__
brew tap mongodb/brew__

## Install the version of choice (5.0 used as an example)
brew install mongodb-community@5.0__

## Add the following configuration to zshrc file
export PATH="/opt/homebrew/opt/mongodb-community@5.0/bin:$PATH"__

## Install Rosetta for Apple M1 Silicon Chip
softwareupdate --install-rosetta__

## Check if mongodb is installed properly
mongo --version__
mongod --version__
mongos --version__
mongosh --version__
which mongo__

## Starting and stopping mongodb server
brew services start mongodb/brew/mongodb-community@5.0__
brew services stop mongodb/brew/mongodb-community@5.0__

## Add configurations to mongod 
mongod --config /opt/homebrew/etc/mongod.conf --fork__

## Start server
mongosh__
