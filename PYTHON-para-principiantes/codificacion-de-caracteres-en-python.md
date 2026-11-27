# Codificación de Caracteres en Python

## Introducción

En este laboratorio, obtendrás una comprensión integral de la codificación de caracteres en Python. Comenzaremos explorando la historia y los conceptos fundamentales de la codificación de caracteres, desde las limitaciones de las primeras codificaciones como ASCII y las codificaciones ANSI específicas de cada país hasta el desarrollo y la importancia del estándar Unicode y sus diversas implementaciones como UTF-8. Aprenderás a verificar la codificación predeterminada en tu entorno Python.

Basándote en esta base, aprenderás técnicas prácticas para trabajar con la codificación de caracteres en Python. Esto incluye el uso de las funciones `ord()` y `chr()` para convertir entre caracteres y sus representaciones enteras, y el dominio de los métodos `encode()` y `decode()` para convertir entre cadenas (*strings*) y bytes. Finalmente, aprenderás a manejar eficazmente los posibles errores de codificación que puedan surgir durante el proceso de decodificación, garantizando un procesamiento de texto robusto y fiable en tus aplicaciones Python.

## Explorar la Historia y Conceptos de la Codificación de Caracteres

En este paso, exploraremos la historia y los conceptos fundamentales de la codificación de caracteres. Comprender cómo las computadoras representan el texto es crucial para trabajar con diversos formatos de datos e idiomas.

Inicialmente, las computadoras se desarrollaron en los Estados Unidos, lo que llevó a la creación de la codificación ASCII. ASCII utiliza un solo byte para representar caracteres e incluye letras inglesas, números y símbolos, sumando 128 caracteres.

A medida que las computadoras se volvieron más extendidas a nivel mundial, ASCII demostró ser insuficiente para representar caracteres de otros idiomas. Esto llevó al desarrollo de varias codificaciones específicas de cada país, como GB2312, GBK, Big5 y Shift_JIS. A estas se las refería a menudo colectivamente como codificaciones ANSI.

Para abordar las limitaciones de estas codificaciones dispares, se desarrolló el estándar Unicode. Unicode tiene como objetivo proporcionar un código binario único para cada carácter en cada idioma, permitiendo un manejo de texto consistente en diferentes plataformas e idiomas. Unicode define los códigos de caracteres, pero no cómo se almacenan.

Varios esquemas de codificación implementan Unicode, incluyendo UCS-4, UTF-8, UTF-16 y UTF-32. Entre estos, UTF-8 es ampliamente utilizado debido a su compatibilidad retroactiva con ASCII.

En Python 3, la codificación predeterminada es UTF-8, lo que permite el uso directo de caracteres de varios idiomas, incluyendo caracteres acentuados y símbolos. En versiones anteriores como Python 2, normalmente necesitarías especificar la codificación al principio de tu script usando comentarios como `# -*- coding: UTF-8 -*-` o `# coding=utf-8`.

Puedes verificar la codificación predeterminada en tu entorno Python utilizando el módulo `sys`.

Primero, abre la terminal integrada en la WebIDE haciendo clic en **Terminal → New Terminal**.

Luego, inicia el intérprete interactivo de Python escribiendo `python` y presionando Enter.

```bash
python
```

Deberías ver una salida similar a esta:

```text
Python 3.10.x (main, ...)
[GCC ...] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>>
```

Ahora, importa el módulo `sys` y verifica la codificación predeterminada:

```python
import sys
sys.getdefaultencoding()
```

La salida mostrará la codificación predeterminada, que típicamente es `utf-8` en Python 3:

```text
>>> import sys
>>> sys.getdefaultencoding()
'utf-8'
>>>
```

Sal del intérprete de Python escribiendo `exit()` y presionando Enter.

```python
exit()
```
## Usar ord() y chr() para Convertir Caracteres e Enteros

