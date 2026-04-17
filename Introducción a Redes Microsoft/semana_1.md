# 🌐 Fundamentos de Redes y Hardware

## 1. Conceptos Globales de Internet
Internet no es una entidad única, sino una **"Red de Redes"**. Sin embargo, es importante diferenciar que no todas las redes son públicas; existen redes privadas corporativas y gubernamentales.

* **AS (Sistema Autónomo):** Es una unidad de enrutamiento gigante. Imaginalo como una "isla" tecnológica (ej. Antel, Google, una Universidad) que tiene sus propias reglas internas de tráfico.
* **BGP (Border Gateway Protocol):** Es el protocolo que permite que estos Sistemas Autónomos se hablen entre sí para formar el mapa global de Internet.

---

## 2. Topologías de Red
La topología es el **mapa físico o lógico** de cómo se conectan los equipos.

### A. Estrella (Star)
Es la topología reina en redes LAN (hogares y oficinas). 
* **Funcionamiento:** Todos los equipos se conectan a un nodo central (Switch).
* **Punto crítico:** Si el Switch central muere, toda la red se cae. Si un cable de una PC se rompe, solo esa PC pierde conexión.

### B. Malla (Mesh)
Es la base de la redundancia en Internet.
* **Funcionamiento:** Los nodos están conectados entre sí. Si un camino falla, el tráfico busca otra ruta automáticamente.

---

## 3. Hardware y Capas del Modelo OSI (Capa 2 y 3)

### Switch (Capa 2 - Enlace de Datos)
Es el "Cerebro de la LAN". Su función es conectar máquinas dentro de la misma red local.
* **Dirección MAC:** Identificador físico único de la tarjeta de red (Hexadecimal: `00:1A:2B...`). Nunca cambia.
* **Tabla CAM:** El Switch "aprende" en qué puerto físico está cada MAC para enviar los datos directamente allí y evitar la saturación.
* **Broadcast:** Un mensaje que se envía a "Todos" (`FF:FF:FF:FF:FF:FF`). Útil para cuando un equipo busca al servidor DHCP.

### Router (Capa 3 - Red)
Es el "Dispositivo de Frontera". Su función es unir redes distintas (ej. tu casa con Internet).
* **Dirección IP:** Dirección lógica asignada para ubicarte en la red. 
* **DHCP:** Protocolo que te da una IP automáticamente apenas te conectas.
* **Gateway (Puerta de Enlace):** Es la IP del Router. Es la "puerta" por donde salen tus datos hacia el mundo exterior.

### Access Point (AP)
Es un puente inalámbrico. Transforma la señal cableada en ondas de radio (Wi-Fi). 
* **Dato técnico:** En las casas usamos un "Router Hogareño" que en realidad es 3 equipos en 1: Router + Switch + Access Point.

---

## 4. Transporte de Datos: TCP vs UDP (Capa 4)
Divide los archivos grandes en **Segmentos** y usa **Puertos** para saber a qué aplicación va cada dato.

| Característica | TCP (Transmission Control Protocol) | UDP (User Datagram Protocol) |
| :--- | :--- | :--- |
| **Fiabilidad** | Alta (Asegura que llegue todo). | Baja (No confirma recepción). |
| **Velocidad** | Más lento (por los chequeos). | Muy rápido (tiempo real). |
| **Uso ideal** | Web (HTTP), Email, Archivos (PDF). | Streaming, Juegos online, VoIP. |
| **Error** | Si falta un bit, se retransmite. | Si falta un bit, se pierde (glitch). |

---

## 5. Arsenal de Diagnóstico (CLI)
Comandos esenciales para ejecutar en la terminal (CMD o Bash):

* `ping -t [IP]`: Prueba de eco constante. Sirve para ver si hay **Latencia** (retraso) o pérdida de paquetes.
* `tracert [IP/Web]`: Rastrea los "saltos" (routers intermediarios) hasta el destino. Si el internet está lento, te dice exactamente en qué punto falla.
* `ipconfig /flushdns`: Borra la memoria caché de nombres web. Si una página no carga pero internet funciona, este comando suele arreglarlo.
* `tcpdump -i eth0 icmp`: (Linux) Es un "microscopio". Te permite ver el paquete crudo pasando por la tarjeta de red. Los hackers y administradores lo usan para "sniffing".

---

## 6. Capa Física y Fenómenos
* **Fibra Óptica:** Transmite pulsos de luz. Es inmune a la interferencia eléctrica pero delicada (se quiebra si se dobla mucho o si entra suciedad en el conector).
* **Jaula de Faraday:** Fenómeno donde materiales metálicos bloquean las ondas electromagnéticas (Wi-Fi/Celular). Por eso en edificios con mucho hierro la señal es mala.
* **UTP (Cable de Red):** El estándar es el RJ45. Tiene límites de distancia (aprox. 100 metros) antes de que la señal se degrade.