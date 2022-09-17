# Segunda clase
> Importar funciónes de otros módulos tanto en la misma como en diferente carpeta con el main.

## Módulos creados
### Suma.py
```
if __name__ == "__main__":
    pass

def suma(a: int | float, b: int | float) -> int | float:
    return a+b
```
### Resta.py
```
if __name__ == "__main__":
    pass

def resta(a: int | float, b: int | float) -> int | float:
    return a-b
```
### Multi.py
```
if __name__ == "__main__":
    pass

def multiplicar(a: int | float, b: int | float) -> int | float:
    return a*b
```
### Div.py
```
if __name__ == "__main__":
    pass

def dividir(a: int | float, b: int | float) -> int | float:
    return a/b
```
### Cuadrado.py
```
if __name__ == "__main__":
    pass

def cuadrado(a: int | float) -> int | float:
    return a*a
```
### Op_Variadas.py
```
def suma(a: int | float, b: int | float) -> int | float:
    return a+b


def resta(a: int | float, b: int | float) -> int | float:
    return a-b


def multiplicacion(a: int | float, b: int | float) -> int | float:
    return a*b


def division(a: int | float, b: int | float) -> int | float:
    return a/b


def cuadrado(a: int | float) -> int | float:
    return a*a
```
## Importar funciones desde scripts individuales
> Todos los scripts se encuentran en la misma carpeta que el main.

*Código*
```
import Suma as sm
import Resta as rs  # rs = "alias" de resta
import Multi as mp
import Div as dv
import Cuadrado as cd

if __name__ == "__main__":
    print(sm.suma(5, 6))
    print(rs.resta(8, 7))
    print(mp.multiplicar(2, 6))
    print(dv.dividir(10, 5))
    print(cd.cuadrado(8))
```
*Impresión en pantalla:*

11\
1\
12\
2.0\
64

## Importar desde un solo archivo
> EL scripts se encuentra en la misma carpeta que el main.

*Código*
```
from Op_Variadas import *

if __name__ == "__main__":
    print(suma(5, 6))
    print(resta(8, 7))
    print(multiplicacion(2, 6))
    print(division(10, 5))
    print(cuadrado(8))
```
*Impresión en pantalla:*

11\
1\
12\
2.0\
64

## Importar funciones desde una carpeta
> Todos los scripts se encuentran en la carpeta "Clase02Ope", carpeta diferenta a la que se encuentra el main.

*Código*
```
import Clase02Ope.Op_Variadas as op            # Importar todas las funciones desde un archivo
import Clase02Ope.Suma as s                   # Importar y redefinir una función individual
from Clase02Ope.Op_Variadas import multiplicacion    # Importar una sola función de un archivo con varias de estas

if __name__ == "__main__":
    print(s.suma(5, 6))
    print(op.resta(8, 7))
    print(multiplicacion(2, 6))
    print(op.division(10, 5))
    print(op.cuadrado(8))
```
*Impresión en pantalla:*

11\
1\
12\
2.0\
64
