# Innovatech Chile - Módulo de Despachos (Backend)

Este repositorio contiene la API REST para el sistema de Despachos de Innovatech Chile, construida utilizando Spring Boot y Java 17.

## Requerimientos e Infraestructura
- **Lenguaje:** Java 17 (Eclipse Temurin)
- **Gestor de Dependencias:** Maven
- **Base de Datos:** MySQL 8.0
- **Puerto expuesto:** 8080

## Contenedorización y Buenas Prácticas (DevOps)
El proyecto implementa un `Dockerfile` optimizado utilizando **Multi-stage build** para reducir el tamaño de la imagen final de producción. Adicionalmente, por motivos de seguridad y siguiendo el principio de mínimo privilegio, el contenedor se ejecuta bajo un usuario **No-Root** (`spring`).

## Persistencia de Datos
La persistencia de la base de datos se maneja a través de un **Named Volume** de Docker (`mysql_data`), asegurando la continuidad operativa del sistema y evitando la pérdida de información crítica ante reinicios de los contenedores.

## Despliegue Local
Para levantar el stack completo (API + Base de datos) de forma local, ejecute:
```bash
docker-compose up --build -d