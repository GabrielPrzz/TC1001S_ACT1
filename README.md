# Paint 🎨

## Descripción

**Paint** es una aplicación interactiva de dibujo basada en Turtle Graphics. Dibuja diferentes formas geométricas (líneas, cuadrados, círculos, rectángulos y triángulos) con múltiples colores en una interfaz intuitiva.

## Requisitos

- **Python** 3.7+
- **turtle** (incluido en la instalación estándar de Python)
- **freegames** (librería personalizada)

## Instalación

### 1. Clonar o descargar el repositorio
```bash
git clone https://github.com/tu-usuario/paint-game.git
cd paint-game
```

### 2. Instalar dependencias
```bash
pip install freegames
```

## Uso

Ejecuta la aplicación con:
```bash
python paint.py
```

## Controles

### 🖱️ Dibujo
- **Click en el canvas** - Primer click: punto inicial | Segundo click: punto final
- Se dibuja automáticamente la forma seleccionada

### 🎨 Colores (Presiona la tecla)

| Tecla | Color |
|-------|-------|
| `K` | Negro |
| `W` | Blanco |
| `G` | Verde |
| `B` | Azul |
| `R` | Rojo |
| `P` | Rosa |

### 📐 Formas (Presiona la tecla)

| Tecla | Forma |
|-------|-------|
| `L` | Línea |
| `S` | Cuadrado |
| `C` | Círculo |
| `R` | Rectángulo |
| `T` | Triángulo |

### 🔧 Utilidades

| Tecla | Acción |
|-------|--------|
| `U` | Deshacer (Undo) |

## Características

✅ **5 Formas geométricas** - Línea, Cuadrado, Círculo, Rectángulo, Triángulo  
✅ **6 Colores disponibles** - Negro, Blanco, Verde, Azul, Rojo, Rosa  
✅ **Sistema de selección intuitivo** - Click 2 veces: inicio → fin  
✅ **Función deshacer** - Revierte el último dibujo  
✅ **Interfaz simple** - Controles por teclado  

## Estructura del Código

```
paint.py
├── Funciones de Dibujo
│   ├── line()       # Dibuja línea recta
│   ├── square()     # Dibuja cuadrado
│   ├── circle()     # Dibuja círculo
│   ├── rectangle()  # Dibuja rectángulo
│   └── triangle()   # Dibuja triángulo
├── Lógica Principal
│   ├── tap()        # Maneja clicks del ratón
│   └── store()      # Almacena valores en state
├── Variables Globales
│   └── state        # Diccionario con posición y forma actual
└── Configuración
    ├── setup()      # Inicializa ventana
    ├── onscreenclick()  # Detecta clicks
    └── onkey()      # Mapea teclas a funciones
```

## Ejemplo de Uso

1. **Ejecutar el programa**
   ```bash
   python paint.py
   ```

2. **Seleccionar un color** - Presiona `R` (rojo)

3. **Seleccionar una forma** - Presiona `S` (cuadrado)

4. **Dibujar**
   - Click en (100, 100) → punto inicial
   - Click en (200, 200) → punto final
   - Se dibuja un cuadrado rojo

5. **Cambiar forma** - Presiona `C` (círculo)

6. **Deshacer si cometes error** - Presiona `U`

## Caracteristicass agregadas

### 1. Se agrego un color extra (rosa) ✅
```python
onkey(lambda: color('pink'), 'P')  #Rosa
```

### 2. Dibujar circle ✅
```python
def circle(start, end):
    """Draw circle from start to end."""
    up()
    goto(start.x, start.y)  # Cambiar a start
    down()
    begin_fill()
    diameter = math.sqrt((end.x-start.x)**2+(end.y-start.y)**2)
    for count in range(30):
        forward(math.pi*diameter/30)
        left(360.0/30.0)
    end_fill()
```

### 3. Dibujar rectangle ✅
```python
def rectangle(start, end):
    """Draw rectangle from start to end."""
    up()
    goto(start.x, start.y)
    down()
    begin_fill()
    width = end.x - start.x
    length = end.y - start.y  # Remover /2
    for count in range(2):
        forward(width)
        left(90)
        forward(length)
        left(90)
    end_fill()
```

### 4. Dibujar triangle ✅
```python
def triangle(start, end):
    """Draw triangle from start to end."""
    up()
    goto(start.x, start.y)
    down()
    begin_fill()
    side_length = end.x - start.x
    for count in range(3):
        forward(side_length)
        left(120)  # 360/3 = 120
    end_fill()
```

## Posibles Mejoras Avanzadas

- 🎨 **Paleta de colores RGB** - Selector visual de colores
- 📏 **Ancho de línea ajustable** - Presionar teclas para aumentar/disminuir
- 🖌️ **Pincel/Lápiz** - Dibujar a mano libre
- 💾 **Guardar imagen** - Exportar dibujo como PNG/JPG
- 📐 **Polígonos personalizados** - N lados configurables
- 🔄 **Rehacer (Redo)** - Complemento al undo
- 🧹 **Limpiar canvas** - Borrar todo
- 📚 **Galería de dibujos** - Historial de creaciones

## Licencia

Utiliza la librería `freegames` de [Giles Thomas](https://github.com/giles/freegames).

## Autor

Creado como práctica de programación gráfica con Turtle.

---

**¡A crear!** 🎨 Ejecuta `python paint.py` y diseña tus obras maestras.
