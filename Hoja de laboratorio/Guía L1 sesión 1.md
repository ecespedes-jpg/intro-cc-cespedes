
## 1. Momento 1 - Predecir 
---
>[!question] Pregunta 1
>Les llega una cadena de 1 679 ceros y unos, sin nada más. ¿Qué es lo primero que intentarían para encontrarle sentido? Escriban tres ideas, en orden.

**Respuesta:** 
1. Contar cuantos ceros y unos hay para ver que tan larga es la cadena. 
2. Intentaría agrupar la misma cantidad de números es decir (cadenas de 8 en 8), después empezaría a hacer sumas entre esos grupos y así asignar una letra de abecedarios para ver si hay algún mensaje coherente oculto. 
3. Diseñaría cuadriculas y asignando un color a cada número por ejemplo, 1 blanco y 0 negro para descubrir algún dibujo. 
>[!question] Conocer el dato
>Antes de calcular nada, se mira. Un dato que no se miró antes de usarlo es un dato en el que se confió sin razón. Contesten **con código**: 
>- ¿Cuántos caracteres tiene `bits`? (`len`)
>- ¿Qué caracteres **distintos** aparecen? (`set`)
>-  ¿Cuántos unos y cuántos ceros hay? (`.count`)
>- Miren los primeros 60 caracteres. ¿Ven algún patrón a simple vista?
>
>

**Respuesta:** En primer lugar, la cantidad de unos es mucho menor que los ceros; además los unos siguen un patrón cada tantos ceros como si delimitaran algo, mientras que los ceros tienen bloques de separaciones con cantidades similares. 

```python
n_caracteres = len(bits)        
distintos = set(bits)          
n_unos = bits.count("1")          
n_ceros = bits.count("0")          

print("caracteres:", n_caracteres)
print("distintos :", distintos)
print("unos/ceros:", n_unos, n_ceros)
print(bits[:60])
```

>[!question] Pregunta 2
>*¿Cuál es la diferencia entre el carácter `'1'` y el bit 1? Dos líneas.*

**Respuesta:** El carácter '1' es un símbolo de texto y el disco un carácter ocupa 8 bits, mientras que el bit 1 es una unidad binaria de información (0 o 1)  y ocupa 1 bit de memoria. 

>[!question] Pregunta 3
 ¿Por qué quien diseñó el mensaje eligió un número que es producto de **dos primos**? ¿Qué habría pasado si el mensaje tuviera 1 680 bits, que se pueden acomodar de 40 maneras?


**Respuesta**: Se eligió un número que es producto de dos primos (1679 = 23 × 73), para que quien reciba el mensaje pueda descubrir cómo acomodarlo sin necesidad de instrucciones previas. Como 1679 solo tiene cuatro divisores 1, 23, 73 y 1679, si descartamos poner todos los bits en una sola línea (1 × 1679 o 1679 × 1), únicamente quedan dos rectángulos posibles para probar: 73 × 23 o 23 × 73. Al armarlos, uno se ve como puro ruido y el otro muestra de inmediato el dibujo ordenado, lo que elimina casi por completo la duda sobre cómo leerlo.

Si el mensaje hubiera tenido 1680 bits, existirían 40 formas distintas de armar un rectángulo, 38 cuadrículas diferentes si quitamos las de una sola fila o columna; con tantas opciones posibles habría demasiada ambigüedad: encontrar el ancho correcto sería mucho más difícil y quien lo reciba podría confundirse entre decenas de combinaciones sin sentido, o ni siquiera notar que los bits esconden una imagen.

>[!question] Pregunta 4
**Lo que leyeron:** Punto 5 leer y descifrar 

- Primera sección (filas 0 a 1): los números 1, 2, 3, 4, 5, 6, 7, 8, 9, 10. Dirección de lectura: De arriba hacia abajo, porque es la única dirección en la que aparece la secuencia ordenada del 1 al 10.
- Segunda sección (filas 5 a 8): los números 1, 6, 7, 8, 15, que corresponden a hidrógeno (H), carbono (C), nitrógeno (N), oxígeno (O) y fósforo (P). ¿De qué molécula de la vida son esos elementos? **Respuesta**: Del ADN

