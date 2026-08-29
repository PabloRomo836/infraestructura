# Lab 05 - Docker Compose

## Objetivo

Implementar un servidor Nginx utilizando Docker Compose,
administrando su configuración mediante un archivo compose.yaml.

## Descripción

En este laboratorio se configuró un servicio Nginx mediante
Docker Compose.

El servidor utiliza la imagen oficial de Nginx y publica el
puerto 80 del contenedor en el puerto 8080 del sistema anfitrión.

La página web de TechCare se monta mediante un bind mount,
permitiendo modificar el archivo index.html desde Debian sin
necesidad de reconstruir la imagen.

## Infraestructura utilizada

- Windows 10
- WSL2
- Debian
- Docker Desktop
- Docker Compose
- Nginx

## Estructura

```text
lab05-compose/
├── compose.yaml
└── index.html 
