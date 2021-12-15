# htaccess
### 1.- Añadir autentificación a un directorio web con .htaccess

``` ruby 
htpasswd -c /clave usuarioweb
```
![LAMP](https://github.com/anasalasro/ImplantacionAplicacionesWeb/blob/main/imagenesgit/Imagen10.png)  
![LAMP](https://github.com/anasalasro/ImplantacionAplicacionesWeb/blob/main/imagenesgit/Imagen11.png)  
Añadimos lo siguente al .htaccess  
![LAMP](https://github.com/anasalasro/ImplantacionAplicacionesWeb/blob/main/imagenesgit/Imagen12.png)  

Reiniciamos el servicio de apache y nos conectamos por el navegador

``` ruby 
systemctl status apache2.service
```
Comprobamos en el navegador, nos autentificamos y podemos acceder:
![LAMP](https://github.com/anasalasro/ImplantacionAplicacionesWeb/blob/main/imagenesgit/Imagen13.png)  
![LAMP](https://github.com/anasalasro/ImplantacionAplicacionesWeb/blob/main/imagenesgit/Imagen14.png)  
