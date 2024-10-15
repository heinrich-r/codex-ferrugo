# Linux Commands

A list of frequently used Linux commands - might differ based on distro.

Add user to Sudo group
: 
```bash
su
sudo adduser {username}
sudo usermod -aG sudo {username}
shutdown -r now
```

Install ohmyzsh
:
```bash
sudo apt install zsh
sh -c "$(wget https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh -O -)"
```

Set up SSH Server
:
```bash
sudo apt update
sudo apt install openssh-server
sudo systemctl enable ssh
```

Install docker & docker-engine
:
```bash
sudo apt install \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg \
    lsb-release
distro=$(lsb_release -is | tr '[:upper:]' '[:lower:]')
curl -fsSL https://download.docker.com/linux/$distro/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
echo \
  "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/$distro \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt update
sudo apt install docker-ce docker-ce-cli containerd.io
sudo docker run hello-world
sudo usermod -aG docker {username}
```