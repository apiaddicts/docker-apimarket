Para levantar el entorno completo (frontend, backend y base de datos), sigue estos pasos:

1.  Asegúrate de estar en el directorio raíz de este proyecto (donde se encuentran `docker-compose.yml`, `.env`, `Dockerfile.frontend` y `Dockerfile.backend`).
2.  Ejecuta el siguiente comando para construir las imágenes y levantar los contenedores:
    ```bash
    docker-compose up --build
    ```
    La primera vez que ejecutes este comando, tardará un poco ya que clonará los repositorios y construirá las imágenes.

Una vez que los contenedores estén corriendo:
-   El frontend debería estar accesible en `http://localhost:3000`.
-   El backend (Strapi) debería estar accesible en `http://localhost:1337`.

### Variables de Entorno

A continuación se muestra una tabla con las variables de entorno necesarias para configurar el proyecto:

| Variable | Descripción | Servicio |
| --- | --- | --- |
| `FRONTEND_PORT` | Puerto para el contenedor del frontend. | `frontend` |
| `VITE_APP_STRAPI_URL` | URL del backend de Strapi, utilizada por el frontend. | `frontend` |
| `VITE_PORT` | Puerto de Vite para el frontend. | `frontend` |
| `BACKEND_PORT` | Puerto para el contenedor del backend. | `backend` |
| `APP_KEYS` | Claves de la aplicación Strapi. | `backend` |
| `DATABASE_CLIENT` | Cliente de la base de datos (por ejemplo, `postgres`). | `backend` |
| `DATABASE_HOST` | Host de la base de datos (el nombre del contenedor de la base de datos). | `backend` |
| `DATABASE_PORT` | Puerto de la base de datos. | `backend` |
| `DATABASE_NAME` | Nombre de la base de datos. | `backend` |
| `DATABASE_USERNAME` | Usuario de la base de datos. | `backend` |
| `DATABASE_PASSWORD` | Contraseña de la base de datos. | `backend` |
| `DATABASE_SSL` | Indica si la conexión a la base de datos necesita SSL. | `backend` |
| `DB_PORT` | Puerto para el contenedor de la base de datos. | `database` |
| `POSTGRES_DB` | Nombre de la base de datos. | `database` |
| `POSTGRES_USER` | Usuario de la base de datos. | `database` |
| `POSTGRES_PASSWORD` | Contraseña de la base de datos. | `database` |
| `AWS_ACCESS_KEY_ID` | (Opcional) ID de la clave de acceso de AWS para S3. | `backend` |
| `AWS_SECRET_ACCESS_KEY` | (Opcional) Clave de acceso secreta de AWS para S3. | `backend` |
| `AWS_REGION` | (Opcional) Región de AWS para S3. | `backend` |
| `AWS_BUCKET` | (Opcional) Nombre del bucket de AWS para S3. | `backend` |
| `AWS_BUCKET_SUBDIRECTORY` | (Opcional) Subdirectorio del bucket de AWS para S3. | `backend` |
| `AWS_CDN_DOMAIN` | (Opcional) Dominio de CDN de AWS. | `backend` |


**Nota Importante:**
Si necesitas configurar variables de entorno adicionales para Strapi o el frontend (como credenciales de AWS S3, etc.), deberás agregarlas al archivo `.env` y/o directamente en la sección `environment` de los servicios correspondientes en `docker-compose.yml`.
