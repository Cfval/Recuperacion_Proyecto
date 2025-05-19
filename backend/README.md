# Entorno Desarrollo
Cómo poner en marcha el entorno de desarrollo

# Instalación de Docker
sudo apt update && sudo apt install -y docker.io

# Instalación de Docker Compose
sudo apt install -y docker-compose

# Instalación de Apache2
sudo apt install -y apache2 

# Clonar el repositorio 
```bash
git clone https://github.com/Cfval/Recuperacion_Proyecto.git
```
## Crear y arrancar infraestructura

```bash
docker compose -f docker-compose-dev.yml up -d
```
## VirtualHosts
Añade al archivo `hosts` el dominio:
```bash
<ip_maquina_anfitrión> films.api.dev.com
```

## Otras acciones
Arrancar o parar entorno
```bash
docker compose -f docker-compose-dev.yml start/stop
```

Limpiar entorno (elimina contendores, volúmenes, redes e imágenes)
```bash
docker compose -f docker-compose-dev.yml down -v --rmi all
```

# Entorno Producción
En esta sección se explica cómo poner en marcha el proyecto en un entorno de producción

## Crear variables de entorno
Se deberá crear el archivo `.env` en la raíz del proyecto, deberá contener las siguientes variables de entorno:
```bash
MYSQL_ROOT_PASSWORD=<password>
MYSQL_USER=<user>
MYSQL_PASSWORD=<password>
```

## Crear archivo de configuración
Se deberá crear el archivo `app/dbconfiguration.yml` que contendrá la conexión del backend con la base de datos, se deberá crear dentro de la carpeta app con la siguiente información:

```yml
ip: "db"
dbname: "films"
user: "<mysql_user>"
pass: "<mysql_password>"
```
*Nota: Estos datos dependerán de los valores de las variables de entorno que hayas especificado.

## Crear y arrancar infraestructura

```bash
docker compose up -d
```

## VirtualHosts
Debe estar creado y configurado el dominio para que apunte al entorno de producción:
```bash
filmsara.api.chickenkiller.com
```

## Otras acciones
Arrancar o parar entorno
```bash
docker compose start/stop
```

Limpiar entorno (elimina contendores, volúmene, redes e imágenes)
```bash
docker compose down -v --rmi all
```