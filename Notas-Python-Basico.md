# Notas de Python nivel basico

## Variables:

Python es un lenguaje de programacion el cual infiere los tipos de las variables; es decir, no es necesario declarar el tipo de variable al ser creada.

```python
a=1
b=1.5
c="Hola!"
d=True
e=None
```

Como podemos observar en el codigo anterior, los tipos que se muestran son los siguientes:

- int: Se refiere a un numero entero.
- float: Se refiere a un numero decimal.
- char: Se refiere a un caracter.
- string: Se refiere a un conjunto de caracteres.
- Boolean: Se refiere a un valor que puede ser 'True' o 'False' .

Ahora veamos un ejemplo de codigo en el cual primero se solicita el nombre de la persona y luego se hace un programa que retorna un saludo para esa persona

```python
name=input("Name: ")
print("Hola, " + name)
```

## Cadenas de formato

Mientras que el acapite anterior se observa que podemos usar `=` para concatenar palabras, existen formas mas faciles de realizar esta tarea con cadenas de formato, a continuacion se muestra un ejemplo.

```python
print(f"Hello, {input("Name: ")}")
```

Se debe tener en cuenta que la funcion input siempre retorna un valor del tipo string.

## Condicionales

```python
num = int(input("Number: "))
if num > 0:
    print("Number is positive")
elif num < 0:
    print("Number is negative")
else:
    print("Number is 0")
```

En la anterior pieza de codigo se agrega el `int()` debido a que se requiere que el dato ingresado sea un numero.

## Secuencias

### Strings
*Ordered:* Yes

*Mutable:* No

```Python
name = "Harry"
print(name[0])
print(name[1])
```

Este codigo imprime la primera y la segunda letra de la palabra Harry respectivamente.

### Lists
*Ordered:* Yes

*Mutable:* Yes

Como se puede observar en el siguiente ejemplo en las listas se puede imprimir la lista completa o los elementos. Ademas, se pueden agregar nuevos elementos a la lista con `append` e incluso ordenar la lista usando `sort()`

```Python
# This is a Python comment
names = ["Harry", "Ron", "Hermione"]
# Print the entire list:
print(names)
# Print the second element of the list:
print(names[1])
# Add a new name to the list:
names.append("Draco")
# Sort the list:
names.sort()
# Print the new list:
print(names)
```

