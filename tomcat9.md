```ruby
apt install tomcat9
apt install tomcat9-docs
apt install tomcat9-examples 
apt install tomcat9-admin 
```
Añadimos:
```ruby
root@debianAnaSalas:/etc/tomcat9# nano tomcat-users.xml 
<role rolename="manager-gui"/>
<user username="tomcat" password="s3cret" roles="manager-gui"/>
```

![LAMP](https://github.com/anasalasro/ImplantacionAplicacionesWeb/blob/main/imagenesgit/tomcat.PNG) 
![LAMP](https://github.com/anasalasro/ImplantacionAplicacionesWeb/blob/main/imagenesgit/tomcat1.PNG) 
![LAMP](https://github.com/anasalasro/ImplantacionAplicacionesWeb/blob/main/imagenesgit/tomcat2.PNG) 
