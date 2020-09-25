# Javascript Notes

## Variables

|                                  |                            |
| -------------------------------- | -------------------------- |
| var a;                           | variable                   |
| var b = "apple";                 | string                     |
| var c = "Hello" + " " + "world"; | "Hello world"              |
| var d = 1+2+"3";                 | "33"                       |
| var e = [1,4,6,8];               | array                      |
| var f = false;                   | boolean                    |
| var g = /()/;                    | RegEx                      |
| var h = function()();            | function onbject           |
| const PI = 3.14;                 | constant                   |
| var a = 1,b = 2, c = a + b;      | one line                   |
| let z = 'zzz';                   | block scope local variable |

## Data types

```js
var age = 18; //number
var name = "Dan"; //string
var name = { first: "Dan", last: "Fred" }; //object
var isReal = false; //boolean
var langs = ["Java", "JavaScript", "CSharp"]; //array
var a;
typeof a; //undefined
var a = null; //value null
```

## Strict mode

```js
"use strict"; //Utilice el modo estricto para escribir código seguro
x = 1; //Lanza un error porque la variable no está definida
```

## Loops

```js
//DO WHILE LOOP
var i = 1;                      //inicializa
do(                             //ingrese el ciclo al menos una vez
    i*= 2;                      //incremento para evitar un bucle infinito
    document.write(i+",");      //salida
)while(i<100)                   //repite el ciclo si la afirmación es verdadera al final
//BREAK
for(var i=0;i<10;i++){
    if(i==5){
        break;                  //se detiene si existe el ciclo
    }
    document.write(i+",");      //salidas
}
//CONTINUE
for(var i=0;i<10;i++){
    if(i==5){
        continue;                 //se salta el resto del ciclo
    }
    document.write(i+",");      //salto 5
}
//WHILE LOOP
var i=1;                        //inicializa
while(i<100){                   //entra en el ciclo si la afirmación es verdadera
    i*=2;                       //incremento para evitar un bucle infinito
    document.write(i + ",");    //salida
}
```

## If-Else

```js
if((age>=14)&&(age<19)){            //Condicion logica
    status = "en rango";            //condicion ejecutada si es verdadero
}else{                              //bloque else es opcional
    status = "fuera de rango";      //condicion ejecutada si es falso
}
// SWITCH STATEMENT
switch(new Date().getDay()){    //entrada dia
    case 6:                     //si es dia 6
        text = "Sabado";
        break;
    caso 0:                     //si es dia 0
        text = "domingo";
        break;
    default:                    //bloque else
        text = "no dia";
}
```

## 'let' & 'var'

La palabra clave 'let' se introduce en ES2015 con 'const' para declarar una variable, pero si ya tenemos una 'var', entonces también necesitamos 'let'. Debido a que la variable declarar con 'dejar' no se puede volver a declarar, pero puede reaccionar como 'var'.

```js
let name = "JS Start";
```

La palabra clave 'var' se introduce antes de ES2015 y se usa para declarar una variable para almacenar información 'var' se puede declarar y asignar. 'var' puede ser alojado pero 'let' & 'const' no.

```js
var name = "JS Start";
```

### ReDeclare 'let' vs 'var'

```js
let name = "JS Start";
let name = "JavaScript Starrt";
// Esto no functiona

var name = "JS Start";
var name = "JavaScript Start";
//Esto si funciona
```

### Hoisting 'let' vs 'var'

```js
name = "JS Start";
let name;
// Esto no es compatible con Hoisting

name = "JavaScript Start";
var name;
// Esto es compatible con hoisting
```

### Scoping-1

```js
let name = "JS Start";
{
  let name = "JavaScript Start";
}
// Es compatible con el bloque Scooping
console.log(name); // JS Start

var name = "JS Start";
{
  var name = "JavaScript Start";
}
// esto no es soportado con el blo que scoping
console.log(name); // JavaScript Start
```

### Scoping-2

```js
let name = "JS Start";
// esto no es compatible con scoping global
console.log(window.name); // undefined

var name = "JS Start";
// Esto es compatible con scoping global
console.log(window.name); // JS Start
```

## JavaScript ES6: API de matemáticas + número + cadena + matriz + objeto

Todo lo que necesita saber sobre ES6 https://morioh.com/p/f207ec2d8b2f?fbclid=IwAR1ahP0Wwe3Bvbq8yQghUMpvzwPqMK2WvrSQqsKNkWDdXVpAwUCFOMCQD5w

```js
Number.EPSILON; //2.220446049250313e-16
Number.isInteger(Infinity); //false
Number.isNAN("NAN"); //false

Math.acosh(3); //1.7627471740390859
Math.hypot(3, 4); //5
Math.imul(Math.pow(2, 32) - 1, Math.pow(2, 32) - 2); //2

"abcde".includes("cd"); //true
"abc".repeat(3); //"abcabcabc"

Array.from(document.querySelectorAll("*")); //devuelve una matriz
Array.of(1, 2, 3); //[1, 2, 3] similar a la nueva matriz Array(...) pero sin un comportamiento especial de un argumento

[0, 0, 0].fill(7, 1); //[0, 7, 7]
[5, 6, 7].find((x) => x == 7); //7
[1, 2, 3].findIndex((x) => x == 2); //1
[1, 2, 3, 4, 5].copyWithin(3, 0); //[1, 2, 3, 1, 2]
["a", "b", "c"].entries(); //iterator [0,"a"], [1,"b"], [2,"c"]
["a", "b", "c"].keys(); //iterator 0, 1, 2
["a", "b", "c"].values(); //iterator "a", "b", "c"

Object.assign(Point, { origin: new Point(0, 0) });
```

## Consejos rapidos

### Filtrar valores unicos

