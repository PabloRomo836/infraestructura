# Incidente 001 - Recuperación de WSL y Docker Desktop

## Fecha

24/07/2026

## Descripción

Durante la realización del Laboratorio 01 de Docker con Nginx, Docker Desktop dejó de responder y mostró el mensaje:

"WSL is unresponsive"

Además se observaron los siguientes síntomas:

- Debian abría una ventana negra sin mostrar el prompt.
- Docker dejó de responder.
- VS Code perdió la conexión con WSL.
- El comando `wsl -l -v` no devolvía resultados.

## Diagnóstico

Se verificó el estado del servicio principal de WSL mediante:

```powershell
Get-Service LxssManager
```

Resultado:

```text
Status : Stopped
```

El servicio responsable de administrar las distribuciones WSL se encontraba detenido.

## Solución aplicada

Se inició manualmente el servicio:

```powershell
Start-Service LxssManager
```

Verificación:

```powershell
Get-Service LxssManager
```

Resultado:

```text
Status : Running
```

Posteriormente se verificó el estado de las distribuciones:

```powershell
wsl --status
wsl -l -v
```

Resultado:

```text
NAME              STATE     VERSION
Debian            Stopped   2
docker-desktop    Stopped   2
```

Luego se inició Debian normalmente y Docker Desktop recuperó la comunicación con WSL.

## Lecciones aprendidas

- Docker Desktop depende de WSL2 para funcionar correctamente.
- Antes de reinstalar WSL conviene verificar el estado de LxssManager.
- La documentación de incidentes permite acelerar futuras recuperaciones.
- Es recomendable registrar problemas reales encontrados durante los laboratorios.

## Estado final

✅ Debian operatio

✅ Docker Desktop oerativo

✅ VS Code conectado a WSL

✅ Laboratorio 01 recuperado y funcional
