# Variables

## Qué es una variable?

Una variable es un lugar en memoria para guardar un dato

Es como si fuera un cajón, donde lo que se guarda adentro es un dato

Todos los datos se guardan desordenados en memoria, las variables le dicen al programa dónde está ese dato

Todos los datos tienen un tipo, y en Java (y muchos otros lenguajes) se tiene que indicar qué tipo de dato puede guardar una variable. Eso se llama que el lenguaje de programación es *tipado*.

## Tipos de datos

Hay muchos tipos de datos, que se dividen en 2 categorías, los *primitivos* y los *no primitivos*.

Los primitivos son más sencillos, y en general funcionan muy parecidos entre sí. Los no primitivos son especiales, y se implementan distinto. No es importante acordarse esto, pero si querés implementar datos no primitivos vas a ver que se tiene que hacer distinto, y este es el motivo.

### Datos primitivos

> Los importantes (que se usan seguido) los pongo en *cursiva*

| Tipo de dato | Tamaño  | Descripción                                                                          |
|--------------|---------|--------------------------------------------------------------------------------------|
| byte         | 1 byte  | Guarda números enteros desde -128 to 127                                             |
| short        | 2 bytes | Guarda números enteros desde -32,768 to 32,767                                       |
| *int*        | 4 bytes | Guarda números enteros desde -2,147,483,648 to 2,147,483,647                         |
| long         | 8 bytes | Guarda números enteros desde -9,223,372,036,854,775,808 to 9,223,372,036,854,775,807 |
| float        | 4 bytes | Guarda números racionales con hasta 6 o 7 digitos decimales                          |
| *double*     | 8 bytes | Guarda números racionales con hasta 15 digitos decimales                             |
| *boolean*    | 1 bit   | Guarda un valor `true` o `false` (SI o NO)                                              |
| *char*       | 2 bytes | Guarda un solo caracter ([ASCII](https://www.rapidtables.com/code/text/ascii-table.html))                                                             |

Ejemplo:

```Java
int myNum = 5;               // Número entero
double myDoubleNum = 5.99;   // Número decimal
char myLetter = 'D';         // Caracter
boolean myBool = true;       // Valor booleano
int numeroVacío;             // Variable int vacía
String myText = "Hello";     // String (??????)
```

Con el ejemplo aprendemos varias cosas:

- Cómo se crea una variable
  - `TipoDeDato NombreDeVariable = ValorInicial;`
- No se puede crear una variable sin tipo
- El valor inicial es opcional
  - Se le puede asignar valor más adelante
  - El tipo de dato tiene que coincidir con el tipo de variable
- Todas las líneas de código terminan con un punto y coma (;)
  - Esto le indica al programa dónde termina una instrucción y empieza otra
  - No todos los lenguajes necesitan, Java sí
- Al final de una línea se *puede poner* (si se necesita) un comentario,
  - Se marcan con las 2 barras (//) solo al principio
  - El programa no los detecta como instrucciones, y no hace nada
  - El salto de línea (enter) marca el final del comentario
    - Esto quiere decir que no se puede poner una instrucción *después* de un comentario en la misma línea
  - Hay otra manera de hacer comentarios de varias líneas, no es relevante.
- El valor de una variable de tipo `char` se escribe entre comillas simples

### Qué es el `String`

El tipo de dato `String` es un tipo de datos no primitivo, por ende es un poco más complejo en cuanto al funcionamiento interno (cosas que no nos importan) y a cómo lo implementamos (que sí que nos importa).

**String va con S mayuscula!!!!**

Usando comillas dobles, podés guardar texto en una variable de tipo `String`

### ¿Qué pasa si no uso comillas?

**EXPLOTA TODO 💥💥💥**

¿Por qué? Veamos el siguiente ejemplo

```java
String var1 = "Pedro";
String var2 = var1;
var1 = "Manuela";
String var3 = juan
```

Qué estoy haciendo acá?

1. Creo la variable `var1` y le pongo de valor "Pedro"
2. Creo la variable `var2` y le digo que ponga el valor de la variable `var1`
   - Esto va a copiar el valor de `var1` y ponerlo en `var2`
3. A la variable `var1` (que ya existe) le estoy cambiando el valor a "Manuela"
   - El valor de `var2` sigue siendo "Pedro"
4. Creo la variable `var3` y le digo que ponga el valor de la variable `juan`
   - Busca la variable `juan` y no la encuentra, no sabe qué valor ponerle, y explota

> Esto pasa con todos los tipos de variables

## No viene al caso pero ¿qué es el main?

El main es una función, lo van a ver más adelante. Lo que importa por ahora es que ahí adentro va el código.

```java
// Acá no escribas tu código

public static void main(String[] args) {
    // Escribí tu código acá
}

// Acá tampoco
```

Cuando quieras ejecutar tu programa, el *compilador* (que es lo que lee tu programa y lo traduce a idioma compu para que se pueda ejecutar) va a ir a buscar tu código adentro de ese `main`, si lo dejan afuera el compilador no lo va a encontrar. El compilador lee todo, pero cuando tiene que ver qué hacer va a buscar adentro del main y al resto no le va a dar bola.
