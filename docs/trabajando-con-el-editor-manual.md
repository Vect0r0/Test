# Trabajando con el editor manual

Para trabajar usando el editor manual basta con tener un editor de texto simple a la mano, ahora bien, puedes usar extensiones en aplicaciones como visual studio code para permitirte mas facilidades, como lo es el destacar la syntaxis. Para poder usar el código creado, copialo al portapapeles, accede al procesador deseado y en el apartado de `editar` selecciona la opción de `importar desde el portapapeles`.

## Añadir instrucciones

Para añadir instrucciones tendrás que escribir la instrucción con sus parámetros separados por espacios, debido a no contar con una interfaz tienes que tener cuidado al momento de escribirlos, o puede que al importar tu código, las instrucciones sean invalidas o los parámetros se encuentren en desorden. La forma de escribir cada instrucción suele variar por lo que tendrás que averiguar donde debe ir cada parámetro, por ejemplo, la estructura de la instrucción de operación es la siguiente:

``` 
op add result 3 2
```

La primer palabra es la instrucción, la segunda la operación a realizar (en este caso es una suma), la tercera es la variable donde se almacenará el resultado (en este caso será 5 el valor), y los últimos dos son los parámetros propios. Si copiamos esta linea dentro del juego, podemos ver que funciona correctamente.

![[editor-manual-demostracion-operacion.png]]

Otro ejemplo, si queremos que una torreta (en este caso un duo) dispare a una posición (100,120) debemos escribir lo siguiente

```
control shoot duo1 100 100 true
```

Donde `control` es la instrucción, `shoot` es la acción, `duo1` es el bloque o torreta a controlar, `100` es la coordenada x, `120` es la coodenada y, finalmente `1` se convierte en `true` (podemos usar ambos) que especifica si la torreta disparará o no.

![[editor-manual-demostracion-control.png]]

## Eliminar y duplicar instrucciones

Esta sección puede ser redundante, solo elimina la linea correspondiente a esa instrucción, o copiala y pegala debajo para duplicarla.

## Trabajar los saltos de linea

Trabajar con saltos de linea dentro del editor manual suele complicarse bastante ya que tienes que especificar a que linea tienes que saltar, además de que esta inicia en el indice 0, por lo que tendrás que contar a mano y restar uno, o bien, usar una guía dentro de un editor como visual studio, además de esto, no se actualizarán de manera automática si eliminas o agregas nuevas operaciones.

``` linenums="1"
op add num 1 2
jump 5 greaterThan num 2
print "Numero menor a 2"
printflush message1
end
print "Numero mayor a 2"
printflush message1
```

![[editor-manual-salto-convencional.png]]

Tenemos una manera de facilitar este trabajo y es con el uso de `etiquetas` que básicamente le agregan un identificador a una operación por lo que se facilitará hacer referencia al mismo, y no tendrá los problemas antes descritos. Para crear una, simplemente agrega en una linea arriba de tu instrucción un nombre con el que la quieres identificar, seguida de 2 puntos. Para usarlo simplemente cambia el número que hace referencia a la linea en la instrucción `jump` por el nombre de la etiqueta.

``` linenums="1"
op add num 1 2
jump mayor greaterThan num 2
print "Numero menor a 2"
printflush message1
end

mayor:
print "Numero mayor a 2"
printflush message1
```

![[editor-manual-salto-etiqueta.png]]

Como podemos ver, el resultado ha sido el mismo, solo se ha facilitado más hacerlo con las etiquetas.