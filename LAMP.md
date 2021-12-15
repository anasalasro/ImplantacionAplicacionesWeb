# Pila LAMP.
### 1.- Instalación de apache, mysql y phpmyadmin
Con este comando, descargamos un script y se ejecuta.
``` ruby 
apt install apache2
apt install mysql
apt install phpmyadmin
```
![LAMP](https://github.com/anasalasro/ImplantacionAplicacionesWeb/blob/main/imagenesgit/Imagen1.png)  
![LAMP](https://github.com/anasalasro/ImplantacionAplicacionesWeb/blob/main/imagenesgit/Imagen2.png)  
![LAMP](https://github.com/anasalasro/ImplantacionAplicacionesWeb/blob/main/imagenesgit/Imagen3.png)  

Podemos comprobar el estado de apache y mysql:

``` ruby 
systemctl status apache2.service
systemctl status mysql.service
```
![LAMP](https://github.com/anasalasro/ImplantacionAplicacionesWeb/blob/main/imagenesgit/Imagen4.png)  
![LAMP](https://github.com/anasalasro/ImplantacionAplicacionesWeb/blob/main/imagenesgit/Imagen5.png)  
### 2.- Vemos que podemos acceder a nuestra base de datos a través de phpmyadmin

![LAMP](https://github.com/anasalasro/ImplantacionAplicacionesWeb/blob/main/imagenesgit/Imagen6.png)  
![LAMP](https://github.com/anasalasro/ImplantacionAplicacionesWeb/blob/main/imagenesgit/Imagen7.png) 
### 3.- LAMP master:

![LAMP](https://github.com/anasalasro/ImplantacionAplicacionesWeb/blob/main/imagenesgit/Imagen15.png) 
![LAMP](https://github.com/anasalasro/ImplantacionAplicacionesWeb/blob/main/imagenesgit/Imagen16.png) 
![LAMP](https://github.com/anasalasro/ImplantacionAplicacionesWeb/blob/main/imagenesgit/Imagen17.png) 

### 4.- Instalamos adminer:

``` ruby 
apt install adminer
```
![LAMP](https://github.com/anasalasro/ImplantacionAplicacionesWeb/blob/main/imagenesgit/Imagen8.png) 
![LAMP](https://github.com/anasalasro/ImplantacionAplicacionesWeb/blob/main/imagenesgit/Imagen9.png) 

### 5.- Script LAMP instalación desatendida:

``` ruby
!/bin/bash
#Instalación LAMP

contra=root
contraphp=root

apt-get update
set -x
#INSTALAMOS APACHE2
apt-get install -y apache2
clear

#MYSQL
apt-get install -y debconf-i18n
wget https://dev.mysql.com/get/mysql-apt-config_0.8.19-1_all.deb
export DEBIAN_FRONTEND="noninteractive";
echo  mysql-apt-config mysql-apt-config/select-server select mysql-8.0 | debconf-set-selections;
dpkg -i mysql-apt-config_0.8.19-1_all.deb
apt-get update
apt-get install -y mysql-server
#mysqladmin -u root -p root

#CAMBIAMOS LA CONTRASEÑA DE MYSQL
mysql -u root <<< "ALTER USER 'root'@'localhost' IDENTIFIED BY 'root';"
mysql -u root <<< "FLUSH PRIVILEGES;"

#modulos necesarios
apt install -y php php-mysql
#INSTALAMOS PHPMYADMIN
apt-get install -y php7.4-bz2 php7.4-mbstring php7.4-xml php7.4-zip

#CONFIGURAMOS PHPMYADMIN
echo 'phpmyadmin phpmyadmin/dbconfig-install boolean true' | Sudo debconf-set-selections
echo 'phpmyadmin phpmyadmin/app-password-confirm password $contraphp' | Sudo debconf-set-selections
echo 'phpmyadmin phpmyadmin/mysql/admin-pass password $contraphp' | Sudo debconf-set-selections
echo 'phpmyadmin phpmyadmin/mysql/app-pass password $contraphp' | Sudo debconf-set-selections
echo 'phpmyadmin phpmyadmin/reconfigure-webserver multiselect Apache2' | Sudo debconf-set-selections

apt-get install -y phpmyadmin

#INSTALAMOS ADMINER
mkdir /var/www/html/adminer/
cd /var/www/html/adminer/
wget https://github.com/vrana/adminer/releases/download/v4.7.3/adminer-4.7.3.php
mv adminer-4.7.3.php index.php
chmod 755 -R /var/www/html/adminer/index.php
chown -R www-data:www-data /var/www/html/adminer/

#INSTALAMOS GOACCESS

wget https://tar.goaccess.io/goaccess-1.5.2.tar.gz
tar -xzvf goaccess-1.5.2.tar.gz
cd goaccess-1.5.2/
./configure --enable-utf8 --enable-geoip=mmdb
make
```
