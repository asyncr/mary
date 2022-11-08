# CREAR UN CONTENEDOR 


## Configuración del entorno
Crea una carpeta en cualquier lugar y considera que esa carpeta la podras eliminar cuando ya no uses el contenedor de mariadb

```
mkdir NAME_FILE
```
Clona esté repositorio en la carpeta creada
```
git clone https://github.com/asyncr/mary NAME_FILE
```
Si tienes problemas con la conexion remota de tu usuario a mariadb elimina ese contenedor.

```
# LISTAR CONTENEDORES EN EJECUCIÓN
docker ps 
# LISTAR TODOS LOS CONTENEDORES
docker ps -a
# ELIMINAR UN CONTENEDOR  
docker stop NAME_CONTAINER or ID_CONTAINER  #SOLO SI TU CONTENEDOR ESTÁ ACTIVO
docker rm NAME_CONTAINER or ID_CONTAINER
```

## Creacion del contenedor
Una vez eliminado el contenedor, crearemos nuestro propio contenedor mediante el archivo docker-compose.yml

Para ello debemos estar en nuestra carpeta donde hemos clonamos el repositorio y ejecutamos lo siguiente:
```
docker-compose build
docker-compose up -d
```

## Iniciamos nuestro contenedor
```
docker exec -ti mary bash
```
Y listo haz creado sin problemas tu contenedor.
Ahora ya lo puedes usar donde lo requieras.

## INFORMACION BÁSICA
- Password para root: __mariadb__
- Nombre del contenedor: __mary__
- Puerto externo del contendor: __3360__
- Puerto interno del contenedor: 3306
- Iniciar el contenedor: __docker start mary__
- Entrar al contenedor: __docker exec -ti mary bash__
- Apagar el contenedor: __docker stop mary__
- IP del contenedor: __docker inspect mary | grep IPAddress__
## ELIMINAR EL CONTENEDOR
```
docker start mary
docker stop mary
docker rm mary
```
## ELIMINAR EL VOLUMEN
```
docker volume ls
docker volume rm mary_maria_data
docker volume ls
```

## /asyncr