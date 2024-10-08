# Instrucciones de control de unidades

Las instrucciones de control de unidades permiten realizar acciones relacionadas a las unidades, hacer que ataquen, se muevan, disparen, tomen objetos etc. El usar estas instrucciones a excepción de `Unit Bind` causará que la unidad deje de hacer su comportamiento normal, los monos dejarán de minar por su cuenta, al igual que los poly dejarán de ayudarte a construir, una vez desvinculados volverán a sus acciones.

## Unit Bind

Esta instrucción vinculará la unidad especificada al procesador, la unidad especificada se guardará dentro de la constante de procesador `@unit`. Después de vinculada, las demás instrucciones relacionadas al control de unidades se realizarán a esta unidad. **El procesador solo vincula una unidad a la vez**, y recorrerá una por una las unidades de este tipo hasta regresar a la primera.

## Unit Control

Esta instrucción le indicará a la unidad realizar una acción con las capacidades de la unidad (disparar, moverse, volar etc) de una larga lista:

###  Inactivo `idle`

### Detenerse `stop`

### Moverse `move` `ucontrol move x(number) y(number)`

Moverá a la unidad a las coordenadas `x` `y` especificadas. Esto lo hará en linea recta sin considerar obstáculos o que sea o no posición valida.
### Aproximarse `approach` `ucontrol approach x y range`

Aproximará a la unidad a las coordenadas `x` `y` especificadas de acuerdo al rango especificado.
### Encontrar camino `pathfind` `ucontrol pathfind x y`

Moverá a la unidad a las coordenadas `x` `y` especificadas. Esto lo hará trazando un camino que tome en cuenta obstáculos y otras situaciones.
### Encontrar camino automático `autoPathfind` `ucontrol autoPathfind`

Moverá la unidad al punto de aparición enemigo o núcleo enemigo mas cercano de manera automática. Tomando en cuenta el camino.
### Propulsarse `boost` `ucontrol boost enable`

Propulsará a la unidad si el valor es `true` y si esta cuenta con la capacidad de hacerlo, de otro modo, bajará al suelo o no se elevará.
### Disparar a posición `target` `ucontrol target x y shoot`

Apuntará a las coordenadas `x` `y` especificadas. Si `shoot` es `true` esta disparará, en caso contrario no hará nada.

### Disparar a objetivo `targetp` `ucontrol targetp unit/block shoot`

Disparará a un objetivo especificado en `unit/block` con predicción de movimiento incluido(si se especificó una unidad). Si `shoot` es `true` esta disparará, en caso contrario no hará nada.

### Soltar item `itemDrop` `ucontrol itemDrop to amount`

Soltará al objetivo especificado en `to` (ya sea un núcleo, torreta, boveda, etc.) la cantidad de items especificadas en `amount`. Como dato adicional, puedes poner `@air` en `to` para desechar los items.
### Tomar item `itemTake` `ucontrol itemTake from item amount`

Tomará del objetivo especificado en `from` (ya sea un núcleo, torreta, boveda, etc.) un `item`, la cantidad especifica se establece en `amount`.

### Soltar cargamento `payDrop` `ucontrol payDrop`

(cargamento siendo bloques o unidades dentro de unidades) 
### Tomar cargamento `payTake` `ucontrol payTake takeUnits`

(cargamento siendo bloques o unidades dentro de unidades)  Tomará el cargamento de su posición actual, si `takeUnits` es `true`, la unidad tomará solo las unidades en esa posición, en caso contrario, solo tomará los bloques.
### Entrar como cargamento `payEnter` `ucontrol payEnter`

(cargamento siendo bloques o unidades dentro de unidades) Entrará como cargamento a bloques que se encuentren en su posición actual y que lo admitan (reconstructores, desconstructores y catapultas).
### Minar `mine` `ucontrol mine x y`

Minará materiales en las coordenadas `x` `y` especificadas, puedes ver si una unidad puede minar un mineral en su información.

### Establecer identificador `flag` `ucontrol flag flag`

