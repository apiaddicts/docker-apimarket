# Docker APIMarket

To bring up the complete environment (frontend, backend, and database), follow these steps:

1.  Make sure you are in the root directory of this project (where `docker-compose.yml`, `.env`, `Dockerfile.frontend`, and `Dockerfile.backend` are located).
2.  Run the following command to build the images and bring up the containers:
    ```bash
    docker-compose up --build
    ```
    The first time you run this command, it will take a while as it will clone the repositories and build the images.

Once the containers are running:
-   The frontend should be accessible at `http://localhost:3000`.
-   The backend (Strapi) should be accessible at `http://localhost:1337`.

### Environment Variables

Below is a table with the necessary environment variables to configure the project:

| Variable | Description | Service |
| --- | --- | --- |
| `FRONTEND_PORT` | Port for the frontend container. | `frontend` |
| `VITE_APP_STRAPI_URL` | URL of the Strapi backend, used by the frontend. | `frontend` |
| `VITE_PORT` | Vite port for the frontend. | `frontend` |
| `BACKEND_PORT` | Port for the backend container. | `backend` |
| `APP_KEYS` | Strapi application keys. | `backend` |
| `DATABASE_CLIENT` | Database client (e.g., `postgres`). | `backend` |
| `DATABASE_HOST` | Database host (the name of the database container). | `backend` |
| `DATABASE_PORT` | Database port. | `backend` |
| `DATABASE_NAME` | Database name. | `backend` |
| `DATABASE_USERNAME` | Database user. | `backend` |
| `DATABASE_PASSWORD` | Database password. | `backend` |
| `DATABASE_SSL` | Indicates if the database connection needs SSL. | `backend` |
| `DB_PORT` | Port for the database container. | `database` |
| `POSTGRES_DB` | Database name. | `database` |
| `POSTGRES_USER` | Database user. | `database` |
| `POSTGRES_PASSWORD` | Database password. | `database` |
| `AWS_ACCESS_KEY_ID` | (Optional) AWS access key ID for S3. | `backend` |
| `AWS_SECRET_ACCESS_KEY` | (Optional) AWS secret access key for S3. | `backend` |
| `AWS_REGION` | (Optional) AWS region for S3. | `backend` |
| `AWS_BUCKET` | (Optional) AWS bucket name for S3. | `backend` |
| `AWS_BUCKET_SUBDIRECTORY` | (Optional) AWS bucket subdirectory for S3. | `backend` |
| `AWS_CDN_DOMAIN` | (Optional) AWS CDN domain. | `backend` |


**Important Note:**
If you need to configure additional environment variables for Strapi or the frontend (such as AWS S3 credentials, etc.), you will need to add them to the `.env` file and/or directly in the `environment` section of the corresponding services in `docker-compose.yml`.
