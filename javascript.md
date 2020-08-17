# Javascript Notes

## 'let' & 'var'

La palabra clave 'let' se introduce en ES2015 con 'const' para declarar una variable, pero si ya tenemos una 'var', entonces también necesitamos 'let'. Debido a que la variable declarar con 'dejar' no se puede volver a declarar, pero puede reaccionar como 'var'.
```
    let name = "JS Start";
```
La palabra clave 'var' se introduce antes de ES2015 y se usa para declarar una variable para almacenar información 'var' se puede declarar y asignar. 'var' puede ser alojado pero 'let' & 'const' no.
```
     var name = "JS Start";
```

### ReDeclare 'let' vs 'var'
```
    let name = "JS Start";
    let name = "JavaScript Starrt";
    // Esto no functiona

    var name = "JS Start";
    var name = "JavaScript Start";
    //Esto si funciona
```
### Hoisting 'let' vs 'var' 
```
    name = "JS Start";
    let name;
    // Esto no es compatible con Hoisting

    name = "JavaScript Start";
    var name;
    // Esto es compatible con hoisting
```
### Scoping-1
```
    let name = "JS Start";
    {
        let name = "JavaScript Start";
    }
    // Es compatible con el bloque Scooping
    console.log(name) // JS Start

    var name = "JS Start";
    {
        var name = "JavaScript Start";
    }
    // esto no es soportado con el blo que scoping
    console.log(name); // JavaScript Start
```

### Scoping-2
```
    let name = "JS Start";
    // esto no es compatible con scoping global
    console.log(window.name);// undefined

    var name = "JS Start";
    // Esto es compatible con scoping global
    console.log(window.name); // JS Start
```
## JavaScript ES6: API de matemáticas + número + cadena + matriz + objeto
Todo lo que necesita saber sobre ES6 https://morioh.com/p/f207ec2d8b2f?fbclid=IwAR1ahP0Wwe3Bvbq8yQghUMpvzwPqMK2WvrSQqsKNkWDdXVpAwUCFOMCQD5w
```
    Number.EPSILON //2.220446049250313e-16
    Number.isInteger(Infinity); //false
    Number.isNAN("NAN"); //false

    Math.acosh(3); //1.7627471740390859
    Math.hypot(3,4); //5
    Math.imul(Math.pow(2,32)-1,Math.pow(2,32)-2); //2

    "abcde".includes("cd"); //true
    "abc".repeat(3); //"abcabcabc"

    Array.from(document.querySelectorAll('*')); //devuelve una matriz
    Array.of(1,2,3); //[1, 2, 3] similar a la nueva matriz Array(...) pero sin un comportamiento especial de un argumento

    [0,0,0].fill(7,1); //[0, 7, 7]
    [5,6,7].find(x=>x==7); //7
    [1,2,3].findIndex(x=>x==2); //1
    [1,2,3,4,5].copyWithin(3,0); //[1, 2, 3, 1, 2]
    ["a","b","c"].entries(); //iterator [0,"a"], [1,"b"], [2,"c"]
    ["a","b","c"].keys(); //iterator 0, 1, 2
    ["a","b","c"].values(); //iterator "a", "b", "c"

    Object.assign(Point,{origin: new Point(0,0) })
```
## Consejos rapidos
### Filtrar valores unicos
```
    const array=[1,1,2,3,6,6,3,1];
    const uniqueArray=[...new Set(array)];
    console.log(uniqueArray); //[1, 2, 3, 6]
```
### Conversion a boolean
```
    const isTrue=!0;
    console.log(isTrue); //true

    const alsoFalse=!!0;
    console.log(alsoFalse); //false
```
### Conversion a string
```
    const val = 5 + "";
    // Result: "5";
    // typeof val: "string"
```
### Conversion a int
```
    let int = "15";
    int = +int;
    //Result: 15
    //typeof int: "number"
```
### conversion float a int
```
    const int = 19.8 | 0;
    //Result: 19
    //typeof int: "number"
```
### Remove last digits
```
    const int = 1553 / 10 | 0;
    //Result: 155
    //typeof int: "number"
```
### Truncar una matriz
```
    let array = [0, 1, 2, 3, 4, 5];
    array.length = 3;
    console.log(array);
    //Result: [0, 1, 2]
```
### Ultimo elemento de una matriz
```
    let array = [0, 1, 2, 3];
    array.slice(-1);
    // Result: [3]
```
## Metodos rapidos para matrices
### PUSH 
El método push () de matriz agrega nuevos elementos al final de una matriz y devuelve la nueva longitud de la matriz.
```
    let array = ["JS"];
    array.push("Start");
    console.log(array);
    ///Result: ["JS", "Start"]
```
### POP
El método array pop() elimina el último elemento de la matriz y devuelve el elemento eliminado y también cambia la longitud de la matriz.
```
    let array = ["JS", "Start"];
    array.pop(); 
    console.log(array); 
    // Result: ["JS"]
```
### UNSHIFT
El método unshift() de matriz agrega el nuevo elemento al comienzo de la matriz y devuelve la nueva longitud de la matriz.
```
    let array=["Start"];
    array.unshift("JS");
    console.log(array);
    //["JS", "Start"]
```
### SHIFT
El método array shift() elimina el primer elemento de la matriz y devuelve el elemento eliminado y también cambia la longitud de la matriz.
```
    let array = ["JS", "Start"];
    array.shift();
    console.log(array);
    // ["Start"]
```
### TOSTRING
El método array toString() convierte una matriz en una cadena y devuelve una cadena como resultado.
```
    const array = ["JS", "Start"];
    result = array.toString();
    console.log(result);
    // "JS,Start"
```
### SLICE
El método array slice() selecciona una parte de una matriz y devuelve una nueva matriz, pero la matriz original no cambia.
```
    const array = ["Like", "JS Start", "Share"];
    result = array.slice(1,2);
    console.log(result);
    // ["JS Start"]
```
### SPLICE
El método array splice() cambia el arreglo original eliminando o reemplazando el elemento existente. Y también puede agregar un nuevo elemento a la matriz.
```
    const array = ["Like", "Share", "Comment"];
    array.splice(2, 1, "JS Start");
    console.log(array);
    // ["Like", "Share", "JS Start"]
```
### INCLUDES
El método includes() de la matriz detecta si el elemento especificado existe en la matriz o no. Si existe, devuelve verdadero o falso.
```
    const array = ["JS", "Start"];
    result = array.includes("Start");
    console.log(result);
    // true
```
### SORT
El método array sort() ordena el elemento de una matriz y cambia la matriz original. De forma predeterminada, se clasifica en orden ascendente.
```
    const array = ["Start", "JS"];
    array.sort();
    console.log(array);
    // ["JS", "Start"]
```
### JOIN 
El método array join () crea y devuelve una nueva cadena concatenando todos los elementos de una matriz. también puede pasar una cadena de separación entre elementos.
```
    const array = ["JS", "Start"];
    result = array.join(" ");
    console.log(result);
    // JS Start
```