# Jenkins Lab

## Ejecutar Docker Compose

Para ejecutar Docker Compose, asegúrate de que tengas Docker Compose instalado en tu sistema. Luego, sigue estos pasos:

1. Navega a la ubicación donde se encuentra tu archivo `docker-compose.yml`.

En este punto debemos modificar el docker-compose para habilitar el puerto 3000.

2. Ejecuta el siguiente comando en tu terminal para iniciar los contenedores definidos en el archivo `docker-compose.yml`:

```bash
docker-compose up -d
```

3. Extraer passwords

```bash
docker logs id_container
```

```bash
docker exec id_container cat /var/jenkins_home/secrets/initialAdminPassword
```
4. Ingresar al contenedor de Jenkins 

Ingresa a Jenkins a través del navegador web utilizando la dirección http://localhost:8080. Luego, utiliza el password obtenido en el paso anterior para completar la configuración inicial y crear el primer usuario.

5. Crear un usuario en Jenkins
<p>

6. Instalar nodeJS en jenkins. En este caso es la version 10.15.2

Desde la interfaz de Jenkins, se puede instalar el plugin de NodeJS, luego configurarlo en la sección de herramientas del sistema para instalar la versión deseada.

![](/imgs/WhatsApp%20Image%202024-10-16%20at%208.51.27%20PM.jpeg)

![](/imgs/WhatsApp%20Image%202024-10-16%20at%208.50.54%20PM.jpeg)

7.  Crear un Job

Para ejecutar la construcción de la aplicación, se creó un job en Jenkins que utiliza el código fuente desde un repositorio Git y ejecuta los comandos npm install, npm run build y npm satat dist/app.js para la aplicación Node.js.

![](/imgs/WhatsApp%20Image%202024-10-16%20at%208.48.55%20PM.jpeg)

8. Configuraciones para CI

![](/imgs/WhatsApp%20Image%202024-10-16%20at%208.52.06%20PM.jpeg)
![](/imgs/WhatsApp%20Image%202024-10-16%20at%208.52.17%20PM.jpeg)

9. Ver los logs para saber el 

![](/imgs/WhatsApp%20Image%202024-10-16%20at%208.48.31%20PM.jpeg)

10. Si todo se configuro correctamente debeiamos poder ver este mensaje que arroja el app.js en nuestro http://localhost:3000

![](/imgs/WhatsApp%20Image%202024-10-16%20at%208.48.14%20PM.jpeg)

## Conclusión

En este laboratorio, hemos configurado Jenkins en un contenedor de Docker, instalamos Node.js, y configuramos un pipeline de CI/CD para automatizar la construcción y ejecución de una aplicación Node.js. Además, se verificó que la aplicación esté corriendo correctamente a través de Jenkins, exponiendo el puerto 3000 para acceder a la aplicación desde el navegador.