>[!question] Momento 3 
>Confrontación
- **En P1:** Predije que lo primero sería contar cuántos ceros y unos había para saber qué tan larga era la cadena. Esto sí coincidió con el trabajo del cuaderno, porque en el primer punto fue justo lo que hicimos para revisar el dato, y saber que el largo total era de 1679 bits fue la pista clave para poder encontrar las medidas del rectángulo.
- **En P2:** Pensé en agrupar los bits de 8 en 8, hacer sumas y asignar letras del abecedario para buscar un mensaje escrito. Al avanzar vi que esto no funcionaba: primero porque 1679 ni siquiera se puede dividir exacto entre 8, y segundo porque el mensaje no usa ningún alfabeto ni idioma, sino números en binario y dibujos.
- **En P3:** Propuse armar cuadrículas y darle un color al 1 y otro al 0 para descubrir un dibujo. En esto sí acerté bastante, porque el mensaje realmente se descifra acomodándolo en una cuadrícula de 73 x 23 donde los bits funcionan como píxeles (aunque se dijo 1 blanco y 0 negro, y en el cuaderno se pinta el 1 y se deja el 0 vacío, la diferencia de color igual deja ver las figuras). Lo que no imaginé era que dentro del mismo dibujo iban a meter números binarios escritos en vertical.
- **¿A qué atribuimos la diferencia?** A que al inicio estaba pensando desde la costumbre de cómo un computador guarda texto (en bloques de 8 bits para formar letras), sin tener en cuenta que un extraterrestre no conoce nuestro abecedario ni nuestras reglas de programación. Quienes diseñaron el mensaje evitaron cualquier idioma y se basaron únicamente en matemáticas básicas, como los divisores de 1679 y el sistema binario, e imágenes.
-  **La frase obligatoria**: Representar es transformar una idea, un objeto o una información en un conjunto de símbolos y reglas, como ceros y unos ordenados en una cuadrícula, para poder guardarla o transmitirla, sabiendo que quien la reciba necesita conocer o descubrir esas mismas convenciones para volver a entender qué significa.

>[!question] Pregunta 5
>1. ¿Qué parte del mensaje habrían podido descifrar sin saber química? ¿Y sin saber que en 1974 Plutón contaba como planeta? Agreguen esas convenciones a su lista.

**Respuesta**:

- Sin saber química: Igual habría podido descifrar toda la parte matemática y los dibujos principales. Es decir, los números del 1 al 10 del inicio, el dibujo de la doble hélice, la silueta del humano con su estatura y población, el Sistema Solar y el radiotelescopio. De la parte química igual habríamos sacado los números 1, 6, 7, 8 y 15 y los valores dentro de los bloques de los nucleótidos, pero sin tabla periódica ni química solo los veríamos como listas de números ordenados sin saber que son átomos ni fórmulas del ADN.
- Sin saber que en 1974 Plutón contaba como planeta: No habría cambiado mucho la interpretación general. Igual se entiende que el bloque grande de la izquierda es una estrella (el Sol) y que a su derecha hay 9 cuerpos orbitando, donde el tercero está levantado justo debajo del humano para indicar que ese es nuestro planeta. Simplemente contaríamos 9 objetos en el sistema sin preocuparnos por si el último hoy se llama planeta enano o planeta.

>[!question] Pregunta 6
>2. La cabeza del humano es **un solo bit**, y la barra del ADN termina justo en ella. ¿Es casualidad o es un mensaje? ¿Cómo lo sabrían?

- Es completamente intencional, no es casualidad. En una cuadrícula tan estrecha, de apenas 23 columnas, cada píxel está puesto a propósito. Que la barra central de la doble hélice baje justo por el eje del dibujo y toque exactamente el único bit que forma la cabeza del humano es una forma visual de conectar nuestro código genético con nuestra especie y nuestra inteligencia.

- ¿Cómo lo sabríamos? Primero, por la simetría, el humano está centrado justo debajo de las columnas 10 y 11 por donde baja esa barra, algo demasiado exacto para pasar por accidente. Segundo, al traducir el número binario de esa barra central, que representa los miles de millones de nucleótidos del genoma humano, , vemos que es un dato biológico que sirve de puente entre las moléculas de arriba y la persona de abajo.

>[!question] Pregunta 7
>Si ustedes hubieran diseñado el mensaje, ¿qué habrían cambiado para que fuera más fácil de leer?

**Respuesta**:

- Poner un marco o marcas en las esquinas: Agregaría un borde o puntos guía en las cuatro esquinas del rectángulo de 73×23 para que quien lo reciba sepa de inmediato dónde empieza y termina la imagen sin tener que adivinar si los bordes vacíos son fondo o relleno.
- Dejar filas en blanco entre secciones: Separaría cada bloque con al menos una fila completa de ceros para que los dibujos no se peguen entre sí (por ejemplo, que la hélice no quede pegada a la cabeza del humano ni los pies queden tan encima del Sistema Solar).
- Escribir todos los números con la misma regla: En el mensaje original los números del 1 al 7 usan una columna, pero el 8, 9 y 10 usan dos columnas, y más abajo el diámetro del telescopio está escrito en horizontal en vez de vertical. Usaría siempre la misma orientación y el mismo ancho fijo de bits para todos los números, así con una sola regla de lectura se descifra todo el mensaje.
