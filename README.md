# 🛡️ Prácticas y Resúmenes de Auditoría en Linux y Windows

Este repositorio reúne prácticas guiadas, resúmenes y comandos útiles para auditar y administrar sistemas operativos Linux (incluido Kali) y Windows. Su objetivo es apoyar la enseñanza en ciberseguridad, administración de sistemas y pruebas de penetración.

---

## 📁 Contenido del Repositorio

| Archivo | Descripción |
|--------|-------------|
| `Linux_01.md` | Comandos para escaneo de red, SMB, conexiones remotas, y uso de `evil-winrm` y `mimikatz.exe`. Pensado para entornos Kali Linux. |
| `Linux_02.md` | Resumen completo de comandos de auditoría, administración de usuarios, exploración de red, uso de `nikto`, `msfconsole`, `auditd`, y ACLs. |
| `Linux_03.md` | Práctica 2 guiada para auditar un sistema Linux: revisión de permisos, usuarios, puertos, procesos, y escalación de privilegios. Incluye reflexiones finales. |
| `Windows_01.md` | Práctica 1 para auditoría de sistemas Windows: revisión de privilegios, conexiones activas, firewall, procesos, carpetas compartidas, y uso de herramientas como TCPView y Process Explorer. |

---

## 🔍 Habilidades Desarrolladas

### En entornos **Linux**:
- 🔐 Manejo de permisos y usuarios
- 🌐 Escaneo de red con `nmap`, `nbtscan`
- 🧠 Detección de vulnerabilidades (`unix-privesc-check`, `nikto`)
- 📂 Inspección de archivos sensibles (`/etc/passwd`, `/etc/shadow`)
- 🛠 Uso de herramientas ofensivas (`msfconsole`, `mimikatz`, `auditd`)
- 📊 Análisis de tráfico y puertos (`netstat`, `route`, `smbmap`)

### En entornos **Windows**:
- 👤 Identificación de cuentas privilegiadas
- 📋 Revisión de parches y actualizaciones (`systeminfo`, `wmic qfe`)
- 🔗 Auditoría de conexiones (`netstat`, `TCPView`)
- 🧩 Detección de tareas ocultas (`schtasks`)
- 🔥 Verificación de estado de antivirus y firewall
- 🔎 Análisis forense de procesos (`tasklist /svc`, `Process Explorer`)

---

## 🧪 Requisitos y Herramientas

- **Linux/Kali Linux:** Entornos como [JSLinux](https://bellard.org/jslinux/), [OnWorks](https://www.onworks.net/), o máquinas virtuales.
- **Windows:** Acceso a CMD como administrador.
- **Herramientas sugeridas:**
  - `nmap`, `nbtscan`, `smbmap`, `nikto`, `auditd`, `Metasploit`
  - `TCPView`, `Process Explorer`, `wmic`
  - `evil-winrm`, `mimikatz.exe`

---

## ⚠️ Consideraciones Éticas

> Este material está diseñado **exclusivamente con fines educativos y formativos**.  
> No debe utilizarse en sistemas reales sin la debida autorización.  
> **Nunca compartas credenciales** en formularios ni redes inseguras.

---

## 📚 Recursos Recomendados

- [Kali Linux Tools](https://tools.kali.org/)
- [Microsoft Sysinternals Suite](https://learn.microsoft.com/en-us/sysinternals/)
- [CriminalIP.io](https://www.criminalip.io/) — Para análisis de direcciones IP sospechosas
