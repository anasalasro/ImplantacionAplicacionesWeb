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
``` ruby 
k0s install controller --single
```

![LAMP](https://github.com/anasalasro/ImplantacionAplicacionesWeb/blob/main/imagenesgit/Imagen6.png)  
![LAMP](https://github.com/anasalasro/ImplantacionAplicacionesWeb/blob/main/imagenesgit/Imagen7.png) 

### 3.- Instalamos adminer:

``` ruby 
apt install adminer
```
![LAMP](https://github.com/anasalasro/ImplantacionAplicacionesWeb/blob/main/imagenesgit/Imagen8.png) 
![LAMP](https://github.com/anasalasro/ImplantacionAplicacionesWeb/blob/main/imagenesgit/Imagen9.png) 

### 4.- k0s incluye kubectl

``` ruby
k0s kubectl get nodes -o wide
```
![k0s](https://github.com/anasalasro/k0s/blob/main/imagenes/informacion.PNG)
