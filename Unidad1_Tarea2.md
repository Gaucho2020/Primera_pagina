# Tarea 2 - Ejercicios Unidad 1 📝

# Aprendiendo a programar como una tortuga 🐢

<img width="630" height="630" alt="image" src="https://github.com/user-attachments/assets/710636ef-9dc6-4028-94c1-a90aaa3f7c08" />

## Reto 1: Simular el comportamiento de la tortuga usando solo print() e input().

Intenta recrear el movimiento de la tortuga únicamente con texto, usando funciones, print() y input() para pedir valores al usuario.

### Solución presentada

```
# Entrada
pasos = int(input("¿Cuántos pasos quieres dar?: "))
print("Creando una tortuga simulada que da", pasos, "pasos")
print("—" * pasos + ">")

```
```
# Salida

¿Cuántos pasos quieres dar?: 50
Creando una tortuga simulada que da 50 pasos
——————————————————————————————————————————————————>

```
El código solicita al usuario cuantos pasos desea dar (entrada) y devuelve impresos los pasos y leyenda con la cantidad de pasos dados.

## Reto 2: Tortuga bajando

Crea el rastro de una tortuga moviéndose hacia abajo usando únicamente print() e input().

### Solución presentada

```
# Entrada
pasos = int(input("¿Cuántos pasos quieres dar?: "))
print("Creando una tortuga simulada que da", pasos, "pasos hacia abajo")
Caracter = ("|")
# Imprimir una línea de pasos descendente
print(f" {Caracter}\n" * (pasos) + " ↓")

```

```
# Salida
Creando una tortuga simulada que da 5 pasos hacia abajo
 |
 |
 |
 |
 |
 ↓

```
Este código recibe del usuario cuantos pasos desea avanzar hacia abajo y devuelve impresos los pasos y leyenda con la información registrada.

## Reto 3: Girar y dibujar usando solo print() e input()

Ahora la tortuga no solo avanza: también gira.

### Solución presentada

```
# Entrada
ancho = int(input("¿Cuántos pasos quieres dar adelante?: "))
alto = int(input("¿Cuántos pasos quieres dar abajo?: "))
print("Creando una tortuga simulada que da", ancho, "pasos hacia adelante y", alto, "pasos hacia abajo")
print("--" * (ancho) + "┐")
Caracter = ("|")
print(((" " * (ancho * 2) ) + f"{Caracter}\n") * (alto) + ("  " * (ancho) + "V"))

```
```
# Salida
¿Cuántos pasos quieres dar adelante?: 10
¿Cuántos pasos quieres dar abajo?: 10
Creando una tortuga simulada que da 10 pasos hacia adelante y 10 pasos hacia abajo
--------------------┐
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
                    V

```
El código realiza simulación de movimientos de tortuga adelante y abajo en forma de "L"

## Reto 4: Encapsula los comportamientos anteriores usando funciones

Reescribe los retos anteriores creando funciones que representen los movimientos de la tortuga solo con texto.

### Solución presentada

```
# Entrada
# Definición de funciones

ancho = int(input("¿Cuántos pasos quieres dar adelante?: "))
alto = int(input("¿Cuántos pasos quieres dar abajo?: "))

def movimiento_adelante(ancho):    # Función de movimiento adelante
    print("Creando una tortuga simulada que da", ancho, "pasos hacia adelante y", alto, "pasos hacia abajo")
    print(" —" * (ancho) + "┐")

def movimiento_abajo(alto):        # Función de movimiento abajo
    Caracter = ("|")
    print(((" " * (ancho * 2) ) + f"{Caracter}\n") * (alto) + ("  " * (ancho) + "V"))

def escalon(ancho_adelante, alto_abajo): # Combinación de las dos funciones 
    movimiento_adelante(ancho_adelante)
    movimiento_abajo(alto_abajo)

escalon(ancho, alto)                      # LLamada a función

```

```
# Salida

¿Cuántos pasos quieres dar adelante?: 19
¿Cuántos pasos quieres dar abajo?: 7
Creando una tortuga simulada que da 19 pasos hacia adelante y 7 pasos hacia abajo
 — — — — — — — — — — — — — — — — — — —┐
                                      |
                                      |
                                      |
                                      |
                                      |
                                      |
                                      |
                                      V

```
En este caso los movimientos son realizados de acuerdo a la información introducida por el usuario.
Se definieron funciones para los movimientos adelante y abajo con las cuales se produce el resultado definido como un escalón.

