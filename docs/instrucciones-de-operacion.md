# Instrucciones de operación

Las instrucciones de operación le permite realizar distintas acciones, estas dentro de las siguientes categorías.

## Set

Set le permite al procesador declarar una variable y asignarle un valor.

[[posible-escritura-en-editor-manual]]

## Operation

Operation le permite al procesador realizar operaciones matemáticas y guardar su resultado,dichas operaciones van desde las básicas como la suma, hasta otras como las operaciones trigonométricas. Esta es la lista completa de operadores, además puedes observarlos presionando el botón de operación en la instrucción.

mas menos multiplicación división-fraccionaria división-entera modulo potencia operador-igual operador-not operador-and operador-menor operador-menor-igual operador-mayor operador-mayor-igual bitshift-izquierda bitshift-derecha operador-or operador-b-and operador-xor operador-flip maximo minimo angulo diferencia-de-angulo longitud ruido absoluto logaritmo logaritmo-base-10 redondeo-menor redondeo-mayor raiz random seno coseno tangente arcoseno arcocoseno arcotangente

## Lookup

Lookup le permite al procesador obtener el tipo de dato de un item/líquido/unidad/bloque haciendo uso de un indice. Para obtener el numero total de estos tipos puedes hacer uso de `@blockCount` para bloques, `@unitCount` para unidades, `@itemCount` para items y `@liquidCount` para líquidos. Estos valores pueden usarse en conjunto con instrucciones jump para crear un bucle y revisar cada uno de estos.

## Pack Color

Pack Color le permite al procesador empaquetar los componentes de un color **R**ed **G**reen **B**lue **A**lpha en una sola variable usándose para establecer colores en las pantallas lógicas. El rango de cada parámetro va del 0 al 1.


