# MirrorMirror

Forked from /ctrlaltdylan

# Kiosk Setup on Raspbian/Jessie

Install the web server packages:

> sudo apt-get update sudo apt-get install nginx php5-fpm php5-cli php5-mcrypt git

Copy the following mirror.conf into /etc/nginx/sites-available/mirror.conf

[mirror.conf](https://gist.github.com/ctrlaltdylan/18d78a608a3d81c964e7)

Link the sites-available to sites-enabled

> sudo ln -s /etc/nginx/sites-available/mirror.conf /etc/nginx/sites-enabled/mirror.conf

Reload nginx

> sudo service nginx reload

Make directory /home/pi/projects

 - Directory is specified in mirror.conf, change if you want to have a different directory

> mkdir /home/pi/projects

Cd into directory

> cd /home/pi/projects

Git clone project

> git clone https://github.com/0ffkilter/MirrorMirror

Install composer and Lumen dependencies

> curl -sS https://getcomposer.org/installer | sudo php -- --install-dir=/usr/local/bin --filename=composer

Cd into projects

> cd MirrorMirror

Run installation package

> sudo composer install

Change directory permissions to allow for read/write

> sudo chmod -R 777 storage

