<primary-label ref="cheatsheet"/>
<secondary-label ref="2024"/>

# Arch Based Linux Commands

A list of frequently used Arch based Linux commands.

Install ohmyzsh
:
```bash
sudo apt install zsh
sh -c "$(wget https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh -O -)"
```

Install PHP
:
```bash
sudo pacman -Syu
sudo pacman -S php
```

Install Docker
:
```bash
sudo pacman -S docker
sudo systemctl start docker
sudo systemctl enable docker
sudo usermod -aG docker $USER
sudo pacman -S docker-compose
```

Install NVM
:
```Bash
wget -qO- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.5/install.sh | bash
```
```Bash
# After installation, add the following lines to your shell configuration file (~/.bashrc, ~/.zshrc, or ~/.bash_profile):
export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"
[ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"
```
```Bash
# Install node version 18
nvm install 18 
```

<i><b>Work in progress. Busy trying out [CachyOS](https://cachyos.org/) and will add commands as I go.</b></i>