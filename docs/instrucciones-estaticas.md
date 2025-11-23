# Instrucciones estáticas

Existen diversas instrucciones que nos permiten modificar el mundo con los procesadores estáticos, aquí hay algunas.

## Get Block

Te permite obtener información en cierta posición, similar al getBlock usado con las unidades pero este no tiene un rango limitado y no depende de una unidad.

* `floor`: Te permite obtener el tipo de casilla.
* `ore`: Te permite obtener el tipo de mineral.
* `block`: Te permite obtener el tipo de bloque en la posición.
* `building`: Te permite obtener la construcción en la posición, con todos sus datos.

## Set Block

Te permite poner bloques en cierta posición.

* `floor`: Te permite poner un tipo de casilla en la posición.
* `ore`: Te permite poner un tipo de mineral en la casilla.
* `building`: Te permite poner una construcción en la casilla, con un equipo y rotación.

## Spawn Unit

Te permite hacer aparecer unidades en cierta posición.

![[instruccion-estatica-spawn-unit.png]]

* `result` es el nombre de la variable que tendrá la unidad que hagas aparecer, es similar a la variable integrada `@unit` que se genera usando `unitBind`, puedes usar esta variable para hacer distintas cosas, como establecer estados alterados, obtener su posición o cualquier otra cosa.
* `spawn` es el tipo de unidad que deseas hacer aparecer.
* `at` es el par de posiciones `x y` en las cuales la unidad aparecerá.
* `team` es el equipo al que pertenecerá la unidad.
* `rot` es la rotación que tendrá la unidad, medida en grados.

Nota: Hay entidades en el juego que son consideradas como unidades, como lo son los misiles de las unidades en erekir, estos y las unidades ocultas pueden ser aparecidas con este comando.

## Apply Status

Te permite aplicar o quitar un estado alterado a una unidad.

Nota: Existen estados alterados no listados (`unarmed`) que evita que la unidad ataque es uno de ellos, solo puede usarse escribiendo el código manualmente.

![[instruccion-estatica-apply-status.png]]
* `apply` permitirá establecer un estado alterado.
* `corroded` es el menú de selección del estado alterado a aplicar. ![[instruccion-estatica-apply-status-status-menu.png]]
* `to` es la referencia a la unidad a la cual aplicar el estado, podrías usar la referencia que generó `Spawn Unit` o alguna otra.
* `for` es la cantidad de segundos que durará el estado alterado.

![[instruccion-estatica-apply-status-clear.png]]

* `clear` removerá todos los estados alterados.
* `from` es la referencia a la unidad a la cual se le removerán los estados alterados.

## Weather Sense

Te permite detectar si el clima seleccionado se encuentra activo en el mapa.

![[instruccion-estatica-weather-sense.png]]
* `result` será 1 si el clima se encuentra activo, 0 en cualquier otro caso.
* `weather` es el tipo de clima.                                                ![[instruccion-estatica-weather-sense-climas.png]]
	* `snowing` nevando.
	* `rain` lluvia.
	* `sandstorm` tormenta de arena.
	* `sporestorm` tormenta de esporas.
	* `fog` niebla.
	* `suspend-particles` partículas suspendidas.


## Weather Set

Te permite establecer un clima determinado en el mapa.

![[instruccion-estatica-weather-set.png]]
* `set weather` es la lista de climas que pueden aplicarse.
* `state` es el booleano que decide si el clima estará activo o no.


## Spawn Wave

Te permite aparecer una oleada en el mapa en cierta posición.

![[instruccion-estatica-spawn-wave.png]]

* `natural` es el booleano que decide si la oleada es natural o no, si la oleada no es natural esta no incrementará el contador de oleadas y no podrás decidir en que posición esta aparecerá.
* `x y` son el par de coordenadas usadas para aparecer la oleada solo si `natural` es falso.