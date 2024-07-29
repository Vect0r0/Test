# Variables y constantes

## Variables
 
### Concepto de variable

Para comenzar, debemos entender el concepto de variable, las variables son "contenedores de información" que se guardan en memoria, en este caso, en un procesador. Estas deben tener un nombre para identificarlas, usarlas y modificaras. Estas además pueden contener distintos tipos de información o datos. Dentro del juego, una variable puede contener la información de una unidad, el estado de un bloque, un numero tan simple como una coordenada, o texto,consulta [[6-tipos-de-datos|tipos de datos]] para ver todos los tipos disponibles. La función principal de estas es hacer flexibles las instrucciones, por ejemplo, si le ordenas a una unidad moverse a la posición 100, 100 solo podrá moverse a esa posición, pero si en otro caso usar variables como `x` y `y`, que son modificadas por el procesador, entonces la unidad podrá moverse a donde el procesador le indique.

### Reglas en variables

Para un buen uso de las mismas, las variables tiene que seguir una serie de reglas:

* El nombre debe ser un nombre valido, no puede ser un número, ejemplo: `123`.
* Este nombre no debe repetirse, si esto se hace el valor que la variable tenia se sobrescribirá, en algunas ocasiones será algo que quieres, pero en caso contrario, no lo hagas, ejemplo: si tu variable `coordenada_x` tenía un valor de `100` y vuelves a definir la variable la cadena `"frog"`, `coordenada_x` tendrá ese nuevo valor.  
* El nombre no puede contener espacios vacíos, puedes hacer uso de guión medio, bajo, o usar mayúsculas como separación de palabras, ejemplo: `oreX`, `ore_x`, `ore-x`.
* Las variables tienen que tener un nombre con sentido y claro, para identificar fácilmente que valor contiene, ejemplo: Es mas sencillo saber el contenido de una variable llamada `unidad_controlada` a una llamada `abalkfalk`.

### Declaración de variables

Para declarar o crear variables existen 2 maneras, como resultado de una instrucción o haciendo uso de la instrucción `set`.

#### Como resultado de una instrucción

Simplemente agrega en el campo de salida el nombre con el que quieres identificar la variable y el sistema la creará y le asignará el valor correspondiente, ejemplo: 
Si quieres declarar una variable que tenga la coordenada x de un bloque, pones el nombre de la misma, en este caso `coordenada-x` en el campo correspondiente, y el sistema la creará y le asignará un valor.

[[Imagen]]

#### Haciendo uso de la instrucción set

Crea una instrucción set y agrega el nombre de tu variable, además del valor que deseas que tenga, ejemplo: Si quieres crear una variable que contenga la cantidad de items en la cual tu fabrica se detendrá, agregas el nombre de la misma, en este caso `cantidad-maxima` con el valor correspondiente, en este caso `25`.

[[Imagen]]

### Conversión implícita de valores (rellenar)
 
## Constantes
### Concepto de constante

Otro concepto importante son las constantes, estas al igual que las variables son contenedores de información, solo que tienen un valor que no puede ser cambiado por el usuario, por ejemplo en el mundo real tenemos a la constante de la gravedad, o el numero PI.

## Constantes y variables propias del procesador

Cada procesador tiene variables y constantes propias, algunas referidas al mundo, como `mapw` que contiene el ancho del mapa en tiles, y otras independientes por procesador, como `thisx`que contiene la coordenada `x` del procesador.

### Relacionadas al procesador

#### *@this* `constante` `construcción`

Hace referencia al mismo procesador.

#### *@thisx* `constante` `numero`

Hace referencia a la coordenada `x` del procesador.
#### *@thisy* `constante` `numero`

Hace referencia a la coordenada `y` del procesador.
#### *@ipt* `constante` `numero` 

Hace referencia a las instrucciones por tick que este procesador está realizando. Adicional a esto, existe otra medida llamada `tps` o ticks por segundo, que en situaciones normales suele ser de 60. 
#### *@counter* `variable` `numero`

Hace referencia al índice de la próxima instrucción a ejecutarse, el indice comienza en 0 y terminará hasta la ultima instrucción - 1, es decir, si el procesador cuenta con 10 instrucciones, el indice va de 0 a 9. [[flujo-de-ejecucion#^465195|Puede ser modificada por el usuario para conseguir comportamientos avanzados.]]

### Relacionadas a las conexiones

#### *@links* `constante` `numero`

Hace referencia a la cantidad de construcciones vinculadas al procesador. Puede usarse para recorrer cada una de estas y realizar acciones.
#### `constante` `numero`


### Relacionadas a las matemáticas

#### *@pi* `constante` `numero`

Referencia al numero pi `3.1415927410125732` (numero pi).
#### *π* `constante` `numero`

Referencia al numero `3.1415927410125732` con más estilo (numero pi).
#### *@e* `constante` `numero`

Referencia al numero `2.7182817459106445` (numero euler).
#### *@degToRad* `constante` `numero`

Referencia al numero `0.01745329238474369`, multiplica este numero con tus grados para convertirlos a radianes.
#### *@radToDeg* `constante` `numero`

Referencia al numero `57.2957763671875`, multiplica este numero con tus radianes para convertirlos a grados.
### Relacionadas al mapa
#### *@time*  `constante` `numero`

Tiempo desde que se empezó a jugar en el mapa, en milisegundos (tiempo en pausa no cuenta).
#### *@tick* `constante` `numero`

Ticks realizados desde que se empezó a jugar en el mapa, (tiempo en pausa no cuenta).
#### *@second* `constante` `numero`

Tiempo desde que se empezó a jugar en el mapa, en segundos (tiempo en pausa no cuenta).
#### *@minute* `constante` `numero`

Tiempo desde que se empezó a jugar en el mapa, en minutos (tiempo en pausa no cuenta).
#### *@waveNumber* `constante` `numero`

Referencia a la oleada actual.
#### *@waveTime* `constante` `numero`

Referencia al tiempo que falta para que inicie la próxima oleada, en segundos.
#### *@mapw* `constante` `numero`

Referencia al ancho del mapa, en casillas o tiles.
#### *@maph* `constante` `numero`

Referencia a lo alto del mapa, en casillas o tiles.

### Relacionadas al control de unidades

#### @unit `constante` `unidad` 

Referencia a la unidad actualmente vinculada. Esta solo cambia cuando se desvincula la unidad o se vincula una nueva. Esta es usada por las instrucciones relacionadas al control de unidades para saber a que unidad afectar. **Solo una unidad puede ser controlada a la vez** por el procesador. Aunque, puedes almacenar la misma en una variable, esta no podrá usarse para controlar a esa unidad pero puedes seguir usandola en sensores. 