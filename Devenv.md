# Laravel Set-up for Linux Distros

### TODO Arch

### This is for Ubuntu 20.04 base distributions
- This will just waste your time but it's important :)
```
sudo apt update
sudo apt upgrade
```

### Install PHP
```
sudo apt install software-properties-common
sudo add-apt-repository ppa:ondrej/php
sudo apt update
```
```
sudo apt install php7.4 php7.4-common php7.4-mysql php7.4-xml php7.4-xmlrpc php7.4-curl php7.4-gd php7.4-imagick php7.4-cli php7.4-dev php7.4-imap php7.4-mbstring php7.4-opcache php7.4-soap php7.4-zip php7.4-intl php7.4-sqlite3 php7.4-bcmath php7.4-zip -y
```

### Composer - Just go to the site to install composer or 
```
sudo apt install composer
```

### Install Laravel
```
composer global require laravel/installer
```

### Open ~/.bashrc then add at the end
```
export PATH="~/.config/composer/vendor/bin:$PATH"
```

### Install valet
```
composer global require cpriego/valet-linux
sudo apt-get install network-manager libnss3-tools jq xsel -y
valet install
sudo apachectl stop
valet restart
```

### Install MySQL 
- guide: https://www.digitalocean.com/community/tutorials/how-to-install-mysql-on-ubuntu-20-04
```
sudo apt install mysql-server -y
sudo mysql_secure_installation
sudo mysql
```

- MySQL
```
SELECT user,authentication_string,plugin,host FROM mysql.user;
ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'Password*000';
FLUSH PRIVILEGES;
SELECT user,authentication_string,plugin,host FROM mysql.user;
```
```
exit
```

- Check mysql auth

### Install PhpMyAdmin
- Just download https://www.phpmyadmin.net/downloads/

### Install vim
```
sudo apt install vim -y
```

### Install git
```
sudo apt install git -y
```
- Fix old keys permissions
```
sudo chmod 600 ~/.ssh/config
sudo chmod 600 ~/.ssh/hju_rsa
sudo chmod 600 ~/.ssh/other_rsa
```

### Set vim as default editor
``git config --global core.editor "vim"``

### Zsh
```
sudo apt install zsh -y
zsh --version
chsh -s $(which zsh)
```

### Install Oh-My-Zsh
```
sudo apt install curl
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```
- Pi Theme
```
wget -O ~/.oh-my-zsh/themes/pi.zsh-theme https://raw.githubusercontent.com/tobyjamesthomas/pi/master/pi.zsh-theme
```

### Install Mailhog

- Arch only
```
yay -S mailhog-bin
```

- Debian
Check https://www.lullabot.com/articles/installing-mailhog-for-ubuntu-1604
