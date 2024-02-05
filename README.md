Tarea:

# Ahora estoy usando SSH, flipa meu.

1.- Descarga la imagen ubuntu y comprueba que está en tu equipo

El comando necesario para descargar la imagen de ubuntu es el siguiente:

docker run -it - -name docker_pract_xoel ubuntu:22.04
docker pull ubuntu:22.04

Puedes usar cualquiera de los dos comandos y la versión del ubuntu que tu quieras. Puedes ver todos los nombres de esas versiones en Docker Hub. 

Para comprobar que lo has descargado, puedes verlo desde el Visual Studio con la extensión de Docker o desde la terminal con docker ps.

2.- Crea un contenedor sin ponerle nombre. ¿está arrancado? Obtén el nombre.

Para crear un contenedor sin nombre podemos usar este comando desde la terminal:

docker run -it ubuntu bash

Al usar este comando, el contenedor estará ya arrancado. Para obtener el nombre abriremos una nueva pestaña en la terminal y pondremos docker ps para que nos muestre el nombre. En mi caso mi contenedor se llama “angry_liskov” por defecto.

3.- Crea un contenedor con el nombre 'ubu1'. ¿Como puedes acceder a él?

Para crear un contenedor con ubuntu llamado “ubu1” tendremos que hacer el siguiente comando:

docker run -it - -name ubu1 ubuntu bash

Con esto crearemos un contenedor con ubuntu con el nombre correspondiente, se puede ver el nombre con docker ps, como en anteriores ocasiones.

4.- Comprueba que ip tiene y si puedes hacer un ping a google.com.

Para hacer esto tendremos que hacer una actualización de la terminal del contenedor y meterle las funciones para que funcione ifconfig y el comando ping.

Los comandos necesarios son:

apt update
apt install net-tools
apt-get update && apt-get install -y iputils-ping

La IP de nuestro contenedor es 172.17.0.2 y se puede hacer ping a Google (8.8.8.8)

5.- Crea un contenedor con el nombre 'ubu2'. ¿Puedes hacer ping entre los contenedores?

Creamos un nuevo contenedor ubu2 con docker run -it –name y luego le tendremos que meter las net-tools.

La dirección IP de ubu2 es 172.17.0.3, se le puede hacer ping desde el otro contenedor perfectamente.

6.- Sal del terminal, ¿qué ocurrió con el contenedor?

El contenedor se detiene, pero solo el de la pestaña en la que estés al cerrar la ventana. En mi caso se detuvo ubu2 y siguió corriendo ubu1.

Sin embargo, si inicial el contenedor con docker start, no se va a detener.

7.- ¿Cuánta memoria en el disco duro ocupaste? ¿Hay alguna herramienta de docker para calcularlo?

Para ver la memoria que ocupa un contenedor lo veremos con el comando docker ps –size, en mi caso, mi contenedor ocupa 46.2MB.

8.- ¿Cuanta RAM ocupan los contenedores? Crea cuantos contenedores necesites para calcularlo.

Para ver cuanta RAM usa el contenedor, lo veremos con el comando docker stats. Mi contenedor usa 884KiB de memoria RAM.
