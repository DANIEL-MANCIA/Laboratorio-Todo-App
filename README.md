# 📝 TODO App - Sistema de Gestión de Tareas

## Descripción
Sistema completo de gestión de tareas desarrollado con Docker, Node.js, PostgreSQL y Nginx. Permite crear, leer, actualizar y eliminar tareas de manera eficiente.

## 🏗️ Arquitectura
El sistema sigue una arquitectura de tres capas:
- **Frontend**: Servidor Nginx que sirve archivos estáticos (HTML, CSS, JS)
- **Backend**: API REST desarrollada con Node.js y Express
- **Base de Datos**: PostgreSQL para persistencia de datos

Cliente → Nginx (Puerto 8080) → Backend Node.js (Puerto 3000) → PostgreSQL (Puerto 5432)

## 🛠️ Tecnologías

- **Backend**: Node.js + Express + PostgreSQL
- **Frontend**: HTML5 + CSS3 + JavaScript Vanilla
- **Servidor Web**: Nginx
- **Base de Datos**: PostgreSQL 15
- **Orquestación**: Docker + Docker Compose
- **Control de Versiones**: Git

## 📋 Requisitos Previos

- Docker 20+
- Docker Compose 2+
- Git

## 🚀 Instalación y Ejecución

**1. Clonar el repositorio**

- git clone + https://github.com/DANIEL-MANCIA/Laboratorio-Todo-App

- cd todo-app

**2. Levantar servicios**

- **Construir y levantar todos los servicios**

    - docker-compose up -d

- **Ver estado de los servicios** 
    - docker-compose ps

**3. Acceder a la aplicación**

- **Frontend:** http://localhost:8080

- **Backend API:** http://localhost:3000

- **Health Check:** http://localhost:3000/health


## 🎯 Comandos Útiles

**Construir imágenes**
- docker-compose build

**Levantar servicios en segundo plano**
- docker-compose up -d

**Ver logs en tiempo real**
- docker-compose logs -f

**Ver logs de un servicio específico**
- docker-compose logs -f backend

**Detener servicios**
- docker-compose down

**Detener y eliminar volúmenes**
- docker-compose down -v

**Ver estado de servicios**
- docker-compose ps

**Ejecutar comando en contenedor**
- docker-compose exec backend sh
- docker-compose exec db psql -U todo_user -d todoapp

**Reconstruir desde cero**
- docker-compose down -v
- docker-compose build --no-cache
- docker-compose up

### 📁 Estructura del Proyecto

todo-app/
├── docker-compose.yml
├── README.md
├── .gitignore
├── backend/
│   ├── Dockerfile
│   ├── package.json
│   ├── .dockerignore
│   └── src/
|       ├── config
|       ├── controller
|       ├── middleware
|       ├── routes
|       └── index.js
├── frontend/
│   ├── Dockerfile
│   ├── .dockerignore
│   ├── nginx.conf
│   ├── index.html
│   ├── styles.css
|   └── src/
|       ├── componetns
|       ├── services
|       ├── styles
|       ├── utlis
|       └── app.js
└── docs/
    ├── img
    └── arquitectura.md

## 🔌 API Endpoints
**Tareas:**

**GET /tasks**

- **Descripción:** Obtiene todas las tareas

- **Response:** Array de objetos task

- **Status Code:** 200 OK

**POST /tasks**

- **Descripción:** Crea una nueva tarea

- **Request Body:** {"title": "Nueva tarea"}

- **Response:** Objeto task creado

- **Status Code:** 201 Created

**PUT /tasks/:id**

- **Descripción:** Actualiza el estado de una tarea

- **Request Body:** {"completed": true}

- **Response:** Objeto task actualizado

- **Status Code:** 200 OK

**DELETE /tasks/:id**

- **Descripción:** Elimina una tarea

- **Response:** Sin contenido

- **Status Code:** 204 No Content

**Health Check:**

- GET /health - Estado del servicio y conexión a BD


## 🔢 Modelo de Datos

**Tabla:** tasks

Column     | Type        | Constraints
-----------|-------------|---------------
id         | SERIAL      | PRIMARY KEY
title      | VARCHAR(255)| NOT NULL
completed  | BOOLEAN     | DEFAULT false
created_at | TIMESTAMP   | DEFAULT NOW()


## 🧑🏽‍💻 Variables de Entorno

**Backend**

- DB_HOST=db

- DB_USER=postgres

- DB_PASSWORD=password

- DB_NAME=todoapp

- DB_PORT=5432

**Base de Datos**

- POSTGRES_USER=postgres

- POSTGRES_PASSWORD=password

- POSTGRES_DB=todoapp

## 👥 Autores
Estudiante 1: [Daniel Mancia](https://github.com/DANIEL-MANCIA) - Backend

Estudiante 2: [Fernando Gonzalez](https://github.com/JosueFer23) - Frontend

## 📅 Fecha de Entrega

- **Fecha:** Miercoles 15 Octubre 2025



