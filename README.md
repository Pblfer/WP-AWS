# WP-AWS
Install only wordpress on EC2 for make a real stack

```
sudo -s
apt-get update
apt-get upgrade
apt-get install apache2 python-software-properties unzip
add-apt-repository ppa:ondrej/php
apt-get update
apt-get install php7.2
sudo apt-get install php-mysql

nano /etc/apache2/sites-enabled/000-default.conf
```
```
<VirtualHost *:80>
        #ServerName dantta.com
        #ServerAlias *.dantta.com A 34.195.202.25
        DocumentRoot /var/www/staging

        <Directory /var/www/staging>
        Options -Indexes
        AllowOverride All
        Order allow,deny
        Allow from all
        </Directory>
</VirtualHost>
```
```
cd /var/www/html
rm -rf *
cd ../
mkdir staging
cd staging
wget https://wordpress.org/latest.zip
unzip latest.zip
cd wordpress/
mv * /var/www/staging
cd ..
rmdir wordpress/
rm latest.zip

sudo chown -R www-data:www-data /var/www/staging
sudo service apache2 restart
```

# AWS PLUGIN INSTALL CURL
``
sudo apt-get install php5-curl
nano /etc/php/7.2/cli/php.ini
service apache2 restart
``