## Reto 5: La tortuga baja las escalas

Ajusta tus funciones para que la tortuga pueda bajar escalones.
Cada escalón debe conservar la posición horizontal acumulada y dibujar correctamente tanto el tramo horizontal como el vertical.

### Solución presentada

### Opción # 1 : Ingresando código de manera manual
```
# Entrada
print("Creando una tortuga simulada que da 5 pasos hacia adelante y 3 pasos hacia abajo en 3 secciones de escalera")

# Sección 1
print(" —" * (5) + "┐")
Caracter = ("|")
print("  " * (5)+ Caracter)
print("  " * (5)+ Caracter)
print("  " * (5)+ Caracter)
print("  " * (5)+ Caracter)
print("  " * (5)+ "↓")

# Sección 2
print("  " * (5) + " —" * (5) + "┐")
Caracter = ("|")
print("  " * (10)+ Caracter)
print("  " * (10)+ Caracter)
print("  " * (10)+ Caracter)
print("  " * (10)+ Caracter)
print("  " * (10)+ "↓")

# Sección 3
print("    " * (5) + " —" * (5) + "┐")
Caracter = ("|")
print("  " * (15)+ Caracter)
print("  " * (15)+ Caracter)
print("  " * (15)+ Caracter)
print("  " * (15)+ Caracter)
print("  " * (15)+ "↓")

```

```
# Salida

Creando una tortuga simulada que da 5 pasos hacia adelante y 3 pasos hacia abajo en 3 secciones de escalera
 — — — — —┐
          |
          |
          |
          |
          ↓
           — — — — —┐
                    |
                    |
                    |
                    |
                    ↓
                     — — — — —┐
                              |
                              |
                              |
                              |
                              ↓

```
Esta versión manual realiza una escalera de tres niveles donde la tortuga avanza 5 pasoa hacia adelante, 3 hacia abajo en 3 secciones de escalones.

### Opción # 2 : Usando funciones y ciclos


```
# Entrada
ancho = int(input("¿Cuántos pasos quieres dar adelante?: "))
alto = int(input("¿Cuántos pasos quieres dar abajo?: "))
secciones = int(input("¿Cuántas secciones de escalones deseas?: "))

def cantidad_escalas(ancho, alto, secciones):
    desplazamiento = 0                                      # Control de indentación para alinear los escalones

    for i in range(secciones):        
        print(" " * desplazamiento + "—" * ancho + "┐")     # Movimiento hacia adelante
        
        for j in range(alto):                               # Movimiento hacia abajo
            print(" " * (desplazamiento + ancho) + "|")
        print(" " * (desplazamiento + ancho) + "↓")
        
        desplazamiento += ancho                             # Incrementar el espacio por línea

cantidad_escalas(ancho, alto, secciones)

```
```
# Salida
¿Cuántos pasos quieres dar adelante?: 5
¿Cuántos pasos quieres dar abajo?: 2
¿Cuántas secciones de escalones deseas?: 3
—————┐
     |
     |
     ↓
     —————┐
          |
          |
          ↓
          —————┐
               |
               |
               ↓
```
Esta versión permite el movimiento del objeto tortuga en forma escalonada acorde a los datos introducidos por el usuario. Para esto usa funciones y ciclos for i in para repetir escalones.

## Referencias de IA

- Gemini: Conversación para indicaciones de como generar nuevo archivo en el repositorio. https://gemini.google.com/app/42f2e5a182bcd775?utm_source=app_launcher&utm_medium=owned&utm_campaign=base_all
- Gemini: Conversación para obtener orientación en ejercicio 1 y uso de VS Code para estructuración de código. https://gemini.google.com/app/47a9e6d79158136a?utm_source=app_launcher&utm_medium=owned&utm_campaign=base_all
- Copilot: Conversación en versión de escritorio para orientación en ejercicio 3. https://copilot.microsoft.com/shares/JYbgDpHJbFShg9ExzhApB
- Copilot: Conversación en versión de escritorio para orientación en ejercicio 5. https://copilot.microsoft.com/shares/AswMRiMxGaVnfi5F8iNBY

## Referencias 
- Github. (s.f.). Documentación de Github. https://docs.github.com/es/enterprise-cloud@latest/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax
  





