# Instrucciones de operación

Las instrucciones de operación le permite realizar distintas acciones, estas dentro de las siguientes categorías.

## Set

Set le permite al procesador declarar una variable y asignarle un valor.

[[posible-escritura-en-editor-manual]]

## Operation

Operation le permite al procesador realizar operaciones matemáticas y guardar su resultado,dichas operaciones van desde las básicas como la suma, hasta otras como las operaciones trigonométricas. Esta es la lista completa de operadores, además puedes observarlos presionando el botón de operación en la instrucción. 

### Suma `+` `op add result a b`
### Resta `-` `op sub result a b`
### Multiplicación `*` `op mul result ab`
### División normal `*` `op div result a b`
### División entera `//` `op idiv result a b`
### Modulo `%` `op mod result a b`
### Potencia `^` `op pow result a b`
### Comparativa igual `==` `op equal result a b`
### Negación `not` `op notEqual result a b`
### Comparativa Y `and` `op land result a b`
### Menor que `<` `op lessThan result a b`
### Menor e igual `<=` `op lessThanEq result a b`
### Mayor que `>` `op greaterThan result a b`
### Mayor e igual `>=` `op greaterThanEq result a b`
### Igualdad estricta `===` `op strictEqual result a b`
### Bitshift Izquierda `«` `op shl result a b`
### Bitshift derecha `»` `op shr result a b`
### Comparativa or `or` `op or result a b`
### Comparativa b-and `b-and` `op and result a b`
### Operación xor `xor` `op xor result a b`
### Flip de bits `flip` `op not result a `
### Mínimo `min` `op max result a `
### Máximo `max` `op min result a b`
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


mas menos multiplicación división-fraccionaria división-entera modulo potencia operador-igual operador-not operador-and operador-menor operador-menor-igual operador-mayor operador-mayor-igual bitshift-izquierda bitshift-derecha operador-or operador-b-and operador-xor operador-flip maximo minimo angulo diferencia-de-angulo longitud ruido absoluto logaritmo logaritmo-base-10 redondeo-menor redondeo-mayor raiz random seno coseno tangente arcoseno arcocoseno arcotangente

## Lookup

Lookup le permite al procesador obtener el tipo de dato de un item/líquido/unidad/bloque haciendo uso de un indice. Para obtener el numero total de estos tipos puedes hacer uso de `@blockCount` para bloques, `@unitCount` para unidades, `@itemCount` para items y `@liquidCount` para líquidos. Estos valores pueden usarse en conjunto con instrucciones jump para crear un bucle y revisar cada uno de estos.

## Pack Color

Pack Color le permite al procesador empaquetar los componentes de un color **R**ed **G**reen **B**lue **A**lpha en una sola variable usándose para establecer colores en las pantallas lógicas. El rango de cada parámetro va del 0 al 1.


