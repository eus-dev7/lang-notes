# Python Notes

## Condicionales

Las estructuras de control condicionales, son las que nos permiten evaluar si una o mas condiciones se cumplen.

#### La evaluacion de condiciones solo puede resultar en uno de dos resultados(True o False)

**Operadores relacionales**

| Operador | Descripcion       |
| -------- | ----------------- |
| =        | Igual que         |
| !=       | Distinto que      |
| <        | Menor que         |
| >        | Mayor que         |
| <=       | Menor o igual que |
| >=       | Mayor o igual que |

**Operadores relacionales**

| Operador | Descripcion  |
| -------- | ------------ |
| and      | y            |
| or       | o            |
| xor      | O excluyente |

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

La importacion de modulos debe realizarse al comienzo del documento, en orden alfabetico de paquetes y modulos.

## Manejo de archivos

#### Operaciones permitidas

| Operacion | Descripcion                             |
| --------- | --------------------------------------- |
| r         | Lectura                                 |
| r+        | Lectura/Escritura                       |
| w         | Sobreescritura. Si no existe se creara  |
| a         | Añadir. Se escribe al final del archivo |
| b         | Binario                                 |
| +         | Permite lectura/escritura simultanea    |
| U         | Salto de linea universal                |
| rb        | Lectura binaria                         |
| wb        | Sobreescritura binaria                  |
| r+b       | Lectura/Escritura binaria               |

#### Abrir y cerrar archivos

Para poder abrir un archivo se utiliza **Open()** indicando su ubicacion y nombre, segundo opcionalmente por el modo de operacion y la codificacion del archivo.

Si no se indica el modo, por defecto se abrira en modo lectura y se utilizara la codificacion por defecto del sistema. Si existe algun error se producira una excepcion de tipo **IOerror**.

Para cerrar el archivo se utiliza el metodo **close()**

```py
ObjFile = open('dir/file.txt')
ObjFile = open('dir/file.txt','r')
ObjFile = open('dir/file.txt',mode='r',encoding='utf-8')

ObjFile.close()
```

#### with-as

**with-as** permite usar los archivos de forma optima cerrandolos y liberando memoria al concluir el proceso de lectura.

No es necesario llamar al metodo **close()** al final.

```py
# Abrimos el archivo y cerramos conforme se termina de leer
with open('file.txt') as file:
  # Recorremos linea por linea
  for line in file:
    # Imprimimos la ultima linea leida
    print(line)
```

#### Metodo read

Con el metodo **read()** es posible leer un numero de bytes determinados.
Si no se indica un numéro se leerá todo lo que reste o si se alcanzó el final del archivo se devolverá una cadena vacia

```py
# Abrimos el archivo en modo lectura
file = open('file.txt','r')

# Se inicia un ciclo para leer linea por linea
while True:
  # Se lee la linea actual
  line =  file.readline()
  if not line:
    # Si no hay lineas se rompe el bucle
    break
  print(line)

file.close()
```

#### Metodo readlines

El metodo readlines lee todas las lineas de un archivo como una lista, Si se indica el parametro de tamaño leera esa cantidad de bytes del archivo y lo necesario hasta completar la ultima linea.

```py
# Abrimos un archivo en modo lectura
file = open('file.txt','r')
# Leemos todas las lineas y asignamos a una lista
list = file.readlines()
# Iniciamos un contador
numln = 0
# Recorremos todos los elementos de la lista
for line in list:
  # Incrementamos el contador
  numln += 1
  # Mostramos la posicion y la linea de la lista
  print(numln,line)
file.close()
```

## Redes neuronales

### Perceptron

Parte 1

