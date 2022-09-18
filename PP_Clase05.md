# Listas
> La quinta clase abarco todo lo relacionado con las listas.

Durante esta clase aprendí que Python es considerado un lenguaje orientado a objetos, además de contener un tipado dinámico y se un lenguaje interpretado.

Las listas son un objeto iterable (recorre sus elementos) de Python, en las cuales se puede meter todo tipo de datos.\
Son indexadas, lo que nos dice que trabaja con índices, en este caso iniciando con el índice 0.
```
lista1 = [1,2,3,4]
print(lista1)
lista2 = [1,3.4,"a",True,[4,5,6],(1,2,3),{8,"a",5.4}]
print(lista2)
print(len(lista1)) # Función que retorna el tamaño de un objeto.
print(lista2[6])
```
Imprime: \
[1, 2, 3, 4]\
[1, 3.4, 'a', True, [4, 5, 6], (1, 2, 3), {8, 5.4, 'a'}]\
4\
{8, 5.4, 'a'}

## Métodos de las listas
Append, extend e insert.
```
lista_cal = [] # Lista vacía.
print(lista_cal)
lista_cal.append(5) # Append es un método por retornar "none". Agrga elementos al final de la lista.
print(lista_cal)
lista_cal.append(8)
print(lista_cal)
lista_cal.extend([1,2,3,4]) # Extiende con otra lista.
print(lista_cal)
lista_cal.insert(0,6) # Cambia el dato de la posición 0 con un 6.
```
Imprime: \
[]\
[5]\
[5, 8]\
[5, 8, 1, 2, 3, 4]
## Ejercicio
### Planteamiento del problema
Rellenar una lista con los números naturales del 1 al 10.
```
l_num = []
for i in range(1,11):
    l_num.append(i)
print(l_num)
```
Imprime:\
[1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

## Índices negativos 
Conteo de índices en retroceso, siendo menos uno el primer (último) elemento en ser contado.
```
lista1 = [1,2,3,4]
print(lista1[-4])
```
Imprime:\
1
## Slices
También conocidas como rebanadas. Divide a las listas en, como su nombre lo dice, rebanadas.
```
lista1 = [1,2,3,4,5,6,7,8,9,10]
print(lista1)
print(lista1[:]) # [:] Lado izquiero el inicio, lado derecho el final.
print(lista1[0:10])
print(lista1[int(len(lista1)/2):])
print(lista1[:int(len(lista1)/2)])
print(lista1[0:-1])
print(lista1[3:7]) # El ultimo índice lo omite.
print(lista1[-7:-3])
```
Imprime:\
[1, 2, 3, 4, 5, 6, 7, 8, 9, 10]\
[1, 2, 3, 4, 5, 6, 7, 8, 9, 10]\
[1, 2, 3, 4, 5, 6, 7, 8, 9, 10]\
[6, 7, 8, 9, 10]\
[1, 2, 3, 4, 5]\
[1, 2, 3, 4, 5, 6, 7, 8, 9]\
[4, 5, 6, 7]\
[4, 5, 6, 7]
## Mutabilidad
```
lista1 = [1, "dos", 3, "cuatro"]
print(lista1)
# Las listas son mutables.
lista1[1] = 2 # Para modificar un dato, lo único que se necesita hacer es acceder al dato y modificarlo.
print(lista1)
lista2 = lista1 # Se guardan ambas listas en la misma dirección, por lo que si se modifica una se modifica la otra.
lista2 = lista1[:] # Forma correcta. Copia todos los elementos a una nueva lista asignando una nueva dirección de memoria.
print(f"{id(lista1)} Lista 1: {lista1}")
print(f"{id(lista2)} Lista 2: {lista2}")
lista2[1] = 2 # Lo mismo que .insert
print("-------------")
print(f"Lista 1: {lista1}")
print(f"Lista 2: {lista2}")
```
Imprime:\
[1, 'dos', 3, 'cuatro']\
[1, 2, 3, 'cuatro']\
2124547436032 Lista 1: [1, 2, 3, 'cuatro']\
2124547738112 Lista 2: [1, 2, 3, 'cuatro']\
-------------\
Lista 1: [1, 2, 3, 'cuatro']\
Lista 2: [1, 2, 3, 'cuatro']
## Borrar elementos
Uso de la función del().
```
lista1 = [0,1,2,3,4]
lista2 = [5,6,7]
lista1.extend(lista2)
print(lista1)
del lista1[0] # Rompe con la sintaxis de python por no necesitar los paréntesis a pesar de ser función.
print(lista1)
del (lista1[2:5])
print(lista1)
```
Imprime:\
[0, 1, 2, 3, 4, 5, 6, 7]\
[1, 2, 3, 4, 5, 6, 7]\
[1, 2, 6, 7]
## Ejercicio con slices
### Planteamiento del problema
Agregar varios elementos al final y al inicio de una lista con el uso de slices.
```
lista1 = [0,1,2,3,4]
lista2 = [5,6,7]
print(lista1)
print(lista2)
# Agregar varios datos al final con slices.
lista1[5:] = [5,6,7] 
print(lista1)
lista1[5:] = lista2
print(lista1)
lista1[len(lista1):] = lista2
print(lista1)
lista1.append(lista2) # Se agregaría como un solo elemento en lugar de 3.
print(lista1)
lista1.extend(lista2) # La opción más optima por estar optimizada.
print(lista1)

# Agragar varios datos al inicio de una lista.
lista1[:0] = lista2
print(lista1)
```
Imprime:\
[0, 1, 2, 3, 4]\
[5, 6, 7]\
[0, 1, 2, 3, 4, 5, 6, 7]\
[0, 1, 2, 3, 4, 5, 6, 7]\
[0, 1, 2, 3, 4, 5, 6, 7, 5, 6, 7]\
[0, 1, 2, 3, 4, 5, 6, 7, 5, 6, 7, [5, 6, 7]]\
[0, 1, 2, 3, 4, 5, 6, 7, 5, 6, 7, [5, 6, 7], 5, 6, 7]\
[5, 6, 7, 0, 1, 2, 3, 4, 5, 6, 7, 5, 6, 7, [5, 6, 7], 5, 6, 7]
