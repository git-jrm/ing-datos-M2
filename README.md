# Portafolio Módulo 2 - Ingeniería de datos

Este es el portafolio del módulo 2 del bootcamp de fundamentos de Ingeniería de Datos.

En este espacio se reunen los ejercicios desarrollados en clases, link al repo del proyecto del módulo (PyLearningHub), así como también los conocimientos y experiencias aprendidas en el transcurso.

## Clase 1 - AE1
### #1 Calculadora básica
Construye un programa que simule una calculadora basica, pero cada operacion (suma, resta, multiplicacion, division) debe estar definida como una funcion diferente. Luego, crear una funcion principal que le pregunte al usuario que operacion desea realizar y la ejecute:
```
ops = {1: '+', 2: '-', 3: '*', 4: '/'}

def suma(a, b):
    return a + b
def resta(a, b):
    return a - b
def mult(a, b):
    return a * b
def div(a, b):
    return a / b

while True:
    op = int(input("Elija opcion:   (1)+   (2)-   (3)*   (4)/   (5)Salir   : "))
    if op == 5: break
    if op not in ops: continue

    a, b = int(input("Número 1: ")), int(input("Número 2: "))

    if op == 4 and b == 0:
        print("Error: División por cero")
    else:
        if op == 1: print(f"Resultado: {suma(a, b)}")
        elif op == 2: print(f"Resultado: {resta(a, b)}")
        elif op == 3: print(f"Resultado: {mult(a, b)}")
        elif op == 4: print(f"Resultado: {div(a, b)}")
        #print(f"Resultado: {eval(f'{a}{ops[op]}{b}')}")
```
Versión optimizada con `eval`:
```
ops = {1: '+', 2: '-', 3: '*', 4: '/'}

def suma(a, b):
    return a + b
def resta(a, b):
    return a - b
def mult(a, b):
    return a * b
def div(a, b):
    return a / b

while True:
    op = int(input("Elija opcion:   (1)+   (2)-   (3)*   (4)/   (5)Salir   : "))
    if op == 5: break
    if op not in ops: continue

    a, b = int(input("Número 1: ")), int(input("Número 2: "))

    if op == 4 and b == 0:
        print("Error: División por cero")
    else:
        print(f"Resultado: {eval(f'{a}{ops[op]}{b}')}")
```
### #2 Verifica mayor
```
nombre = input("Nombre: ")
edad = int(input("Edad: "))
if edad >= 18:
    print(f"Hola {nombre}, eres mayor de edad")
else:
    print(f"Hola {nombre}, eres menor de edad")
```
Versión estilizada con asignación de condicional:
```
nombre = input("Nombre: ")
edad = int(input("Edad: "))
mayor_de_edad = edad >= 18
if mayor_de_edad:
    print(f"Hola {nombre}, eres mayor de edad")
else:
    print(f"Hola {nombre}, eres menor de edad")

```

## Ejercicio clase 2 - AE2
### #1 Verifica beneficio
```
nombre = input("Nombre:").capitalize()
edad_str = input("Edad:")
try:
    edad = int(edad_str)
except ValueError:
    print(f"edad no valida: {edad_str}")
    exit()
paises = ["chile", "argentina", "colombia"]
pais = input("País:").lower()
elegible = edad >= 18 and pais in paises

if elegible:
    print(f"Hola {nombre} de {pais} si puede acceder al beneficio")
else:
    print(f"Hola {nombre} de {pais} no puede acceder al beneficio")
```
## Ejercicio clase 3 - AE3
### #1 Verifica beneficio modularizado
```
def ingreso():
    nombre = input("Nombre:").capitalize()
    edad_str = input("Edad:")
    try:
        edad = int(edad_str)
    except ValueError:
        print(f"** ERROR: {nombre} tiene edad no valida: {edad_str}")
        edad = 0
    pais = input("País:").capitalize()
    return nombre, edad, pais

def elegible(edad, pais):
    paises = ["Chile", "Argentina", "Colombia"]
    elegible = edad >= 18 and pais in paises
    return elegible

def mensaje(nombre, edad, pais, elegible):
    return f"Hola {nombre} ({edad} años) de {pais}, cumple: {elegible}"

def main(**args):
    if(args):
        nombre = args.get("nombre", "").capitalize()
        edad = args.get("edad", 0)
        try:
            edad = int(edad)
        except ValueError:
            print(f"** ERROR: {nombre} tiene edad no valida: {edad}")
            edad = 0
        pais = args.get("pais", "").capitalize()
    else:
        nombre, edad, pais = ingreso()
    es = elegible(edad, pais)
    print(mensaje(nombre, edad, pais, es))

main() # SIN PARAMETROS
main(nombre="LAURA", edad="30", pais="ESPAÑA")
main(nombre="fELIPE", edad="veinte", pais="CHILE")
main(pais="Colombia", edad=40, nombre="JUan")
```
## Ejercicio clase 4 - AE4
### #1 
```
```
## Ejercicio clase 5 - AE5
### #1 
```
```
## Ejercicio clase 6 - AE6
### #1 
```
```
