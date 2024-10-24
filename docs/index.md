# PRÁCTICA 2.3: Proxy inverso con Nginx

En esta práctica vamos a crear un proxy inverso para nuestro servidor web.

## Configuraciones iniciales

Para comenzar vamos a duplicar nuestra maquina virtual con el servidor web (generandola con nueva MAC, si no no tendríamos ip en esta máquina):

![alt](capturas/1.png)

Como podemos comprobar ambas tienen direcciones ip diferentes:

![alt](capturas/2.png)

El diagrama quedaría así:

![alt](capturas/8.png)

Donde la nueva máquina actua como proxy inverso.

Cambiamos el nombre de nuestra web por webserver y modificamos los archivos pertinentes:

![alt](capturas/4.png) 
![alt](capturas/5.png)
![alt](capturas/3.png)

## Nginx proxy inverso

Ahora, cuando intentamos acceder a http://ejemplo-proxy (o el nombre que tuvieráis de vuestra web de las prácticas anteriores), en realidad estaremos accediendo al proxy, que nos redirigirá a http://webserver:8080, el servidor web que acabamos de configurar para que escuche con ese nombre en el puerto 8080.

Para ello:

Crear un archivo de configuración en sites-available con el nombre deaw_manuel-proxy 

![alt](capturas/6.png)

y hay que cambiar el archivo host que configuramos en la práctica 2.1

## COMPROBACIONES

Miramos los archivos access.log de la máquina:

![alt](capturas/7.png)

Además añadimos una cabecera de la siguiente forma:

![alt](capturas/9.png)

y comprobamos en el navegador que se muestra:

![alt](capturas/10.png)
