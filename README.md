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

## Ejercicio 3 - Host virtual en apache (script)
## Ejercicio 4 - Creación de usuario del sistema para acceso a ftp, ssh, smtp (script)
## Ejercicio 5 - Los clientes podrán acceder mediante ftp para la administración de archivos configurando adecuadamente TLS
## Ejercicio 6 - Se creará un subdominio en el servidor DNS con las resolución directa e inversa (script)
## Ejercicio 7 - Se creará una base de datos además de un usuario con todos los permisos sobre dicha base de datos (ALL PRIVILEGES) (script)
## Ejercicio 8 - Se habilitará la ejecución de aplicaciones Python con el servidor web 