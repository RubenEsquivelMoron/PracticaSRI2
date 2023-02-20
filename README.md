# PracticaSRI2

## Ejercicio 1 - Alojamiento a paginas web estaticas y dinamicas con php

- Comenzaremos instalando la pila LAMP en nuestro sistema con el comando. Para ello, comenzaremos actualizando los repositorios de linux con el siguiente comando:
```bash
sudo apt update
```
- Tras actualizar los repositorios, seguiremos por instalar apache
```bash
sudo apt install apache2
```
- Seguidamente, instalaremos MySQL
```bash
sudo apt install mysql-server
```
- Y por ultimo, instalaremos php
```bash
sudo apt install php libapache2-mod-php php-mysql
```
- Y ya tendriamos la pila LAMP instalada para dar alojamiento a las paginas web estaticas y dinamicas con php


## Ejercicio 2 - Creación de usuarios y del directorio correspondiente para el alojamiento web (script)



## Ejercicio 3 - Host virtual en apache (script)
- Comenzaremos actualizando los repositorios
```bash
ssudo apt update
```
- Despues, deberemos crear una carpeta een el directortorio /var/www/ donde gestionaremos las paginas y los host virtuales
```bash
sudo mkdir -p /var/www/paco/public_html
```
- Ahora tenemos la estructura de directorio para nuestros archivos, pero son propiedad de nuestro usuario root. Si queremos que nuestro usuario regular pueda modificar archivos en nuestros directorios web, podemos cambiar la propiedad haciendo esto:
```bash
sudo chown -R $USER:$USER /var/www/paco/public_html
```
- Tambien, deberemos permitir el acceso de lectura al directorio /var/www con el comando:
```bash
sudo chmod -R 755 /var/www
```
- Ahora, crearemos la pagina de inicio en la pagina que tenemos de prueeba:
```bash
nano /var/www/paco/public_html/index.html
```
- Entraremos al index.html con:
```bash
sudo nano index.html
```
- Y editaremos el fichero para crear una pagina web por defecto
```html
<html>
  <head>
    <title>paco</title>
  </head>
  <body>
    <h1>Esta es la pagina web de paco</h1>
  </body>
</html>
```
- Guardaremos eel archivo, y nos dirigiremos a la ruta /etc/apache/sites-available/
- Ahi, crearemos el archivo .conf y podemos hacerlo desde cero, o tambien podemos copiar el archivo 000-default.conf
```bash
sudo cp /etc/apache2/sites-available/000-default.conf /etc/apache2/sites-available/paco.conf
```
- Ahora, editaremos el archivo con
```bash
sudo nano /etc/apache2/sites-available/paco.conf
```
- Y escribiremos lo siguiente:
```bash
<VirtualHost *:80>
     ServerAdmin admin@paco.marisma.local
     ServerName www.paco.marisma.local
     ServerAlias paco.marisma.local
     DocumentRoot /var/www/paco/public_html
     ErrorLog /error.log
     CustomLog /access.log combined
</VirtualHost>
```
- Seguidamente, deberemos habilitar nuestro sitio web
```bash
sudo a2ensite paco.conf
```
- Tambien, deberemos deshabilitar el sitio web por defecto (000-default.conf)
```bash
sudo a2dissite 000-default.conf
```
- Tambien deberemos asignar una ip y un dominio a cada host que creemos en el archivo ubicado en /etc
```bash
sudo nano /etc/hosts
```
- Editaremos el archivo agregando una ip y un dominio a cadaa host que creemos
```bash
127.0.0.1   localhost
127.0.1.1   guest-desktop
your_server_IP paco.marisma.local
```
- Por ultimo reiniciaremos apache para guardar/aplicar los cambios en el sistema
```bash
sudo service apache22 restart
```
- Y ya tendremos nuestro sitio web habilitado, el cual para probarlo, deberemos irnos al navegador y escribir:
```
http://paco.com
```

### Resultado:
### Script automatico de creacion 

## Ejercicio 4 - Creación de usuario del sistema para acceso a ftp, ssh, smtp (script)
## Ejercicio 5 - Los clientes podrán acceder mediante ftp para la administración de archivos configurando adecuadamente TLS
## Ejercicio 6 - Se creará un subdominio en el servidor DNS con las resolución directa e inversa (script)
## Ejercicio 7 - Se creará una base de datos además de un usuario con todos los permisos sobre dicha base de datos (ALL PRIVILEGES) (script)
## Ejercicio 8 - Se habilitará la ejecución de aplicaciones Python con el servidor web 
