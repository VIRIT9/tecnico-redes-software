# Semana 3: Práctico 1 - Instalación y Redes

### 1. Preparación del Sistema (Instalación)
Para el primer práctico, el profe recomendó instalar **Debian** (o Rocky Linux como alternativa). La idea es hacer un despliegue (*deploy* o *provision*) limpio:

* **Sin GUI (Interfaz Gráfica):** Es lo ideal para servidores. Se busca un sistema mínimo (tipo Arch OS) donde todo se maneje por consola y archivos de configuración.
* **Escritorios (Si se necesita):**
    * **Ligeros:** XFCE o LXQT (consumen poco).
    * **Pesados:** GNOME.
    * **Equilibrado:** Linux Mint.  

---
* **"Deploy"** o **"Provision"** es básicamente el proceso de instalar y dejar el sistema listo para producir.
---

### 2. Configuración de Red y Conectividad
Esta parte es para que la máquina virtual (VM) se vea con el resto de la red.

* **Topología de Red:**
    * La red física (ej. LAN UTU) usa un rango como `10.255.0.0/16`.
    * El router/firewall (Mikrotik) gestiona el **Bridge** (puente) y la WLAN.
    * En la VM de Debian, la interfaz suele aparecer como `enp0s3` o similar.
* **Modos de Conexión en VirtualBox:**
    * **Bridge (Adaptador Puente):** Para que la VM tenga una IP propia en el mismo rango que la red física (ej. `192.168.88.x`). Así aparece en "Red" de la compu.
    * **NAT:** Se usa más que nada para que la VM tenga salida a internet a través del host.

---

### 3. Acceso Remoto (SSH)
Para no tener que usar la ventanita de VirtualBox, usamos SSH:

* **Puerto estándar:** 22.
* **NAT/Redirección:** Si se usa NAT, a veces hay que mapear puertos (ej. entrar por el puerto `2222` del host para llegar al `22` de la VM).
* **Prueba rápida:** El profe recomienda verificar siempre la IP antes de intentar conectar.

---

### 4. Machete de Comandos de Red y Sistema
Para que el práctico salga bien, hay que dominar estos:

| Comando | Para qué sirve |
| :--- | :--- |
| `ip config /all` | (En Windows) Ver toda la info de red del host. |
| `ip a` | (En Linux) Ver la IP de la VM. |
| `hostname` | Ver el nombre que le pusimos a la máquina. |
| `uname -a` | Ver info del kernel y el sistema instalado. |
| `wget` | Para descargar archivos o herramientas directo de internet. |

---
