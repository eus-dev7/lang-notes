# Python Notes

## Condicionales

Las estructuras de control condicionales, son las que nos permiten evaluar si una o mas condiciones se cumplen.

#### La evaluacion de condiciones solo puede resultar en uno de dos resultados(True o False)

```py
# Operadores relacionales
=     Igual que
!=    Distinto que
<     Menor que
>     Mayor que
<=    Menor o igual que
>=    Mayor o igual que
# Operadores relacionales
and   y
or    o
xor   O excluyente
```

## Iterativas

A diferencia de las estructuras de control condicionales, las iterativas (o bucles) nos permiten ejecutar un mismo codigo de manera repetida mientras se cumpla una condicion.

### Bucle for

El bule for, nos permite iterar sobre una variable compleja de tipo lista o tupla para cada uno de los elementos.

```py
frutas = ['manzana','naranja','uva']
for fruta in frutas:
                          # Acciones
```

Tambien podemos ocupar un rango para el for

```py
for a in range(start, stop, step):          # El rango inicia en el valor entero start, se detiene en el valor stop, y el step en el paso(el incremento en el rango)
                                            # Acciones
```

### Buble while

Se encarga de ejecutar una misma accion "mientras que" una condicion se cumpla.

```py
while varible_uno Comparacion variable_dos:
                                                # Acciones
  variable_uno +=1                              # Se incrementa el valor de esta variable en uno cada que se acciona el bucle.
```

Si el valor que condiciona no es numerico y no puede incrementarse podemos usar una estructura de control condicional anidada dentro del bucle, y frenar la ejecucion cuando el condicional deje de cumplirse con la palabra reservada 'break'

```py
while True:
                    # Acciones
  if Condicion:
    break           # fin del bucle
```

## Modulos empaquetados

Cada uno de nuestros archivos .py se denominan **modulos**.
Estos modulos, a la vez, pueden formar **paquetes**.

Un paquete es una carpeta que contiene los archivos .py.
Para esto debe contener un archivo de inicio llamado `__init__.py` . **Este archivo no necesita contener nada**.

```py
- Modulo.py         # Los modulos no necesariamente deben pertenecer a un paquete.
- Paquete
- - __init__.py
- - modulo1.py
- - subpaquete       # Los paquetes pueden contener subpaquetes.
- - - __init__.py
- - - modulo1.py
- - - modulo2.py
```

## Importando modulos enteros

El contenido de cada modulo, podra ser utilizado a la vez, por otros modulos. Para ello, es necesario **importar los modulos** que se requiera utilizar. Para importar se utiliza la instruccion **import**, seguida del nombre del paquete o modulo.

```py
import modulo                         # Importar un modulo
import paquete.modulo1                # Importar modulo dentro de un paquete
import paquete.subpaquete.modulo1     # Importar modulo dentro de un subpaquete
```

La instruccion **import** seguida de `nombre_del_paquete.nombre_del_modulo`, nos permite hacer uso de todo el codigo que dicho modulo contenga.
**Python tiene sus propios modulos**. Los cuales forman parte de su **libreria de modulos estandar**, que tambien pueden ser importados.

## Namespaces

Para **acceder** (Desde el modulo dunde se realizo la importacion), a cualquier elemento del modulo importado, se realiza mediante el **namespace**, seguido de un punto(.) y el nombre del elemento que se desee obtener.

```py
print modulo.CONSTANTE_1
print paquete.modulo1.CONSTANTE_1
print paquete.subpaquete.modulo1.CONSTANTE_1
```

## Alias

Es posible tambien abreviar los namespaces mediante un "alias". Para ello, durante la importacion, se asigna la palabra clave **as** seguida del alias con el cual nos referimos a ese namespace.

```py
import modulo as m
import paquete.modulo1 as pm
import paquete.subpaquete.modulo1 as psm

print m.CONSTANTE_1
print mp.CONSTANTE_1
print psm.CONSTANTE_1
```

## Importar modulos sin namespaces

En python es posible importar de un modulo solo los elementos que se desee utilizar. Para ello se utiliza la instruccion **from** seguida del namespace, mas la instruccion **import** seguida del elemento a importar.

```py
from paquete.modulo1 import CONST_1
print CONST_1
# ES POSIBLE IMPORTAR MAS DE UN ELEMENTO
from paquete.modulo1 import CONST_1, CONST_2
```

Para importar elementos desde modulos diferentes con los mismos nombre, hay que utilizar un alias.

```py
from paquete.modulo1 import CONST_1 as C1
from paquete.subpaquete.modulo1 import CONST_1 as CS1
```
