# Ejercicio 1

Montar un contenedor de Apache

---

1. En la consola corremos el comando docker images para validar identificar la imagen que necesitamos subir. En caso de que no sepamos el nombre de la imagen podemos validarlo en el sitio de Docker Hub.
   
    ```cmd
    docker images
    ```


2. Corremos el comando docker run para que cree un contenedor con la imagen httpd. con el parámetro -p le definimos que el puerto externo es el 81 y que internamente vamos a escuchar en el pruerto 80. Para que el comaando sea exitoso debemos asegurar que tenemos disponible el puerto 81 en nuestra nmáquina. Con el parámetro --name le indicamos el nombre que le dará al contenedor.

    ```cmd
    docker run -d -p 81:80 --name web2 httpd
    ```


3. Para validar que el contendor está corriendo podemos hacerlo con el comando docker ps.
    ```cmd
    docker ps -a
    ```

4. Ahora podemos abrir un navegador en el puerto en localhost:81

5. Finalmente eliminemos el contenedor llamado web2
    ```cmd
    docker rm -fv web2
    ```

