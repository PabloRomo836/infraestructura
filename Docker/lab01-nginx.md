labs
├── Docker
├── Git
├── Linux
├── Redes
├── Scripts
└── infraestructura

# Laboratorio 01 - Nginx con docker

## Objetivo

Desplegar un servidor web Nginx mediante Docker. 

## Comando utilizado

docker run -d --name nginx-lab -p 8080:80 nginx 

## Verificación 

docker ps

## Resultado 

Acceso exitoso mediante: 
http://localhost:8080 

## Aprendizajes 

- Uso de imágenes Docker
- Creación de contenedores
- Mapeo de puertos
- Verificación con docker ps
