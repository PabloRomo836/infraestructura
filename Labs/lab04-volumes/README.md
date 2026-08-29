# Lab 04 - Persistencia de Datos con Docker Volumes

## Objetivo

Comprender cómo funcionan los volúmenes Docker y verificar que los datos permanecen almacenados aunque un contenedor sea eliminado.

---

## Entorno

* Windows 10
* WSL2
* Debian
* Docker Desktop
* Docker Engine

---

## Creación del volumen

Comando utilizado:

```bash
docker volume create datos-techcare
```

Verificación:

```bash
docker volume ls
```

Resultado:

```text
local     datos-techcare
```

---

## Creación del primer contenedor

Comando:

```bash
docker run -it \
--name volumen-lab \
-v datos-techcare:/datos \
debian bash
```

---

## Creación de datos

Dentro del contenedor:

```bash
echo "Laboratorio de Volumes" > /datos/info.txt
```

Verificación:

```bash
cat /datos/info.txt
```

Resultado:

```text
Laboratorio de Volumes
```

---

## Eliminación del contenedor

Salida del contenedor:

```bash
exit
```

Eliminación:

```bash
docker rm volumen-lab
```

---

## Verificación de persistencia

Creación de un nuevo contenedor utilizando el mismo volumen:

```bash
docker run -it \
--name volumen-lab2 \
-v datos-techcare:/datos \
debian bash
```

Verificación:

```bash
cat /datos/info.txt
```

Resultado:

```text
Laboratorio de Volumes
```

El archivo seguía existiendo a pesar de haber eliminado el contenedor original.

---

## Conceptos aprendidos

### Sin volumen

Si los datos se guardan dentro del contenedor:

```text
Contenedor -> Datos
```

al eliminar el contenedor también se eliminan los datos.

### Con volumen

```text
Docker Volume -> Datos
        |
        └── Contenedor
```

Los datos sobreviven aunque el contenedor sea eliminado.

---

## Casos de uso reales

* PostgreSQL
* MySQL
* MariaDB
* WordPress
* Nextcloud
* GitLab
* Aplicaciones empresariales

---

## Lecciones aprendidas

* Los volúmenes permiten persistencia de datos.
* Un mismo volumen puede ser utilizado por diferentes contenedores.
* Los datos permanecen disponibles aunque los contenedores sean eliminados.
* Docker separa la aplicación de los datos.

---

## Estado

✅ Laboratorio completado con éxito.

