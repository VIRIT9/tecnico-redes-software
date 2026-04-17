# Apuntes de Redes: Capa 1 y Capa 2

## Capa 1: Nivel Físico (Physical Layer)
En esta capa se define el medio de transmisión y la señalización.

### Medios de Transmisión
* **STP (Shielded Twisted Pair):** Cables de par trenzado blindados.
    * **Ventajas:** Inhiben el ruido electromagnético (EMI).
    * **Desventajas:** Más caros y rígidos que el UTP común.
    * **Nota de diseño:** No se recomienda su uso en tiradas verticales largas por el peso y la tensión; para enlaces verticales (backbone) es preferible usar **Fibra Óptica**.
* **Saturación de Recursos:** Si el enlace es de mala calidad (enlace "malo"), el CPU y la RAM pueden saturarse procesando retransmisiones y errores de paquetes.
* **Pachera (Patch Panel):** Punto intermedio de conexión. Del jack de la pared va a la computadora, permitiendo organizar los cables de manera "corrida" y profesional.

---

## Capa 2: Enlace de Datos (Data Link Layer)
Aquí es donde viven los **Switches** y se maneja el direccionamiento físico (MAC).

### Componentes de Red
* **Switch:** Dispositivo de Capa 2. Conecta dispositivos dentro de una misma red local (LAN).
* **Router:** Dispositivo de Capa 3. Es quien "divide" las redes y permite la comunicación con el exterior (Internet).

### Diagramado y Gestión
* **Topología:** Representación visual de la red.
* **Herramientas:** * **Draw.io:** Excelente para diagramas lógicos y físicos.
    * **Excel:** A veces es más rápido y eficiente para llevar un control de inventario de IPs y puertos.
* **Acceso Web:** Generalmente, la info de la red se obtiene vía navegador en `http://192.168.0.1/` (requiere credenciales de usuario).

---

## Direccionamiento IP y Subredes

Para configurar un equipo (Host), necesitamos cuatro datos fundamentales:
1.  **Dirección IP:** Identificador del dispositivo.
2.  **Máscara de Subred:** Define qué parte es red y qué parte es host.
3.  **Gateway (Puerta de Enlace):** La IP del router para salir de la red local.
4.  **DNS (Domain Name System):** Traduce nombres (google.com) a IPs (ej: 8.8.8.8 o 8.8.4.4).

### El Sistema Binario en Redes
Una dirección IPv4 tiene **32 bits**, divididos en 4 octetos.

* **Representación de Máscara (Ejemplo /24):**
  `11111111.11111111.11111111.00000000`
  * Esta cadena representa **24** bits activos (encendidos).
  * **Jerarquía de bits:**
    * **Izquierda:** Bits más importantes (definen la red).
    * **Derecha:** Bits menos importantes (identifican al host/dispositivo).

* **¿Por qué varía la cantidad de "1"?**
  La cantidad de bits encendidos define el tamaño de la red. 
  * **Menos unos (ej. /8 o /16):** Redes más grandes con espacio para miles o millones de dispositivos.
  * **Más unos (ej. /28):** Redes pequeñas con pocos dispositivos (subredes).
  * **Ceros a la derecha:** Cuantos más ceros hay a la derecha, más espacio queda para conectar equipos (celulares, laptops, etc).

* **Dirección de Red:** Identifica a la red en sí (ej: `192.168.0.0`).
* **Broadcast:** Dirección para enviar datos a todos los nodos (ej: `192.168.0.255`). Todos los bits de host están "prendidos" (1).
* **Cálculo de Dispositivos (Hosts):**
    * Fórmula: `2^n - 2`
    * Donde `n` es el número de bits de host. En una máscara `/24` (256 combinaciones), tenemos `256 - 2 = 254` dispositivos utilizables.

### Ejemplo de Configuración Manual (Windows)
Para un host en una red estándar:
* **IP:** `192.168.0.254` (Se suele cambiar la IP del router o asignar IPs altas para evitar conflictos con el pool DHCP).
* **Máscara:** `255.255.255.0` (Equivalente a `/24` en binario).
* **GW:** `192.168.0.1`
* **DNS:** `8.8.8.8` (Google Primary) / `8.8.4.4` (Google Secondary).

---

## Herramientas de Diagnóstico
* **NMAP:** Herramienta potente para descubrimiento de redes y auditoría de seguridad. Permite ver qué equipos están activos y qué puertos tienen abiertos.
* **DHCP Pool:** El rango de direcciones que el router otorga automáticamente (ej: del `192.168.0.10` al `192.168.0.100`).
* **SSID:** El nombre de la red Wi-Fi.
* **PSK:** (Pre-Shared Key) Es la contraseña de la red inalámbrica.
