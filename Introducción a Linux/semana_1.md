# Introducción a Sistemas Operativos: GNU/Linux

## 1. Arquitectura del Sistema
El sistema se divide en capas que permiten la interacción entre el hardware y el usuario:

* **Kernel:** El núcleo del sistema. Administra el hardware (CPU, memoria, dispositivos).
* **Shell:** El intérprete de comandos. Es la interfaz que rodea al Kernel.
* **X:** La interfaz gráfica (GUI) para Linux.
* **BASH (Bourne Again SHell):** La herramienta/intérprete estándar para interactuar con la Shell.
* **Interacción:** El usuario interactúa con la Shell para enviar instrucciones al Kernel.

> **Nota:** Se debe decir **GNU/Linux**, ya que Linux es técnicamente solo el Kernel, mientras que las herramientas del sistema pertenecen al proyecto GNU.

---

## 2. El Sistema de Archivos y Dispositivos
En Linux, **"todo es un archivo"**. Los dispositivos se encuentran en directorios específicos:

| Directorio / Archivo | Descripción |
| :--- | :--- |
| `/dev/sda` | Representa el primer disco duro físico (SATA/SCSI). |
| `/dev/sda1` | Primera partición del disco `sda`. |
| `/dev/sdb` | Segundo disco duro físico. |
| `/proc/` | Sistema de archivos virtual que administra dispositivos y procesos. |
| `/etc/` | Contiene los archivos de **configuración** del sistema. |
| `/bin/` | Contiene los binarios (comandos ejecutables) esenciales. |

### Comandos de información de Hardware
* **CPU:** Es el procesador.
* **cpuinfo:** Comando o archivo (`/proc/cpuinfo`) que muestra la arquitectura e información detallada de la CPU.
* **TTY:** Representa la terminal física o consola (teletype). Es el lugar donde el usuario interactúa con el sistema a través del monitor.

---

## 3. Comandos Esenciales (CLI)
Uso de la consola (`$`) para meter comandos:

* `ls`: Muestra archivos. Con `-l` muestra más info (permisos, tamaño, fechas).
* `dir`: Similar a `ls`, muestra el contenido del directorio.
* `wc`: (Word Count) Cuenta líneas, palabras o caracteres. Útil para contar archivos si se combina con otros comandos.
* `cat`: (Concatenate) Muestra el contenido de un archivo. Ejemplo: `/bin/cat` es un comando binario compilado (no es texto plano, si intentas leerlo verás "cosas raras").
* `grep`: Permite filtrar salidas.
    * Ejemplo: `grep conf` busca todas las líneas que contengan "conf".

### Tuberías (Pipes `|`)
Las **tuberías** permiten concatenar comandos: la salida de un comando entra como entrada del siguiente.
> *Ejemplo:* `ls | wc -l` (Lista los archivos y luego cuenta cuántas líneas resultaron).

---

## 4. Distribuciones y Gestión de Paquetes
Existen diferentes "sabores" de Linux según su filosofía y gestión de software:

### Familia Debian (Ubuntu, etc.)
* Usa paquetes **.DEB** (paquetes binarios ya compilados).
* **Gestor:** `apt` (Advanced Package Tool).
* *Instalación:* `apt install mysql-server` (Instala el servidor de base de datos de forma sencilla pero no siempre intuitiva).

### Familia Red Hat (RHEL, Fedora, CentOS)
* Enfoque profesional/DevOps.
* Usa paquetes **.RPM**.
* **Gestor:** `dnf` (versión moderna) o `yum` (antiguo).

### Filosofía de Software
* **Vesper / Software Propietario:** Software que no es libre (o es libre solo parcialmente).
* **Software Libre:** Respeta la libertad de los usuarios y la comunidad.

