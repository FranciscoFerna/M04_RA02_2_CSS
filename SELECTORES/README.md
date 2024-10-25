## 1. Selector Universal (`*`)

- **Sintaxis**: `*`
- **Descripción**: Selecciona **todos los elementos** en el documento. Se usa para aplicar estilos generales.
- **Ejemplo**:
  ```css
  * {
      margin: 0;
      padding: 0;
  }
  ```

## 2. Selector de Tipo

- **Sintaxis**: `elemento`
- **Descripción**: Selecciona todos los elementos del tipo especificado.
- **Ejemplo**:
  ```css
  p {
      color: green;
  }
  ```

## 3. Selector de Clase (`.`)

- **Sintaxis**: `.clase`
- **Descripción**: Selecciona todos los elementos que tienen la clase especificada.
- **Ejemplo**:
  ```css
  .destacado {
      font-weight: bold;
  }
  ```

## 4. Selector de ID (`#`)

- **Sintaxis**: `#id`
- **Descripción**: Selecciona el elemento que tiene el ID especificado. Los IDs deben ser únicos en una página.
- **Ejemplo**:
  ```css
  #header {
      background-color: lightblue;
  }
  ```

## 5. Selector de Atributo

- **Sintaxis**: `[atributo]` o `[atributo="valor"]`
- **Descripción**: Selecciona elementos que tienen un atributo específico o que tienen un atributo con un valor específico.
- **Ejemplo**:
  ```css
  input[type="text"] {
      border: 1px solid black;
  }
  ```

## 6. Selector Descendente (` `)

- **Sintaxis**: `A B`
- **Descripción**: Selecciona todos los elementos `B` que son descendientes de un elemento `A`, sin importar cuántos niveles de profundidad haya.
- **Ejemplo**:
  ```css
  div p {
      color: red;
  }
  ```
  Este código selecciona todos los párrafos (`<p>`) que están dentro de un `div`.

## 7. Selector Descendente Directo (`>`)

- **Sintaxis**: `A > B`
- **Descripción**: Selecciona los elementos `B` que son **hijos directos** de un elemento `A`.
- **Ejemplo**:
  ```css
  ul > li {
      list-style-type: none;
  }
  ```
  Aquí se seleccionan solo los elementos `li` que son hijos directos de un `ul`.

## 8. Selector de Adyacencia (`+`)

- **Sintaxis**: `A + B`
- **Descripción**: Selecciona el elemento `B` que es el **hermano inmediato** del elemento `A`.
- **Ejemplo**:
  ```css
  h1 + p {
      color: blue;
  }
  ```

## 9. Selector de Hermanos Generales (`~`)

- **Sintaxis**: `A ~ B`
- **Descripción**: Selecciona todos los elementos `B` que son hermanos de `A`, sin importar si son inmediatos o no.
- **Ejemplo**:
  ```css
  h1 ~ p {
      color: orange;
  }
  ```
  Esto selecciona todos los párrafos (`<p>`) que son hermanos de un encabezado (`<h1>`).

## 10. Selector Combinado

- **Sintaxis**: `A, B`
- **Descripción**: Selecciona los elementos `A` y `B` al mismo tiempo.
- **Ejemplo**:
  ```css
  h1, h2 {
      color: purple;
  }
  ```

## Resumen

Los selectores CSS son fundamentales para aplicar estilos de manera específica a los elementos en un documento HTML. Conocer y entender estos selectores permite una mayor flexibilidad y control sobre la presentación visual de una página web.

Este resumen cubre los selectores más utilizados en CSS y proporciona ejemplos para cada uno, lo que debería ser útil para entender cómo funcionan y cómo se pueden aplicar en la práctica.
