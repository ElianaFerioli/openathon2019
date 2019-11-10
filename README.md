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

