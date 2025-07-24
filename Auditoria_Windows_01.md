
# 🛡️ Práctica 1: Auditoría Windows

> 📝 Esta práctica busca familiarizarte con comandos útiles para auditar un sistema Windows, detectar vulnerabilidades comunes, y reconocer señales de compromiso.

---

## 📥 Instalación de Herramientas

1. **Process Explorer**  
   🔗 [Descargar](https://bit.ly/3EZDQpr)

2. **TCPView**  
   🔗 [Descargar](https://bit.ly/3Ha7FW8)

> 📝 Ambas herramientas son de Microsoft y no deberían representar problemas de seguridad. Asegúrate de tener permisos si estás en equipo de trabajo.

---

## 🖥️ Comandos en CMD

### 🔹 1. Obtener nombre del equipo
```bash
hostname
```
> 📝 No copies este nombre en formularios. Solo úsalo como referencia interna.

---

### 🔹 2. Usuarios y privilegios
```bash
net users
whoami
whoami /priv
```
> 📝 Busca privilegios que tengan estado `Enabled`. Evalúa si tu cuenta tiene privilegios elevados.

---

### 🔹 3. Investigar cuentas
```bash
net user <nombre_usuario>
net user Administrator
```
> 📝 Puedes revisar si la cuenta está activa, expiración de contraseña, y últimos accesos.

---

### 🔹 4. Información del sistema
```bash
systeminfo
```
> 📝 Presta atención a la sección `Hotfix(s)`. ¿Tu sistema tiene suficientes parches aplicados?

---

### 🔹 5. Detalles de parches
```bash
wmic qfe
```
> 📝 Incluye URLs y fechas. Útil para forense post-incidente.

---

### 🔹 6. Grupos privilegiados
```bash
net users
net localgroup
net localgroup "Administrators"
```
> 📝 Verifica si tu cuenta está en el grupo `Administrators`. También busca cuentas desconocidas.

---

### 🔹 7. Accesos remotos y de poder
```bash
net localgroup "Remote Desktop Users"
net localgroup "Power Users"
```
> 📝 Busca usuarios no autorizados con permisos especiales. Señal de backdoors.

---

## 🌐 Auditoría de Red

### 🔹 8. Interfaces y rutas
```bash
ipconfig /all
route print
```
> 📝 `route print` muestra los segmentos de red. ¿Hay rutas extrañas inyectadas?

---

### 🔹 9. Conexiones activas
```bash
netstat -aon
netstat -b
```
> 📝 Analiza procesos que hacen conexiones. ¡Posibles backdoors!  
> Usa **TCPView** para un análisis visual. Ejecuta el `.exe` adecuado para tu sistema.

---

### 🔹 10. TCPView
> 📝 Equivalente gráfico de `netstat`.  
> ¿Procesos conectándose a IPs públicas raras? Verifica en:  
🔗 [CriminalIP.io](https://www.criminalip.io/)

---

## 🧠 Procesos y Servicios

### 🔹 11. Listar procesos
```bash
tasklist /svc
tasklist /svc /fi "STATUS eq running"
```
> 📝 Observa nombres con entropía alta (letras raras). Útil para detectar malware.

---

### 🔹 12. Process Explorer
> 📝 Visualiza árbol de procesos. Busca archivos anómalos cargados o DLLs raras.

---

## 🗂️ Carpetas Compartidas

### 🔹 13. Ver carpetas compartidas
```bash
net share
```

### 🔹 14. Permisos de carpetas
```bash
net share "Nombre de carpeta"
```
> 📝 ¿Permisos de escritura para `Everyone`? ¡Alerta de seguridad!

---

## 🛡️ Seguridad del Sistema

### 🔹 15. Verificar antivirus
```bash
sc query windefend
```
> 📝 Si no está `RUNNING`, asegúrate de tener otro antivirus.

---

### 🔹 16. Verificar firewall
```bash
netsh firewall show state
netsh advfirewall show allprofiles
```
> 📝 ¿Está `Enabled`? También puedes abrir `Windows Defender Firewall` desde el menú.

---

### 🔹 17. Reglas de entrada
> 📝 En `Inbound Rules`, revisa si hay apps sospechosas permitidas desde internet.

---

## 🧩 Software instalado

### 🔹 18. Listar programas
```bash
wmic product get name,version
```
> 📝 Busca **PUAs (Potentially Unwanted Applications)**.

---

## ⏰ Tareas Calendarizadas

### 🔹 19. Ver tareas activas
```bash
schtasks /query
```
> 📝 Táctica común de atacantes: tareas ocultas con nombres genéricos.  
> Busca patrones raros o tareas que se ejecuten frecuentemente sin razón.

---

## 💬 Pregunta de reflexión

> **¿Cómo aplicarías estas herramientas y comandos en la operación diaria de tu organización?**  
> Considera su utilidad en:
> - Diagnóstico de incidentes
> - Auditoría proactiva
> - Tareas de pentesting interno
> - Validación de higiene digital

---

⚠️ **Nota final:**  
Nunca compartas contraseñas por formularios.  
Este material es educativo y no está vinculado a Google ni a ninguna entidad oficial.
