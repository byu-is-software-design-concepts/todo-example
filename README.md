# Setup

## Get MongoDB

See https://docs.mongodb.com/manual/installation/

For a Mac using Homebrew:

```bash
brew tap mongodb/brew
brew install mongodb-community
brew services start mongodb-community
```

Database will be setup when the project is run for the first time

## Setup

```bash
npm install # For global project
cd client && npm install && cd .. # For client
```

## Run tests

See `package.json`

```bash
npm run test # unit tests
npm run test-integration # integration tests
npm run test-acceptance # acceptance tests
```

## Run project

```bash
npm start # starts both client and server
```

## Technologies used to deploy

```
MongoDB Atlas
TeamCity
GitHub Pages
Heroku
```

## Build steps

###### 1

```bash
# Overwrite environment variables
cp .env.production .env

# Install
npm install
cd client && npm install

# GitHub Login
git remote set-url origin https://%gitHubUser%:%gitHubPassword%@github.com/patrik-drean/todo-example

# Heroku Login
curl https://cli-assets.heroku.com/install.sh | sh # Install Heroku CLI

echo "
machine api.heroku.com
  login %herokuUser%
  password %herokuToken%
machine git.heroku.com
  login %herokuUser%
  password %herokuToken%" > ~/.netrc

heroku git:remote -a %herokuAppName%
```
