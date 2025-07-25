
# 🛠 Notas TEC – Comandos en Kali Linux para pruebas de red y pentesting

---

## 📡 Información de servidores

```bash
nslookup biblioteca.tec.mx
```

---

## 🌐 Ver nuestra IP

```bash
hostname -I
```

---

## 🔍 Escaneo de red

### Hacer barridos de red (ping sweep)
```bash
nmap -sn 192.168.64.4
```

### Ver todos los puertos abiertos (superficie de ataque)
```bash
nmap -O 192.168.64.4
```

### Ver todos los puertos que se pueden acceder
```bash
nmap 192.168.64.4
```

---

## 🧪 Scanner SMB

```bash
smbmap -H 192.168.64.4
```

---

## 🔎 Buscar contraseñas hardcodeadas

En el buscador de carpetas (Windows o Linux con entorno gráfico), buscar:

```
content:password
```

---

## 🧠 Conexiones remotas (Evil-WinRM)

```bash
evil-winrm -i 192.168.117.133 -u "Manuel Barrera" -p "MyP4$$-01#"
evil-winrm -i 192.168.117.133 -u sysadmin -H "HASHDEUSUARIO"
```

---

## 🧾 Ver cuenta con la que estoy conectado

```bash
whoami
whoami /priv
```

---

## 🧰 Herramientas útiles

### Instalar herramienta `net` (comando samba)

```bash
sudo apt install samba-common-bin
```

---

## 🔐 mimikatz.exe

> Puedes ponerte en el medio entre servidor y cliente en tickets de Kerberos.

---

## ⚙️ Utilidades y pruebas

### Página vulnerable para pruebas
- `DVWA`

### Ping y leer `/etc/passwd`

```bash
ping -c 192.168.117.134 && cat /etc/passwd
```

### Escuchar conexiones entrantes en un puerto

```bash
nc -lvnp 1234
```

---

