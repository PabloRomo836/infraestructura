# Lab 07 - Redes en Debian / WSL2

## Objetivo

Practicar herramientas básicas de diagnóstico y administración de redes
en Debian ejecutándose mediante WSL2.

Se trabajó con:

- Interfaces de red
- Direcciones IPv4 e IPv6
- Rutas
- Gateway
- Conectividad IP
- DNS
- Puertos y sockets
- SSH
- Procesos asociados a puertos
- Traceroute
- Troubleshooting de conectividad

---

## Entorno

- Sistema operativo: Debian 13 (Trixie)
- Plataforma: WSL2
- Host: Windows
- Interfaz principal: eth0

---

## 3. Identificación de interfaces

Comando:

```bash
ip addr 
# Incidente y advertencias encontradas durante el diagnóstico

Durante las pruebas de red se encontraron varios resultados que inicialmente
podían interpretarse como errores. Se realizaron pruebas adicionales antes de
modificar cualquier configuración.

## 4. Gateway sin respuesta a ping

Se comprobó el gateway configurado:

```bash
ping -c 4 172.22.80.1
