# ¿Que es la lógica?

La lógica (mlog) es un lenguaje de programación tipo scripting (ejecutado en tiempo real) creado para profundizar más en la automatización y creación de procesos en el juego, ya que nos permite modificar las entidades del mismo dependiendo de ciertas acciones, condiciones etc.

## Funciones de la lógica

El sistema en su estado actual puede realizar las siguientes funciones, entre muchas otras cosas:

* Obtener información de unidades, bloques y del propio jugador.
* Controlar bloques, unidades y torretas.
* Mostrar figuras y colores en pantallas.
* Mostrar información como texto en bloques de mensaje.
* Leer y escribir información de celdas de memoria.
* Realizar operaciones matemáticas.

Con estas acciones podemos realizar un sin fin de mecanismos, todo dependerá de nuestra capacidad para hacerlos realidad. 

## Acceder a la lógica dentro del juego.

Para usar la lógica dentro del juego, se cuenta con un conjunto de bloques específicos para lo mismo. La categoría lógica.

![[categoria-logica.png]]

`Bloque de mensaje`

: a
`Interruptor`

: b
`Microprocesador`

: c
`Procesador lógico`

: d
`Hiperprocesador`

: e
`Unidad de memoria`

: f
`Servidor de memoria`

: g
`Pantalla lógica`

: h
`Pantalla lógica grande`
: i
`Lorem ipsum dolor sit amet`

:   Sed sagittis eleifend rutrum. Donec vitae suscipit est. Nullam tempus
    tellus non sem sollicitudin, quis rutrum leo facilisis.

`Cras arcu libero`

:   Aliquam metus eros, pretium sed nulla venenatis, faucibus auctor ex. Proin
    ut eros sed sapien ullamcorper consequat. Nunc ligula ante.

    Duis mollis est eget nibh volutpat, fermentum aliquet dui mollis.
    Nam vulputate tincidunt fringilla.
    Nullam dignissim ultrices urna non auctor.

## Limitaciones de la lógica

La lógica cuenta con distintas limitaciones aplicadas a propósito, ya que el objetivo de la misma es proporcionar automatización a las acciones de unidades y bloques. Además tiene que estar optimizada ya que está corriendo dentro de un juego.

* Una unidad no podrá minar si no cuenta con la capacidad de hacerlo.
* Una unidad no podrá disparar si no cuenta con armas.
* Una unidad no podrá volar si no cuenta con la capacidad.


Además de esto, los procesadores lógicos cuentan con una cantidad definida de instrucciones realizables por segundo, la misma está en el formato de `ipt` o instrucciones por `tick`, dentro de condiciones normales el juego realiza `60` instrucciones por `tick`, estas son las estadísticas de los 3 procesadores.

* `Microprocesador - 2 ipt` = 120 instrucciones por segundo.
* `Procesador lógico - 8 ipt` = 480 instrucciones por segundo.
* `Hiperprocesador - 25 ipt` = 1500 instrucciones por segundo.