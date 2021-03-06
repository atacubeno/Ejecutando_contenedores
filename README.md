![1](https://user-images.githubusercontent.com/91874745/167040995-45ee0843-e456-4e96-a617-92254c26b561.gif)

#  Ejecutando contenedores en [***Docker***](https://www.docker.com)

## Ejemplo 1


 **Vista por consola (se describen los pasos a seguir más detalladamente a continuación).**
 
 ![1primero](https://user-images.githubusercontent.com/91874745/167041963-07e5aa0a-a231-4b12-9a91-0170ac335c07.gif)


 ***Primer paso: descargar  una imagen de manera previa***
 
Antes de empezar hay que iniciar [***Docker***](https://www.docker.com), para esto abrimos la app [***Docker***](https://www.docker.com) (en mi caso tengo la versión de escritorio) y enseguida nos indica tenemos que ejecutar el comando `docker run -d -p 08:80 docker/getting-started` por consola y después volver a la app.
  
  <img width="1272" alt="1 2" src="https://user-images.githubusercontent.com/91874745/167042268-5c201cbc-9e63-4afa-967b-87c99cfa6e10.png">

  
  Procedemos con el ejemplo 1 de este ejercicio para la ejecución de un contendor, en la misma consola descargaremos una imagen previa usamos el comando `docker pull ubuntu:18.04` y veremos algo así:
  
  <img width="575" alt="1" src="https://user-images.githubusercontent.com/91874745/167042537-e30950df-af1f-4ef8-97a8-dea512b22479.png">


  ***Segundo paso: crear un contenedor de ubunto:18.04***
  
  Para crear un contenedor de ubuntu:18.04 y tener acceso a un shell en él (si no hemos descargado la imagen de manera previa se descargará), para esto usaremos `docker run -it ubuntu:18.04/bin/bash`.
  
  <img width="574" alt="2" src="https://user-images.githubusercontent.com/91874745/167042772-3406c90d-5ef6-48a8-9a0c-c66032a1bc4a.png">
  
  Podemos comprobar que estamos corriendo dicho contenedor:
  
  <img width="576" alt="5" src="https://user-images.githubusercontent.com/91874745/167043738-ba6cccc2-c30b-40bc-b281-1f858715b1f1.png">


  Como podemos ver ha habido cambios en la consola ya que al crear el contenedor se nos da acceso a un shell del mismo, en este caso Ubuntu.
  Es importante destacar que estos cambios también se notarán en la app; tenemos dos contenedores, uno del inicio de [***Docker***](https://www.docker.com) y otro de **Ubuntu**, ambos con una leyenda que dice RUNNING.
  
  <img width="1266" alt="3" src="https://user-images.githubusercontent.com/91874745/167043127-9d7457ff-860d-49b9-8d78-fee97f13bb10.png">

  En la versión de escritorio nos aparecerá un botón de stop para detener el contenedor, entre otras opciones:
  
  <img width="1266" alt="4" src="https://user-images.githubusercontent.com/91874745/167043496-336272a3-2dfd-4a09-972e-31247a6e5c86.png">

  Para salir de la shell de **Ubuntu** con `exit`bastaría, y volveríamos a estar en la consola de nuestro sistema operativo.
  
  <img width="572" alt="6" src="https://user-images.githubusercontent.com/91874745/167044136-4eb2983c-6c0e-4628-a48f-c094af8eb9c9.png">

  Y vemos que también afecta a la versión de escritorio, y esto sucede en cada cosa que hagamos relacionada con [***Docker***](https://www.docker.com)       desde la consola. Al hacer el `exit` por consola, nuestro contenedor ya no tiene la leyenda ***RUNNING*** si no ***EXITED***, se ha detenido:
  
  
  <img width="1270" alt="7" src="https://user-images.githubusercontent.com/91874745/167044523-8da7f62d-d138-4700-8c2b-eb8f8d88b37d.png">


  ## Ejemplo 2 
  
  **Vista de los siguientes ejemplos por consola (a continuación se describen los pasos detalladamente).**
  
  ![eje 2 y 4](https://user-images.githubusercontent.com/91874745/167042130-72375592-0176-46c7-b190-7bacc84cac78.gif)


  Para crear un contenedor de centOS:18.04 y listar el contenido de la carpeta /. Lo conseguimos con `docker run ubuntu:18.04 ls/`.
    Y para comprobar que todo ha ido bien nos tendría que mostrar lo siguiente en la consola:
  
  <img width="572" alt="8" src="https://user-images.githubusercontent.com/91874745/167044571-26e0a19e-844b-4f9e-8700-43a46aa698f8.png">


  Y en la versión de escritorio vemos que se ha detenido.
  
  <img width="1262" alt="9" src="https://user-images.githubusercontent.com/91874745/167044688-f652e872-adc1-4f32-9df8-1217e106dbcb.png">

 Además si accedemos al contenedor veremos lo mismo que por shell:
 
 <img width="1272" alt="10" src="https://user-images.githubusercontent.com/91874745/167044844-59465b23-5686-4163-8b5a-c408747efafa.png">


  ## Ejemplo 4 

  **Primer paso: crear un contenedor de debian 9 y mostrar el contenido de una carpeta establecida con el parámetro -w. **
  
  Ejecutaremos por consola `docker run it -it -w /etc debian:9 ls`: 
  
  <img width="571" alt="11" src="https://user-images.githubusercontent.com/91874745/167045104-9961df57-8676-4fd3-b5f7-75217ccdf0c9.png">


  Al crear el contenedor se ejecuta la orden `ls` desde el directorio `/etc`, posteriormente el contenedor pasa a estar parado y ya no tendremos acceso a este como se puede ver a continuación, que esta como `EXITED`: 
  
  <img width="1264" alt="12" src="https://user-images.githubusercontent.com/91874745/167045448-211b4bc9-3f70-4d86-832d-c8218b9bd096.png">

En la app al abrir el contenedor veremos:

<img width="1268" alt="13" src="https://user-images.githubusercontent.com/91874745/167045576-e54dc52b-93e6-4861-8f54-8d7cf8a8e6a0.png">


  **Segundo paso: mostrar los contenedores** 
  
  Cada que creamos contenedores, hay dos órdenes que nos van a interesar para hacer un seguimiento de qué tenemos en nuestro sistema.
  
  En caso de querer los **contenedores en ejecución (Estado Up)** usaremos el comando `docker ps`:
  
  <img width="1164" alt="14" src="https://user-images.githubusercontent.com/91874745/167046063-77d678b0-03a2-45c4-9498-139b79d343ee.png">

 Para mostrar **todos los contenedores creados ya sea que estén en ejecución (estado Up) o parados (estado Exited)** usaremos el comando `docker ps -a`.  
 
<img width="1166" alt="15" src="https://user-images.githubusercontent.com/91874745/167046155-110f6d8d-607b-4237-997c-3b8e77e35788.png">

Con esto terminamos los ejemplos.

![whale-docker](https://user-images.githubusercontent.com/91874745/167046719-32c5dfca-d811-4676-b58d-6158308c97af.gif)



