# pyenv + pipenv Setup

## Installation
1. Install Python build dependencies for our system. Ubuntu in this case:
```bash
sudo apt-get update; sudo apt-get install make build-essential libssl-dev zlib1g-dev \
libbz2-dev libreadline-dev libsqlite3-dev wget curl llvm \
libncursesw5-dev xz-utils tk-dev libxml2-dev libxmlsec1-dev libffi-dev liblzma-dev
```

2. Install pyenv from the official site:
```bash
curl https://pyenv.run | bash
```

3. Set pyenv PATH variables:
```bash
echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.zprofile
echo 'export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.zprofile
echo 'eval "$(pyenv init --path)"' >> ~/.zprofile

echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.profile
echo 'export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.profile
echo 'eval "$(pyenv init --path)"' >> ~/.profile

echo 'eval "$(pyenv init -)"' >> ~/.zshrc
```

4. Install a default Python version with pyenv:
```bash
pyenv install 3.8.10
pyenv global 3.8.10
```

5. Install pipenv as user:
```bash
pip install --user pipenv
```

6. Add pipenv to the path, according to our terminal:
```bash
echo 'export PATH="$HOME/.local/bin:$PATH"' >> ~/.zprofile

echo 'export PATH="$HOME/.local/bin:$PATH"' >> ~/.profile
```

## Initialize a project
1. Install desired Python version:
```bash
pyenv install 3.10.1
```

2. Create a directory for the project:
```bash
mkdir myproject
cd myproject
```

3. Initialize pipenv environment, with our target Python version:
```bash
pipenv install --python 3.10.1
```

4. Enable pipenv environment:
```bash
pipenv shell
```

5. Install any dependency:
```bash
pipenv install pymysql
```