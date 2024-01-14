# practica6-jenkins
Practica 6 Jenkins - Despliegue DAW2
# Instalar Jenkins en docker
```bash
Crear un puente de red o bridge network con docker con el comando:
docker network create jenkins

Crear un dockerfiles con los datos:

construir la imagen con el comando:
docker build -t myjenkins-blueocean:2.426.2-1 .

Corremos la imagen creada como un contenedor con el comando docker run : 
docker run --name jenkins-blueocean --restart=on-failure --detach \
  --network jenkins --env DOCKER_HOST=tcp://docker:2376 \
  --env DOCKER_CERT_PATH=/certs/client --env DOCKER_TLS_VERIFY=1 \
  --publish 8080:8080 --publish 50000:50000 \
  --volume jenkins-data:/var/jenkins_home \
  --volume jenkins-docker-certs:/certs/client:ro \
  myjenkins-blueocean:2.426.2-1 
```
# Iniciamos Jenkins  
En el navegador localhost:8080 la cual nos pedirá una clave
# Recuperamos la contraseña
``` bash
En la terminal entramos al contenedor
docker exec -it <id del contenedor> bash
buscamos la carpeta
cd /var/jenkins_home/secrets/
abrimos el archivo
cat initialAdminPassword
Copiamos la clave en el navegador jenkins y nos aparece la pantalla de bienvenida,
Le damos click a Install suggested plugins
Se instala y luego pedira regristrarnos
Le damos en en skip, y confirmamos el puerto y listo

```