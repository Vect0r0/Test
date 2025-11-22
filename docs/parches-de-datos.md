# Parches de datos

Los parches de datos (antes llamados parches de contenido) son una herramienta poderosa para modificar propiedades de bloques, unidades y objetos a nivel de mapa o de servidor. Algunas aplicaciones de esta función incluyen cambios de balance, modos de juego personalizados o una progresión diferente del juego.
Link a la guía original de anuken (en ingles) https://mindustrygame.github.io/wiki/contentpatches/

Algunas cosas que los parches **pueden** hacer:
* Hacer que una fabrica use más o menos de un recurso.,
* Cambiar los requerimientos de un bloque.,
* Cambiar completamente las armas y balas de una unidad.,
* Cambiar las recetas de una fábrica de unidades.,
* Cambiar los sprites de un bloque, unidades y otras texturas del juego.,
* Cambiar la velocidad de construcción, salud y armadura de un bloque o unidad.,
* Cambiar el tipo de una unidad. (ejemplo de terrestre a aérea )

Algunas cosas que los parches **no pueden** hacer:
* Introducir nuevas texturas al juego.,
* Introducir mecánicas no presentes en el juego vanilla.,
* Cambiar los tipos de los bloques. (ejemplo un muro a torreta),
* Añadir nuevo contenido (objetos, bloques, unidades, etc.),

Los parches de balance no son un remplazo para los mods; estos solo pueden modificar contenido existente

## Escribiendo un parche de datos trivial

Los parches de datos son escritos en JSON o HJSON. Necesitarás un editor de texto para escribirlo ya que actualmente no existe un editor dentro del juego para los mismos. Los parches en esta guía solo serán escritos en HJSON. Para empezar, crea un archivo de texto llamado `miparche.hjson` con el siguiente contenido:

```java
//nombrar un parche es opcional, pero ayuda a identificarlo dentro de la interfaz del juego
name: Mi parche

//hace que todos las cintas transportadoras tengan una vida máxima de 50
block.conveyor.health: 50
```

## Aplicando los parches de datos

### Aplicando los parches en los mapas

Abre tu mapa en el editor, abre el menú de la parte superior izquierda (o presiona la tecla ESC en escritorio). Ve a información del mapa -> Parches de contenido -> Añadir y entonces especifica el archivo del parche que guardaste en el paso anterior. Puedes ver cualquier error generado por el parche presionando el ícono de advertencia, o actualizar el archivo con el botón de actualizar.

### Aplicando los parches en servidores dedicados

Abre el directorio de tu servidor (que actualmente debería contener carpetas para plugins, mapas, archivos de guardado, etc), localiza el directorio patches y suelta tu archivo de parche ahí. Los archivos de parche deberán tener la extensión hjson/json/json5 para poder ser cargados. Estos se aplicarán automáticamente a todos los mapas después de que sus propios parches hayan sido aplicados.
Si hiciste todo de manera correcta, el servidor mostrará la cantidad de parches cargados al inicio. Cualquier advertencia o error también será imprimido en la consola. Para volver a cargar los parches mientras el servidor sigue encendido, usa el comando reloadpatches.

## Fundamentos de los parches de datos

Los parches de datos siguen una jerarquía. Al primer nivel, defines el tipo de contenido a ser cambiado: block, liquid, item, unit, weather  (bloque, liquido, item, unidades o climas) etc.
En el segundo nivel, defines el nombre del contenido a ser editado (ejemplo: conveyor,copper, copper-wall-large (cinta transportadora, cobre, muro grande de cobre)). Estos nombres distinguen mayúsculas de minúsculas por lo que tienes que escribirlos de acuerdo al nombre exacto del contenido, puedes ver este nombre en la base de datos del núcleo si tienes la consola activada.
En el tercer nivel, defines las propiedades que serán cambiadas y sus respectivos valores. como un ejemplo:

```java
block: {
  conveyor: {
    health: 50
    //las demás propiedades de las cintas transportadoras van aquí...
  }
  //otros bloques van aquí...
}
//otro tipo de contenido aquí
```

