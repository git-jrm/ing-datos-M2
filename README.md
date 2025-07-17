# Portafolio Módulo 2 - Ingeniería de datos

Este es el portafolio del módulo 2 del bootcamp de fundamentos de Ingeniería de Datos.

En este espacio se reunen los ejercicios desarrollados en clases, link al repo del proyecto del módulo (PyLearningHub), así como también los conocimientos y experiencias aprendidas en el transcurso.

## Clase 1 - AE1

### #1 Calculadora básica
Construye un programa que simule una calculadora basica, pero cada operacion (suma, resta, multiplicacion, division) debe estar definida como una funcion diferente. Luego, crear una funcion principal que le pregunte al usuario que operacion desea realizar y la ejecute:
```Python
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
**💻 Terminal:**
```bash
$ python3 M2-06-02/01-calc.py
Elija opcion:   (1)+   (2)-   (3)*   (4)/   (5)Salir   : 1
Número 1: 10
Número 2: 33
Resultado: 43
Elija opcion:   (1)+   (2)-   (3)*   (4)/   (5)Salir   : 4
Número 1: 4
Número 2: 0
Error: División por cero
Elija opcion:   (1)+   (2)-   (3)*   (4)/   (5)Salir   : 5
```

Versión optimizada con `eval`:
```Python
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
**💻 Terminal:**
```Bash
$ python3 M2-06-02/01-calc2.py
```
```text
Elija opcion:   (1)+   (2)-   (3)*   (4)/   (5)Salir   : 2
Número 1: 100
Número 2: 99
Resultado: 1
Elija opcion:   (1)+   (2)-   (3)*   (4)/   (5)Salir   : 3
Número 1: 5
Número 2: 10
Resultado: 50
Elija opcion:   (1)+   (2)-   (3)*   (4)/   (5)Salir   : 5
```

### #2 Verifica mayor
```Python
nombre = input("Nombre: ")
edad = int(input("Edad: "))
if edad >= 18:
    print(f"Hola {nombre}, eres mayor de edad")
else:
    print(f"Hola {nombre}, eres menor de edad")
```
**💻 Terminal:**
```Bash
$ python3 M2-06-02/02-mayor.py

```
```text
Hola jose, eres mayor de edad
```

Versión estilizada con asignación de condicional:
```Python
nombre = input("Nombre: ")
edad = int(input("Edad: "))
mayor_de_edad = edad >= 18
if mayor_de_edad:
    print(f"Hola {nombre}, eres mayor de edad")
else:
    print(f"Hola {nombre}, eres menor de edad")
```
**💻 Terminal:**
```Bash
$ python3 M2-06-
```
```text

```

## Ejercicio clase 2 - AE2
### #1 Verifica beneficio
```Python
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
`operaciones.py`:
```Python
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

```
`main.py`:
```Python
import operaciones

print(operaciones.main())
```

## Ejercicio clase 4 - AE4
### #1 Promedio y aprobados
```Python
notas = []
notas = [80,60,50,48,59,85,69,47]
cantidad_notas = len(notas)
total_acumulado = 0
aprobaron = 0
aprobadas = []

for nota in notas:
    total_acumulado += nota
    if nota >= 60:
        aprobaron += 1
        aprobadas.append(nota)

# Cálcula promedio
promedio = total_acumulado / cantidad_notas

# Resultados
print(f"promedio: {promedio}")
print(f"aprobaron: {aprobaron}")
print(f"aprobadas: {aprobadas}")
```
### #2 Alumnos mayores y menores
```Python
emp = {
    'emp1': {'nombre': 'Ana', 'edad': 28},
    'emp2': {'nombre': 'Luis', 'edad': 35},
    'emp3': {'nombre': 'María', 'edad': 22},
    'emp4': {'nombre': 'Pedro', 'edad': 40},
}
menores = []

for k, v in emp.items():
    if v['edad'] > 30:
        print(f"{k} {v['nombre']} es mayor con {v['edad']} años")
    elif v['edad'] < 30:
        menores.append(v['nombre'])

