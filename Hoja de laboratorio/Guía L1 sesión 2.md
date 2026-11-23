## 1. Momento 1 - Predecir 
---
>[!question] Pregunta 1
>¿Qué fracción de su mensaje creen que la otra especie va a entender? Escriban un número entre 0 y 1 y expliquen qué sección creen que se va a perder primero. 

**Respuesta:** 0.75 (3 de las 4 secciones). La sección que creo que se va a perder primero es la cuarta, la taza de café humeante y los datos del curso, porque mientras el conteo en base 6, la silueta humana y las montañas tienen referentes físicos o matemáticos universales, una taza de café es un objeto cultural propio de nuestra especie y sin instrucciones es casi imposible que otra civilización deduzca qué significa. 

>[!question] Pregunta 2
>Si el canal daña 1 de cada 100 bits, ¿cuántos bits dañados esperan en su mensaje? ¿Y si lo mandan tres veces?


**Respuesta:** Como el mensaje tiene 437 bits (19 x 23) y el canal daña 1 de cada 100 bits (p = 0.01), esperamos 437 * 0.01 = 4.37 bits dañados en un envío (aproximadamente 4 o 5 bits). Si lo mandamos tres veces, 1311 bits en total, esperamos 1311 * 0.01 = 13.11 bits dañados en el camino, unos 13 bits repartidos entre las tres copias, pero al comparar las tres copias por mayoría se espera recuperar el mensaje con 0 errores.

>[!question] Preguntas punto 3
>1. **Ancho fijo.** Si cada número va en un renglón de `COLUMNAS` bits, ¿cuál es el número más grande que cabe en su base? ¿Qué pasa si quieren decir cuántos habitantes tiene Manizales? A esto se le llama **desbordamiento**.
>2. **Decimales.** ¿Cómo dicen la altura de Manizales en metros si el otro no sabe qué es un metro, ni dónde va la coma? _(Pista real: en 1972, las placas de las sondas Pioneer usaron una propiedad del átomo de hidrógeno como regla para medir, porque el hidrógeno es igual en todo el universo.)_
>3. **Texto.** ¿Por qué no pueden mandar la palabra "Manizales" en ASCII o en Unicode? ¿Qué **sí** pueden mandar?
>4. **Forma.** ¿Cómo va a saber la otra especie cuántas columnas tiene su mensaje?

**Respuesta**: 
1. Ancho fijo: Como cada renglón mide 19 bits y cada dígito en base 6 ocupa 3 bits, en un solo renglón caben máximo 19//3=6 dígitos. El número más grande que podemos escribir ahí es 66−1=46655. Si quisiéramos mandar los habitantes de Manizales (unos 450000), ocurriría un desbordamiento, porque en base 6 ese número es 13351200 (8 dígitos = 24 bits) y no cabe en una sola fila. Por eso en nuestro mensaje usamos números más pequeños que sí cupieran, como las altitudes (2150 y 5321) y la cantidad de estudiantes que es 25.
2. Decimales: No podemos mandar la coma decimal ni asumir que la otra especie conoce el metro, porque el metro es una medida humana arbitraria. Como solución, usamos únicamente números enteros y dibujé una referencia física visual, la montaña junto a la silueta, para dar contexto de escala; si quisiéra dar medidas exactas en el espacio, tendríamos que expresarlas como múltiplos enteros de una constante física universal, como la longitud de onda del hidrógeno que usaron las sondas Pioneer.
3. Texto: No podemos mandar "Manizales" en ASCII o Unicode porque esas tablas son acuerdos exclusivos de los computadores humanos: un receptor extraterrestre no conoce nuestro alfabeto, nuestro idioma ni qué número le asignamos a cada letra. Lo que sí podemos mandar son números naturales (mediante conteo), relaciones matemáticas y dibujos en cuadrícula de cosas físicas (nuestro cuerpo, las montañas, la taza de café).
4. Forma: La otra especie sabrá que el mensaje tiene 19 columnas porque la longitud total es 437 bits, que es un número semiprimo (19×23). Al buscar sus divisores, solo existen dos cuadrículas posibles (19×23 o 23×19, sin contar una sola línea): al probar ambas, una se ve como puro ruido desordenado y la de 19 columnas revela de inmediato el conteo ordenado y los dibujos.

