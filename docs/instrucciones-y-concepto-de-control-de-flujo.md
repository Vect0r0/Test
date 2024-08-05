# Flujo de ejecución, concepto e instrucciones

## Concepto

El flujo de ejecución es el orden en el que las instrucciones se ejecutarán dentro de un procesador, este puede modificarse para alterar que instrucciones se ejecutarán en un caso específico y cuales no. Este cuenta con una serie de características:

* Normalmente se ejecuta de arriba hacia abajo.
* Cuando se ha ejecutado la última instrucción del procesador, el flujo se reiniciará, ejecutando todo desde la primera instrucción. Creando un comportamiento de bucle.
* Todo lo realizado en los bucles de ejecución del procesador (declarar variables, asignar valores, etc.) es mantenido, no se elimina.

## Instrucciones

Existen diversas instrucciones que permitirán modificar el flujo de ejecución de un procesador, estas se encuentran dentro de su propia categoría, `Control de flujo` con un color cían:

[[imagen-instrucciones]]
### wait

Detiene la ejecución del procesador una cierta cantidad de segundos.
### stop

Detendrá completamente la ejecución de instrucciones en el procesador.
### end

Reiniciará el flujo de ejecución, regresando a la primera instrucción, es equivalente a haber llegado a la última instrucción.
### jump

La piedra angular del sistema lógico, los saltos permiten crear comportamientos diversos en base a toma de decisiones, cosa que no sería posible sin ellos. Estos cuentan con una condición, que, cuando se cumple, saltará a una instrucción específica, ignorando las que le seguían, cuenta con las siguientes comparativas:

* `Igualdad == `: Compara 2 objetos, numeros, etc. Resultando verdadero si son iguales. Convertirá los mismos si es necesario.
* `Negación not `: Niega la comparativa de 2 objetos, números, etc. Es decir, invertirá el resultado de una igualdad. Convertirá los tipos mismos si es necesario.
* `Menor que < `: Compara 2 objetos, números, etc. Resulta verdadero si el primero es menor que el segundo.
* `Menor o igual que <=` Compara 2 objetos, números, etc. Resulta verdadero si el primero es menor o igual que el segundo.
* `Mayor que, Mayor o igual que`.
* `Igualdad estricta === `: Equivalente a la igualdad, solo que no convertirá los objetos.

## Manipulación avanzada del flujo de ejecución

Esta técnica se desarrolló en base a la variable `counter` que existe en cada procesador, esta variable indica cual será el indice de la próxima instrucción a ejecutarse, y al ser una variable, puede ser modificada, por lo que por ejemplo puedes simular el funcionamiento de una instrucción `jump`, o creación de estructuras como funciones. (No conozco mucho de esto)

