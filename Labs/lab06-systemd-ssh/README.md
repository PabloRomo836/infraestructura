# Lab 06 - Administración de servicios con systemd y SSH

## 🎯 Objetivo

Aprender a administrar servicios en Debian mediante systemd, utilizando
systemctl para consultar, iniciar, detener, reiniciar, habilitar y
deshabilitar servicios.

También se realizaron verificaciones de red mediante ss y análisis de
registros mediante journalctl y grep.

---

## 🖥️ Entorno utilizado

- Windows 10
- WSL2
- Debian GNU/Linux 13 (trixie)
- systemd 257
- OpenSSH Server
- Terminal Bash

---

## 🔎 Verificación inicial

Se verificó el sistema operativo mediante:

```bash
cat /etc/os-release 


