### Instalar DVPWA con Docker

🔹 1. Clonar el repositorio de DVPWA
Abre tu terminal y ejecuta:

```
git clone https://github.com/anxolerd/dvpwa.git
cd dvpwa
```

🔹 2. Ejecutar DVPWA con Docker Compose
Dentro del directorio dvpwa, encontrarás un archivo docker-compose.yml que define los servicios necesarios. Para iniciar la aplicación, simplemente ejecuta:

```
docker-compose up
```
Esto descargará las imágenes necesarias y levantará los contenedores definidos.


<p align="center">
<img src="img/lab03a_02.png" width="500">
</p>


🔹 3. Acceder a la aplicación
Una vez que los contenedores estén en funcionamiento, puedes acceder a DVPWA desde tu navegador web en:

```
http://localhost:8080
```

Aquí podrás interactuar con la aplicación y explorar sus vulnerabilidades para fines educativos y de prueba.
Medium


<p align="center">
<img src="img/lab03a_01.png" width="500">
</p>

 - Capturar pantalla y guardarlo en un archivo con su apellido_nombre_02 en la ruta de la clase 06.

🔹 4. Restaurar la base de datos (si es necesario)
Si realizas cambios en la base de datos que desees revertir, como eliminar tablas, puedes restaurarla ejecutando:

```
docker-compose stop postgres
docker-compose rm
docker-compose up postgres
```
Esto detendrá el contenedor de PostgreSQL, lo eliminará y lo volverá a crear con los datos iniciales.

Para más información y detalles adicionales, puedes consultar el repositorio oficial de DVPWA en GitHub:

👉 https://github.com/anxolerd/dvpwa