# Portafolio Módulo 2 - Ingeniería de datos

Este es el portafolio del módulo 2 del bootcamp de fundamentos de Ingeniería de Datos. 🚀

En este espacio se reunen los ejercicios y `Scripts` desarrollados en clases, los conocimientos y experiencias aprendidas en el transcurso del bootcamp.

Además en este módulo se realizó el proyecto [PyLearningHub](https://github.com/git-jrm/PyLearningHub).

## Índice:
- [Clase 1 - ejercicio 1 : Calculadora básica](#clase-1---ejercicio-1)
- [Clase 1 - ejercicio 2 : Verifica mayor](#clase-1---ejercicio-2)
- [Clase 2 - ejercicio 1 : Verifica beneficio](#clase-2---ejercicio-1)
- [Clase 3 - ejercicio 1 : Verifica beneficio modularizado](#clase-3---ejercicio-1)
- [Clase 4 - ejercicio 1 : Promedio y aprobados](#clase-4---ejercicio-1)
- [Clase 4 - ejercicio 2 : Alumnos mayores y menores](#clase-4---ejercicio-2)
- [Clase 5 - ejercicio 1 : Modelado clase Auto](#clase-5---ejercicio-1)
- [Clase 6 - ejercicio 1 : Excepción personalizada](#clase-6---ejercicio-1)
- [Evolución del Aprendizaje](#evolución-del-aprendizaje-)
- [Conclusión](#conclusión-)

## Clase 1 - ejercicio 1

### Calculadora básica 🧮
> Explicación : Se pide construir un programa que simule una calculadora basica, pero cada operacion (suma, resta, multiplicacion, division) debe estar definida como una funcion diferente. Luego, crear una funcion principal que le pregunte al usuario que operacion desea realizar y la ejecute:
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
**Instrucción 💻** ejecutar `$ python3 M2-06-02/01-calc.py`
```bash
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
**Instrucción 💻** ejecutar `$ python3 M2-06-02/01-calc2.py`
```Bash
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

> 💡 _Reflexión_ : Este ejercicio fue clave para comprender cómo estructurar funciones y controlar flujos básicos de programa según la entrada del usuario. También reforzó el manejo de errores como la división por cero. En ingeniería de datos, estas operaciones son esenciales para crear pipelines de transformación de datos mediante cálculos aritméticos.

[Volver](#portafolio-módulo-2---ingeniería-de-datos)

## Clase 1 - ejercicio 2

### Verifica mayor 🔞
> Explicación : Se pide un código que verifique la mayoría de edad:
```Python
nombre = input("Nombre: ")
edad = int(input("Edad: "))
if edad >= 18:
    print(f"Hola {nombre}, eres mayor de edad")
else:
    print(f"Hola {nombre}, eres menor de edad")
```
**Instrucción 💻** ejecutar `$ python3 M2-06-02/02-mayor.py`
```Bash
Nombre: jose
Edad: 33
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
**Instrucción 💻** ejecutar `$ python3 M2-06-02/02-mayor2.py`
```Bash
Nombre: jose
Edad: 33
Hola jose, eres mayor de edad
```

> 💡 _Reflexión_ : Practicamos condicionales simples con entrada del usuario. Aunque fue sencillo, se entiende mejor cómo organizar la lógica para tomar decisiones y mejorar la legibilidad y mantenibilidad del código. La validación de datos es fundamental en procesos ETL, donde debemos verificar que los datos cumplan criterios específicos antes de procesarlos.

[Volver](#portafolio-módulo-2---ingeniería-de-datos)

## Clase 2 - ejercicio 1

### Verifica beneficio ✅
> Explicación : Se pide un código que verifique los requisitos para acceder al beneficio, controlando excepciones.
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
**Instrucción 💻** ejecutar `$ python3 M2-06-04/ejer1-except.py`
```Bash
python3 M2-06-04/ejer1-except.py
Nombre:jose
Edad:33
País:chile
Hola Jose de chile si puede acceder al beneficio
```

> 💡 _Reflexión_ : Aquí aprendimos a validar entradas y a manejar errores con try/except. Esto es muy importante para evitar caídas inesperadas del programa y mejorar su robustez y confiabilidad. El manejo de errores try/except es crítico al procesar datasets reales que pueden contener valores faltantes o inconsistentes.

[Volver](#portafolio-módulo-2---ingeniería-de-datos)

## Clase 3 - ejercicio 1

### Verifica beneficio modularizado 🔧
> Explicación : Se pide modularizar el ejercicio anterior:
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
**Instrucción 💻** ejecutar `$ python3 M2-06-06/main.py`
```Bash    
Nombre:jose
Edad:33
País:chile
Hola Jose (33 años) de Chile, cumple: True
```

> 💡 _Reflexión_ : Modularizar el código es un paso indispensable ya que permite dividirlo en funciones y/o modulos reutilizables, lo cual mejora la organización, facilita el mantenimiento y prepara el programa para escalar. La modularización permite crear librerías de funciones de limpieza y validación que pueden reutilizarse en múltiples proyectos de datos.

[Volver](#portafolio-módulo-2---ingeniería-de-datos)

## Clase 4 - ejercicio 1

### Promedio y aprobados 📊
> Explicación : Se pide recorrer una lista y obtener promedio y aprobados:
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
**Instrucción 💻** ejecutar `$ python3 M2-06-09/ejer1.py`
```Bash
promedio: 62.25
aprobaron: 4
aprobadas: [80, 60, 85, 69]
```

> 💡 _Reflexión_ : En este ejercicio vimos cómo usar bucles y condicionales para analizar listas simples con datos. Y vimos maneras simples de clasificar la información, lo que es muy útil para reportes o análisis simples de información. Este tipo de análisis estadístico básico es la base para crear dashboards y reportes automáticos en sistemas de por ej: business intelligence.

[Volver](#portafolio-módulo-2---ingeniería-de-datos)

## Clase 4 - ejercicio 2

### Alumnos mayores y menores 👥
> Explicación : Se pide clasificar según edad del empleado:
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
**Instrucción 💻** ejecutar `$ python3 M2-06-09/ejer2.py`
```Bash
emp2 Luis es mayor con 35 años
emp4 Pedro es mayor con 40 años
menores: ['Ana', 'María']
total: 4
```

> 💡 _Reflexión_ : Este ejercicio fortalece el uso de diccionarios anidados para representar estructuras complejas. Aprendimos a recorrerlos y aplicar lógica condicional sobre sus valores para poder sacarle el máximo provecho a estas estructuras. Trabajar con estructuras de datos nos prepara para manejar JSONs y datasets anidados comunes en APIs y bases de datos NoSQL.

[Volver](#portafolio-módulo-2---ingeniería-de-datos)

## Clase 5 - ejercicio 1

### Modelado clase Auto (POO) 🚗
> Explicación : Se pide modelar clase Auto e implementar su uso:
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
**Instrucción 💻** ejecutar `$ python3 M2-06-11/ejer1-class.py`
```Bash
imposible frenar no circulando
Estado auto rojo: detenido
acelerando
automóvil gira a izquierda.
automóvil gira a derecha.
automóvil gira a izquierda.
Estado auto rojo: detenido
Estado auto azul: detenido
acelerando
automóvil gira a derecha.
Estado auto azul: detenido
```

### BONUS: diagrama UML clase Auto
> Explicación : Se pide adicionalmente generar diagrama UML:
```Python
# BONUS
def uml_clase_auto():
    print("Diagrama UML de clase Auto:   ")
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
**Instrucción 💻** ejecutar `$ python3 M2-06-11/ejer1-class2.py`
```Bash
Diagrama UML de clase Auto:
┌────────────────────────────┐
│           Auto             │
├────────────────────────────┤
│ - estado: str              │
│ - color: str               │
│ - peso: float              │
│ - tamaño: str              │
│ - alto: float              │
│ - largo: float             │
│ - n_ruedas: int            │
│ - n_puertas: int           │
│ - tipo: str                │
├────────────────────────────┤
│ + __init__(...)            │
│ + arrancar()               │
│ + frenar()                 │
│ + acelerar()               │
│ + girar(direccion)         │
│ + estado_actual()          │
└────────────────────────────┘

Atributo de clase:
• ESTADOS_POSIBLES = {'detenido', 'circulando', 'estacionado', 'dañado'}
```

> 💡 _Reflexión_ : Modelar con clases nos permite aplicar los principios de la POO. Entendimos cómo encapsular datos y comportamientos en objetos, y cómo definir comportamientos para simular un caso del mundo real. La POO permite modelar entidades de negocio reales, facilitando la creación de sistemas de gestión de datos útiles enfocados en el negocio.

[Volver](#portafolio-módulo-2---ingeniería-de-datos)

## Clase 6 - ejercicio 1

### Excepción personalizada en sistema biblioteca 📚
> Explicación : Se pide implementar una excepción personalizada que controle cuando un libro no está disponible: 
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
**Instrucción 💻** ejecutar `$ python3 M2-06-13/ejer1.py`
```Bash
Libro prestado: 1984
Libro prestado: 1984
Error definido: No hay stock disponible
El catálogo implementa tipo de dato: <class 'dict'>
```

> 💡 _Reflexión_ : Con este ejercicio entendimos cómo capturar excepciones completamente personalizadas, lo cual es simple y potente. Este ejercicio nos enseña la importancia de anticipar errores y mejorar la robustez del sistema. La creación de excepciones nos permite identificar errores específicos mejorando la visibilidad del sistema.

[Volver](#portafolio-módulo-2---ingeniería-de-datos)


## Evolución del Aprendizaje 📈

En este módulo repasamos desde conceptos básicos de programación (calculadora) hasta dominar POO y manejo avanzado de errores. La progresión fue:
- **Fundamentos**: Funciones y condicionales
- **Robustez**: Manejo de errores y validación
- **Escalabilidad**: Modularización y reutilización
- **Modelado**: POO para representar entidades complejas

Este crecimiento logrado a lo largo de todas las actividades, trabajos y ejercicios, ha sido secuencial y ha ido de menos a más.

[Volver](#portafolio-módulo-2---ingeniería-de-datos)

## Conclusión 🌟

Este **Módulo 2** ha sido un pilar fundamental en nuestra formación, consolidando desde los principios básicos de la programación hasta la maestría en Programación Orientada a Objetos y el manejo avanzado de excepciones. Cada ejercicio y reflexión ha forjado una base sólida, transformando el conocimiento teórico en habilidades prácticas esenciales.

Este crecimiento logrado a lo largo de todas las actividades nos prepara no solo para los siguientes módulos, sino para enfrentar desafíos reales y construir sistemas robustos y escalables en el manejo del lenguaje Python en diversos escenarios de ingeniería de datos. ¡Estamos listos para el próximo nivel! 

[Volver](#portafolio-módulo-2---ingeniería-de-datos)







