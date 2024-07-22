# Instrucciones de operación

Las instrucciones de operación le permite realizar distintas acciones, estas dentro de las siguientes categorías.

## Set

Set le permite al procesador declarar una variable y asignarle un valor.

[[posible-escritura-en-editor-manual]]

## Operation

Operation le permite al procesador realizar operaciones matemáticas y guardar su resultado,dichas operaciones van desde las básicas como la suma, hasta otras como las operaciones trigonométricas. Esta es la lista completa de operadores, además puedes observarlos presionando el botón de operación en la instrucción. 

### Suma `+` `op add result a b`

Retorna la suma de `a` y `b`.

### Resta `-` `op sub result a b`

Retorna la resta de `a` y `b`.
### Multiplicación `*` `op mul result ab`

Retorna la multiplicación de  `a` y `b`
### División normal `/` `op div result a b`

Retorna la división completa de `a`(numerador) y `b`(denominador), retorna `null` cuando se divide entre 0.
### División entera `//` `op idiv result a b`

Retorna la parte entera de la división de `a`(numerador) y `b`(denominador), por ejemplo dividir 5 con 2 dará como resultado 2.
### Modulo `%` `op mod result a b`

Retorna el residuo de una división entera de `a`(numerador) y `b`(denominador), por ejemplo, dividir 5 con 2 dará como resultado 1.
### Potencia `^` `op pow result a b`

Retorna `a` elevado a la `b` potencia, por ejemplo, aplicar potencia de 2 con 3 dará como resultado 8.
### Comparativa igual `==` `op equal result a b`

Retorna `true` o `false` dependiendo si `a` y `b` son iguales.
### Negación `not` `op notEqual result a b`

Retornará lo inverso de la comparativa de igual, si `a` y `b` son iguales, retornará `false`.
### Comparativa Y `and` `op land result a b`

Retornará `true` si ambos `a` y `b` son valores validos o `true`.
### Menor que `<` `op lessThan result a b`

Retornará `true` si `a` es un valor menor a `b`. `false` en otro caso.
### Menor e igual `<=` `op lessThanEq result a b`

Retornará `true` si `a` es un valor menor o igual a `b`. `false` en otro caso.
### Mayor que `>` `op greaterThan result a b`

Retornará `true` si `a` es un valor mayor a `b`. `false` en otro caso.
### Mayor e igual `>=` `op greaterThanEq result a b`

Retornará `true` si `a` es un valor mayor o igual a `b`. `false` en otro caso.
### Igualdad estricta `===` `op strictEqual result a b`

Retornará `true` si `a` y `b` son objetos idénticos, que no hagan uso de la conversión implícita (eso creo).
### Bitshift Izquierda `«` `op shl result a b`
### Bitshift derecha `»` `op shr result a b`
### Comparativa or `or` `op or result a b`
### Comparativa b-and `b-and` `op and result a b`
### Operación xor `xor` `op xor result a b`
### Flip de bits `flip` `op not result a `
### Mínimo `min` `op min result a b`

Retornará el valor mínimo de entre los valores `a` y `b`, por ejemplo, si se usan los valores 5 y 7, se retornará el 5.
### Máximo `max` `op max result a b`

Retornará el valor máximo de entre los valores `a` y `b`, por ejemplo, si se usan los valores 5 y 7, se retornará el 7.
### Ángulo `angle` `op angle result a b`
### Diferencia de ángulos `angle diff` `op angleDiff result a b`
### Longitud de vector `len` `op len result a b`
### Ruido 2d `noise` `op noise result a b`
### Valor absoluto `abs` `op abs result a `
### Logaritmo `log` `op log result a `
### Logaritmo base 10 `log10` `op log10 result a `
### Redondeo a menor  `floor` `op floor result a `
### Redondeo a mayor `ceil` `op ceil result a`
### Raíz cuadrada `*` `op sqrt result a `
### Numero random `sqrt` `op rand result a`
### Seno `sin` `op sin result a `
### Coseno `cos` `op cos result a `
### Tangente `tan` `op tan result a`
### Arcoseno `asin` `op asin result a`
### Arcocoseno `acos` `op acos result a `
### Arcotangente `atan` `op atan result a `

## Lookup

Lookup le permite al procesador obtener el tipo de dato de un item/líquido/unidad/bloque haciendo uso de un indice. Para obtener el numero total de estos tipos puedes hacer uso de `@blockCount` para bloques, `@unitCount` para unidades, `@itemCount` para items y `@liquidCount` para líquidos. Estos valores pueden usarse en conjunto con instrucciones jump para crear un bucle y revisar cada uno de estos.

## Pack Color

Pack Color le permite al procesador empaquetar los componentes de un color **R**ed **G**reen **B**lue **A**lpha en una sola variable usándose para establecer colores en las pantallas lógicas. El rango de cada parámetro va del 0 al 1.


