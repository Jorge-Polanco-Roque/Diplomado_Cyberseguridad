
# 🐧 Práctica 2: Auditoría Linux

> 📝 Esta práctica te permitirá conocer y ejecutar comandos clave para auditar sistemas basados en Linux, Unix o MacOS. Se incluyen técnicas de revisión de permisos, conexiones de red, procesos activos y escalación de privilegios.

---

## 💻 Acceso a entornos Linux

- [JSLinux – Fedora 33](https://bellard.org/jslinux/)
- [Kali Linux en línea (OnWorks)](https://www.onworks.net/os-distributions/debian-based/free-kali-linux-online)

> 📝 Usar solo **un integrante por equipo** para evitar saturación.

---

## 🧪 Comandos de auditoría

### 🔹 1. Identidad del sistema
```bash
hostname
whoami
```
> 📝 No se recomienda operar como root directamente en sistemas críticos.

---

### 🔹 2. Versión y distribución del sistema
```bash
uname -a
lsb_release -a
```
> ¿Qué versión del kernel tiene tu sistema?

---

### 🔹 3. Usuarios y hashing de contraseñas
```bash
cat /etc/passwd
cat /etc/shadow
cat /etc/group
```
> 📝 Revisa el algoritmo de hashing (ej. SHA-512, MD5, etc.) usado en la cuenta root.

---

### 🔹 4. Segmento de red
```bash
hostname -I
ifconfig
```
> 📝 Identifica tu segmento `/24`, por ejemplo `192.168.68.0/24`.

---

### 🔹 5. Escaneo NetBIOS (solo Kali)
```bash
nbtscan -v -h -s : 192.168.68.0/24
```
> 📝 Muestra dominios, workgroups y direcciones MAC.

---

### 🔹 6. Escalación de privilegios (solo Kali)
```bash
sudo apt install unix-privesc-check
unix-privesc-check standard
```
> 🧠 Revisa si se detectan **WARNINGS** y vulnerabilidades.

---

### 🔹 7. Tabla de ruteo y puertos abiertos
```bash
route -n
netstat -aon | grep LISTEN
w
```
> 📝 Análisis de sesiones activas y puertos en estado `LISTEN`.

---

### 🔹 8. Escaneo de red (solo Kali)
```bash
nmap -sn 192.168.68.0/24
```
> Detecta hosts activos en la red.

---

### 🔹 9. Carpetas compartidas (solo Kali)
```bash
smbmap -H <IP>
```
> ¿Encontraste carpetas compartidas con riesgos en los permisos?

---

### 🔹 10. Análisis de procesos
```bash
ps aux
```
> ¿Cuál es el `PID` del proceso `init`?

---

## 🔐 Práctica con permisos

### Crear usuario y cambiar contexto:
```bash
adduser diplomado
su diplomado
whoami
exit
```

### Crear y escribir archivos:
```bash
touch archivo1.txt
touch archivo2.txt
echo "archivo de Root" > archivo1.txt
echo "archivo de usuario Diplomado" > archivo2.txt
cat archivo1.txt
cat archivo2.txt
```

### Cambiar permisos:
```bash
chown diplomado archivo2.txt
chgrp diplomado archivo2.txt
chmod go-r archivo1.txt
ls -l
```

### Validar acceso con otro usuario:
```bash
su diplomado
cat archivo1.txt  # ¿Permission denied?
exit
whoami
cat archivo1.txt  # Con root
```

---

## 🧩 Reflexiones

> ¿Qué resultado obtuviste al intentar leer `archivo1.txt` como usuario `diplomado`?
> ¿Y como usuario `root`?

---

## 🎯 Conclusión

Has aprendido a:

- Verificar configuración de usuarios, contraseñas y procesos
- Detectar rutas de red maliciosas y backdoors
- Manipular permisos y propietarios en Linux
- Usar herramientas como `nmap`, `netstat`, `unix-privesc-check`, `smbmap`

---

⚠️ **Recuerda:**  
No compartas contraseñas mediante formularios.  
Este material es exclusivamente educativo.

