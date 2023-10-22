# Configura multiple GitHub accounts with differente SSH keys

## Setup

1. Generate one SSH key for each account:

```bash
ssh-keygen -t ed25519 -C "example1@gmail.com"
ssh-keygen -t ed25519 -C "example2@gmail.com"
```

2. Add your SSH keys to your GitHub accounts. [Reference here.](https://docs.github.com/es/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account)

3. Add generated keys to the authentication agent:

```bash
ssh-add ~/.ssh/id_id_ed25519_ghexample1
ssh-add ~/.ssh/id_id_ed25519_ghexample2
```

4. Add entries to the SSH config file:

```bash
nano ~/.ssh/config
```

```
# Secondary account, not used by default
Host github-example2.com
    HostName github.com
    User git
    IdentityFile ~/.ssh/id_id_ed25519_ghexample2

# Personal account, main default config
Host github.com
    HostName github.com
    User git
    IdentityFile ~/.ssh/id_id_ed25519_ghexample1
```

5. Clone your repository:

```bash
# Clone a repository for the main/default account
git clone git@github.com:Example1/RepositoryName.git

# Clone a repository for the secondary account
git clone git@github-example2.com:Example2/RepositoryName.git
```

6. **DO NOT FORGET TO MODIFY GIT CONFIG EVERYTIME YOU CLONE A NEW REPOSITORY**

```bash
git config user.name "example1"
git config user.email "example1@gmail.com"
```
