# Flujo de ejecución

El flujo de ejecución consiste en el orden en el que las instrucciones se ejecutarán dentro de un procesador, este puede modificarse para ejecutar una serie de instrucciones en determinadas ocasiones, o no ejecutar nada. Este flujo tiene una serie de características:

* Se ejecuta de arriba hacia abajo.
* Cuando se llega a la ultima instrucción del procesador, se regresará a la primera instrucción, es decir, el procesador tiene un comportamiento de ciclo.
* Este flujo puede ser modificado con instrucciones específicas.
* Todo lo realizado en un ciclo de ejecución del procesador se mantendrá en la siguiente vuelta.

## Instrucciones de control de flujo

^2b84cf

Existen diversas instrucciones que permitirán modificar el flujo de ejecución de un procesador, estas se encuentran dentro de su propia categoría, `Control de flujo` con un color cían:

[[Imagen|Categoría control de flujo]]
### wait

Detiene la ejecución del procesador una cierta cantidad de segundos.
### stop

Detendrá completamente la ejecución de instrucciones en el procesador.
### end

Regresará a la primera instrucción del procesador. Esto es equivalente a llegar a la ultima instrucción del procesador.
### jump

"Saltará" a una instrucción específica si se cumple una condición específica.

## Manipulación avanzada del flujo de ejecución

^79b104

Esta técnica se desarrolló en base a la variable `counter` que existe en cada procesador, esta variable indica cual será el indice de la próxima instrucción a ejecutarse, y al ser una variable, puede ser modificada, por lo que por ejemplo puedes simular el funcionamiento de una instrucción `jump`, o creación de estructuras como funciones. (No conozco mucho de esto) ^465195