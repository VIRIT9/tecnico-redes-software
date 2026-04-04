# Modelado de Datos y Sistemas de Gestión (SGBD)

## I. Modelo Entidad-Relación (MER)
Es la forma más común de diseñar bases de datos a nivel conceptual antes de pasar a tablas reales.

### 1. Componentes Principales
* **Entidades (Rectángulos):** Objetos de los que guardamos datos.
    * *Concretas:* Físicas (AUTO, PROFESOR).
    * *Abstractas:* Conceptuales (CURSO, POSICIÓN_TRABAJO).
* **Atributos (Óvalos):** Características de la entidad (ej. Color, Nombre).
* **Relaciones (Rombos):** Acción que une a las entidades (ej. PROFESOR *dicta* CURSO).

### 2. Las Claves (Fundamentales)
* **PK (Primary Key):** Atributo único e irrepetible (ej. Cédula). Se representa subrayado.
* **FK (Foreign Key):** Una PK que "viaja" a otra tabla para crear un vínculo.

### 3. Cardinalidad
Define cómo se relacionan numéricamente las entidades:
* **1:1 (Uno a uno):** Un profesor tiene un solo escritorio.
* **1:N (Uno a muchos):** Un profesor dicta muchos cursos.
* **N:N (Muchos a muchos):** Muchos alumnos se inscriben en muchos cursos.

### 4. Entidades Fuertes y Débiles
* **Entidad Fuerte:** Existe por sí sola (CLIENTE).
* **Entidad Débil:** Depende de otra para existir (TICKET depende de VENTA).

