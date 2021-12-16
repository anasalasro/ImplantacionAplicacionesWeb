# Bookmedik.
### 1.- Descargamos bookmedik
Con este comando, descargamos un script y se ejecuta.
``` ruby 
unzip bookmedik-master.zip
```
Copiamos el bookmedik a /var/www/html/:

``` ruby 
cp -R bookmedik-master /var/www/html/
``` 
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
Reiniciamos
``` ruby 
 systemctl restart nginx.service 
```
Insytalamos el paquete necesario:
``` ruby 
 apt install php-fpm
```

### 3.- Accedemos:
``` ruby 
 cd /var/www/html/bookmedik-master/
 nano index.php 
```

``` ruby 
 cd core/controller/
nano Database.php 
```

![LAMP](https://github.com/anasalasro/ImplantacionAplicacionesWeb/blob/main/imagenesgit/Imagen15.png) 



![LAMP](https://github.com/anasalasro/ImplantacionAplicacionesWeb/blob/main/imagenesgit/Imagen15.png) 
![LAMP](https://github.com/anasalasro/ImplantacionAplicacionesWeb/blob/main/imagenesgit/Imagen16.png) 
![LAMP](https://github.com/anasalasro/ImplantacionAplicacionesWeb/blob/main/imagenesgit/Imagen17.png) 

### 4.- Configuramos adminer:
Nos decargamos:
``` ruby 
adminer-4.8.1-mysql.php 
/var/www/html# cp /home/usuario/Descargas/adminer-4.8.1-mysql.php .
mv adminer-4.8.1-mysql.php adminer.php
```
![LAMP](https://github.com/anasalasro/ImplantacionAplicacionesWeb/blob/main/imagenesgit/Imagen8.png) 
![LAMP](https://github.com/anasalasro/ImplantacionAplicacionesWeb/blob/main/imagenesgit/Imagen9.png) 