Alternativamente, si solo estás modificando una sola propiedad, puede ser más conveniente usar la sintaxis corta:

```java
block.conveyor.health: 50
```

## Ver todas las propiedades del contenido

Si estás familiarizado con Java, puedes ver el archivo del contenido relevante para ti en el código fuente (ejemplo [Block.java](https://github.com/Anuken/Mindustry/blob/master/core/src/mindustry/world/Block.java) para los bloques).
Si no, puedes habilitar la consola en el menú del juego, después hacer clic en el botón "Ver campos de contenido" en la base de datos para un bloque, unidad o líquido específico.
Nota: Esto solo mostrará los campos para esa clase específica, si quieres ver los campos de la "superclase", haz clic en el link que le sigue a la palabra extends.
Por ejemplo, [Conveyors/Cintas transportadoras](https://mindustrygame.github.io/wiki/Modding%20Classes/Conveyor/) tendrá todos los campos mostrados en su página, además de los campos en la "superclase" [Block/Bloques](https://mindustrygame.github.io/wiki/Modding%20Classes/Block/).

## Accediendo a arreglos/secuencias

Cuando acceder a un arreglo (T[]) o secuencia (Seq) es necesario, deberías hacerlo de la siguiente manera:

```java
//desplaza en gran cantidad una de las dos armas del dagger 
unit.dagger.weapons.0.x: 100
```

Nota, modificar las balas de armas reflejadas afectará a ambos lados, debido a que ambos comparten el mismo tipo de bala:

```java
//esto hará que ambas armas del dagger hagan 55 puntos de daño
unit.dagger.weapons.0.bullet.damage: 55
```

## Agregando y sobrescribiendo a arreglos/secuencias

A veces será necesario añadir a una secuencia y no sobrescribirla, puede hacerse de esta manera:

```java
//añade un laser superpoderoso a las armas del flare, manteniendo las otras intactas
//nota, .+ antes de la asignación añade el elemento
//puede agregarse un solo elemento, no solo un arreglo
unit.flare.weapons.+: {
  x:0
  y:0
  reload: 10
  bullet: {
    type: LaserBulletType
    damage: 100
  }
}
```

Alternativamente puedes sobrescribir el arreglo:

```java
//el flare ahora solo tendrá esta arma, las anteriores serán sobrescritas
//nota, cuando estas sobrescribiendo tendrás que usar [] debido a que estás asignando un nuevo valor
unit.flare.weapons: [
  {
    x: 0
    y: 0
    reload: 10
    bullet: {
      type: LaserBulletType
      damage: 100
    }
  }
]
```

Esta sintaxis soporta campos de tipo `T[]`, `Seq<T>` y `ObjectSet`

## Información general

- Los valores de tiempo se miden generalmente en ticks (a veces llamados frames) que son 1/60 partes de un segundo. Si un campo describe una duración, probablemente esté en ticks. Si un campo describe el tiempo de consumo, probablemente esté en unidades por tick.
- La distancia, posición y tamaños se miden generalmente en unidades del mundo que son 1/8 de una casilla. Esto es por que mindustry solía tener sprites 8*8 y una unidad del mundo era de 1 pixel. Esto es horrible pero se mantiene por razones históricas.
- Cuando interactúas con coordenadas a través de procesadores lógicos estas se convierten internamente de y a unidades del mundo. Los parches, al modificar los campos directamente, no tienen este lujo.
- Conjuntos de líquidos y objetos pueden definirse como 'nombre/cantidad'. Por ejemplo un campo `ItemStack` puede tener un valor de `thorium/100`.

## Advertencias y limitaciones

* Crear o asignar una arma con `mirror: true` no funcionará ya que la inicialización no se vuelve a realizar para las unidades. Tendrás que crear una versión reflejada y asignarle `x/shootX/flipSprite`.
* El `range` y `maxRange` no se actualizará, incluso si incrementas el tiempo de vida de las balas de una unidad. Estos valores tienen que asignarse manualmente.
* Similarmente, los campos de las unidades no se actualizarán incluso si reasignas el tipo. Por ejemplo reasignar el tipo de unidad terrestre a naval aún causará que las unidades se ahoguen.

