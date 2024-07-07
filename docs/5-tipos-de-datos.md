# Tipos de datos

Podemos decir que los tipos de datos en la lógica se dividen en 2 grupos, los números y los objetos:

# Números

Básicamente un número decimal, puede ser negativo o positivo, además de que puede representar `verdadero` (usado como `true`) con valores diferentes al `0` y `falso` (usado como `false`) con el valor `0`. Además, el `0` también representará un valor nulo (usado como `null`).

Hay instrucciones que solo aceptarán números enteros, por lo que el procesador "truncará (recortará la parte decimal)" en esos casos.

Internamente, los números se almacenan como valores de punto flotante de 64-Bits (conocidos como `double`), y operados como enteros de 64-Bits cuando se realiza un cambio de bits.

# Objetos

Dentro de los objetos encontramos distintas variaciones:

## Cadena de caracteres (`String`)

Este es un objeto que representa texto dentro de comillas, ejemplo: `"hola mundo"`.

## Construcción (`Building`)

Este objeto representará una construcción física dentro del mundo. Por ejemplo, puede ser una torreta, un muro o una cinta. Por lo que dentro del mismo contendrá valores como sus coordenadas, vida total u objetos almacenados.

## Unidad (`Unit`)

Este objeto representará una unidad física dentro del mundo. Por ejemplo un mono, un mega o la unidad del propio jugador.