>[!question] Pregunta 4
>**¿Cuál de las dos protecciones elegirían para un mensaje que tarda 25 000 años en llegar, y por qué?** Con sus números. Piensen en la diferencia entre **detectar** un error y **corregirlo**.

**Respuesta:** Elegiría la protección por repetición (repetir3 + votar). La diferencia clave está entre detectar un error y corregirlo: con paridad el costo es muy bajo (460 bits frente a los 437 originales) y detecta casi todos los fallos (979 de 983 envíos con error, con solo 4 sin detectar), pero no permite reparar los bits dañados. En un mensaje que tarda 25 000 años en llegar, el receptor no puede pedir retransmisión (esperar una respuesta tomaría 50 000 años).

En cambio, aunque la repetición triplica el costo a 1311 bits, le da al receptor la capacidad de corregir los errores por mayoría en el destino, recuperando el mensaje completamente intacto en 887 de 1000 envíos (88.7 %), frente a apenas 17 envíos intactos (1.7 %) si no se corrige nada. Cuando solo hay una oportunidad de comunicarse a esa distancia, el costo en bits se justifica por completo.

>[!question] Pregunta 5
>**Lo que entendimos del mensaje de la especie Glitx Synkai :**

**Respuesta**: 
- **Ancho que se dedujo:** `47` columnas, porque al quitar la protección de repetición por 3 (`7473 / 3 = 2491` bits), `2491` es un semiprimo que solo se puede acomodar en `47 x 53` o `53 x 47`. Al dibujarlo con `47` columnas todas las figuras y números quedan bien alineados, mientras que con `53` se ve todo cortado en diagonal.
- **Base que se dedujo:** `8`, porque en las primeras 10 filas aparece el conteo escrito de a 3 bits por dígito: del `1` al `7` (`001` hasta `111`) ocupan un solo dígito, y justo en la octava fila aparece `[1, 0]` (`001 000`), lo que demuestra que su base es 8 (y siguen con `11` y `12`, que son 9 y 10).
- **Protección que creo que usaron:** Repetición por 3 (`repetir3`), porque la longitud del archivo (`7473`) es exactamente el triple de `2491` y los bits vienen agrupados en tríos iguales, con algunos errores aislados que `votar()` corrige sin problema.
- **Lo que dice cada sección:**
    1. **Filas 0 a 9 (Conteo):** Los números del 1 al 10 escritos en base 8 (`1, 2, 3, 4, 5, 6, 7, 10, 11, 12`), usando 3 bits por cada dígito de izquierda a derecha.
    2. **Filas 11 a 31 (Código QR):** Un código QR de `21 x 21` píxeles con sus tres cuadros guía en las esquinas, pensado para escanearlo y acceder a información externa.
    3. **Filas 33 a 41 (Mirar / dirección):** Un rectángulo o pantalla a la izquierda, un par de ojos mirando hacia la derecha y una flecha apuntando hacia la derecha.
    4. **Filas 44 a 52 (Observador):** Otro par de ojos mirando hacia la izquierda, un cuadro en el centro y la silueta de una persona a la derecha representando a su especie.

>[!question] Momento 3
>1. **Confronten P4** con lo que de verdad se entendió de su mensaje. ¿Por qué la diferencia?
>2. **La convención escondida:** ¿qué supusieron **sin darse cuenta** que la otra especie no tenía?
>3. **Paridad contra repetición:** cuál eligieron y por qué, con las mediciones de la sección 4.
>4. Una frase que empiece por *"Representar es..."*. Compárenla con la de la sesión 1: ¿cambió?

