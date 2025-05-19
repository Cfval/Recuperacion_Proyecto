# Entorno Desarrollo
En esta sección se explica cómo poner en marcha el proyecto en tu entorno de desarrollo

## Crear y arrancar infraestructura

```bash
docker compose -f docker-compose-dev.yml up -d
```
## VirtualHosts
Añade al archivo `hosts` el dominio:
```bash
<ip_maquina_anfitrión> films.dev.com
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

## Crear y arrancar infraestructura

```bash
docker compose up -d
```

## VirtualHosts
Debe estar creado y configurado el dominio para que apunte al entorno de producción:
```bash
filmscfv.gleeze.com
```

## Otras acciones
Arrancar o parar entorno
```bash
docker compose start/stop
```

Limpiar entorno (elimina contendores, volúmenes, redes e imágenes)
```bash
docker compose down -v --rmi all
```