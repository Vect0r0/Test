# Instrucciones de control de bloques

Las instrucciones de control de bloques son instrucciones que permiten modificar el estado de los bloques, ya sean pantallas, bloques de mensaje, torretas, fábricas, bloques con selección (clasificadores) entre otras.

## Vinculando bloques al procesador 

Vincular bloques al procesador es una manera sencilla de obtener una referencia a ellos en el código, lo que te permite modificarlos con las instrucciones mostradas a continuación, para vincular bloques, presiona sobre el procesador deseado, lo que desplegará un rango, este rango es el rango en el que la estructura debe estar para ser vinculada, seguido de esto solo presiona sobre la que quieras vincular, verás un texto sobre de la misma que indica como acceder a ella en el procesador, por ejemplo, si vinculas 3 duos, sus nombres serán duo1 duo2 y duo3.

![[control-bloques-rango.png]]

![[control-bloques-rango-seleccion.png]]
## Get Link

Esta instrucción te permitirá obtener un bloque vinculado al procesador haciendo uso de un índice que corresponde al orden en el que las construcciones se vincularon, este inicia en 0, por lo que si tienes 3 construcciones vinculadas, terminará en 2 debido a esto. Por ejemplo, en el siguiente caso se tiene un procesador con 3 bloques vinculados, estos se vincularon en el orden de `scatter`, `duo` y finalmente `scorch`.

![[control-bloques-getlink-seleccion.png]]

si hacemos uso de la instrucción en el índice 0 obtendremos al `scatter`, 1 el `duo` y 2 el `scorch`, si solicitamos un número como el 3, obtendremos `null` ya que no hay mas bloques vinculados.

![[control-bloques-getlink-0.png]]
![[control-bloques-getlink-1.png]]
![[control-bloques-getlink-2.png]]

Esta instrucción obtiene utilidad al mezclarse con la constante [[variables-y-constantes#*@links* `constante` `numero`|@links]], ya que podemos por ejemplo, recorrer todos los bloques vinculados al procesador para realizar acciones, como en el caso de los sistemas para evitar que los reactores exploten.

## Control 

Esta instrucción te permitirá modificar el estado de los bloques, cuenta con 5 opciones:

### Enabled

Establece si está activo o no `true` para activar, `false` para desactivar, si tienes activado los marcadores, podrás ver un recuadro color morado cuando un bloque haya sido desactivado vía lógica. 
### Shoot

Ordenará a que coordenadas `x` `y` disparará una torreta, `shoot` se establece en `true` para disparar y en `false` para no hacer nada.

### Shootp

Permite disparar a un bloque o unidad con predicción de movimiento `shoot` se establece en `true` para disparar y en  `false` para no hacer nada.
### Config

Permite establecer distintas configuraciones entre los bloques, este comportamiento es visto en: 

* Clasificadores, donde podrás establecer el material a filtrar, ejemplo: `@copper`.
* Fabricas de unidades, donde podrás elegir que unidad se construirá.

Y en otros bloques que cuenten con un menú desplegable de selección.
### Color

Permite establecer el color en un iluminador, el color se maneja en rgb.

## Radar

Esta instrucción usará un bloque con rango como las torretas a manera de un radar para detectar unidades dentro del mismo, haciendo uso de diferentes filtros mostrados a continuación:

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

## Sensor

Este comando es de gran utilidad, te permite obtener propiedades de bloques y unidades, cosas como coordenadas, items, configuración, salud etc.
Draw print flush 
Get link
Control 
Radar
Sensor

## Draw flush

## Print flush