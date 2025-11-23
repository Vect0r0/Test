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
* `scathe-missile` ahora tiene 3 variantes `scathe-missile` `scathe-missile-surge` y `scathe-missile-phase`.


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
* `weather` es el tipo de clima. ![[instruccion-estatica-weather-sense-climas.png]]
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


## Set Rule

Te permite establecer o cambiar una regla de la partida.

![[instruccion-estatica-set-rule.png]]

![[instrucciones-estaticas-set-rule-rules.png]]

La mayoría de estas reglas tienen una descripción dentro del juego que aparece al poner el mouse encima de ellas o dejar apretado el dedo en móviles y solo se explicarán las que tienen más detalles o no cuentan con ella (si quieren una en especifico pídanla).

* `mapArea` permite modificar el área del mapa en la cual se puede jugar, todo bloque fuera de ella se inactivará inmediatamente además de que las unidades no podrían pasar de ese borde, `x` `y` son el punto inicial desde donde inicia la zona, `w/width` es el ancho de la zona, o cuanto se extiende desde el punto `x` a la derecha y `h/height` es el largo de la zona, o cuanto se extiende desde `y` hacia arriba.
* `canGameOver` valor booleano que dice si se puede o no perder en el mapa, ya sea perdiendo todos tus núcleos o destruyendo los enemigos, esta regla puede evitarlo.


## Flush Message

Te permite mostrar un mensaje en la pantalla usando el texto almacenado en la cola/buffer de texto. 

![[instruccion-estatica-flush-message.png]]

* `announce` es la lista de tipos de formato para mostrar el mensaje.
	*  ![[instruccion-estatica-flush-message-announce.png]]
	* ![[instruccion-estatica-flush-message-notify.png]]
	* ![[instruccion-estatica-flush-message-toast.png]]
	* ![[instruccion-estatica-flush-message-mission.png]]
* `for` es la cantidad de segundos que se mostrará el mensaje en pantalla.
* `succes` es el nombre de la variable booleana que indicará si este mensaje fue mostrado con éxito, anteriormente estas instrucciones esperaban a que finalizara el mensaje anterior, ahora si no está la oportunidad son saltadas, ese es el por que de la instrucción ya que ahora tu tendrás que configurar el código para evitar errores.


## Cutscene

Te permite crear una cinemática, mientras esté activa el jugador no podrá moverse o realizar acciones.

![[instruccion-estatica-cutscene.png]]

* `pan` es la lista de acciones a realizar
	* `pan` se moverá a las coordenadas `x` `y` especificadas a una cierta velocidad.
	* `zoom` hará zoom en la posición de la cámara actual, el zoom va del `0` al `1`.
	* `stop` detendrá la cinemática anterior.


## Effect

Creará un efecto de partículas. Los campos que se mostrarán dependerán del efecto de partículas seleccionado.

![[logica-estatica-effect.png]]

* `bubble` es la lista desplegable de los efectos a usar, en el juego se ven de manera gráfica.
* `x` `y` son el par de coordenadas en las cuales el efecto se creará.
* `size` será el tamaño del efecto.
* `color` es el color hexadecimal que tendrá la partícula, dentro del juego tienes un selector.
* `rotation` es la rotación en grados que tendrá el efecto.
* `data` es el tipo de bloque a usar.


## Explosion

Creará una explosion