# NVM + NPM + NodeJS setup

## Installation
1. Install NVM from the official repository:
```bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash
```

2. Install latest stable version:
```bash
nvm install --lts
```

3. Check that NodeJS and NPM were installed:
```bash
nvm ls

node --version
npm --version
```

## Initialize a project
1. Create a directory for the project:
```bash
mkdir myproject
cd myproject
```

3. Select NodeJS version:
```bash
nvm use --lts
nvm use v8.2.1
```

4. Check all NodeJS versions:
```bash
nvm ls-remote
```

5. DO NOT USE SUDO TO INSTALL NEW PACKAGES: