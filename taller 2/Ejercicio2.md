# Ejercicio 1

En este ejercicio vamos a crear una imagen de Docker para un aplicativo creado en PHP

---

1. Creemos la carpetas necesarias para nuestro espacio de trabajo

    ```cmd
    > mkdir webphp
    > cd webphp
    > mkdir web
    > cd ..    
    ```
2. A continuación vamos a crear el DockerFile. El DockerFile es el archvo que contiene la información para compilar nuestra imagen. Se debe crear el archivo en el directorio de trabajo sin extensión.
 
    ```
    FROM php:7.3-apache
    COPY web /var/www/html
    EXPOSE 80
    ```
3. En la carpeta web vamos a crear el archivo index.php con el siguiente contenido.

    ```php
    <html>
        <head>
            <title>Prueba de PHP</title>
        </head>
        <body>
            <?php echo '<p>Hola Mundo</p>'; ?>
        </body>
    </html>
    ```


4. Creemos nuestra imagen en el directorio de trabajo donde tenemos el DockerFile

```cmd
> docker build -t imagen_web_php .
```

5. validamos que la imagen esté creada.

```
> docker images
```

```
docker run -it -p 80:80 imagen_web_php
```