# Documentación Practica DNS con Docker

**Autor:** Jorge Garre Corrales

### 1. Crear fichero docker-compose.yml

![](assets/20251208_213947_image.png)

### 2. Ficheros de configuración del servidor

Este es el comando que he usado para ver la IP del contenedor

![](assets/20251209_000441_image.png)

Estos son los ficheros que nos hacen falta

1. named.conf
2. named.conf.options
3. named.conf.local
4. jorgegarre.test.dns
5. jorgegarre.test.rev

#### 2.1 Fichero named.conf

Este fichero ya viene configurado correctamente en esta imagen ya que viene con el paquete de bind, este es el comando que he ejecutado para comprobar el fichero

![](assets/20251209_001322_image.png)

#### 2.2 Fichero named.conf.options

He copiado el fichero de el contenedor a mi carpeta config

![](assets/20251209_001647_image.png)

Y lo he configurado de la siguiente forma

![](assets/20251209_002022_image.png)


![](assets/20251209_002729_image.png)