```py
import numpy as np
class Perceptron:
  # PARTE 1
  # Definimos el contructor de nuestra clase Perceptron, que recibira dos parametros:
  # N: Es la cantidad de columnas en nuestros vectores de entrada.
  # alpha: es el porcentaje de aprenndizaje del Perceptron. Podemos definir este valor por defecto 0.01, otros valores normales son en el rango de α = 0.1, 0.01, 0.001.
  def __init__(self, N, alpha=0.1):
    # Almacenamos nuestra matriz de peso W con valores aleatorios muestreados de una distribucion normal.
    # La matriz de ponderaciones tendra N+1 entradas, una para cada una de las N entradas en el vector de caracteristicas, mas una para el sesgo.
    # Dividimos W por la raiiz cuadrada del numero de entradas
    self.W = np.random.randn(N+1)/np.sqrt(N)
    self.alpha = alpha
  # La funcion de paso retorna 1 si es positiva, cualquier otroo caso retorna 0
  def step(self, x):
    return 1 if x > 0 else 0

  # PARTE 2
  # El metodo fit requiere 3 parametros:
  # X: Es el valor actual de nuestros datos de entrenamiento.
  # Y: E la variable objetivo de salida(la prediccion).
  # epochs: La cantidad de veces que nuestro perceptron sera entrenado.
  def fit(self, X, epochs=10):
    # Comenzamos a recorrer la cantidad de veces que queremos entrenar nuetro preceptron. En cada vuelta tambien recorremos cada punto de datos individual de X.
    # El valor de X son nuestros valores reales de entrenamiento, la variable Y son nuestras etiquetas de clase de salida de destino(los valores que el perceptron deberia aprender)
    # Obtenemos el producto escalar entre las caracteristicas de entrada X y la matriz de peso W, pasamos dicho valor a la funcion de paso del perceptron para obtener la prediccion.
    X = np.c_[X, np.ones((X.shape[0]))]
    for epoch in np.arange(0, epochs):
      for (x, target) in zip(X, y):
        p = self.step(np.dot(x, self.W))
        # Aqui se realiza una actualizacion del peso (W) solo si la prediccion no coincide con el objetivo de salida. Si nno coincide determinamos el error calculando su signo (positivo o negativo) mediante una operacion de diferenncia.
        # La actualizacion de la matriz de paso se realiza escalando este valor por nuestra tasa de aprendizaje alfa
        if p != target:
          error = p - target
          self.W += -self.alpha * errror * x
  # PARTE 3
  # Nuestro metodo de prediccion requiere un conjunto de datos de entrada X que deben clasificarse
  # Se realiza una verificacion para verificar si es necesario agregar una columna de sesgo.
  def predict(self, X, addBias=True):
    # Para obtener las predicciones de salida se X se debe realizar el mismo procedimiento que en el  entrenamiento.  Simplemente se toma el producto escalar entra las caracteristicas de entrada X y la matriz de peso W
    X = np.atleast_2d(X)
    if addBias:
      X = np.c_[X, np.ones((X.shape[0]))]
    # Finalmente se pasa el valor a travez de la funcion de paso y se retorna a la funcion de llamada.
    return self.step(np.dot(X, self.W))
```

```py
# PARTE 4
import numpy as np

# Definimos dos arreglos conn los valores reales de entrada y salida de unna compuerta logica, en este caso es una compuerta OR.
X = np.array([[0, 0],[0, 1],[1, 0],[1, 1]])
y = np.array([[0],[1],[1],[1]])
# Iniciamos el entrenamiento de nuestro perceptron solo usando los datos de entreda. Como dato adicional definimos que sera entrenando durante 20 ciclos con un porcentaje de aprendizaje igual a 0.1.
p = Perceptron(X.shape[1], alpha=0.1)
p.fit(X, y, apochs=20)
# Una vez entrenado el perceptron vamos a usarlo para predecir las salidas de la compuerta, usando los mismos valores de entreda usaremos el metodo predict para obtener los valores predichos por el perceptron.
for (x, target) in zip(X, y):
  pred = p.predict(x)
  print("Resultado: entradas={}, valor real={}, valor predicho={}".format(x, target[0], pred))

# RESULTADOS
# OR
# Resultado entradas=[0 0], valor real=0, valor predicho=0
# Resultado entradas=[0 1], valor real=1, valor predicho=1
# Resultado entradas=[1 0], valor real=1, valor predicho=1
# Resultado entradas=[1 1], valor real=1, valor predicho=1
# AND
# Resultado entradas=[0 0], valor real=0, valor predicho=0
# Resultado entradas=[0 1], valor real=0, valor predicho=0
# Resultado entradas=[1 0], valor real=0, valor predicho=0
# Resultado entradas=[1 1], valor real=1, valor predicho=1
# XOR
# Resultado entradas=[0 0], valor real=0, valor predicho=1
# Resultado entradas=[0 1], valor real=1, valor predicho=0
# Resultado entradas=[1 0], valor real=1, valor predicho=0
# Resultado entradas=[1 1], valor real=0, valor predicho=0
```
