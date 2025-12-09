# Documentación Practica DNS con Docker

**Autor:** Jorge Garre Corrales


##  Índice

1. [Crear fichero docker-compose.yml](#1-crear-fichero-docker-composeyml)
2. [Ficheros de configuración del servidor](#2-ficheros-de-configuración-del-servidor)
   - [2.1 Fichero named.conf](#21-fichero-namedconf)
   - [2.2 Fichero named.conf.options](#22-fichero-namedconfoptions)
   - [2.3 Fichero named.conf.local](#23-fichero-namedconflocal)
   - [2.4 Fichero jorgegarre.test.dns](#24-fichero-jorgegarretestdns)
   - [2.5 Fichero jorgegarre.test.rev](#25-fichero-jorgegarretestrev)
3. [Comprobaciones](#3-comprobaciones)

### 1. Crear fichero docker-compose.yml

![](assets/20251209_134445_image.png)

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

![](assets/20251209_135755_image.png)


Mas tarde al hacer las comprobaciones de la configuración lo lograba conectarme al contenedor por lo que tuve que cambiar la linea listen-on port 53 { 172.19.0.2; }; por lo siguiente para que pudiera acceder desde la IP de mi ordenador

![](assets/20251209_171709_image.png)



#### 2.3 Fichero named.conf.local

He copiado el fichero del contenedor y le he puesto la siguiente configuración

![](assets/20251209_002441_image.png)

#### 2.4 Fichero jorgegarre.test.dns

He creado el fichero y le he puesto la siguiente configuración

![](assets/20251209_003910_image.png)

#### 2.5 Fichero jorgegarre.test.rev

He creado el fichero y le he puesto la siguiente configuración

![](assets/20251209_004210_image.png)

Y por ultimo debemos de pasarle los ficheros de configuración al contenedor, para ello he añadido la siguiente configuración al fichero docker-compose.yml

![](assets/20251209_004409_image.png)

### 3. Comprobaciones

Para hacer las comprobaciones he accedido a la terminal de el contenedor Docker con el siguiente comando

Comprobación de fichero named.conf

![](assets/20251209_004820_image.png)

Comprobación de jorgegarre.test.dns (Zona directa)

![](assets/20251209_140430_image.png)

Comprobación de jorgegarre.test.rev (Zona inversa)

![](assets/20251209_141149_image.png)


Comprobación con dig

![](assets/20251209_171833_image.png)



Comprobación inversa

![](assets/20251209_172033_image.png)


Comprobación con nslookup

![](assets/20251209_171945_image.png)
