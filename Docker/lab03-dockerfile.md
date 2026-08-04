# Lab 03 - Dockerfile Personalizado

## Objetivo
Crear una imagen Docker propia basada en Nginx y desplegar una página web personalizada.

## Archivos utilizados

- Dockerfile
- index.html
- LogoNuevo.png

## Dockerfile utilizado

FROM nginx:latest

COPY index.html /usr/share/nginx/html/
COPY LogoNuevo.png /usr/share/nginx/html/

## Construcción de imagen

docker build -t techcare-nginx:v1 .

## Ejecución

docker run -d \
--name techcare-web \
-p 8080:80 \
techcare-nginx:v1

## Verificación

Acceso desde navegador:

http://localhost:8080

## Resultado

La página personalizada de TechCare se visualizó correctamente con logo corporativo.

## Conceptos aprendidos

- Dockerfile
- Imagen personalizada
- COPY
- docker build
- docker run
- Capas de imagen
- Nginx como servidor web

## Estado

COMPLETADO
