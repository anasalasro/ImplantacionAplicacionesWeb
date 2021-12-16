# Instalación del Servidor Nginx 
### 1.- Instalación de nginx
Con este comando, descargamos un script y se ejecuta.
``` ruby 
apt-get install nginx -y 
```
### 2.- Una vez instalado, inicia el servicio Nginx y habilítalo para que se inicie al reiniciar el sistema:

``` ruby 
systemctl start nginx
systemctl enable nginx
```

### 3.- Configuración de los Servidores de aplicaciones:
En el primer servidor de aplicaciones, elimina el archivo index.html predeterminado y crea uno nuevo:

``` ruby 
rm -rf /usr/share/nginx/html/index.html
nano /usr/share/nginx/html/index.html

<html>
<title>Primer Server</title>
<body>
Primer Server
</body>
</html>
Guarda y cierra el archivo.
```
En el segundo servidor de aplicaciones, elimina el archivo index.html predeterminado y crea uno nuevo:
``` ruby 
rm -rf /usr/share/nginx/html/index.html
nano /usr/share/nginx/html/index.html

<html>
<title>Segundo Server</title>
<body>
Segundo Server
</body>
</html>
Guarda y cierra el archivo.
```
### 4.- Configura un balanceador de carga Nginx:
Elimina el archivo de configuración predeterminado de Nginx y crea un nuevo archivo de configuración del balanceador de carga:
``` ruby 
rm -rf /etc/nginx/sites-enabled/default 
nano /etc/nginx/conf.d/load-balancing.conf

upstream backend {
        server 192.168.10.11;
        server 192.168.10.12;
    }
	
    server {
        listen      80;
        server_name loadbalancing.example.com;

        location / {
	        proxy_redirect      off;
	        proxy_set_header    X-Real-IP $remote_addr;
	        proxy_set_header    X-Forwarded-For $proxy_add_x_forwarded_for;
	        proxy_set_header    Host $http_host;
		proxy_pass http://backend;
	}
}
```
