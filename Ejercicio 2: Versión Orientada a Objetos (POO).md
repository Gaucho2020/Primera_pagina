#  🫧 Versión Orientada a Objetos (POO)

<img width="1300" height="804" alt="image" src="https://github.com/user-attachments/assets/a694f47a-d033-48b5-9921-8ab5f449e812" />

El objetivo es refactorizar el paquete anterior utilizando **Clases y Objetos**. Eliminando las variables globales y aplicando Encapsulamiento.

## ⚙️ Requerimientos funcionales

### Clase `tortuga`

Toda la lógica debe estar dentro de una clase. 

### Encapsulamiento

* Antes: `alineación` era una variable global.
* Ahora: `self.alineacion` es un **atributo de instancia**, inicializado en el constructor (`__init__`).
* Prohibido usar `global`.

### Interfaz de objetos

Código

## 📁 Estructura de archivos

<img width="168" height="181" alt="image" src="https://github.com/user-attachments/assets/0f036db1-820a-4709-b2cf-b3a677b30b9f" />

## 📲 Pasos de implementación

#### Creamos la clase

* Definimos `class Tortuga`
* Usamos `__init__` para inicializar `self.alineacion = 0`

```
# Creación de la clase tortuga

class Tortuga:
    def __init__(self):                    # Constructor de la clase tortuga
                self.alineacion = 0        # Estado inicial de la tortuga
```

#### Métodos de la clase `Tortuga`

Convertimos las funciones en **métodos**. Usando `self`

🔩 `adelante(self, ancho):`

```
 def adelante(self, ancho):                                      # Mover la tortuga delante
        print(" " * self.alineacion + " —" * ancho + "┐")
        self.alineacion += ancho * 2                             # Actualiza posición
```
* **Propósito:** Mueve la tortuga hacia adelante en el eje horizontal.
* **Cómo funciona:**
    * Usa `self.alineacion` para calcular la cantidad de espacios antes de dibujar.
    * Imprime una línea horizontal (—) repetida según el parámetro ancho.
    * Actualiza la posición sumando `ancho * 2`, lo que simula el avance.
* Importancia: Permite que la tortuga “camine” hacia adelante manteniendo su propio estado interno.


🔩 `abajo(self, alto):`

```
 def abajo(self, alto):                            # Mover la tortuga hacia abajo
     for _ in range(alto):
         print(" " * self.alineacion + "|")
     print(" " * self.alineacion + "🐢")
```
* **Propósito:** Mueve la tortuga hacia abajo en el eje vertical.
* **Cómo funciona:**
    * Repite el símbolo "|" tantas veces como indique `alto`, alineado con la posición actual (`self.alineacion`).
    * Finalmente imprime el ícono de la tortuga "🐢" en la nueva posición.
* Importancia: Representa el descenso de la tortuga en la “pantalla” de texto, manteniendo la alineación horizontal.

🔩 `reinicio(self):`

```
def reinicio(self):                     # Reinicia la posición a 0
        self.alineacion = 0
```
* **Propósito:** Devuelve la tortuga a la posición inicial.
* **Cómo funciona:**
    * Asigna `0` al atributo `self.alineacion`.
* Importancia: Permite reiniciar el recorrido y empezar un nuevo dibujo desde el inicio, sin necesidad de crear otro objeto.

> [!NOTA]
>
> * Cada método usa el estado interno (`self.alineacion`) en lugar de variables globales.
> * Esto asegura que cada objeto `Tortuga` tenga su propio recorrido independiente.
> * La interfaz es intuitiva: `adelante(ancho)`, `abajo(alto)` y `reinicio()` son comandos simples que simulan el movimiento de una tortuga en texto.




   

