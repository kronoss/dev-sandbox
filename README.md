# Entorno de Desarrollo Sandbox con Docker Compose

Este repositorio contiene un entorno de desarrollo local configurado con Docker Compose para PostgreSQL y pgAdmin 4. Con este entorno, puedes rápidamente levantar una base de datos PostgreSQL y utilizar pgAdmin para administrarla a través de una interfaz web.

## Requisitos
Antes de comenzar, asegúrate de tener instalado lo siguiente en tu sistema:

Docker: Instalación de Docker
Docker Compose: Instalación de Docker Compose

## Uso
1.- Clona este repositorio en tu máquina local:


> git clone https://github.com/kronoss/dev-sandbox.git 

2.- Navega al directorio del repositorio:

> cd dev-sandbox 

3.- Levanta los contenedores usando Docker Compose:

> docker-compose up -d

Este comando levantará dos servicios: PostgreSQL y pgAdmin.
Accede a pgAdmin desde tu navegador web:
Abre tu navegador y ve a http://localhost:5050
Ingresa las siguientes credenciales predeterminadas para iniciar sesión en pgAdmin:

> Usuario: pgadmin@example.com
> Contraseña: admin

## Configura la conexión a PostgreSQL en pgAdmin:
1. Una vez iniciada sesión en pgAdmin, haz clic en Add New Server (Agregar nuevo servidor).
2. En la pestaña General: En Name (Nombre), ingresa un nombre para tu conexión.
3. En la pestaña Connection (Conexión):En Host name/address (Nombre/dirección del host), ingresa postgres (nombre del servicio del contenedor de PostgreSQL).
En Username (Nombre de usuario), ingresa postgres.
En Password (Contraseña), ingresa la contraseña especificada en el archivo docker-compose.yml (por defecto, password).
4. Haz clic en Save (Guardar).

Ahora puedes administrar tu base de datos PostgreSQL desde pgAdmin.

## Detener y Limpiar
Para detener y eliminar los contenedores creados, ejecuta:

> docker-compose down

Esto detendrá y eliminará los contenedores, pero mantendrá los datos de PostgreSQL en un volumen persistente (vol_pgdata).

## Personalización
Si deseas personalizar las configuraciones del entorno, puedes editar el archivo docker-compose.yml para cambiar los puertos, contraseñas u otras configuraciones relacionadas con los servicios de PostgreSQL y pgAdmin 4.