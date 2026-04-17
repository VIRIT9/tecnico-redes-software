
### 1. Arquitectura de Servidores
En clase vimos cómo interactúan los distintos proveedores de servicios. Un entorno real se divide principalmente en dos:

* **Servidor Web:** Es el que entrega el contenido al cliente (navegador).
    * **Proveedores comunes:** Apache2 y Nginx.
    * **Contenido:** HTML, CSS, JS y scripts del lado del servidor como **PHP 8.2**.
    * **Protocolos:** HTTP (Puerto 80) y HTTPS (Puerto 443).
* **Servidor de Base de Datos (BD):** Contiene la información y los productos.
    * **Proveedores comunes:** MySQL y PostgreSQL.
    * **Backup:** Se usa `mysqldump` para generar un respaldo `.sql`.

> **Tip del profe:** Para estudiar programación, es bueno tener algo ligero, recomendó distros(distribuciones) como **Lubuntu** o **Zorin** (que es parecido a Windows y más atractivo).

---

### 2. Gestión de Paquetes y Servicios (Comandos clave)
Para instalar y manejar el servidor en Debian/Ubuntu usamos los siguientes comandos:

* **Instalación:**
    * `sudo apt update`: Actualiza la lista de paquetes desde internet.
    * `sudo apt install apache2`: Instala el servidor web.
    * `sudo apt install php8.2`: Instala la versión estable de PHP.
    * `sudo apt install git`: Fundamental para clonar repositorios.
* **Búsqueda:**
    * `apt search "nombre"` o `apt-cache search php8.2`.
* **Control de servicios:**
    * `sudo systemctl start apache2`: Inicia el servidor.
    * `sudo systemctl status apache2`: Revisa si el servidor está corriendo o si dio error.

---

### 3. Diagnóstico y Monitoreo del Sistema
Para saber qué está pasando con el hardware y la red:

* **Memoria:** `free -m` (Muestra la RAM disponible en MB).
* **CPU:** `lscpu` (Detalles del procesador).
* **Red y Puertos:** * `netstat` o `nmap`: Para ver qué puertos están abiertos.
    * `curl http://localhost`: Para probar el servidor web desde la consola.
* **Archivos:** `cat /etc/hosts`: Muestra la configuración de resolución de nombres local.

---

### 4. Acceso Remoto y Seguridad (SSH)
El profesor explicó cómo entrar al servidor de forma segura:

* **Instalación:** `sudo apt install openssh-server`.
* **Conexión:** `ssh localhost` (para probar) o `ssh usuario@ip_remota`.
* **Copiar archivos remotamente:** Se usa el comando **SCP**. 
    * Ejemplo: `scp respaldo.sql servidor:/ruta/`
* **Automatización:** `ssh-copy-id localhost` permite copiar tu clave para entrar sin poner contraseña cada vez.

---

### 5. Usuarios y Tareas Programadas
* **Crear usuarios:** `sudo useradd -m [nombre]` (el `-m` crea la carpeta en `/home`).
* **Grupos:** Se pueden revisar en `/etc/group`.
* **Scripts:** Un script es un programa que automatiza tareas. 
* **Tareas Programadas:** Por ejemplo, ejecutar un script de respaldo todos los días a las 22:00.

---
**Notas adicionales:**
* `cfdisk`: Herramienta para manejar particiones de disco.
* `who`: Para ver quién está conectado al sistema.
* `exit`: Para cerrar la sesión de la terminal o SSH.