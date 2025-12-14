# 🐢Evolución de Mini Turtle 

<img width="600" height="320" alt="image" src="https://github.com/user-attachments/assets/01cc21d4-4f62-4ee0-a313-043771ca7107" />

La evolución de *mini_turtle* refleja el esfuerzo por crear una herramienta de programación accesible y clara para principiantes. Inspirado en la clásica librería *turtle* de Python, este proyecto busca simplificar los conceptos básicos de movimiento y control, ofreciendo una interfaz limpia y directa. 
*Mini_turtle* busca pasar de ser un conjunto reducido de funciones a un paquete modular y bien documentado, pensado para enseñar programación de manera intuitiva. Cada versión enfocada en mejorar la experiencia del usuario: desde la organización del código y la facilidad de importación de funciones, incorporando ejemplos prácticos y un diseño más amigable.
Esta evolución con sus avances técnicos, muestra un compromiso pedagógico y de aprendizaje par transformar la programación en una experiencia creativa, accesible y motivadora para estudiantes y entusiastas.

# Versión Funcional (Modularidad)

El objetivo es transformar las funciones sueltas `adelante()` y `abajo()` en un paquete Python distribuible llamado **mini_turtle**. Esto demostrará la separación entre la lógica  y la interfaz pública.

## Requerimientos funcionales

### *Interfaz limpia*

Significa que la forma de usar el paquete debe ser simple, clara y directa, sin necesidad de acceder a submódulos complicados ni escribir rutas largas.
El usuario final debe tener una experiencia sencilla al importar y usar las funciones.


<img width="462" height="79" alt="image" src="https://github.com/user-attachments/assets/ee133dc4-eb9c-4d30-8e7c-8be7e65cd6af" />


Esto implica que:

* El paquete `mini_turtle` debe estar diseñado para exponer directamente esas funciones `adelante, abajo, reinicio` en su nivel superior.

* No debería ser necesario hacer algo más complejo, en otras palabras, el paquete debe estar organizado para que el usuario pueda importar las funciones de manera *limpia y directa*.

### *Función reiniciar* nueva funcionalidad

La función `reinicio()` restablece el estado del entorno gráfico de `mini_turtle` a su configuración inicial.
Se utiliza para limpiar la pantalla, devolver la tortuga a su posición de origen y eliminar cualquier trazo previo.
Esto permite comenzar un nuevo dibujo sin necesidad de cerrar o reiniciar el programa completo.

#### De esta manera.
```

def reinicio():       # Reinicia la variable global 'alineación' a 0. Sirve para devolver la posición o estado de alineación al valor inicial,
                      asegurando que el programa comience desde un punto de referencia limpio.          
    global alineación
    alineación = 0

```
#### En resumen
*  **Qué hace:** pone la variable alineación en 0.
*  **Por qué:** permite reiniciar la posición o estado del sistema.
*  **Cómo:** usa la palabra clave global para modificar la variable definida fuera de la función.

## 📂 Estructura del proyecto


<img width="237" height="246" alt="image" src="https://github.com/user-attachments/assets/d2c182f3-8299-4640-a02a-c2e4d0053b6c" />


##  📲 Implementación del proyecto

### 1. 🧩 Módulo de lógica `drawer_logic`

<img width="403" height="59" alt="image" src="https://github.com/user-attachments/assets/04f8135c-ce2e-4b93-bbe6-53c480957792" />

Aquí se concentran todas las funciones principales y las variables globales que controlan el dibujo.

```
# Drawer_logic.py

alineación = 0                  # Variable global iniciada en 0

def adelante(ancho):            #Función para ir adelante
    global alineación
    print(" " * alineación + " —" * ancho + "┐")
    alineación += ancho * 2      # Posición actualizada adelante

def abajo(alto):                 #Función para ir abajo
    global alineación
    for _ in range(alto):
        print(" " * alineación + "|")
    print(" " * alineación + "🐢")

def reinicio():                  # Función para reiniciar la posición a 0
    global alineación
    alineación = 0

```

### 2. 🎲 Interfaz `__init__.py`

<img width="303" height="58" alt="image" src="https://github.com/user-attachments/assets/d8d9f78b-0ec9-4c74-a410-61438908bfa9" />

#### Importación desde `drawer_logic`

*  Este archivo define qué funciones estarán disponibles cuando alguien importe el paquete.
*  Se importan desde `drawer_logic`.

```
# mini_turtle/__init__.py
from .drawer_logic import adelante, abajo, reinicio
```

#### Definición de `__all__`

```
# Definir __all__ 
__all__ = ["adelante", "abajo", "reinicio"]

```

*  `__all__` es una lista que define la **interfaz pública** del paquete.
*  Solo las funciones incluidas en esa lista estarán disponibles si alguien hace:

```
from mini_turtle import adelante, abajo, reinicio
```
### 3. 📋 Prueba `main.py`                                

Dibujaremos una tortuga moviendose tres escalones hacia adelante y dos hacia abajo, y luego se reiniciará su posición para que repita el mismo recorrido por segunda vez.

```
from mini_turtle import adelante, abajo, reinicio

adelante(3)      # mueve la tortuga hacia adelante 3 pasos
abajo(2)         # baja la tortuga 2 pasos

adelante(3)       # mueve la tortuga hacia adelante 3 pasos
abajo(2)          # baja la tortuga 2 pasos

reinicio()        # Reinicia la posición a 0 

adelante(3)      # mueve la tortuga hacia adelante 3 pasos
abajo(2)         # baja la tortuga 2 pasos

adelante(3)       # mueve la tortuga hacia adelante 3 pasos
abajo(2)          # baja la tortuga 2 pasos
```

#### 🎯 Resultado

```
 — — —┐
      |
      |
      🐢
       — — —┐
            |
            |
            🐢
 — — —┐
      |
      |
      🐢
       — — —┐
            |
            |
            🐢

```

# Referencias IA

- Copilot: Conversación en versión de escritorio para documentar uso de función. https://copilot.microsoft.com/shares/SfA4rPc4XZQPQwGdXP4Zz
- Copilot: Conversación en versión de escritorio para entender y documentar lista ***__all__***. https://copilot.microsoft.com/shares/3KxEHvqzLG9KrRdfoP9V1
  





