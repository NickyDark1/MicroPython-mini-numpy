# MiniArray - Biblioteca Optimizada para Operaciones Numéricas en MicroPython

**MiniArray** es una implementación optimizada de arrays multidimensionales para MicroPython, con soporte para operaciones element-wise, reducciones, álgebra lineal y funciones matemáticas. Se basa en `array` de MicroPython y acelera cálculos usando el decorador `@micropython.viper` en funciones de bajo nivel.

## 📌 Características

- ✅ **Soporte para arrays multidimensionales** con acceso indexado.
- ✅ **Operaciones element-wise** aceleradas (suma, resta, multiplicación, división).
- ✅ **Reducciones** como `sum()`, `prod()`, `min()`, `max()`, `mean()`, `std()`, etc.
- ✅ **Funciones matemáticas** (`sin`, `cos`, `sqrt`, `log`, etc.) aplicadas a todos los elementos.
- ✅ **Álgebra lineal básica**: Producto punto, determinante, inversa de matrices, resolución de sistemas lineales.
- ✅ **Funciones de apilado**: `vstack()`, `hstack()`, `concatenate()`.
- ✅ **Operaciones de indexación y slicing**, incluyendo **indexación booleana**.
- ✅ **Soporte para Viper** para optimización en plataformas compatibles con MicroPython.

---

## 🚀 Instalación

Este módulo está diseñado para MicroPython, pero puede ejecutarse en Python estándar con algunas modificaciones. Para usarlo, simplemente copia el archivo en tu proyecto de MicroPython:

1. **Copia el código** en tu microcontrolador con MicroPython (por ejemplo, en `main.py`).
2. Usa un cliente como **Thonny** o **rshell** para transferir el script a tu dispositivo.

---

## 🛠️ Uso

### 1⃣ Creación de un MiniArray

```python
from miniarray import MiniArray

# Crear un array unidimensional
a = MiniArray([1, 2, 3, 4])

# Crear un array 2D
b = MiniArray([1, 2, 3, 4, 5, 6], shape=(2, 3))

print(a)  # MiniArray([1, 2, 3, 4], shape=(4,))
print(b)  # MiniArray([1, 2, 3, 4, 5, 6], shape=(2,3))
```

---

### 2⃣ Operaciones Element-Wise

```python
c = MiniArray([10, 20, 30, 40])
print(a + c)  # MiniArray([11, 22, 33, 44], shape=(4,))
print(a * c)  # MiniArray([10, 40, 90, 160], shape=(4,))
print(a ** 2)  # MiniArray([1, 4, 9, 16], shape=(4,))
```

---

### 3⃣ Operaciones de Reducción

```python
print(a.sum())   # 10
print(a.prod())  # 24
print(a.min())   # 1
print(a.max())   # 4
print(a.mean())  # 2.5
print(a.std())   # 1.11803
```

---

### 4⃣ Álgebra Lineal

```python
A = MiniArray([4, 7, 2, 6], shape=(2,2))
b = MiniArray([1, 0])

print(A.det())  # Determinante de A
print(A.inv())  # Matriz inversa
print(A.solve(b))  # Resolver Ax = b
```

---

### 5⃣ Funciones Matemáticas

```python
import math
f = MiniArray([0, math.pi/2, math.pi], typecode='f')

print(f.sin())   # [0, 1, 0]
print(f.sqrt())  # [0, 1.253, 1.772]
print(f.log())   # [-inf, 0.451, 1.145]  # (para valores positivos)
```

---

### 6⃣ Apilado y Concatenación

```python
c = MiniArray([1, 2, 3, 4, 5, 6], shape=(2, 3))
print(MiniArray.vstack([c, c]))  # Apilar verticalmente
print(MiniArray.hstack([c, c]))  # Apilar horizontalmente
```

---

### 7⃣ Creación de Arrays Especiales

```python
from miniarray import zeros, ones, eye

print(zeros((2,2)))  # Matriz de ceros
print(ones((2,2)))   # Matriz de unos
print(eye(3))        # Matriz identidad 3x3
```

---

## ⚙️ Compatibilidad

✅ **MicroPython** (optimizado con `@micropython.viper`)  
✅ **Python estándar** (con ajustes menores)  
✅ **ESP32, esp8266, otros microcontroladores con MicroPython**  

---

## 🐝 Licencia

Este código se distribuye bajo la **Licencia MIT**, lo que significa que puedes usarlo, modificarlo y compartirlo libremente.

---

## 📢 Contribuciones

Si deseas mejorar este proyecto, ¡las contribuciones son bienvenidas! Puedes:

- Reportar problemas en la sección **Issues**.
- Enviar mejoras a través de **Pull Requests**.
- Sugerir nuevas funcionalidades.

---

¡Gracias por usar **MiniArray**! 🚀