En este paso, aprenderemos a usar las funciones integradas de Python `ord()` y `chr()` para convertir entre caracteres y sus representaciones enteras correspondientes en Unicode.

En Python 3, las cadenas (strings) se representan utilizando Unicode. La función ord() toma un solo carácter como entrada y devuelve su valor entero decimal Unicode correspondiente.

Creemos un nuevo archivo Python para experimentar con estas funciones. En la WebIDE, haz clic derecho en el directorio project en el explorador de archivos y selecciona` New File`. Nombra el archivo `char_conversion.py`.

Abre char_conversion.py en el editor y añade el siguiente código:

```python
# Use ord() to get the Unicode decimal value of characters
char1 = 'a'
char2 = 'é'
char3 = ';'

print(f"The Unicode decimal value of '{char1}' is: {ord(char1)}")
print(f"The Unicode decimal value of '{char2}' is: {ord(char2)}")
print(f"The Unicode decimal value of '{char3}' is: {ord(char3)}")
```

Guarda el archivo presionando Ctrl + S (o Cmd + S en macOS).

Ahora, abre la terminal integrada nuevamente (si no está abierta) y ejecuta el script usando el comando python:

```python
python char_conversion.py
```

Deberías ver una salida similar a esta:

```python
The Unicode decimal value of 'a' is: 97
The Unicode decimal value of 'é' is: 233
The Unicode decimal value of ';' is: 59
```

La función chr() realiza la operación inversa. Toma un entero decimal (o un entero hexadecimal) que representa un punto de código Unicode y devuelve el carácter correspondiente.

Agreguemos más código a char_conversion.py para usar la función chr(). Añade las siguientes líneas al código existente:

```python
# Use chr() to get the character from a Unicode decimal value
int1 = 8364
int2 = 8482

print(f"The character for Unicode decimal value {int1} is: {chr(int1)}")
print(f"The character for Unicode decimal value {int2} is: {chr(int2)}")

# You can also use hexadecimal values with chr()
hex_int = 0x00A9 # Hexadecimal for the character '©'
print(f"The character for Unicode hexadecimal value {hex(hex_int)} is: {chr(hex_int)}")
```

Guarda el archivo nuevamente.

Ejecuta el script desde la terminal:

```python
python char_conversion.py
```

La salida ahora debería incluir los resultados de la función `chr()`:

```python
The Unicode decimal value of 'a' is: 97
The Unicode decimal value of 'é' is: 233
The Unicode decimal value of ';' is: 59
The character for Unicode decimal value 8364 is: €
The character for Unicode decimal value 8482 is: ™
The character for Unicode hexadecimal value 0xa9 is: ©
```

Quizás te preguntes cómo encontrar la representación hexadecimal Unicode de un carácter. Puedes usar la función ord() para obtener el valor decimal y luego la función integrada hex() para convertir el valor decimal a su representación de cadena hexadecimal.

Añade el siguiente código a char_conversion.py:

```python
# Convert a character to its hexadecimal Unicode representation
char_copyright = '©'
decimal_copyright = ord(char_copyright)
hexadecimal_copyright = hex(decimal_copyright)

print(f"The hexadecimal Unicode value of '{char_copyright}' is: {hexadecimal_copyright}")
```

Guarda el archivo y ejecútalo una última vez:

```python
python char_conversion.py
```
La salida final incluirá el valor hexadecimal para el carácter '©':

```python
The Unicode decimal value of 'a' is: 97
The Unicode decimal value of 'é' is: 233
The Unicode decimal value of ';' is: 59
The character for Unicode decimal value 8364 is: €
The character for Unicode decimal value 8482 is: ™
The character for Unicode hexadecimal value 0xa9 is: ©
The hexadecimal Unicode value of '©' is: 0xa9
```

Esto demuestra cómo `ord()` `chr()` y `hex()` se pueden usar juntas para trabajar con codificaciones de caracteres en Python.
> **Nota del maquetador:** quedan cuatro temas pendientes de esta lección.
