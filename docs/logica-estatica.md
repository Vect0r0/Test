# ¿Qué es la lógica estática?

La lógica estática es una variante de la lógica común, esta es más poderosa y su principal objetivo es ser usada por los creadores de mapas para extender la funcionalidad del sistema lógico común, con funciones avanzadas y especializadas para la creación de mapas. Estos procesadores no se pueden usar de manera común y tiene que seguirse un proceso para modificarlos.

## Funciones de la lógica estática

Algunas de las funciones que la lógica estática posee son las siguientes:

* Aparecer unidades de cualquier tipo en una posición, equipo y rotación exactas.
* Cambiar las propiedades de los bloques.
* Colocar bloques a voluntad.
* Crear efectos gráficos y de sonido.
* Cambiar el clima del juego.
* Cambiar distintas reglas del juego (ejemplo que bloques están baneados).
* Crear explosiones.
* Aplicar estados alterados a las unidades.
* Mostrar mensajes globales a los jugadores.
* Interactuar con el sistema de los objetivos para desencadenar eventos.
* Y muchas cosas más.

## Limitaciones de la lógica estática

Este sistema tiene pocas limitaciones.

* La velocidad de los procesadores tiene un límite máximo, que suele ser muchísimo más alto que el de los procesadores normales pero sigue siendo un factor a considerar.
* No puedes crear comportamientos fuera de los vanilla, aunque si podrás darles un nuevo propósito, todo dependerá de tu capacidad.

## Acceder a la lógica estática dentro del juego

Para acceder a la lógica estática dentro del juego debemos acceder al editor de mapas, seleccionando editor en el menú principal y abriendo el mapa que deseamos modificar. Dentro del editor tenemos 2 formas de acceder a la lógica estática: 
### Menú de procesadores estáticos

Dentro de la información del mapa tendremos un apartado dedicado específicamente a la edición de los procesadores estáticos, 

![[logica-estatica-menu.png]]

Dentro de este apartado podemos observar procesadores que ya existen en nuestro mapa, además de agregar nuevos, asignarles íconos, nombres y establecer su código. Este menú es una manera ordenada de agregar comportamiento a los mapas. Este menú tiene una variante cuando editas dentro del juego, te permitirá ver la posición exacta del procesador, por si tu código requiere vincular bloques de manera manual o alguna otra acción.

![[logica-estatica-menu-dedicado.png]]

### Edición dentro del juego

Dentro del editor y al seleccionar la opción de editar dentro del juego podrás modificar los procesadores estáticos como si fuera un procesador común, asignándoles código y vinculándolos etc.

![[logica-estatica-bloques.png]]

Tendrás disponibles 4 bloques estáticos (amarillos) para su uso.

`Procesador estático`

: Es el único procesador necesario para acceder a la lógica estática, tiene un rango de vinculación infinito y una ejecución de instrucciones de velocidad variable.

`Unidad de memoria estática`

: Permite almacenar información en forma de números, con capacidad máxima de 512 unidades.

`Mensaje estático`

: Permite mostrar texto.

`Interruptor estático`

: Puede ser activado y desactivado.

Ten en cuenta que todos estos bloques son `indestructibles` dentro del juego por lo que no tienes que preocuparte de su posición etc.
