# Variables y constantes

## Variables
 
### Concepto de variable

Para comenzar, debemos entender el concepto de variable, las variables son "contenedores de información" que se guardan en memoria, en este caso, en un procesador. Estas deben tener un nombre para identificarlas, usarlas y modificaras. Estas además pueden contener distintos tipos de información o datos. Dentro del juego, una variable puede contener la información de una unidad, el estado de un bloque, un numero tan simple como una coordenada, o texto,consulta [[Tipos de datos]] para ver todos los tipos disponibles.

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

#### *@thisx* `constante` `numero`
#### *@thisy* `constante` `numero`
#### *@ipt* `constante` `numero` 
#### *@counter* `variable` `numero`

### Relacionadas a las conexiones

#### *@links* `constante` `numero`
#### `constante` `numero`
### Relacionadas a las matemáticas
#### *@pi*
#### *π*
#### *@e*
#### *@degToRad*
#### *@radToDeg*
### Relacionadas al mapa
#### *@time* 
#### *@tick*
#### *@second*
#### *@minute*
#### *@waveNumber*
#### *@waveTime*
#### *@mapw*
#### *@maph*