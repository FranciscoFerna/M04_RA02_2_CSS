
# Pseudoclases y Pseudoelementos

## Overview: Bloques de construcción CSS

El conjunto de selectores que estudiaremos en este artículo se conocen como **pseudoclases** y **pseudoelementos**. Hay muchos y a menudo sirven para fines muy específicos. Una vez que sepas cómo usarlos, puedes echar un vistazo a la lista para ver si alguno sirve para la página que quieres crear. Una vez más, la página correspondiente de MDN resulta muy útil para conocer qué navegadores los admiten o no.

## Prerrequisitos
- Conocimientos básicos de informática
- Tener el software básico instalado
- Conocimientos básicos de trabajar con archivos
- HTML básico (véase Introducción a HTML)
- Nociones de cómo funciona el CSS (véase Primeros pasos con el CSS)

## Objetivo
Obtener información sobre los selectores de pseudoclases y pseudoelementos.

## ¿Qué es una pseudoclase?
Una pseudoclase es un selector que marca los elementos que están en un estado específico, por ejemplo, los que son el primer elemento de su tipo, o aquellos por los que el cursor les pasa por encima. Tienden a actuar como si hubieras aplicado una clase en una parte determinada del documento y, a menudo, ayudan a reducir el exceso de clases y proporcionan un marcado más flexible y fácil de mantener.

Las pseudoclases son palabras clave que comienzan con dos puntos:

```css
:pseudo-class-name
```

### Ejemplos simples de pseudoclases
Echemos un vistazo a algunos ejemplos. Si queremos el primer párrafo de un artículo en letra más grande y en negrita, podemos añadir una clase a ese párrafo y luego añadirle CSS a esa clase. Sin embargo, podría ser complicado de mantener. ¿Y si añadimos un párrafo nuevo en la parte superior del documento? Habría que mover la clase para que quede antes del nuevo párrafo. En lugar de añadir la clase, podríamos utilizar el selector de pseudoclase `:first-child`, que siempre seleccionará el primer elemento hijo del artículo, y de esta forma no tendremos que editar el código HTML (esto no siempre es posible, tal vez debido a que lo genera un CMS).

Todas las pseudoclases se comportan del mismo modo. Seleccionan un fragmento del documento que está en un estado determinado y se comportan como si se hubiera añadido una clase a su HTML. Echa un vistazo a otros ejemplos en MDN:

- `:last-child`
- `:only-child`
- `:invalid`

**Nota:** Es válido escribir pseudoclases y pseudoelementos sin que les preceda un selector de elemento. En el ejemplo anterior, podría escribirse `:first-child` y la regla se aplicaría a cualquier elemento que sea el primer hijo de un elemento `<article>`, no solo a un párrafo primer hijo. `:first-child` equivale a `*:first-child`. Pero normalmente se quiere más control y hay que ser más específico.

## Pseudoclases de acción de usuario
Algunas pseudoclases solo intervienen cuando el usuario interactúa con el documento de alguna manera. Estas pseudoclases de acción de usuario, que también reciben el nombre de pseudoclases dinámicas, actúan como si se añadiese una clase al elemento cuando el usuario interactúa con él. Algunos ejemplos son:

- `:hover`: solo interviene si el usuario pasa el cursor sobre un elemento, normalmente un enlace.
- `:focus`: solo interviene si el usuario selecciona el elemento con los controles del teclado.

## ¿Qué es un pseudoelemento?
Los pseudoelementos se comportan de manera similar. Sin embargo, actúan como si hubieras añadido un elemento HTML totalmente nuevo en el marcado, en lugar de haber aplicado una clase nueva a los elementos presentes. Los pseudoelementos empiezan con un doble signo de dos puntos:

```css
::pseudo-element-name
```

**Nota:** Algunos de los primeros pseudoelementos utilizaban la sintaxis de un solo signo de dos puntos, así que puede ser que en ocasiones los veas escritos de esta forma en algún código o ejemplo. Los navegadores modernos leen tanto los pseudoelementos con la sintaxis de los dos puntos simple como la de los dos puntos doble para garantizar la compatibilidad retrospectiva.

Por ejemplo, si deseas seleccionar la primera línea de un párrafo simplemente puedes delimitarlo con el elemento `<span>` y utilizar un selector de elementos. Sin embargo, fallará si el número de palabras que has delimitado resulta ser más largo o más corto que el ancho del elemento padre. Ya que normalmente no sabemos cuántas palabras caben en una línea porque esto cambia con el ancho de la pantalla o con los cambios de tamaño de la letra, no es posible hacer esto introduciendo solo HTML.

El pseudoelemento `::first-line` soluciona este problema: no importa si el número de palabras aumenta o disminuye, siempre se selecciona la primera línea.

## Combinar pseudoclases y pseudoelementos
Si quieres poner en negrita la primera línea del primer párrafo, puedes encadenar los selectores `:first-child` y `::first-line`. Añade al ejemplo anterior el CSS siguiente. Queremos que se seleccione la primera línea del primer elemento `<p>` que esté dentro de un elemento `<article>`.

```css
article p:first-child::first-line {
  font-size: 120%;
  font-weight: bold;
}
```

## Generar contenido con `::before` y `::after`
Hay un par de pseudoelementos especiales que se utilizan junto con la propiedad `content` para introducir contenido en el documento usando el CSS.

Puedes utilizarlos para insertar una cadena de texto, como en el ejemplo siguiente. Intenta cambiar el valor del texto de la propiedad `content` y observa el cambio en la salida. También puedes cambiar el pseudoelemento `::before` por `::after` y verás que el texto se inserta al final del elemento, en lugar de al principio.

