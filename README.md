![1](https://user-images.githubusercontent.com/91874745/167040995-45ee0843-e456-4e96-a617-92254c26b561.gif)

#  Ejecutando contenedores en [***Docker***](https://www.docker.com)

## Ejemplo 1 


 **Vista por consola (se describen pasos en los siguientes puntos).**
 
 ![1primero](https://user-images.githubusercontent.com/91874745/167041963-07e5aa0a-a231-4b12-9a91-0170ac335c07.gif)


  **Primer paso** 
  Antes de empezar hay que iniciar [***Docker***](https://www.docker.com), para esto abrimos la app [***Docker***](https://www.docker.com) (en mi caso tengo la versión de escritorio) y enseguida nos indica tenemos que ejecutar el comando `docker run -d -p 08:80 docker/getting-started` por consola y después volver a la app.
  
  Procedemos con el ejemplo 1 de este ejercicio para la ejecución de un contendor, en la misma consola para descargarnos una imagen previa usamos el comando `docker pull ubuntu:18.04`

  **Segundo paso**
  Crear un contenedor de ubunto:18.04 y tener acceso a un shell en él. Si no hemos descargado la imagen de manera previa se descargará, para esto usaremos `docker run -it ubuntu:18.04/bin/bash`

  Como podemos ver ha habido cambios en la consola ya que al crear el contenedor se nos da acceso a un shell del mismo, en este caso ubuntu

  ## Ejemplo 2 

  Para crear un contenedor de centOS:18.04 y listar el contenido de la carpeta /. Lo conseguimos con `docker run ubuntu:18.04 ls/` y para comprobar que todo ha ido bien nos tendría que mostrar lo siguiente:


  ## Ejemplo 4 

  **Primer paso**
  Crear un contenedor de debian 9 y mostrar el contenido de una carpeta establecida con el parámetro -w.
  
  Ejecutaremos por consola `docker run it -it -w /etc debian:9 ls`. 

  Al crear el contenedor se ejecuta la orden `ls` desde el directorio `/etc`, posteriormente el contenedor pasa a estar parado y ya no tendremos acceso a este.

  **Segundo paso**
  Cada que creemos con tenedores, hay dos órdenes que nos van a interesar para hacer un seguimiento de qué tenemos en nuestro sistma.

  **Para mostrar los contenedores en ejecución (estado up) usamos `docker ps`** 

  **Para mostrar todos los contenedores creados ya sea que estén en ejecución (estado Up) o parados (estado Exited)** usaremos el comando `docker ps -a`. Con esto hemos terminado los ejemplos.
