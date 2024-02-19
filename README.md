Todo App Laravel Sail (George Mero)

1.  Abre tu terminal o línea de comandos.

2.  Navega al directorio donde deseas clonar el proyecto.

3.  Ejecuta el siguiente comando para clonar el repositorio del proyecto desde GitHub:

    ```
    git clone <URL_del_repositorio> nombre_del_proyecto
    ```

4.  dar permisos a la carpeta para que laravel sail pueda levantar el conternedor.

    ```
    sudo chmod -R 777 ct-candidates-app
    ```

    Da permisos al usuario del sisitema.

    ```
    sudo chown -R $USER:$USER ct-candidates-app
    ```

    Accede al directorio del proyecto clonado utilizando el siguiente comando:

    ```
    cd ct-candidates-app
    ```

5.  Copia el archivo de ejemplo `.env.example` y renómbralo como `.env` ejecutando el siguiente comando:

    ```
    cp .env.example .env
    ```

6.  En caso que tenga otros proyectos de laravel sail en su sistema ejecute para evitar posibles problemas
    ```
    ./vendor/bin/sail down --rmi all -v
    ```
7.  installe las dependencias de composer

    ```
     docker run --rm \
    -u "$(id -u):$(id -g)" \
    -v "$(pwd):/var/www/html" \
    -w /var/www/html \
    laravelsail/php83-composer:latest \
    composer install --ignore-platform-reqs
    ```

8.  genere la llave

    ```
    ./vendor/bin/sail artisan key:generate
    ```

9.  Ahora, ejecuta el comando Sail para iniciar los contenedores Docker:

    ```
    ./vendor/bin/sail up -d
    ```

    Este comando iniciará los contenedores necesarios para ejecutar el proyecto Laravel con Laravel Sail.

10. Ejecuta las migraciones con los seeder:

    ```
    ./vendor/bin/sail artisan migrate --seed
    ```

11. Instala dependecias npm:

    ```
    ./vendor/bin/sail npm install
    ```

12. Compile los diseños :

    ```
    ./vendor/bin/sail npm run build
    ```

13. Una vez que todos los contenedores estén en funcionamiento, puedes acceder a tu aplicación Laravel en tu navegador web visitando `http://localhost`.

14. Registrese en la aplicacion `http://localhost/register`  con un correo y contraseña para poder usarla:

  

15. Cuando hayas terminado , puedes detener los contenedores Docker ejecutando el siguiente comando:

    ```
    ./vendor/bin/sail down
    ```

Esto detendrá todos los contenedores Docker asociados con el proyecto.

¡Eso es todo! Gracias por clonar el repo Si tienes alguna pregunta, no dudes en preguntar.
