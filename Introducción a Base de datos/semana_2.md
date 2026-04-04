# Semana 2: Conceptos Técnicos y Beneficios de las BD

## 1. Operaciones C.R.U.D.
Es el "trabajo diario" de cualquier base de datos. Representa las cuatro operaciones básicas que realizamos sobre la información:
* **C (Create):** Crear un registro nuevo (ej. dar de alta a un cliente).
* **R (Read):** Leer o buscar datos (ej. consultar un saldo o buscar un nombre).
* **U (Update):** Actualizar información (ej. cambiar la dirección de domicilio).
* **D (Delete):** Borrar datos (ej. dar de baja un servicio o eliminar un registro).

---

## 2. ¿Qué es una Base de Datos (BD)?
Es una colección organizada de datos estructurados, almacenados electrónicamente en un sistema informático. Su propósito es recopilar, gestionar y recuperar información de manera eficiente.

### Diferencia Clave: RAM vs. Disco
* **Memoria RAM (Random Access Memory):** Es volátil, lo que significa que toda la información se borra cuando se apaga el sistema.
* **Base de Datos (Disco):** Es almacenamiento permanente. Los datos persisten aunque se apague la computadora.

---

## 3. Beneficios Principales de las Bases de Datos

### A. Independencia de datos
La forma física en que se almacena la información está separada de las aplicaciones. 
* **Ventaja:** Permite cambiar el motor o la infraestructura (ej. de MySQL a PostgreSQL) sin tener que reescribir el software.

### B. Reducción de redundancia e inconsistencia
Centralizar los datos elimina la información duplicada. 
* **Efecto:** Al actualizar un dato en un único lugar, todos los sistemas ven el cambio al instante, evitando valores contradictorios.

### C. Integridad de los datos
Reglas y restricciones automáticas para garantizar que los datos sean correctos:
* **Integridad de entidad:** Cada registro debe ser único mediante la **Clave Primaria (PK)**.
* **Integridad referencial:** Las relaciones entre tablas deben ser consistentes (ej. no borrar un cliente que tiene facturas activas).
* **Integridad de dominio:** Los valores deben cumplir reglas específicas (ej. fechas válidas o campos numéricos).

### D. Seguridad y Control de Acceso
* **Autenticación:** Proceso de verificar la identidad del usuario (¿Quién eres?).
* **Autorización:** Determina qué acciones tiene permitido realizar el usuario (¿Qué puedes hacer?).

### E. Acceso Concurrente
Varios usuarios pueden acceder y modificar datos simultáneamente sin que la información se corrompa:
* **Bloqueos (Locks):** El sistema pone un cartel de "en uso" cuando alguien modifica un dato.
* **Transacciones (ACID):** Operaciones de "todo o nada" para asegurar la validez de los datos.

---

## 4. Respaldo y Recuperación (Backups)
* **Respaldo Completo:** Una copia total de toda la base de datos (una "foto" completa).
* **Respaldo Incremental:** Guarda solo los cambios realizados desde el último respaldo (ahorra espacio).
* **Respaldo Diferencial:** Guarda todos los cambios realizados desde el último respaldo completo.

## 5. Historia y Auditoría
Mantiene un registro detallado de todos los cambios: quién creó el dato, qué cambió, cuándo se hizo y cómo quedó el estado final.