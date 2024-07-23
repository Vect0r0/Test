# Instrucciones de control de unidades

Las instrucciones de control de unidades permiten realizar acciones relacionadas a las unidades, hacer que ataquen, se muevan, disparen, tomen objetos etc.

## Unit Bind

Esta instrucción vinculará la unidad especificada al procesador, la unidad especificada se guardará dentro de la variable de procesador `@unit`. Después de vinculada, las demás instrucciones relacionadas al control de unidades se realizarán a esta unidad. **El procesador solo vincula una unidad a la vez**.


## Unit Control

Esta instrucción le indicará a la unidad realizar una acción con las capacidades de la unidad (disparar, moverse, volar etc) de una larga lista:

###  Inactivo `idle`

### Detenerse `stop`

### Moverse `move` `ucontrol move x y`

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

### Construir `build`

### Obtener bloque `getBlock`

### Dentro de `within`

### Desvincular `unbind`

idle stop move approach pathfind autopathfind boost target targetp itemDrop itemTake payDrop payTake payEnter mine flag build getBlock within unbind






