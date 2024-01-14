# practica6-jenkins
Practica 6 Jenkins - Despliegue DAW2
# Instalar Jenkins en docker
```bash
Crear un puente de red o bridge network con docker con el comando:
docker network create jenkins
Crear un dockerfiles con los datos:
construir la imagen con el comando:
docker build -t myjenkins-blueocean:2.426.2-1 .
```