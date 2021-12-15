# Cerbot
### 1.- script de instalación

``` ruby 
apt-get update
apt-get upgrade

snap install core
snap refresh core

apt-get install nginx
service apache2 stop
service apache2 disable

apt-get remove certbot
snap install --classic certbot
ln -s /snap/bin/certbot /usr/bin/certbot
certbot --nginx

apt install php-fpm
apt install php-mysql
```
Nos creamos un dns:

![noip](https://github.com/anasalasro/ImplantacionAplicacionesWeb/blob/main/imagenesgit/noip.PNG)  
### 2.- Vemos la configuración que nos genera automaticamente cerbot:

![noip](https://github.com/anasalasro/ImplantacionAplicacionesWeb/blob/main/imagenesgit/configuracionNginx.PNG) 
### 3.- certificado


![noip](https://github.com/anasalasro/ImplantacionAplicacionesWeb/blob/main/imagenesgit/certificado.PNG) 

### 4.- Vemos que al conectarnos a adminer tenemos nuestro sitio seguro

![noip](https://github.com/anasalasro/ImplantacionAplicacionesWeb/blob/main/imagenesgit/adminerAmazon.PNG) 