![image](https://user-images.githubusercontent.com/54380137/116915227-5f67ed00-ac11-11eb-92d3-aca7964a2d5a.png)

### Tuples
*Ordered:* Yes

*Mutable:* No

Se usan generalmente cuando necesitas guardar coordenadas x e y o datos similares.

```python
point=(12.5, 10.6)
```

### Sets
*Ordered:* No

*Mutable:* N/A

Los sets son diferentes a los tipos de secuencias antes vistos ya que no son ordenados y no permites la existencia de 2 o mas elementos iguales.

```python
# Create an empty set:
s = set()

# Add some elements:
s.add(1)
s.add(2)
s.add(3)
s.add(4)
s.add(3)
s.add(1)

# Remove 2 from the set
s.remove(2)

# Print the set:
print(s)

# Find the size of the set:
print(f"The set has {len(s)} elements.")

""" This is a python multi-line comment:
Output:
{1, 3, 4}
The set has 3 elements.
"""
```

### Diccionarios
*Ordered:* No

*Mutable:* Yes

Un diccionario en python es un set de valores los cuales tienen una llave mediante la cual pueden ser encontrados, lo que quiere decir que a cada llave le corresponde una determinada informacion

```python
# Define a dictionary
houses = {"Harry": "Gryffindor", "Draco": "Slytherin"}
# Print out Harry's house
print(houses["Harry"])
# Adding values to a dictionary:
houses["Hermione"] = "Gryffindor"
# Print out Hermione's House:
print(houses["Hermione"])

""" Output:
Gryffindor
Gryffindor
"""
```

### Loops
Los los loops son una forma muy util en programacion la cual te permite realizar tareas que se repiten a traves del tiempo.

- A continuacion se muestran distintas formas de interactuar con el for Loop

```python
for i in [0, 1, 2, 3, 4, 5]:
    print(i)

""" Output:
0
1
2
3
4
5
"""
```
```python
for i in range(6):
    print(i)

""" Output:
0
1
2
3
4
5
"""
```

```python
# Create a list:
names = ["Harry", "Ron", "Hermione"]

# Print each name:
for name in names:
    print(name)

""" Output:
Harry
Ron
Hermione
"""
```

```python
name = "Harry"
for char in name:
    print(char)

""" Output:
H
a
r
r
y
"""
```

##Functions

```python
def square(x):
    return x*x
```

```python
for i in range (10):
    print(f"The square of {i} is {square(i)}")
""" Output:
The square of 0 is 0
the square of 1 is 1
The square of 2 is 4
the square of 3 is 9
The square of 4 is 16
the square of 5 is 25
The square of 6 is 36
the square of 7 is 49
The square of 8 is 64
the square of 9 is 81
```

##Modules

```python
from functions import square

for i in range(10):
    print(f"The square of {i} is {square(i)}")
```

```python
import functions

for i in range(10):
    print(f"The square of {i} is {functions.square(i)}")
```

##Object-Oriented Programming

```python
class Point():
    # A method defininghow to create a point:
    def _init_(self,x,y)
        self.x = x
        self.y = y
        
p = Point(2, 8)
print(p.x)
print(p.y)

""" Output:
2
8
"""
```
```python
class Flight():
    # Method to create new flight with given capacity
    def __init__(self, capacity):
        self.capacity = capacity
        self.passengers = []

    # Method to add a passenger to the flight:
    def add_passenger(self, name):
        self.passengers.append(name)
```        
    
```python
class Flight():
    # Method to create new flight with given capacity
    def __init__(self, capacity):
        self.capacity = capacity
        self.passengers = []

    # Method to add a passenger to the flight:
    def add_passenger(self, name):
        if not self.open_seats():
            return False
        self.passengers.append(name)
        return True

    # Method to return number of open seats
    def open_seats(self):
        return self.capacity - len(self.passengers)
```

```python
# Create a new flight with o=up to 3 passengers
flight = Flight(3)

# Create a list of people
people = ["Harry", "Ron", "Hermione", "Ginny"]

# Attempt to add each person in the list to a flight
for person in people:
    if flight.add_passenger(person):
        print(f"Added {person} to flight successfully")
    else:
        print(f"No available seats for {person}")

""" Output:
Added Harry to flight successfully
Added Ron to flight successfully
Added Hermione to flight successfully
No available seats for Ginny
"""
```

##Functional Programing

###Decorators

```python
def announce(f):
    def wrapper():
        print("About to run the function")
        f()
        print("Done with the function")
    return wrapper

@announce
def hello():
    print("Hello, world!")

hello()

""" Output:
About to run the function
Hello, world!
Done with the function
"""
```

###Lamba Functions

```python
square = lambda x: x * x
```

```python
people = [
    {"name": "Harry", "house": "Gryffindor"},
    {"name": "Cho", "house": "Ravenclaw"},
    {"name": "Draco", "house": "Slytherin"}
]

def f(person):
    return person["name"]

people.sort(key=f)

print(people)

""" Output:
[{'name': 'Cho', 'house': 'Ravenclaw'}, {'name': 'Draco', 'house': 'Slytherin'}, {'name': 'Harry', 'house': 'Gryffindor'}]
"""
```

```python
people = [
    {"name": "Harry", "house": "Gryffindor"},
    {"name": "Cho", "house": "Ravenclaw"},
    {"name": "Draco", "house": "Slytherin"}
]

people.sort(key=lambda person: person["name"])

print(people)

""" Output:
[{'name': 'Cho', 'house': 'Ravenclaw'}, {'name': 'Draco', 'house': 'Slytherin'}, {'name': 'Harry', 'house': 'Gryffindor'}]
"""
```

###Exceptions

```python
x = int(input("x: "))
y = int(input("y: "))

result = x / y

print(f"{x} / {y} = {result}")
```

```python
import sys

x = int(input("x: "))
y = int(input("y: "))

try:
    result = x / y
except ZeroDivisionError:
    print("Error: Cannot divide by 0.")
    # Exit the program
    sys.exit(1)

print(f"{x} / {y} = {result}")
```

```python
import sys

try:
    x = int(input("x: "))
    y = int(input("y: "))
except ValueError:
    print("Error: Invalid input")
    sys.exit(1)

try:
    result = x / y
except ZeroDivisionError:
    print("Error: Cannot divide by 0.")
    # Exit the program
    sys.exit(1)

print(f"{x} / {y} = {result}")
```
