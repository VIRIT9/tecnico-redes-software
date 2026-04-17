# Semana 1: Fundamentos de STEAM

## 1. Comparativa de Placas
| Característica | Arduino | Micro:bit |
| :--- | :--- | :--- |
| **Enfoque** | Hardware abierto, prototipado manual. | Educativo, todo-en-uno. |
| **Componentes** | Requiere módulos y circuitos externos. | Sensores integrados (luz, temp, acelerómetro). |
| **Uso ideal** | Proyectos complejos y personalizados. | Aprendizaje rápido y robótica básica. |

---

## 2. Magnitudes Eléctricas Fundamentales
La electricidad es el movimiento de electrones a través de un conductor (como el cobre de los cables).

* **Voltaje ($V$):** La "presión" que empuja los electrones. Unidad: **Voltios (V)**.
* **Intensidad ($I$):** El flujo o cantidad de electrones. Unidad: **Amperios (A)**.
* **Resistencia ($R$):** La oposición al flujo. Unidad: **Ohmios ($\Omega$)**.



---
### 📝 Glosario de Unidades
* **A (Amperios):** Unidad base de la Intensidad ($I$). Es una cantidad grande de corriente.
* **mA (Miliamperios):** La milésima parte de un Amperio ($1/1000$). Es lo que suelen consumir los LEDs y componentes pequeños de Arduino.

---

## 3. Leyes de Ohm y Watt

### Ley de Ohm
Es la base de toda la electrónica. Relaciona $V$, $I$ y $R$.
* $V = I \times R$
* $I = V / R$
* $R = V / I$

### Ley de Watt (Potencia)
Mide la energía transformada en calor o trabajo por unidad de tiempo.
* $P = V \times I$
* **Unidad:** Watts (W).
* *Nota:* Si no conocemos el Voltaje, usamos $P = I^2 \times R$.

---

## 4. Análisis de Circuitos

### Circuito en Serie
Los componentes forman un único camino para la corriente.
* **Corriente ($I$):** Es la misma en todo el circuito.
* **Voltaje ($V$):** Se reparte entre las resistencias.
* **$R_{total}$:** Suma directa ($R_1 + R_2$).

### Circuito en Paralelo
La corriente se divide en diferentes ramas (nodos).
* **Corriente ($I$):** Se divide según la resistencia de cada rama.
* **Voltaje ($V$):** Es igual en todas las ramas.
* **$R_{total}$ (para 2 R):** $(R_1 \times R_2) / (R_1 + R_2)$.



---

## 5. Conversión de Unidades
* **$A \rightarrow mA$:** Multiplicar por $1000$.
* **$mA \rightarrow A$:** Dividir por $1000$. 

A (Amperios)
mA (miliamperios)

> 💡 **Concepto Clave:** Un **Cortocircuito** ocurre cuando $R$ tiende a $0$, provocando que la Intensidad suba peligrosamente, generando calor extremo (Efecto Joule).