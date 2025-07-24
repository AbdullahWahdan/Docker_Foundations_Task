# Guided Lab: Web + Database App with Docker Compose

## Objective
This lab guides you through running a multi-service application using Docker Compose. It includes an NGINX web server and a PostgreSQL 16 database.

---

## Prerequisites
- Docker and Docker Compose installed
- Git or zip access to the lab files
- Internet connection to pull images

---

## Step-by-Step Instructions

### 1. Clone the Repo

```bash
git clone https://github.com/AbdullahWahdan/Docker_Foundations_Task
cd docker-foundations-lab/compose
````

---

### 2. Understand the Compose File

Your `docker-compose.yml` defines:

* **web** service using `nginx:latest`, exposed on port `8080`, with an HTTP healthcheck.
* **db** service using `postgres:16` with user credentials and a named volume `db-data`.
* Both services are connected to a custom **bridge network** called `app-network`.

```yaml
version: '3.8'

services:
  web:
    image: nginx:latest
    ports:
      - "8080:80"
    networks:
      - app-network
    depends_on:
      - db
    healthcheck:
      test: ["CMD", "curl", "-f", "http://localhost"]
      interval: 30s
      timeout: 10s
      retries: 5

  db:
    image: postgres:16
    environment:
      POSTGRES_USER: user
      POSTGRES_PASSWORD: pass
      POSTGRES_DB: app_db
    volumes:
      - db-data:/var/lib/postgresql/data
    networks:
      - app-network
    healthcheck:
      test: ["CMD-SHELL", "pg_isready -U user -d app_db"]
      interval: 30s
      timeout: 10s
      retries: 5

networks:
  app-network:
    driver: bridge

volumes:
  db-data:
```

---

### 3. Run the App

Start the containers in detached mode:

```bash
docker-compose up -d
```

This will pull images, create a bridge network, and run both services.

---

### 4. Verify Everything Is Working

* Visit the web server: [http://localhost:8080](http://localhost:8080)
* View running containers:

```bash
docker ps
```

* Check logs:

```bash
docker-compose logs web
docker-compose logs db
```

---

### 5. Tear Down

Stop and remove everything (including volumes):

```bash
docker-compose down -v
```

---

## Expected Outcome

* NGINX container serves a default welcome page on port 8080.
* PostgreSQL container is healthy and initialized with user `user`, password `pass`, and database `app_db`.
* Healthchecks confirm both services are operational.

---