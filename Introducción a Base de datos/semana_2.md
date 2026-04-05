# Semana 2: Modelos de BD y Sistemas de Gestión (SGBD)

Un modelo de DB define la estructura lógica de cómo se organizan los datos, incluyendo las relaciones y restricciones entre ellos.

## 1. Base de Datos Jerárquica (El Árbol)
Es el modelo más antiguo. Organiza los datos en una estructura de árbol invertido.
* **Estructura:** Un "padre" puede tener varios "hijos", pero cada hijo solo tiene un padre.
* **Regla crítica:** Si eliminas al Padre, se borra todo lo que está abajo (nodos hijos).
* **Uso:** Sistemas de archivos de SO y directorios de red (LDAP).

| Ventajas | Desventajas |
| :--- | :--- |
| Alto rendimiento en estructuras fijas. | Poca flexibilidad para datos no jerárquicos. |
| Simplicidad para organigramas. | Genera redundancia si un hijo necesita varios padres. |

---

## 2. Base de Datos en Red
Evolución del modelo jerárquico que rompe la rigidez del árbol.
* **Estructura:** Permite relaciones de **Muchos a Muchos**. Un hijo puede tener varios padres.
* **Navegación:** Usa **punteros** (flechas lógicas) para recorrer los datos. Si un puente se rompe, el nodo queda "huérfano".
* **Uso:** Históricamente en bancos y reservas de aerolíneas.

---

## 3. Base de Datos Orientada a Objetos
Almacena los datos como **objetos** (como en Java, C++ o Python).
* **Innovación:** No solo guarda datos (atributos), sino también **métodos** (comportamientos o funciones que el objeto puede realizar).
* **Uso:** Ingeniería (CAD), sistemas científicos y de geografía (GIS).

---

## 4. Base de Datos Relacional (El Estándar)
Organiza la información en tablas (Entidades y Relaciones). Es el modelo más usado hoy.
* **Características:** Estructura fija (el diseño se define antes de cargar los datos). Usa lenguaje **SQL**.
* **Propiedades ACID (Garantía de validez):**
    * **Atomicidad:** "Todo o nada". Si un paso falla, la transacción vuelve al inicio.
    * **Consistencia:** Solo inicia operaciones que puede concluir bajo las reglas de integridad.
    * **Aislamiento (Isolation):** Las operaciones son invisibles entre sí hasta que terminan.
    * **Durabilidad:** Una vez guardado, el dato persiste aunque el sistema falle.



---

## 5. Bases de Datos No Relacionales (NoSQL)
Diseñadas para datos no estructurados y grandes volúmenes. Priorizan la **rapidez** sobre la integridad estricta (no aplica ACID).
* **Tipos comunes:**
    * **Clave-Valor (Redis):** Carritos de compra.
    * **Documentos (MongoDB):** Blogs y catálogos.
    * **Grafos (Neo4j):** Redes sociales (amigos de amigos).
    * **Columnas (Cassandra):** Big Data e IoT.

---

## VI. Caso de Éxito: NETFLIX (Modelo Híbrido)
Netflix combina ambos mundos para ser eficiente:
1. **SQL (MySQL):** Para facturación, cuentas de usuarios y datos maestros. Requiere consistencia total.
2. **NoSQL (Cassandra/EVCache):** Para el historial de visualizaciones (billones de datos) y recomendaciones rápidas.

---

## VII. Sistema Gestor de Base de Datos (SGBD / DBMS)
Es el software que actúa como intermediario entre nosotros y los datos físicos.

| Concepto | Analogía | Definición |
| :--- | :--- | :--- |
| **Base de Datos** | El Contenido | Los archivos físicos (nombres, stock) guardados en disco. |
| **SGBD** | La Herramienta | El programa que organiza, lee y escribe (MySQL, Oracle, PostgreSQL). |