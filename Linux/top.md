# 🖥️ Glosario Básico del Comando `top` en macOS

Este comando sirve para ver **qué procesos están usando más recursos** de tu computadora, como la memoria y el CPU.

---

## 📌 Sección Superior – Información del Sistema

| Elemento       | Qué Significa                                                                 |
|----------------|--------------------------------------------------------------------------------|
| **Processes**   | Número total de tareas activas. Dice cuántas están funcionando y cuántas dormidas. |
| **Load Avg**    | Qué tan cargada está tu computadora (a 1, 5 y 15 minutos). Más de 3 puede ser mucho. |
| **CPU usage**   | Cómo se está usando el procesador:                                            |
|                | • `user`: por programas abiertos por ti.                                       |
|                | • `sys`: por el sistema operativo.                                             |
|                | • `idle`: lo que queda libre (entre más, mejor).                              |
| **PhysMem**     | Cuánta memoria RAM está en uso o libre.                                       |
| **VM**          | Cuánta memoria virtual (RAM simulada en disco) se está usando.                |
| **Disks**       | Cuántos datos se han leído y escrito en el disco duro.                        |
| **Networks**    | Cuántos datos han entrado o salido por la red.                                |
| **SharedLibs**  | Cantidad de librerías compartidas que están en uso por las apps.              |

---

## 📊 Tabla de Procesos – Lo que hacen tus programas

| Columna      | Significado Simple |
|--------------|--------------------|
| **PID**      | ID único del proceso. |
| **COMMAND**  | Nombre del programa. |
| **%CPU**     | Qué tanto está usando el CPU (procesador). |
| **TIME**     | Cuánto tiempo ha usado el CPU desde que empezó. |
| **#TH**      | Cuántos hilos (tareas internas) tiene el programa. |
| **#WQ**      | Hilos en espera (pendientes por hacer algo). |
| **#PORTS**   | Conexiones abiertas con otros programas o la red. |
| **MEM**      | Memoria RAM que está usando el programa. |
| **PURG**     | Memoria que se puede liberar si se necesita. |
| **CMPRS**    | Memoria que se ha comprimido para ahorrar espacio. |
| **PGRP**     | Grupo de procesos al que pertenece. |
| **PPID**     | ID del programa que lo inició (padre). |
| **STATE**    | Estado actual (corriendo, dormido, etc.). |
| **BOOSTS**   | Si tiene prioridad especial (por ejemplo, apps de pantalla o audio). |

---

## 🔬 Métricas Avanzadas (Opcional)

| Columna      | Qué Mide |
|--------------|----------|
| **%CPU_ME**  | CPU usado en tareas de medios (video/audio). |
| **%CPU_OTHRS** | CPU usado por otros hilos del proceso. |
| **UID**      | Usuario que ejecuta el proceso. |
| **FAULTS**   | Fallos de página (cuando necesita memoria que no tiene a mano). |
| **COW**      | Copias en memoria hechas solo cuando se modifican. |
| **MSGSENT**  | Mensajes enviados a otros procesos. |
| **MSGRECV**  | Mensajes recibidos. |
| **SYSBSD**   | Llamadas al sistema hechas con funciones comunes. |
| **SYSMACH**  | Llamadas al sistema más profundas (nivel del núcleo). |

---

## 🧠 ¿Cómo leer esto?

- Si un proceso tiene **%CPU muy alto**, es el que más está trabajando (o consumiendo).
- Si usa **mucha MEM**, podría estar consumiendo mucha RAM.
- Si el sistema está lento y hay **poco idle en CPU usage**, probablemente algo está consumiendo todos los recursos.

---

