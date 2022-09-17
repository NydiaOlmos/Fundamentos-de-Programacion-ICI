# F-Strings
> El tema se abarcó durante la tercera y cuarta clase, así que decidí juntar los apuntes de ambas clases en un solo documento.
## Tercera clase
Introducción al tema.\
*Código*
```
n1 = 10 
msg = "Hola"

print(n1, msg)
print(str(n1)+msg) # Str = Convierte un entero a cadena.

print(f"\"{n1}\" {msg}") # \" Secuencia de escape.
```
*Impresión en pantalla:*

10 Hola\
10Hola\
<NO>"10" Hola

### Ejercicio
#### Planteamiento del problema
Hacer una función que reciba el nombre de una persona el año de nacimiento y el año actual retornando el mensaje: \
"Hola < nombre > tienes < edad > años"\
*Código*
```
def mensaje (name:str, a_nac: int, a_actual: int) -> str:
    return f"Hola {name} tienes {a_actual - a_nac} años."

def mensaje1 (name:str, a_nac: int, a_actual: int) -> str:
    edad = a_actual - a_nac
    return f"Hola {name} tienes {edad} años." # Otra forma de reprecentar lo de arriba.

def calcular_edad (a_nac: int, a_actual: int) -> int:
    return a_actual - a_nac

def mensaje2 (name: str, a_nac: int, a_actual: int) -> str:
    return f"Hola {name} tienes {calcular_edad(a_nac, a_actual)} años."

if __name__ == "__main__":
    nombre = input("¿Cuál es su nombre? ")
    a_nacimiento = input("¿En qué año naciste? ")
    a_actual = 2022
    print(mensaje(nombre, int(a_nacimiento), 2022)) # int = De cadena a entero.
    res = mensaje1("Nydia", 2002, 2022)
    print(res) # Otra forma de reprecentarlo.
    print(mensaje2("Regina", 2010, 2022))
```

*Input*
	
| Variable | Ingreso |
| ----------- | ----------- |
| nombre | Nydia |
| a_nacimiento | 2003 |
  
*Impresión en pantalla:*
  
¿Cuál es su nombre? Nydia
¿En qué año naciste? 2003\
Hola Nydia tienes 19 años. \
Hola Nydia tienes 20 años. \
Hola Regina tienes 12 años.
  
### F-strings y su comportamiento con las listas
*Código*
```
alumnos = ["Hugo", "Paco", "Luis", "Lupita"]

print(f"Alumnos: {alumnos}")

for i in range (len(alumnos)):# Longitud de la lista.
    print(f"Alumnos: {alumnos[i]}") # La forma de acceder a cada uno de los elementos en una lista, indice.
```
*Impresión en pantalla:*
  
Alumnos: ['Hugo', 'Paco', 'Luis', 'Lupita']\
Alumnos: Hugo\
Alumnos: Paco\
Alumnos: Luis\
Alumnos: Lupita
### F-strings y su comportamiento con las tuplas
La tupla es inmutable, a diferencia de la lista. Inmutable nos dice que, la tupla ya no puede crecer.\
*Código*
```
alumnos = ("Hugo", "Paco", "Luis", "Lupita") 
 
for i in range (len(alumnos)):# Longitud de la tupla.
    print(f"Alumno {i + 1}: {alumnos[i]}")
```
*Impresión en pantalla:*
  
Alumno 1: Hugo\
Alumno 2: Paco  \
Alumno 3: Luis  \
Alumno 4: Lupita
  
### F-strings y su comportamiento con los sets
En los sets no se pueden repetir los valores.\
*Código*
```
alumnos = {"Hugo", "Paco", "Luis", "Lupita"} 
# No funciona el querer dividirlo como en el ejemplo anteriro.
print(f"Alumno: {alumnos}")
```
*Impresión en pantalla:*
  
Alumno: {'Luis', 'Paco', 'Hugo', 'Lupita'}
### F-strings y su comportamiento con los diccionarios
*Código*
```
alumnos = {"Nombre" : "Hugo", "Materia1" : 10, "Materia2" : 5}
print(f"Alumno: {alumnos}")
print(f"Alumno: {alumnos['Nombre']}")
```
*Impresión en pantalla:*

Alumno: {'Nombre': 'Hugo', 'Materia1': 10, 'Materia2': 5}\
Alumno: Hugo
  
### Ejercicio
#### Planteamiento del ejercicio
Conocer la camtidad de datos repetidos que existen en una lista\
*Código*
```
numeros_list = [1,2,5,5,1,2,5,3,5,8,5,1]
numeros_set = {1,2,5,5,1,2,5,3,5,8,5,1}
print(numeros_list)
print(numeros_set)
largo_set = len(numeros_set)
largo_list = len(numeros_list)
print(largo_list - largo_set) # Para contar la cantidad de números repetidos.
```
*Impresión en pantalla:*

[1, 2, 5, 5, 1, 2, 5, 3, 5, 8, 5, 1]\
{1, 2, 3, 5, 8}\
7
  
