# Incendios forestales

Esta organización contiene repositorios para el análisis de datos relacionados con incendios forestales. Estos análisis se realizan a través de programas desarrollados en el lenguaje de programación R.

El ambiente de desarrollo se implementa a través de un contenedor Docker.

## Contenedor Docker

### Construcción y ejecución

```shell
# Construcción
# (debe ejecutarse en el directorio en el que se ubica el Dockerfile)
docker build -t incendios-forestales .

# Ejecución
docker run -d --name incendios-forestales \
  -p 8787:8787 \
  -v ~/incendios-forestales/git:/home/rstudio \
  --env-file ./incendios-forestales.env \
  incendios-forestales
```
  
### Acceso

[http://localhost:8787](http://localhost:8787)

Username: rstudio  
Password: incendios

### Detención y borrado

```shell
# Detención
docker stop incendios-forestales

# Borrado
docker rm incendios-forestales
```

### Ejemplo de contenido del archivo `./incendios-forestales.env`

```shell
# Clave para ingresar a RStudio
PASSWORD=incendios
```