Establecerá una `flag` o identificador en la unidad, es básicamente un número que la unidad tendrá y que puede ser utilizada para un mejor manejo de unidades e identificación.

### Construir `build`

### Obtener bloque `getBlock`

### Dentro de `within` `ucontrol within x y radius result`

Detectará si la unidad vinculada se encuentra dentro del rango delimitado por las coordenadas `x` `y` y el `radius`. El resultado se almacenará en `result`.
### Desvincular `unbind` `ucontrol unbind`

idle stop move approach pathfind autopathfind boost target targetp itemDrop itemTake payDrop payTake payEnter mine flag build getBlock within unbind

## Unit Radar

Esta instrucción usará el rango de la unidad vinculada como un radar para detectar unidades dentro del mismo, haciendo uso de diferentes filtros mostrados a continuación:

* `any`: cualquier unidad.
* `ally`: unidad aliada.
* `enemy`: unidad enemiga.
* `player`: unidad controlada por el jugador.
* `attacker`: unidad que cuente con armas.
* `boss`: unidad con el estado de jefe.
* `flying`: unidad que actualmente esté en el aire.
* `ground`: unidad que se encuentre en el suelo.

Puedes hacer uso de 3 de estos filtros, los cuales seleccionas para especificar las unidades.


Todas las unidades que cumplan con los 3 filtros anteriores se encontrarán en una especie de lista, esa lista se ordenará dependiendo del ordenamiento que selecciones, el cual cuenta con las siguientes opciones:

* `distance`: distancia respecto a la unidad.
* `health`: salud actual de las unidades.
* `shield`: cantidad de escudo actual.
* `armor`: puntos de armadura, puedes revisar si una unidad cuenta con esto en su información.
* `maxHealth`: salud total de las unidades.

Por ultimo está el parámetro `order` que cuenta con dos modos:

* con valor `1`: ordenará la lista de unidades de manera ascendente.
* con valor `0`: ordenará la lista de unidades de manera descendente, específicamente, la invertirá.

La unidad resultante se almacenará en la variable `output` para su uso.

## Unit Locate

Esta instrucción localizará haciendo uso de la unidad vinculada estructuras u objetos de interés dentro del mapa, contiene 4 categorías de búsqueda:

### Minerales `ore`

Permitirá buscar vetas de minerales en el mapa, deberás seleccionar el mineral que la unidad debe buscar y te dará las coordenadas de la misma, además de una variable `found` que será `true` si este existe en el mapa, de otra manera `false`.

![[Pasted image 20240731225640.png]]
### Construcción `building`

Permitirá buscar construcciones dentro del mapa, cuenta con distintos parámetros para realizar la búsqueda, los cuales se muestran debajo:

`Group` o `Grupo` especificará cual es el grupo del bloque al que se quiere acceder, en el tenemos los siguientes:

* `core` buscará núcleos
* `storage` buscará almacenes o contenedores.
* `generator` buscará bloques que generen energía.
* `turret` buscará torretas.
* `factory` buscará fabricas.
* `repair` buscará bloques que reparan unidades.
* `battery` buscará baterías.
* `reactor` buscará reactores.

Si `enemy` se establece como `true`, buscará solo bloques enemigos, `outX` y `outY` son las coordenadas donde se encuentra el bloque, además la variable `found`será `true` si existe en el mapa esa construcción, `false` de otra manera.

![[Pasted image 20240731225656.png]]
![[Pasted image 20240731225722.png]]
![[Pasted image 20240731225740.png]]
![[Pasted image 20240731225752.png]]
### Punto de aparición `spawn`

Permitirá buscar puntos de aparición del enemigo, o núcleos en el caso de los mapas de ataque. `outX` y `outY` serán las coordenadas donde este se encuentra, `found` será `true` si existe en el mundo y `building` será el núcleo correspondiente en el caso que sea uno.
### Bloque dañado `damaged`

Permitirá buscar bloques dañados aliados. `outX` y `outY` serán las coordenadas donde este se encuentra, `found` será `true` si existe en el mundo y `building` será el bloque dañado correspondiente.

