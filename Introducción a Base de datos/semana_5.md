# Modelo Entidad-Relación (Cardinalidad)

## 1. Cardinalidad
La cardinalidad describe la relación numérica entre las entidades. Se determina analizando los límites mínimos y máximos en ambos sentidos de la relación.

### Conceptos Clave
* **Mínimo:** El número menor de instancias (0 o 1). Indica si la participación es opcional u obligatoria.
* **Máximo:** El número mayor de instancias (1 o N). Define el tipo de relación.
* **Lectura:** Siempre se lee de izquierda a derecha y de derecha a izquierda para definir el diseño final.

### Tipos de Relaciones
| Relación | Notación | Descripción | Ejemplo |
| :--- | :--- | :--- | :--- |
| **Uno a Uno** | `(1:1)` | Cada registro de A se relaciona con solo uno de B. | `COMPRA` - `TICKET` |
| **Opcional** | `(0:1)` | Una entidad puede existir sin estar relacionada. | `JUGADOR` - `CLUB` (Un jugador libre) |
| **Uno a Muchos** | `(1:N)` | Un registro en A puede tener múltiples en B. | `COCINA` - `PLATOS` |
| **Muchos a Muchos**| `(N:M)` | Múltiples registros de A con múltiples de B. | `ALUMNOS` - `PROFESOR` |

---

## 2. Implementación Lógica y Tablas Intermedias
En el paso del diagrama al modelo relacional (tablas), existen reglas específicas:

### Resolución de Relaciones N:M
Las bases de datos relacionales no soportan relaciones "Muchos a Muchos" directamente. Para resolverlas se crea una **Entidad Intermedia** (o Tabla de Rompimiento).
* **Composición:** Esta tabla contiene las llaves primarias (**PK**) de ambas entidades.
* **PK Compuesta:** La combinación de ambas llaves suele formar la PK de la nueva tabla.
* **Atributos propios:** La relación puede tener atributos (ej. en la relación `Alumnos-Profesor`, la tabla intermedia podría tener el atributo `fecha_inscripcion`).



---

## 3. Jerarquía de Entidades

### Entidades Fuertes
Son aquellas que tienen existencia propia y no dependen de otra para ser identificadas.
* **Representación:** Rectángulo de línea simple.
* **Ejemplo:** `VENTA`.

### Entidades Débiles
Su existencia depende de una entidad fuerte. Si se elimina la fuerte, la débil pierde sentido.
* **Representación:** Rectángulo de doble línea.
* **Claves:** Dependen de la clave de la entidad fuerte para completar su identidad (Clave Compuesta).
* **Ejemplo:** `FACTURA`. No tiene sentido una factura que no esté asociada a una `VENTA` específica.

---

## 4. Atributos Especiales

* **PK (Primary Key):** Identificador único (ej. `ID_ALUMNO`). Se subraya en los diagramas.
* **FK (Foreign Key):** Clave que referencia a la PK de otra tabla para crear el vínculo.
* **Atributo Derivado:** Valor que no se almacena, sino que se calcula (ej. `Total_Venta` calculado a partir de `Precio * Cantidad`). Se representa con un óvalo de línea punteada.

---

## 5. Herramientas y Entorno
Para implementar estos modelos de datos de forma práctica:
* **XAMPP:** Entorno que permite gestionar bases de datos MariaDB/MySQL mediante **phpMyAdmin**.
* **Diagramas:** Se pueden usar herramientas como Lucidchart, Draw.io o MySQL Workbench para diseñar el DER antes de programar.