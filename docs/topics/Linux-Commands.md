<primary-label ref="cheatsheet"/>
<secondary-label ref="2024"/>

# Linux Commands

A list of frequently used Linux commands.

Add user to Sudo group
: 
```bash
su
sudo adduser {new username}
sudo usermod -aG sudo {new username}
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

Install & Set up Git
:
```bash
sudo apt update
sudo apt install git
git config {--global} user.username {git username}
git config {--global} user.email {git email}
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
sudo usermod -aG docker $USERNAME
```

Set up Firewall
:
```bash
sudo apt update
sudo apt install ufw
sudo ufw app list
sudo ufw allow OpenSSH
sudo ufw enable
sudo ufw status
```

Install Nginx
:
```bash
sudo apt install nginx
sudo ufw app list
sudo ufw allow 'Nginx HTTP'
sudo systemctl status nginx
```

Set up Nginx
:
```bash
sudo mkdir -p /var/www/your_domain/html
sudo chown -R $USER:$USER /var/www/your_domain/html
sudo chmod -R 755 /var/www/your_domain
nano /var/www/your_domain/html/index.html
sudo nano /etc/nginx/sites-available/your_domain
sudo ln -s /etc/nginx/sites-available/your_domain /etc/nginx/sites-enabled/
sudo nano /etc/nginx/nginx.conf  ## {server_names_hash_bucket_size 64;}
sudo nginx -t
sudo systemctl restart nginx
```