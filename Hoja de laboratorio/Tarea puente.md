>[!question] Pregunta 1
>_Cinco líneas: ¿por qué comparar dos huellas de 64 caracteres es una manera confiable de saber que dos archivos de 1 679 caracteres son idénticos? ¿Qué tendría que pasar para que dos mensajes distintos tuvieran la misma huella?_

**Respuesta**: Esta huella de 64 caracteres funciona como una firma única del archivo: si dos textos son exactamente iguales, siempre van a generar el mismo código. Además, si llegara a cambiar aunque sea un solo cero o un uno entre los 1679 caracteres originales, la huella cambiaría por completo, haciendo que cualquier diferencia mínima se note de inmediato. Para que dos mensajes distintos tuvieran la misma huella tendría que ocurrir una coincidencia enorme en la que el cálculo mezcle datos diferentes y termine dando exactamente el mismo resultado. Como existen muchísimas combinaciones posibles para armar esa clave de 64 caracteres, es prácticamente imposible que dos archivos diferentes coincidan por accidente. Por eso, si ambas huellas son iguales, podemos estar tranquilos de que los dos archivos son idénticos carácter por carácter.

>[!question] Tabla de seguimiento
>**Tabla de seguimiento** de `a_base_rec(1974, 6)`: una fila por llamada, con `n`, `n // 6`, `n % 6` y lo que devuelve. Dibujen la pila: ¿qué queda esperando en cada llamada? 

| llamada | n | n // 6 | n % 6 | devuelve |
| :--- | :--- | :--- | :--- | :--- |
| 1 | 1974 | 329 | 0 | `[1, 3, 0, 5, 0]` |
| 2 | 329 | 54 | 5 | `[1, 3, 0, 5]` |
| 3 | 54 | 9 | 0 | `[1, 3, 0]` |
| 4 | 9 | 1 | 3 | `[1, 3]` |
| 5 (caso base) | 1 | 0 | 1 | `[1]` |

**Pila de llamadas (qué queda esperando en cada una):**
[Llamada 1] a_base_rec(1974, 6) -> espera resultado + [0]  ==> devuelve [1, 3, 0, 5] + [0] = [1, 3, 0, 5, 0]
  └─ [Llamada 2] a_base_rec(329, 6) -> espera resultado + [5]  ==> devuelve [1, 3, 0] + [5] = [1, 3, 0, 5]
       └─ [Llamada 3] a_base_rec(54, 6) -> espera resultado + [0]  ==> devuelve [1, 3] + [0] = [1, 3, 0]
            └─ [Llamada 4] a_base_rec(9, 6) -> espera resultado + [3]  ==> devuelve [1] + [3] = [1, 3]
                 └─ [Llamada 5] a_base_rec(1, 6) -> CASO BASE (1 < 6) ==> devuelve [1]

>[!question] Contrato de lectura

1. Contar el total de ceros y unos del mensaje (437) y factorizarlo en dos números primos para descubrir que la imagen es un rectángulo de 19 columnas por 23 filas.
2. Observar la primera franja superior y notar una secuencia que aumenta de uno en uno hasta agotar sus símbolos en el `5` y pasar al `10`, deduciendo que el sistema numérico es base 6.
3. Aplicar la base 6 para leer las cantidades que acompañan cada dibujo en las secciones siguientes.
4. Interpretar la silueta central junto con los números `2`, `5` y `32` como nuestra anatomía (extremidades y total de dedos), y el dibujo de las montañas con las cifras `13542` y `40345` como la altitud de nuestra ciudad (Manizales) y su volcán vecino.
5. Identificar el dibujo final como una taza de café humeante (símbolo de nuestra cultura cafetera), junto con el número de estudiantes del salón (41 en base 6) y la cantidad de integrantes de nuestro grupo (1).