Sin embargo, en realidad no es habitual insertar cadenas de texto desde el CSS, porque ese texto resulta inaccesible para algunos lectores de pantalla y puede ser difícil de buscar y modificar en el futuro.

Un uso más adecuado de estos pseudoelementos es insertar un icono. Por ejemplo, la pequeña flecha que añadimos en el ejemplo siguiente es un indicador visual que no queremos que el lector de pantalla muestre.

Estos pseudoelementos también se utilizan con frecuencia para insertar una cadena vacía a la que luego se le puede aplicar estilo, como a cualquier otro elemento de la página.

En el ejemplo siguiente hemos añadido una cadena vacía mediante el pseudoelemento `::before`. Le hemos asociado `display: block` para poder aplicarle estilo para que tenga una anchura y una altura determinadas. A continuación, utilizamos el CSS para aplicar estilo de la misma forma que lo haríamos con cualquier otro elemento. Juega con el CSS y cambia la forma en que se ve y se comporta.

El uso de los pseudoelementos `::before` y `::after`, junto con la propiedad `content`, se conoce como **contenido generado** en CSS, y verás que esta técnica se utiliza a menudo para diversas tareas. Un buen ejemplo es la página web CSS Arrow Please, que te ayuda a generar una flecha con CSS. Echa un vistazo al CSS a medida que creas tu flecha y verás cómo funcionan los pseudoelementos `::before` y `::after`. Cada vez que veas estos selectores, echa un vistazo a la propiedad `content` para ver qué se añade al documento.

## Sección de referencia
Hay un gran número de pseudoclases y pseudoelementos, así que resulta útil tener una lista para ir consultándolos. A continuación encontrarás un par de tablas con enlaces a sus páginas de referencia en MDN. Tómalas como referencia para ver de qué dispones para seleccionar qué tipos de elementos.


### Pseudoclases
| Selector                | Descripción                                                                                      |
|------------------------|--------------------------------------------------------------------------------------------------|
| `:active`              | Selecciona un elemento cuando el usuario lo activa (por ejemplo, con un clic).                  |
| `:any-link`            | Selecciona los estados `:link` y `:visited` de un enlace.                                      |
| `:blank`               | Selecciona un elemento `<input>` cuyo valor de entrada está vacío.                             |
| `:checked`             | Selecciona un botón de opción o casilla de verificación que está seleccionado.                  |
| `:current`             | Selecciona el elemento que se muestra actualmente, o un ancestro de ese elemento.              |
| `:default`             | Selecciona uno o más elementos de interfaz de usuario cuyo valor es el predeterminado.          |
| `:dir`                 | Selecciona un elemento según su direccionalidad (por ejemplo, ltr o rtl).                     |
| `:disabled`            | Selecciona elementos de la interfaz de usuario que están inactivos.                            |
| `:empty`               | Selecciona un elemento que no tiene elementos hijos, excepto por algún espacio en blanco opcional. |
| `:enabled`             | Selecciona elementos de la interfaz de usuario que están activos.                               |
| `:first`               | En Paged Media, selecciona la primera página.                                                  |
| `:first-child`         | Selecciona el primer hijo entre elementos hermanos.                                             |
| `:first-of-type`       | Selecciona el primer hijo entre un grupo de elementos que son del mismo tipo.                   |
| `:focus`               | Selecciona un elemento que tiene el foco.                                                       |
| `:hover`               | Selecciona un elemento sobre el que el usuario pasa el cursor.                                 |
| `:in-range`            | Selecciona elementos de interfaz de usuario cuyo valor se encuentra en el rango especificado.  |
| `:last-child`          | Selecciona el último hijo entre elementos hermanos.                                             |
| `:last-of-type`        | Selecciona el último hijo entre un grupo de elementos que son del mismo tipo.                   |
| `:link`                | Selecciona un enlace que no ha sido visitado por el usuario.                                   |
| `:not`                 | Selecciona cualquier elemento que no coincida con el selector que especifiques.                 |
| `:nth-child`           | Selecciona el enésimo hijo entre elementos hermanos.                                            |
| `:nth-last-child`      | Selecciona el enésimo hijo entre elementos hermanos, contados desde el final.                  |
| `:nth-of-type`         | Selecciona el enésimo hijo entre un grupo de elementos que son del mismo tipo.                  |
| `:nth-last-of-type`    | Selecciona el enésimo hijo entre un grupo de elementos que son del mismo tipo, contados desde el final. |
| `:only-child`          | Selecciona un elemento que es el único hijo de su padre.                                       |
| `:only-of-type`        | Selecciona un elemento que es el único de su tipo entre sus hermanos.                          |
| `:required`            | Selecciona un campo de entrada que es obligatorio.                                             |
| `:target`              | Selecciona un elemento con un ID que coincide con el identificador especificado en la URL.     |
| `:valid`               | Selecciona elementos de entrada que son válidos.                                              |

### Pseudoelementos
| Selector           | Descripción                                                                                         |
|-------------------|-----------------------------------------------------------------------------------------------------|
| `::after`         | Selecciona un pseudo-elemento que se inserta al final del contenido de un elemento.                |
| `::before`        | Selecciona un pseudo-elemento que se inserta al principio del contenido de un elemento.             |
| `::first-letter`  | Selecciona la primera letra de un bloque de texto.                                                |
| `::first-line`    | Selecciona la primera línea de un bloque de texto.                                                |
| `::marker`        | Selecciona el marcador de un elemento de lista.                                                   |
| `::placeholder`   | Selecciona el texto de sugerencia dentro de un campo de entrada.                                   |
| `::selection`     | Selecciona la parte del texto que ha sido seleccionada por el usuario.                             |

