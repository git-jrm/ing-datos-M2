# Portafolio Módulo 2 - Ingeniería de datos

Este es el portafolio del módulo 2 del bootcamp de fundamentos de Ingeniería de Datos.

En este espacio se reunen los ejercicios desarrollados en clases, link al repo del proyecto del módulo (PyLearningHub), así como también los conocimientos y experiencias aprendidas en el transcurso.

## ejercicio clase 1

Calculadora básica: Construye un programa que simule una calculadora basica, pero cada operacion (suma, resta, multiplicacion, division) debe estar definida como una funcion diferente. Luego, crear una funcion principal que le pregunte al usuario que operacion desea realizar y la ejecute:

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
Versión optimizada con `eval`
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
