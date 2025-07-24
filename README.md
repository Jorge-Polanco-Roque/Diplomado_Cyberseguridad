# 🛡️ Diplomado en Auditoría y Pentesting en Sistemas Operativos

Este diplomado tiene como objetivo formar competencias prácticas en la auditoría de sistemas Windows y el uso de herramientas de pentesting en entornos Linux (Kali). A través de prácticas guiadas y comandos reales, los participantes desarrollarán habilidades esenciales para identificar vulnerabilidades, fortalecer la postura de seguridad y responder ante incidentes.

---

## 📦 Módulos del Diplomado

### ✅ Módulo 1: Auditoría en Windows

Se abordan herramientas nativas del sistema y utilidades de Microsoft para auditar posibles vulnerabilidades.

**Temas y herramientas:**

- `hostname`, `net users`, `whoami`, `whoami /priv` — Identificación y privilegios del usuario.
- `systeminfo`, `wmic qfe` — Revisión de parches instalados.
- `net localgroup` — Análisis de grupos como Administrators, Remote Desktop Users y Power Users.
- `netstat -aon`, `netstat -b` — Detección de conexiones activas sospechosas.
- **TCPView** — Visualizador gráfico de conexiones de red.
- `tasklist /svc`, `Process Explorer` — Evaluación de procesos activos en el sistema.
- `net share` — Detección de carpetas compartidas con permisos inseguros.
- `sc query windefend`, `netsh advfirewall show allprofiles` — Estado de antivirus y firewall.
- `schtasks /query` — Revisión de tareas calendarizadas sospechosas.

> 🧠 Estas prácticas permiten identificar configuraciones inseguras, detectar puertas traseras y validar la higiene digital del sistema operativo Windows.

---

### 🐧 Módulo 2: Pentesting con Kali Linux

Se exploran comandos clave para análisis de red, explotación básica y acceso a sistemas vulnerables.

**Comandos clave:**

- `nslookup`, `hostname -I` — Identificación de red.
- `nmap -sn`, `nmap -O` — Escaneo de red y detección de puertos abiertos.
- `smbmap -H` — Escaneo de recursos compartidos SMB.
- `whoami /priv` — Verificación de privilegios en sistemas Windows desde acceso remoto.
- `evil-winrm` — Conexión remota a sistemas Windows mediante credenciales o hashes.
- `nc -lvnp` — Escucha de conexiones reversas.
- `ping && cat /etc/passwd` — Comprobación de ejecución de comandos vía inyección.
- `mimikatz.exe` — Herramienta para manipulación de tickets Kerberos.

> ⚠️ Este módulo busca preparar al alumno para escenarios de pentesting reales donde se comprometen máquinas vulnerables para simular ataques controlados.

---

## 🧰 Herramientas usadas

- [TCPView (Microsoft)](https://bit.ly/3Ha7FW8)
- [Process Explorer (Microsoft)](https://bit.ly/3EZDQpr)
- Kali Linux (entorno de pruebas y explotación)
- Nmap, smbmap, netcat, Evil-WinRM, mimikatz

---

## 🎯 Objetivo General

Capacitar a los participantes en la detección, análisis y mitigación de amenazas en sistemas operativos mediante técnicas de auditoría, escaneo de red y simulación de ataques éticos.

---

## ✅ Recomendaciones Finales

- Siempre ejecutar pruebas en entornos controlados o con permisos explícitos.
- No compartir credenciales ni hashes sensibles fuera de contextos seguros.
- Mantener sistemas actualizados y realizar auditorías periódicas.