print(f"menores: {menores}")
print(f"total: {len(emp)}")
```

## Ejercicio clase 5 - AE5
### #1 Modelado clase Auto (POO)
```Python
class Auto():
    ESTADOS_POSIBLES = {"detenido", "circulando", "estacionado", "dañado"}
    def __init__(self, estado, color, peso, tamaño, alto, largo, n_ruedas, n_puertas, tipo):
        self.estado = estado
        self.color = color
        self.peso = peso
        self.tamaño = tamaño
        self.alto = alto
        self.largo = largo
        self.n_ruedas = n_ruedas
        self.n_puertas = n_puertas
        self.tipo = tipo

    def arrancar(self):
        if self.estado == "detenido" or self.estado == "estacionado":
            self.estado = "circulando"
        else:
            print(f"imposible arrancar desde '{self.estado}'.")

    def frenar(self):
        if self.estado == "circulando":
            self.estado = "detenido"
        else:
            print("imposible frenar no circulando")

    def acelerar(self):
        if self.estado == "circulando":
            print("acelerando")
        else:
            print("imposible acelerar no circulando")

    def girar(self, direccion):
        if self.estado == "circulando":
            print(f"automóvil gira a {direccion}.")
        else:
            print("imposible girar no circulando")

    def estado_actual(self):
        print(f"Estado auto {self.color}: {self.estado}")

auto = Auto("detenido","rojo", 1200, "mediano", 1.5, 4.0, 4, 4, "sedán")
auto.frenar()
auto.estado_actual()
auto.arrancar()
auto.acelerar()
auto.girar("izquierda")
auto.girar("derecha")
auto.girar("izquierda")
auto.frenar()
auto.estado_actual()

auto2 = Auto("detenido","azul", 2900, "grande", 5.5, 7.0, 4, 4, "camioneta")
auto2.estado_actual()
auto2.arrancar()
auto2.acelerar()
auto2.girar("derecha")
auto2.frenar()
auto2.estado_actual()
```
### BONUS: diagrama UML clase Auto
```Python
# BONUS
def uml_clase_auto():
    print("UML de Clase: Auto\n")
    print("┌────────────────────────────┐")
    print("│           Auto             │")
    print("├────────────────────────────┤")
    print("│ - estado: str              │")
    print("│ - color: str               │")
    print("│ - peso: float              │")
    print("│ - tamaño: str              │")
    print("│ - alto: float              │")
    print("│ - largo: float             │")
    print("│ - n_ruedas: int            │")
    print("│ - n_puertas: int           │")
    print("│ - tipo: str                │")
    print("├────────────────────────────┤")
    print("│ + __init__(...)            │")
    print("│ + arrancar()               │")
    print("│ + frenar()                 │")
    print("│ + acelerar()               │")
    print("│ + girar(direccion)         │")
    print("│ + estado_actual()          │")
    print("└────────────────────────────┘\n")
    print("Atributo de clase:")
    print("• ESTADOS_POSIBLES = {'detenido', 'circulando', 'estacionado', 'dañado'}")

uml_clase_auto()
```

## Ejercicio clase 6 - AE6
### #1 Excepción personalizada en sistema biblioteca
```Python
class Libro:
    def __init__(self, titulo, autor, stock):
        self.titulo = titulo
        self.autor = autor
        self.stock = stock

class LibroNoDisponibleError(Exception):
    pass

class Biblioteca:
    def __init__(self):
        self.catalogo = {}

    def agregar_libro(self, libro):
        # self.catalogo[libro.titulo].append(libro) # error : KeyError
        self.catalogo[libro.titulo] = libro

    def prestar_libro(self, titulo):
        if titulo not in self.catalogo:
            raise ValueError("Libro no está en catálogo")
        libro = self.catalogo[titulo]
        if libro.stock > 0:
            libro.stock -= 1
            print(f"Libro prestado: {titulo}")
        else:
            raise LibroNoDisponibleError("No hay stock disponible")

biblioteca = Biblioteca()
libro1 = Libro("1984", "Orwell", 2)
libro2 = Libro("Brave New World", "Huxley", 2)
biblioteca.agregar_libro(libro1)
biblioteca.agregar_libro(libro2)

try:
    biblioteca.prestar_libro("1984")
    biblioteca.prestar_libro("1984")
    biblioteca.prestar_libro("1984") # Lanza Exception y no sigue
    biblioteca.prestar_libro("Brave New World")
except LibroNoDisponibleError as e:
    print("Error definido:", e)
except Exception as e:
    print("Error general:", e)
finally:
    print(f"El catálogo implementa tipo de dato: {type(biblioteca.catalogo)}")
    biblioteca = None
    libro1 = None
    libro2 = None
```
