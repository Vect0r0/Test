# Tipos de datos

Podemos decir que los tipos de datos en la lógica se dividen en 2 grupos, los números y los objetos:

## Números

Básicamente un número decimal, puede ser negativo o positivo, además de que puede representar `verdadero` (usado como `true`) con valores diferentes al `0` y `falso` (usado como `false`) con el valor `0`. Además, el `0` también representará un valor nulo (usado como `null`).

Hay instrucciones que solo aceptarán números enteros, por lo que el procesador "truncará (recortará la parte decimal)" en esos casos.

Internamente, los números se almacenan como valores de punto flotante de 64-Bits (conocidos como `double`), y operados como enteros de 64-Bits cuando se realiza un cambio de bits.

## Objetos

Dentro de los objetos encontramos distintas variaciones:

### Cadena de caracteres (`String`)

Este es un objeto que representa texto dentro de comillas, ejemplo: `"hola mundo"`.

### Construcción (`Building`)

Este objeto representará una construcción física dentro del mundo. Por ejemplo, puede ser una torreta, un muro o una cinta. Por lo que dentro del mismo contendrá valores como sus coordenadas, vida total u objetos almacenados.

### Unidad (`Unit`)

Este objeto representará una unidad física dentro del mundo. Por ejemplo un mono, un mega o la unidad del propio jugador.

### Tipo de Bloque/Unidad (`Content`)

Esto representará el "concepto" de cualquier contenido en el juego, si estas familiarizado con la programación, podemos decir que esto es la "clase", y `building` y `unit` serían los "objetos". Estos no cuentan con una representación física, por lo que algunas propiedades no existirán como si lo hicieran su contra-parte de "objeto", por ejemplo, @duo es una variable de tipo `content`, no tendrá propiedades como la coordenada x, la cantidad de munición, la rotación, etc. Algunas propiedades se compartirán con el "objeto", como el tamaño, la salud máxima y el rango.

```
set string "hola mundo"
set number1 10
set number2 10.2
set construccion duo1
ubind @poly
set unidad @unit
set tipo-de-bloque @duo
set tipo-de-unidad @mega
```

[[Imagen|Visualización del menú Variables con el código anterior]]

