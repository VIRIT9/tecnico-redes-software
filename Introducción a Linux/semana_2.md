
# Semana 2: Virtualización y Administración de Archivos en Linux


## 1. Requisitos de Hardware (Especificaciones)
Para un desempeño óptimo en tareas técnicas y desarrollo, se identifican los siguientes componentes mínimos:

* **CPU:** Mínimo un procesador **i5**.
* **Almacenamiento:** **SSD 500GB** (Los discos mecánicos son considerablemente más lentos).
* **RAM:** Mínimo **8GB**.
* **Red:** Soporte para WiFi 5G y puerto Ethernet.
* **Atajo rápido:** `Ctrl + Shift + Esc` para abrir el Administrador de Tareas y ver las características del hardware en tiempo real.

---

## 2. Entornos Virtuales
Existen diferentes formas de ejecutar Linux dentro de un sistema anfitrión (como Windows):

### A. WSLv2 (Windows Subsystem for Linux)
* Funciona como un **contenedor** ligero.
* **Ubuntu:** Es la distribución por defecto; es más "pesada" pero excelente para desarrollar.
* **Concepto de Localhost:** Permite que las bases de datos (DB) y servidores web (WEB) dentro de WSL se comuniquen con el sistema Windows.
* **Restricción:** No se pueden poner dos aplicaciones escuchando en el mismo puerto.


### B. Oracle VirtualBox (Máquinas Virtuales)
* **Arranque Virtual:** Emula el "fierro" (hardware) de forma completa (CPU, RAM, Disco).
* **Adaptador Puente (Bridge):** Permite que la máquina virtual se conecte "afuera" de la red física como si fuera un dispositivo independiente.
* **Configuración:** Es vital verificar qué interfaz de red (WiFi o Ethernet) conectamos al adaptador.

---

## 3. Estructura de Directorios Avanzada
Continuando con la jerarquía del sistema de archivos:

| Directorio | Función / Contenido |
| :--- | :--- |
| `/home` | Contiene las carpetas personales de los usuarios (ej. `/home/juan`). Archivos de **texto** (editables). |
| `/etc` | Archivos **binarios** de configuración (no se deben editar directamente como texto simple). |
| `/var` | Archivos de **log** y datos variables que crecen con el tiempo. |
| `/usr` | Contiene los programas del usuario (equivalente a *Program Files* o *AppData* en Windows). |
| `/dev` | Archivos que representan los componentes de hardware. |

---

## 4. Comandos de Gestión y Navegación
Comandos esenciales para moverse por la terminal:

* `pwd`: (Print Working Directory) Muestra la ruta donde estás parado actualmente.
* `cd`: Cambiar de directorio.
    * `cd /`: Vas a la **Raíz** del sistema.
    * `cd ~`: Vas al **Home** del usuario actual.
* `ls`: Listar archivos y directorios.
    * `ls -la`: Lista **todos** los archivos, incluyendo los ocultos (los que empiezan con punto).
* `mkdir [nombre]`: Crea un directorio nuevo.
* `touch [archivo]`: Crea un archivo vacío.
* `cp [origen] [destino]`: Copiar archivos o carpetas.
* `mv [origen] [destino]`: Mover o **renombrar** un archivo.
* `rm`: Borrar (remover) archivos.

---

## 5. Notas Adicionales y Tips
* **Distrowatch:** Sitio web recomendado para ver cuáles son las distribuciones de Linux más populares (Top) actualmente.
* **WSL Commands:**
    * `wsl --install`: Para instalar el subsistema.
    * `wsl --shutdown`: Para apagar todas las instancias de Linux corriendo.
* **Teclado:** Atajo `Windows + Space` para cambiar rápidamente al teclado en Inglés (útil para programar).