**Respuestas:** 
1. En P4 había predicho **0.75** (3 de las 4 secciones): esperába que la otra especie entendiera el conteo en base 6, la silueta humana y las montañas por tener referentes matemáticos o físicos universales, mientras que la cuarta sección (la taza de café humeante y los datos del curso) se perdería primero por ser un objeto cultural propio sin instrucciones previas. Al revisarlo frente a cómo funciona realmente el mensaje, la estructura matemática sí permite descifrar la base y la forma: al quitar la repetición por 3 de los `1311` bits enviados, queda el número semiprimo `437` (`19 × 23`), lo que deja encontrar el ancho de `19` columnas y deducir la base 6 viendo dónde el conteo pasa del `5` al `10`. Sin embargo, mientras las figuras más directas, como la silueta humana o las montañas, se pueden asociar visualmente, la taza de café y las cifras sueltas que acompañan cada sección resultan muy difíciles de interpretar sin contexto. La diferencia entre lo que esperamos y lo que ocurre al leerlo sin instrucciones se debe a que nosotros dibujamos sabiendo de antemano qué queríamos representar, pero en una cuadrícula de `19` columnas de ancho unos pocos píxeles encendidos no alcanzan para explicar un objeto cultural ni qué estamos midiendo con cada número. 
2. Sin darnos cuenta, asumimos varias reglas que no estaban escritas dentro del mensaje para la otra especie:
- **El ancho fijo por dígito (`ANCHO = 3`) y los ceros de relleno:** Dí por sentado que al ver los primeros renglones iban a agrupar cada fila en bloques de `3` bits para leer cada dígito en base 6 por separado, en vez de leer toda la fila de `19` bits como un solo número binario gigante, y que iban a ignorar los ceros de relleno que `renglon()` agrega a la derecha.
- **El sentido de lectura:** Asumí que iban a leer la cuadrícula de arriba hacia abajo y de izquierda a derecha, empezando por el conteo en las primeras filas.
- **Las unidades y el contexto cultural:** Supuse que los números debajo de las montañas (`13542` y `40345` en base 6, que son `2150` y `5321`) se entenderían como altitudes en metros y no como otra cantidad, que un bloque con líneas onduladas arriba representa una taza de café caliente, y que los números finales (`41` y `1` en base 6, equivalentes a `25` y `1`) correspondían a los estudiantes del salón y a los integrantes del equipo.
1. Elegí **repetición** (`PROTECCION = "repeticion"`), enviando `1311` bits en total frente a los `437` bits originales. En las `1000` simulaciones de la sección 4 con probabilidad de error `p = 0.01` obtuvimos lo siguiente:
 - **Paridad** (`460` bits, un costo de solo `23` bits extra) presentó errores en `983` de los `1000` envíos; `filas_danadas` detectó `979` y dejó pasar `4` sin detectar (lo cual ocurre cuando se voltean dos bits en un mismo renglón, manteniendo par la cantidad de unos). Además, aunque detecte la fila dañada, no permite saber qué bit exacto cambió.
- **Repetición** (`1311` bits, el triple del tamaño original) permitió que `votar` recuperara el mensaje **exacto** en `887` de `1000` transmisiones (`88.7%`).
- Para un mensaje que tarda 25 000 años en llegar, detectar un error sin poder arreglarlo no sirve de nada porque es imposible pedir que lo reenvíen; por eso se justifica gastar el triple de bits para que el receptor corrija los daños por mayoría al llegar.
4. **Frase:** Representar es traducir ideas, cantidades y objetos de nuestro entorno a símbolos y reglas matemáticas dentro de una estructura compartida, sabiendo que todo lo que demos por obvio y no quede explícito en el mensaje (como nuestras unidades o cultura) se puede perder o malinterpretar al otro lado.
 - **¿Cambió respecto a la sesión 1?** En la sesión 1 había escrito que representar era _"transformar una idea, un objeto o una información en un conjunto de símbolos y reglas, como ceros y unos ordenados en una cuadrícula, para poder guardarla o transmitirla, sabiendo que quien la reciba necesita conocer o descubrir esas mismas convenciones para volver a entender qué significa"_. La base de la definición se mantiene, pero cambió el enfoque: en la sesión 1 lo pensé desde quien _recibe_ y descifra un mensaje ya terminado, mientras que en la sesión 2, al diseñar nuestro propio mensaje en base 6 y probarlo en un canal con ruido, entendimos que representar también implica evitar convenciones ocultas y añadir redundancia para que la información sobreviva al viaje.
