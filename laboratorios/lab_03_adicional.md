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

🔹 3. Acceder a la aplicación
Una vez que los contenedores estén en funcionamiento, puedes acceder a DVPWA desde tu navegador web en:

```
http://localhost:8080
```

Aquí podrás interactuar con la aplicación y explorar sus vulnerabilidades para fines educativos y de prueba.
Medium

🔹 4. Reconstruir los contenedores (opcional)
Si necesitas reconstruir los contenedores, por ejemplo, después de realizar cambios en el código o en la configuración, puedes utilizar el script proporcionado:

```
./recreate.sh
```
Este script detendrá y eliminará los contenedores existentes, y luego los recreará desde cero.
GitHub

🔹 5. Restaurar la base de datos (si es necesario)
Si realizas cambios en la base de datos que desees revertir, como eliminar tablas, puedes restaurarla ejecutando:

```
docker-compose stop postgres
docker-compose rm
docker-compose up postgres
```
Esto detendrá el contenedor de PostgreSQL, lo eliminará y lo volverá a crear con los datos iniciales.

Para más información y detalles adicionales, puedes consultar el repositorio oficial de DVPWA en GitHub:

👉 https://github.com/anxolerd/dvpwa