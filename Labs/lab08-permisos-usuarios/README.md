# Lab 08 - Permisos y Propiedad de Usuarios en Linux

## 1. ¿Qué son los permisos de Linux?
Son las reglas que usa el sistema para controlar qué puede hacer cada usuario con un archivo o directorio. Cada recurso tiene un **propietario** (`u`), un **grupo** (`g`) y una categoría para el **resto de los usuarios** (`o`), lo que permite proteger archivos sensibles del sistema (como `/etc/shadow`) y evitar modificaciones accidentales[cite: 2, 3].

## 2. ¿Qué significan `r`, `w` y `x`?
Son los tres permisos básicos y cada uno tiene un valor numérico para usar en modo octal:
* **`r` (Read / Lectura - valor 4):** Permite ver el contenido de un archivo o listar lo que hay dentro de un directorio.
* **`w` (Write / Escritura - valor 2):** Permite modificar o guardar cambios en un archivo, o crear/borrar archivos dentro de un directorio.
* **`x` (Execute / Ejecución - valor 1):** Permite ejecutar un archivo como programa o script, y en directorios permite entrar (`cd`) en ellos.

**Ejemplo:** `-rwxr-x---` (`750`) significa que el propietario tiene control total (`rwx`), el grupo puede leer y ejecutar (`r-x`), y los demás usuarios no tienen ningún acceso (`---`)[cite: 3].

## 3. ¿Cuál es la diferencia entre `chmod`, `chown` y `chgrp`?
* **`chmod` (Change Mode):** Modifica **qué se puede hacer** con el archivo (los permisos `r`, `w`, `x`), tanto en formato simbólico (`chmod g+r archivo`) como numérico (`chmod 640 archivo`).
* **`chown` (Change Owner):** Cambia **quién es el propietario** del archivo y, opcionalmente, también su grupo al mismo tiempo (`sudo chown pablo:docker archivo`).
* **`chgrp` (Change Group):** Cambia **únicamente el grupo** al que pertenece el archivo (`sudo chgrp docker archivo`).

## 4. ¿Qué aprendí al realizar la práctica de `configuracion.conf`?
Aprendí a combinar la gestión de propiedad y permisos desde cero en un flujo real de administración:
1. Crear un recurso (`touch configuracion.conf`) y verificar su estado inicial con `ls -l`.
2. Reasignar propietario y grupo en un solo comando (`sudo chown pablo:docker configuracion.conf`).
3. Aplicar permisos restrictivos usando notación octal (`chmod 640 configuracion.conf` → `-rw-r-----`), asegurando que solo el dueño pueda editar, el grupo pueda leer y nadie más tenga acceso.
