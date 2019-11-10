# Lab 05 - Creando un stack de servicios con docker-compose
<br/>
<p align="center">
<img src="./resources/docker-compose.png">
<br/>
</p>
<br/>

## Objetivos y resultados
El objetivo de este laboratorio es crear una stack de servicios orquestados por **docker-compose**. Para ello, aprovecharemos la imágenes Docker que hemos generado en los laboratiorios anteriores.
Como resultado, obtendremos un fichero YAML con toda la configuración necesarioa para levantar nuestro stack con un solo comando.
<br/>
## ¿Qué es docker-compose?
Se trata de una herramienta ideal para ejecutar **stacks** de aplicaciones contenerizadas. 
Mediante una definición YAML, se configuran todos los servicios implicados en el stack y, mediante un único comando, permite desplegar un stack completo de servicios. 
<br/>
## ¿Cuál es la ventaja de usar docker-compose?
Se trata de un tipo de orquestación de stacks de contenedores. Cuando queremos gestionar distintos servicios que tienen que interactuar entre sí, compose se encarga de mantener los procesos y configurar la red subyacente para que estos estén constantemente **up and running**. Si alguno de los servicios falla, compose se encarga de volver a arrancarlo manteniendo la integridad del stack. 
<br/>
## ¿Cómo funciona?
En un fichero docker-compose, es posible definir tres tipos de recursos básicos:
<br/>
**-	Servicios:** la sección de servicios hace referencia a la configuración de los contendores. Teniendo en cuenta nuestro objetivo final, nuestra sección se servicios estará compuesta por tres servicios contenerizados, un servicio de front, un back y una capa de persistencia.
<br/>
**-	Volúmenes:** hace referencia a un espacio de disco físico que será reservado en el host para persistir la información de uno o varios servicios contenerizados.
<br/>
**-	Redes:** hace referencia a la capa de comunicación que se va a definir para el stack. Aquí se definirán las reglas de comunicación entre los contenedores e incluso entre los contenedores y el host.
<br/>
```version: '3'
services:
  frontend:
    image: my-front
    ...
  backend:
    image: my-back
    ...
  db:
    image: persistence
    ...
volumes:
   my-volume:
networks:
   my-stack-network:
```
## Crear un stack de servicios gestionados por doker-compose.

### Paso 1. Instalar docker-compose.
Descarga el paquete
<br/>
```curl -L "https://github.com/docker/compose/releases/download/1.24.1/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose```
<br/>
Aplica permisos de ejecución al fichero binario
<br/>
```chmod +x /usr/local/bin/docker-compose```
<br/>
Añádelo al PATH mediante un enlace simbólico
<br/>
```ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose```
> **Recomendamos usar la versión estable**
> Tras la instalación, ejecuta el siguiente comando:
> ```docker-compose --version```
> Si todo ha ido bien, se mostrará la versión instalada de docker-compose.
<br/>