### Pequeña base de datos
*Código 1*
```
e = ["Nombre", "Est_Dat", "Prog_Func", "Inglés"]
alumnos = ["Hugo Alberto", "Paco", "Luis", "Lupita"]
m_e_d = [9, 7, 9, 8]
m_p_f = [10, 8, 7, 9]
m_i = [6, 9, 7, 10]

ancho = 15 # Para evitar cambiar el 10 en todos lados.
# print(f"{e[0]:^10}{e[1]:^10}{e[2]:^10}{e[3]:^10}")
print(f"{e[0]:^{ancho}}{e[1]:^{ancho}}{e[2]:^{ancho}}{e[3]:^{ancho}}") # :< izquierda :> derecha :^ centrado
for i in range(len(alumnos)):
    print(f"{alumnos[i]:<{ancho}}{m_e_d[i]:^{ancho}}{m_p_f[i]:^{ancho}}{m_i[i]:^{ancho}}") # Números de espacios <">

```
*Impresión en pantalla:*

![screenshot de la terminal](https://user-images.githubusercontent.com/111654273/190879322-adb32b58-1560-49b8-89a9-cc44601eb18d.png)

*Código 2*
```
h = ["Nombre", "Est_Dat", "Prog_Func", "Inglés"]
alumnos = ["Hugo Alberto", "Paco", "Luis", "Lupita"]
m_e_d = [9, 7, 9, 8]
m_p_f = [10, 8, 7, 9]
m_i = [6, 9, 7, 10]


def reporte (ancho: int):
    print(f"{h[0]:^{ancho}}{h[1]:^{ancho}}{h[2]:^{ancho}}{h[3]:^{ancho}}")
    for i in range(len(alumnos)):
        print(f"{alumnos[i]:.<{ancho}}{m_e_d[i]:*^{ancho}}{m_p_f[i]:+>{ancho}}{m_i[i]:-^{ancho}}") # :*^, :.<, :+> Se rellenan los espacios vacíos con el símbolo.

if __name__ == "__main__":
    reporte(16)
```
*Impresión en pantalla:*
  
![screenshot de la terminal](https://user-images.githubusercontent.com/111654273/190879512-fa577e91-af4b-4755-be8e-53c803fae834.png)
## Cuarta clase
### F-Strings y su comportamiento con sistemas numéricos y números especiales 
*Código*
```
numero_Big = 123456789123456789
print(f"{numero_Big:,d}") # :,d Agrega la coma de separación en los números grandes.
numero_PI =3.141592678547898965865
print(f"{numero_PI:.4f}") # :.xf Recorta los decimales a la cantidad elegida.

# Notación científica. 
numero_PI =314.1592678547898965865
print(f"{numero_PI:e}") # :e Notación científica. 
print(f"{numero_PI:.2e}") # :.xe Recorte de decimales + notación científica.
# Porcentaje.
numero_porciento = 0.2584478585
print(f"{numero_porciento:%}")
print(f"{numero_porciento:.2%}")

#Números bianrios.
print(f"{25:b}") # :b Transforma en automático a binario.

# Unicosdes
print(f"{13:c}") # 13 es el enter // :c Código ascii.

# Hexadecimal
print(f"{255:x}") # :x Conversión a hexadecimal.

#Octal
print(f"{255:o}")
```
*Impresión en pantalla:*

123,456,789,123,456,789\
3.1416      \
3.141593e+02\
3.14e+02   \ 
25.844786%  \
25.84%      \
11001      

ff\
377
### Ejercicio
#### Planteamiento del problema
Escriba una función que genere una tabla de multiplicar recibiendo como argumentos la cantidad de números y la tabla a generar.\
*Código que realice*
```
def resultado (a: int, b: int) -> int:
    return a*b

def tabla (num: int, t1: int, fmt:int):
    for i in range(1, num+1):
        print(f"{t1:^{fmt}} * {i:^{fmt}} = {resultado(i, t1):^{fmt}}")

def n_tablas (lim_inf: int, lim_sup: int, num: int, fmt: int):
    for i in range(lim_inf, lim_sup+1):
        tabla(num, i, fmt)
        print("")

if __name__ == "__main__": 
    n_tablas(5, 10, 3, 5)
```
*Impresión en pantalla:*

![screenshot de la terminal](https://user-images.githubusercontent.com/111654273/190879701-12c27768-8c2f-4c29-b498-9e651fce8c32.png)\
*Código del maestro*
```
def producto (a: int, b: int) -> int: return a*b

def tablas(m:int, n:int, fmt: int):
    for i in range(1, m+1): # for i in range(número inicial, tope, incremento) //  Si no se específica se considera 1 automático.
        tabla(n, i, fmt)

def tabla(n: int, t: int, fmt: int):
    for i in range(1, n+1):
        print(f"{t:^{fmt}} X {i:^{fmt}} = {producto(i, t):^{fmt}}")
    print()

if __name__ == "__main__":
    tablas(3, 4, 6)
```
*Impresión en pantalla:*

![screenshot de la terminal](https://user-images.githubusercontent.com/111654273/190879738-666e6562-1fdd-40cf-b284-05455182a1d7.png)

