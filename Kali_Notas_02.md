# 🛡️ Resumen de Comandos en Linux: Exploración, Administración y Auditoría

Este documento resume los comandos utilizados para tareas de escaneo de red, gestión de usuarios, administración del sistema, auditoría y modificación de archivos, aplicables en entornos Linux enfocados a seguridad informática y administración.

---

## 🔍 Comandos de Exploración de Red y Herramientas de Escaneo

### `nbtscan`
Escanea la red local en busca de dispositivos activos.  
- `-v`: Muestra detalles.  
- `-h`: Muestra ayuda.  
- `-s`: Define el formato de salida.

```bash
nbtscan -v -h -s : 192.168.64.4/24
```

> Se utilizaron diversas combinaciones de parámetros para lograr escaneos más detallados y con privilegios elevados.

---

### `nmap`
Escanea redes o dispositivos individuales.  
Usos comunes:

```bash
nmap -sn 192.168.64.4/24                  # Escaneo ping (dispositivos activos)
nmap -O 192.168.64.4                      # Obtener información del sistema operativo
nmap -p0-65535 -sSV 192.168.117.134       # Escaneo completo de puertos y servicios
```

---

### `msfconsole`
Lanza la consola de Metasploit para pruebas de penetración y explotación de vulnerabilidades.

---

### `nikto`
Herramienta de escaneo web para detectar vulnerabilidades HTTP.

```bash
nikto -h 192.168.117.134
```

---

## 👤 Comandos de Gestión de Usuarios y Permisos

### Crear usuario y grupo

```bash
adduser Jorge                      # Crear nuevo usuario
usermod -aG REDES Jorge           # Añadir el usuario "Jorge" al grupo "REDES"
groupadd REDES                    # Crear un grupo llamado "REDES"
```

---

### Cambiar propiedad y permisos de archivos

```bash
chown Jorge testing_echo.txt         # Cambia propiedad del archivo a Jorge
chmod go-r testing_echo.txt          # Revoca permisos de lectura para grupo y otros
```

---

### Visualizar información de usuarios y contraseñas

```bash
cat /etc/passwd                     # Ver lista de usuarios
cat /etc/shadow                     # Ver contraseñas cifradas (requiere privilegios)
cat /etc/passwd | grep root         # Filtra solo la cuenta root
```

---

### Ver nombre de usuario actual

```bash
whoami
```

---

## ⚙️ Comandos de Administración del Sistema

### Cambio de usuario con privilegios

```bash
su Jorge                            # Cambiar a usuario Jorge
su root                             # Cambiar a usuario root
```

---

### Información del sistema

```bash
hostname -I                         # Dirección IP local
ls, cd, pwd                         # Navegación y estructura de archivos
uname -a                            # Información del kernel
lsb_release -a                      # Versión de la distribución
clear                               # Limpiar pantalla de terminal
```

---

### Historial de comandos

```bash
history | tail -n 50                # Muestra los últimos 50 comandos ejecutados
```

---

## 🔎 Comandos de Auditoría y Monitoreo

### `ausearch`
Herramienta de auditoría para buscar eventos en los registros.

```bash
ausearch -x bash --start recent -i > historial_auditado.txt
```

> Busca en los logs las ejecuciones recientes de comandos como `bash`.

---

### `auditd`
Servicio que permite el monitoreo continuo del sistema.

```bash
apt-get install auditd
```

---

## 🗂️ Exploración y Modificación de Archivos

### Editores y comandos básicos

```bash
nano ./Desktop/testing_echo.txt         # Editor de texto desde terminal
echo "Testing echo" > ./Desktop/testing_echo.txt    # Escribir texto en archivo
```

---

### Control de acceso (ACL)

```bash
getfacl ./Desktop/char.txt              # Lista de control de acceso del archivo
```

---

### Gestión de directorios y archivos

```bash
mkdir ./Desktop/antm_temp               # Crear nuevo directorio
xdg-open .                              # Abre el explorador en la ubicación actual
```

---

## 🧠 Resumen de los Tiempos y Secuencia de Comandos

- **Primer conjunto**: Exploración de red con `nbtscan` y `nmap`, creación de usuarios, modificación de permisos y uso del historial de comandos.
- **Segundo conjunto**: Enfocado en administración de usuarios, permisos y estructuras de directorio.
- **Tercer conjunto**: Herramientas de escaneo de vulnerabilidades (`nmap`, `nikto`, `msfconsole`) y pruebas de penetración.
- **Global**: Actividad orientada a la seguridad, auditoría y administración de sistemas en un entorno Linux.

---

> Este resumen es útil para cursos de ciberseguridad, auditoría de sistemas y administración básica de servidores Linux.
