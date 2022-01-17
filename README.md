# week2_day1

## Contenidos

> JS | Array advanced methods: `.map()`, `.filter()`, `.reduce()`, `.reverse()` and `.sort()`
> 
> JS | Reference VS value / Shadow copy VS deep copy


## Main points: array advanced methods

Los métodos `.map()`, `.filter()` y `.reduce()` son métodos del objeto Array que no mutan el array original.

- El método `.map()`:
  - Recibe como argumento una función.
  - Retorna un array manipulado de la misma longitud que el original.
  - Transfiere a cada posición del array resultante el retorno de la función argumentada.
    ````javascript
    const values = [2, 4, 6]
    const doubledValues = values.map(elm => elm * 2)      // [4, 8, 12]
    ````
    
- El método `.filter()`
  - Recibe como argumento una función.
  - Retorna un array con una longitud máxima igual a la longitud del array original.
  - Transfiere al array resultante cada posición del array original donde la función argumentada retorna un valor _truthy_.
    ````javascript
    const values = [2, 4, 6]
    const highValues = values.filter(elm => elm < 2)      // [4, 6] 
    ````
  
- El método `.reduce()` 
  - Recibe como argumento una función con dos parámetros por defecto: acumulador y valor iterado.
  - Puede recibir un segundo argumento tomando este como valor inicial para el acumulador.
  - Toma como valor del acumulador para la segunda y sucesivas iteraciones el valor retornado de la anterior iteración.
    ````javascript
    const values = [2, 4, 6]
    const sum = values.reduce((acc, elm) => acc + elm)      // 12 
    ````
  
Los métodos `.sort()` y `.reverse()` **mutan el array original**.

- El método `.sort()` 
  - Recibe como argumento una función de ordenación, de lo contrario ordena los elemtnos según codificación `Unicode`.
    ````javascript
    const values = [12, 110, 2]
    values.sort()             // [110, 12, 2]
    ````

- El método `.reverse()` 
  - Invierte el orden de los elementos presentes en el array.
    ````javascript
    const values = [2, 4, 6]
    values.reverse()          // [6, 4, 2]
    ````
 
## Main points: truthies VS falsies
Los valores _falsies_ (`null, undefined, false, NaN, 0, ''`) son rechazados por defecto en las estructuras condicionales. Todos los demás (_truthys_) son aceptados por defecto.

## Main points: deep copy
Es posible hacer una copia _profunda_ tanto de un objeto/array como de todos los objetos/arrays de su interior a través de la técnica `JSON.parse(JSON.stringify(myArray))`
