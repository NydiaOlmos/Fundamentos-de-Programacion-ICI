# Primera clase
>Introducción a las funciones y explicación del tipado dinámico de python.
## Apuntes y notas
Correcto uso de las funciones y el entry point.\
*Código:*
```
def suma(a,b):
    return a+b
def sumap(a,b): #Evitar el uso
    print(a+b)
def suma2(a:int,b:int)->int: # Recomendado. La flecha es el hind para indicar el tipo de valor que retorna.
    return a+b
def cuadrado(n: int|float)->int|float: return n*n

# entry point
if __name__ == "__main__":
    print(suma(2,2))
    print(cuadrado(2), cuadrado(2.2))
```
*Impresión en pantalla:*

4\
4 4.840000000000001


En realidad el "tipado dinámico" de python no es otra cosa que una buena memoria.\ 
Python en lugar de asignarle una dirección de memoria a las variables, le asigna la dirección de memoria a los datos.\

*Código*
```
x = 10
print(x, "addr: ",id(x))
x = "Hola"
print(x, "addr: ",id(x))
y = 10
print(y, "addr: ",id(y)) # Nota que tiene la misma dirección que la x original.

x = 1
print(x, ":", id(x))
x = x + 1
print(x, ":", id(x))
x = x + 1
print(x, ":", id(x))
x = x + 1
print(x, ":", id(x))
x = x + 1
print(x, ":", id(x))
x = x + 1
print(x, ":", id(x))
x = x + 1
print(x, ":", id(x))
x = x + 1
print(x, ":", id(x))
x = x + 1
print(x, ":", id(x))
x = x + 1
print(x, ":", id(x)) # Se genera una dirección diferente por cada número.

print(x:=10) # Operador tipo morsa.
```
*Impresión en pantalla:*

10 addr:  2068660027920\
Hola addr:  2068664904368\
10 addr:  2068660027920\
1 : 2068660027632\
2 : 2068660027664\
3 : 2068660027696\
4 : 2068660027728\
5 : 2068660027760\
6 : 2068660027792\
7 : 2068660027824\
8 : 2068660027856\
9 : 2068660027888\
10 : 2068660027920\
10

## Ejercicio
### Planteamiento del problema
1. Escribir una función que reciba un mensaje y un nombre y escriba en la pantalla "< mensaje > < nombre >".
2. Escribir una función que reciba el nombre y la edad de una persona.\
El mensaje de salida tiene que ser: "Hola < nombre > tienes < edad > años.
3. Escribir una función que reciba el año actual y el año de nacimiento, usando la función anterior que enviando esta como argumento obtengas el mensaje:\
 "Hola < nombre > tienes < edad > años."

*Código*
```
def mensaje1(msg:str, name:str):
    print(msg, name)

def saludo_con_edad(msg:str, name:str, age:int):
    return f"{msg} {name} tienes {age} años"

def cal_edad(a_actual:int, a_nacimiento:int)->int:
    return a_actual-a_nacimiento

if __name__ == "__main__":
    mensaje = "Hola"
    nombre = "Nydia"
    edad = 19
    mensaje1("Buen día", nombre)
    print(saludo_con_edad(mensaje, nombre, edad))
    print(saludo_con_edad(mensaje, nombre, cal_edad(2022,2003)))
```
*Impresión en pantalla:*

Buen día Nydia\
Hola Nydia tienes 19 años\
Hola Nydia tienes 19 años
