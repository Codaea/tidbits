
`sudo apt install npm` is outdated packages on 6.0, we want at least 10 right?

# INTRODUCING... NVM

node vesion manager

```bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.0/install.sh | bash
```

then to update path,

```bash
source ~/.bashrc
```

install the longterm version with 

```bash
nvm install --lts
```

and set it to default with ` ` make sure it matches exact lts version u have installed

```bash
nvm alias default 18.18.2
```