```js
const array = [1, 1, 2, 3, 6, 6, 3, 1];
const uniqueArray = [...new Set(array)];
console.log(uniqueArray); //[1, 2, 3, 6]
```

### Conversion a boolean

```js
const isTrue = !0;
console.log(isTrue); //true

const alsoFalse = !!0;
console.log(alsoFalse); //false
```

### Conversion a string

```js
const val = 5 + "";
// Result: "5";
// typeof val: "string"
```

### Conversion a int

```js
let int = "15";
int = +int;
//Result: 15
//typeof int: "number"
```

### conversion float a int

```js
const int = 19.8 | 0;
//Result: 19
//typeof int: "number"
```

### Remove last digits

```js
const int = (1553 / 10) | 0;
//Result: 155
//typeof int: "number"
```

### Truncar una matriz

```js
let array = [0, 1, 2, 3, 4, 5];
array.length = 3;
console.log(array);
//Result: [0, 1, 2]
```

### Ultimo elemento de una matriz

```js
let array = [0, 1, 2, 3];
array.slice(-1);
// Result: [3]
```

## Metodos para manejo de hora y fecha

### getDate()

Devuelve un número entero, entre 1 y 31, que representa el día del mes para la fecha indicada según la hora local.

```js
// Hoy es 23 de septiembre de 2020, Jueves
const date = new Date().getDate();
console.log(date);
// Resultado: 23
```

### getDay()

Devuelve un número entero, entre 0 y 6, correspondiente al día de la semana para la fecha indicada, 0 para el domingo, 1 para el lunes, 2 para el martes, etc.

```js
// Hoy es 23 de septiembre de 2020, Jueves
const day = new Date().getDay();
console.log(day);
// Resultado: 4
```

### getMonth()

Devuelve un número entero, entre 0 y 11, que representa el mes en la fecha indicada según la hora local.
0 corresponde a enero, 1 a febrero y si.

```js
// Hoy es 23 de septiembre de 2020, Jueves
const month = new Date().getMonth();
console.log(month);
// Resultado: 08
```

### getHours()

Devuelve un número entero, entre 0 y 23, que representa el correspondiente a la fecha indicada según la hora local.

```js
// 23:37
const hour = new Date().getHours();
console.log(hour);
// Resultado: 23
```

### getMinutes()

Devuelve un número entero, entre 0 y 59, que representa los minutos de la fecha indicada según la hora local.

```js
// 23:37
const minutes = new Date().getMinutes();
console.log(minutes);
// Resultado: 23
```

## Metodos rapidos para matrices

### PUSH

El método push () de matriz agrega nuevos elementos al final de una matriz y devuelve la nueva longitud de la matriz.

```js
let array = ["JS"];
array.push("Start");
console.log(array);
///Result: ["JS", "Start"]
```

### POP

El método array pop() elimina el último elemento de la matriz y devuelve el elemento eliminado y también cambia la longitud de la matriz.

```js
let array = ["JS", "Start"];
array.pop();
console.log(array);
// Result: ["JS"]
```

### UNSHIFT

El método unshift() de matriz agrega el nuevo elemento al comienzo de la matriz y devuelve la nueva longitud de la matriz.

```js
let array = ["Start"];
array.unshift("JS");
console.log(array);
//["JS", "Start"]
```

### SHIFT

El método array shift() elimina el primer elemento de la matriz y devuelve el elemento eliminado y también cambia la longitud de la matriz.

```js
let array = ["JS", "Start"];
array.shift();
console.log(array);
// ["Start"]
```

### TOSTRING

El método array toString() convierte una matriz en una cadena y devuelve una cadena como resultado.

```js
const array = ["JS", "Start"];
result = array.toString();
console.log(result);
// "JS,Start"
```

### SLICE

El método array slice() selecciona una parte de una matriz y devuelve una nueva matriz, pero la matriz original no cambia.

```js
const array = ["Like", "JS Start", "Share"];
result = array.slice(1, 2);
console.log(result);
// ["JS Start"]
```

### SPLICE

El método array splice() cambia el arreglo original eliminando o reemplazando el elemento existente. Y también puede agregar un nuevo elemento a la matriz.

```js
const array = ["Like", "Share", "Comment"];
array.splice(2, 1, "JS Start");
console.log(array);
// ["Like", "Share", "JS Start"]
```

### INCLUDES

El método includes() de la matriz detecta si el elemento especificado existe en la matriz o no. Si existe, devuelve verdadero o falso.

```js
const array = ["JS", "Start"];
result = array.includes("Start");
console.log(result);
// true
```

### SORT

El método array sort() ordena el elemento de una matriz y cambia la matriz original. De forma predeterminada, se clasifica en orden ascendente.

```js
const array = ["Start", "JS"];
array.sort();
console.log(array);
// ["JS", "Start"]
```

### JOIN

El método array join () crea y devuelve una nueva cadena concatenando todos los elementos de una matriz. también puede pasar una cadena de separación entre elementos.

```js
const array = ["JS", "Start"];
result = array.join(" ");
console.log(result);
// JS Start
```

## DECLARACION DE FUNCION

```js
function isEven(param) {
  return param % 2 === 0;
}
isEven(3); // output => false
isEven(4); // output => true
```

### FUNCION EXPRESION

```js
let isEven = function (param) {
  return param % 2 === 0;
};
isEven(3); // output => false
isEven(4); // output => true
```

### FUNCION CONTRUCTOR

```js
let param = "param";
let console = "consoole.log(param";
let get = new function(param, console);
console.log(get("JS"));// output => JS
```

### ARROW FUNCTION

```js
let isEven = (param) => {
  return param % 2 === 0;
};
isEven(3); // output => false
isEven(4); // output => true
```
