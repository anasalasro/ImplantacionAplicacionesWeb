# Bookmedik.
### 1.- Descargamos bookmedik
Con este comando, descargamos un script y se ejecuta.
``` ruby 
unzip bookmedik-master.zip
```
![LAMP](https://github.com/anasalasro/ImplantacionAplicacionesWeb/blob/main/imagenesgit/Imagen1.png)  
![LAMP](https://github.com/anasalasro/ImplantacionAplicacionesWeb/blob/main/imagenesgit/Imagen2.png)  
![LAMP](https://github.com/anasalasro/ImplantacionAplicacionesWeb/blob/main/imagenesgit/Imagen3.png)  

Copiamos el bookmedik a /var/www/html/:

``` ruby 
cp -R bookmedik-master /var/www/html/
```
![LAMP](https://github.com/anasalasro/ImplantacionAplicacionesWeb/blob/main/imagenesgit/Imagen4.png)  
![LAMP](https://github.com/anasalasro/ImplantacionAplicacionesWeb/blob/main/imagenesgit/Imagen5.png)  
### 2.- Configuramos en sites-enabled:
``` ruby 
/etc/nginx# nano sites-enabled/default.old 
server {

        listen 80 default_server;

        listen [::]:80 default_server;

        root /var/www/html;

        index index.php index.html index.htm index.nginx-debian.html;
        
        server_name _;
        location / {
                try_files $uri $uri/ =404;

        }
       }


```
root@debianAnaSalas:/etc/nginx# systemctl restart nginx.service 

root@debianAnaSalas:/etc/nginx# apt install php-fpm


![LAMP](https://github.com/anasalasro/ImplantacionAplicacionesWeb/blob/main/imagenesgit/Imagen6.png)  
![LAMP](https://github.com/anasalasro/ImplantacionAplicacionesWeb/blob/main/imagenesgit/Imagen7.png) 
### 3.- LAMP master:

![LAMP](https://github.com/anasalasro/ImplantacionAplicacionesWeb/blob/main/imagenesgit/Imagen15.png) 
![LAMP](https://github.com/anasalasro/ImplantacionAplicacionesWeb/blob/main/imagenesgit/Imagen16.png) 
![LAMP](https://github.com/anasalasro/ImplantacionAplicacionesWeb/blob/main/imagenesgit/Imagen17.png) 

### 4.- Instalamos adminer:

``` ruby 
/etc/nginx# nano sites-enabled/default.old 
```
![LAMP](https://github.com/anasalasro/ImplantacionAplicacionesWeb/blob/main/imagenesgit/Imagen8.png) 
![LAMP](https://github.com/anasalasro/ImplantacionAplicacionesWeb/blob/main/imagenesgit/Imagen9.png) 
