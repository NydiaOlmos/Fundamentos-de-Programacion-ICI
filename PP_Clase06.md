# Sexta clase
> Por un compromiso que tuvo el maestro y el mal comportamiento de parte del alumando ésta clase fue recotada.\
> Durante la clase retomamoes el tema de funciones.

## Valores por defecto en funciones
Existen situaciones en donde no se requiere mandar la cantidad total de parámetros que exige una función, 
en este caso se asignan valores default a las variables de las funciones para evitar los errores. 
```
def div(a,b):
    return a/b

def suma(a, b, c=0): # Si solo se da 2 argumentos, c toma 0 por defecto.
    return a + b + c

def suma1(a, b = 0, c = 0): # Como a no está predefinida, la línea 27 marcará error.
    return a + b + c

a = 0
b = 2
# print(div(b,a)) #Por posicionamiento, da error.
print(div(b=2,a=0))
print(div(a,b))
print(suma(a,b))

print(suma(4,2))
print(suma(2,3,4))
#print(suma(b = 5, 4)) #Si inicias con un valor nombrado, ya no puedes poner los demás posicionados.
print(suma(4, b = 5)) # Funciona por que la a = 4 está en su posición.
print(suma1(b = 4))
```
Imprime:\
0.0\
0.0\
2\
6\
9\
9
