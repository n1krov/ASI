
# Tipos de parámetros: Cuantitativos y Cualitativos.
![[Pasted image 20251116204458.png]]
## **Explicación de los Conceptos**

Cuando necesitas elegir un nuevo software (SW) o hardware (HW), no puedes simplemente decir "quiero el mejor". Tienes que definir una lista de criterios medibles para comparar las distintas opciones de forma objetiva. Estos criterios se dividen en dos grandes grupos: cuantitativos y cualitativos.

### **Parámetros Cuantitativos (Los Números)**

Piensa en ellos como **todo aquello que se puede medir con un número y una unidad de forma objetiva**. Son las especificaciones técnicas duras.

*   **Definición sencilla:** Son las métricas de capacidad, cantidad o velocidad de un componente de hardware o software.
*   **¿Cómo se obtienen?** Surgen de mediciones directas o proyecciones basadas en fórmulas matemáticas. No admiten opinión: un disco de 2 Terabytes es objetivamente más grande que uno de 1 Terabyte.
*   **Pregunta que responden:** ¿Cuánto? ¿Qué tan rápido? ¿Qué capacidad?
*   **Ejemplos del texto:**
    *   **tps (transacciones por segundo):** ¿Cuántas operaciones puede procesar la base de datos por segundo?
    *   **Tasa de transferencia:** ¿A qué velocidad (en Megabytes por segundo) puede leer o escribir datos el disco duro?
    *   **Capacidad de almacenamiento:** ¿Cuántos Terabytes de información puede guardar?
*   **Otros ejemplos claros:**
    *   **Memoria RAM:** 64 GB.
    *   **Velocidad del procesador:** 3.5 GHz.
    *   **Latencia de la red:** Menos de 10 milisegundos.
    *   **Número de usuarios simultáneos:** Capaz de soportar 500 usuarios conectados.

### **Parámetros Cualitativos (Las Cualidades)**

Piensa en ellos como **los atributos o características que no se pueden medir con un número de forma natural**. Dependen de la experiencia, la observación y las políticas de la empresa. Son subjetivos.

*   **Definición sencilla:** Son las cualidades "blandas" que determinan si un equipo es el adecuado para la organización, más allá de sus especificaciones técnicas.
*   **¿Cómo se tratan?** Como son subjetivos, el apunte menciona dos formas de manejarlos:
    1.  **Transformarlos en cuantitativos:** Se les asigna un puntaje en una escala (por ejemplo, del 1 al 5) para poder compararlos.
    2.  **Controlar su peso:** Asegurarse de que no representen más del 20% del total de la decisión para que la elección siga siendo mayormente objetiva.
*   **Pregunta que responden:** ¿Qué tal es? ¿Es compatible? ¿Es fácil de usar? ¿Es confiable?
*   **Ejemplos del texto:**
    *   **Tecnología de disco:** No se refiere a la capacidad (eso es cuantitativo), sino al *tipo* de tecnología. Por ejemplo: ¿Usamos discos HDD (tecnología más antigua y probada) o SSD NVMe (más nueva pero quizás menos probada en nuestro entorno)? La elección depende de la política de riesgo de la empresa.
    *   **Dimensiones de pantalla:** ¿El monitor de 27 pulgadas cabe físicamente en los escritorios de los empleados? ¿Su diseño es ergonómico?
    *   **Estética:** ¿El diseño de las laptops se alinea con la imagen profesional que queremos proyectar?
*   **Otros ejemplos claros:**
    *   **Facilidad de uso del software:** ¿Qué tan intuitiva es la interfaz para un usuario nuevo?
    *   **Calidad del soporte técnico del proveedor:** ¿Responden rápido? ¿Son eficientes?
    *   **Reputación de la marca:** ¿Es un fabricante conocido por su fiabilidad o por sus fallos?
    *   **Compatibilidad con sistemas existentes:** ¿El nuevo software se integra bien con nuestro sistema de facturación actual?

---

## **Analogía: Comprar un Auto para una Familia**

Imagina que estás eligiendo un auto nuevo. Tu proceso de decisión usaría ambos tipos de parámetros:

| Parámetros Cuantitativos (del folleto) | Parámetros Cualitativos (de tu juicio) |
| :--- | :--- |
| **Potencia del motor:** 150 caballos de fuerza. | **Comodidad de los asientos:** ¿Son cómodos para viajes largos? |
| **Consumo de combustible:** 5 litros cada 100 km. | **Seguridad percibida:** ¿La marca tiene buena reputación en seguridad? |
| **Capacidad del baúl:** 500 litros. | **Diseño y Estética:** ¿Te gusta cómo se ve el auto? |
| **Número de asientos:** 5. | **Facilidad de manejo:** ¿Es ágil para estacionar en la ciudad? |

---

## **Ejemplo Práctico en la Selección de un Servidor (Tu Escenario)**

Supongamos que Afianzadora necesita comprar un nuevo servidor.

1.  **Definición de Criterios Obligatorios:**
    *   **Parámetros Cuantitativos:**
        *   Debe tener al menos 128 GB de RAM.
        *   Debe tener 4 TB de almacenamiento en discos SSD.
        *   Debe tener una tarjeta de red de 10 Gbps.
    *   **Parámetros Cualitativos:**
        *   Debe ser compatible con VMware vSphere 5 (como en el caso).
        *   El proveedor debe ofrecer soporte técnico 24/7 en español.

2.  **Ponderación y Calificación (Transformando lo cualitativo):**
    Ahora comparas dos proveedores, A y B, que cumplen todos los requisitos cuantitativos. Para decidir, calificas los cualitativos en una escala de 1 a 10.

| Criterio Cualitativo | Proveedor A | Proveedor B |
| :--- | :--- | :--- |
| Calidad del soporte técnico | 9 (muy buena reputación) | 6 (reputación regular) |
| Calidad de la documentación | 8 (muy clara) | 5 (confusa y en inglés) |
| Reputación de la marca | 10 (líder del mercado) | 7 (marca secundaria) |
| **Total Cualitativo** | **27** | **18** |

**Decisión:** Aunque ambos servidores tenían la misma "potencia" (parámetros cuantitativos), eliges el del **Proveedor A** porque sus parámetros cualitativos, una vez ponderados, demuestran que se adapta mejor a las necesidades y políticas de la organización.