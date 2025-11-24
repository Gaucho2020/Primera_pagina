# Tarea 2 - Ejercicios Unidad 1 📝

# Aprendiendo a programar como una tortuga 🐢

<img width="232" height="217" alt="image" src="https://github.com/user-attachments/assets/4ea75be7-c36a-4259-8685-fbdb73d39545" />

## Ejemplo base para iniciar
### Código Import Turtle

Con este importamos la librería Python llamada Turtle, que permite crear gráficos y dibujos en una ventana virtual.

```Python
import turtle

t = turtle.Turtle()   # Crea una tortuga
t.forward(100)        # Avanza 100 unidades
turtle.done()         # Mantiene la ventana abierta
```
Como salida a este código tenemos la siguiente imágen

<img width="635" height="407" alt="image" src="https://github.com/user-attachments/assets/858f32a5-e568-4e39-af09-71b2890eda93" />

## Reto 1: Simular el comportamiento de la tortuga usando solo print() e input().

Intenta recrear el movimiento de la tortuga únicamente con texto, usando funciones, print() y input() para pedir valores al usuario.

### Solución presentada

```Python
# Entrada
import turtle

t = turtle.Turtle()   # Crea una tortuga
pasos = int(input("¿Cuántos pasos quieres dar?: "))
print("-" * pasos,">")
print("Creando una tortuga simulada que da", pasos, "pasos")
t.forward(100)        # Avanza 100 unidades
turtle.done()         # Mantiene la ventana abierta
```
```
# Salida

¿Cuántos pasos quieres dar?: 50
-------------------------------------------------- >
Creando una tortuga simulada que da 50 pasos

```
## Reto 2: Tortuga bajando

Crea el rastro de una tortuga moviéndose hacia abajo usando únicamente print() e input().

### Solución presentada

```Python
# Entrada 
import turtle

t = turtle.Turtle()   # Crea una tortuga
pasos = int(input("¿Cuántos pasos quieres dar?: ")) # Usuario indica cantidad de pasos
print("Creando una tortuga simulada que da", pasos, "pasos hacia abajo") # Imprime cantidad de pasos y hacia adonde
for i in range(pasos):
    print("     |")
print("     ↓")

t.right(90)        # Avanza hacia abajo
turtle.done()         # Mantiene la ventana abierta

```

```Python
# Salida
Creando una tortuga simulada que da 5 pasos hacia abajo
     |
     |
     |
     |
     |
     ↓
```
## Reto 3: Girar y dibujar usando solo print() e input()

Ahora la tortuga no solo avanza: también gira.

Salida (versión gráfica): se dibuja una “L”.

```
# Entrada

import turtle
t = turtle.Turtle()
t.right(90)          # Gira 90 grados a la derecha
t.forward(40 * 5)
t.left(90)          # Gira 90 grados a la derecha
t.forward(40 * 5)
turtle.done()

```

# Salida: Dibuja una "L".
<img width="647" height="496" alt="image" src="https://github.com/user-attachments/assets/446a706d-f6fe-424b-8f86-0101afe378df" />


## Dibujando un cuadrado con una diagonal entre vertices

```Python

# Entrada
import turtle
t = turtle.Turtle()
t.forward(40 * 5)
t.right(90)          # Gira 90 grados a la derecha
t.forward(40 * 5)
t.right(90)          # Gira 90 grados a la derecha
t.forward(40 * 5)
t.right(90)          # Gira 90 grados a la derecha
t.forward(40 * 5)
t.right(135)         # Gira 135 grados a la derecha
t.forward(57 * 5)
turtle.done()

```

# Salida 
<img width="604" height="505" alt="image" src="https://github.com/user-attachments/assets/3b4c87f2-a393-458e-97f8-0cc2c8815ce1" />

## Reto 4: Encapsula los comportamientos anteriores usando funciones

Reescribe los retos anteriores creando funciones que representen los movimientos de la tortuga solo con texto.

### Solución presentada

```
# Entrada

import turtle

t = turtle.Turtle()   # Crea una tortuga
pasos = int(input("¿Cuántos pasos quieres dar hacia adelante?: "))
bajar = int(input("¿Cuántas líneas hacia abajo quieres?: "))
print("Creando una tortuga simulada que da", pasos, "pasos adelante")
print("y también", bajar, "pasos hacia abajo")
print("-" * pasos,"→")

t.forward(100)        # Avanza 100 unidades

for i in range(bajar):
    print(" " * pasos + " |")
print(" " * pasos + " ↓")

turtle.done()         # Mantiene la ventana abierta
```

```
# Salida
¿Cuántos pasos quieres dar hacia adelante?: 10
¿Cuántas líneas hacia abajo quieres?: 10
Creando una tortuga simulada que da 10 pasos adelante
y también 10 pasos hacia abajo
---------- →
           |
           |
           |
           |
           |
           |
           |
           |
           |
           |
           ↓
```
En este caso los movimientos son realizados de acuerdo a la información introducida por el usuario.

## Reto 5: La tortuga baja las escalas

### Solución presentada

```Python
# Entrada
import turtle

t = turtle.Turtle()   # Crea una tortuga

pasos = int(input("¿Cuántos pasos quieres dar hacia adelante?: "))
bajar = int(input("¿Cuántas líneas hacia abajo quieres?: "))
t.forward(100)        # Avanza 100 unidades
for i in range(3):
    print(" " * (i * pasos) + "-" * pasos,"→")
    for j in range(bajar):
        print(" " * (i * pasos + pasos) + " |")
    print(" " * (i * pasos + pasos) + " ↓")
print("Creando una tortuga simulada que da", pasos, "pasos adelante")
print("y", bajar, "pasos hacia abajo en una escalera de 3 niveles")
turtle.done()         # Mantiene la ventana abierta

```

```Python
# Salida
¿Cuántos pasos quieres dar hacia adelante?: 5
¿Cuántas líneas hacia abajo quieres?: 2
----- →
      |
      |
      ↓
     ----- →
           |
           |
           ↓
          ----- →
                |
                |
                ↓
Creando una tortuga simulada que da 5 pasos adelante
y 2 pasos hacia abajo en una escalera de 3 niveles

```
## Referencias de IA







