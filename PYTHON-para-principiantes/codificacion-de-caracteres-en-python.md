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

> **Nota del maquetador:** quedan cuatro temas pendientes de esta lección.
