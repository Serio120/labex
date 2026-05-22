# Laboratorio llamado: Programación en C++ para Principiantes
Empezado 22/05/2026

## Lección 1: Escribe tu primer programa en C++

## Introducción

En este laboratorio, aprenderás a escribir tu primer programa en C++. Comenzarás instalando el compilador GCC (GNU Compiler Collection) y configurando las variables de entorno necesarias en Ubuntu 22.04. Luego, crearás un nuevo archivo de código fuente en C++, escribirás la estructura básica del programa y utilizarás la instrucción cout para imprimir el mensaje "Hello World". También aprenderás a compilar y ejecutar el programa, así como a añadir comentarios de una o varias líneas, utilizar endl y \n para saltos de línea, y corregir errores de sintaxis comunes, como la falta de puntos y coma.

Comenzaremos actualizando la lista de paquetes para asegurarnos de tener la información más reciente sobre los paquetes disponibles:

```bash
sudo apt update
```

A continuación, instalaremos el compilador GCC y las herramientas de desarrollo relacionadas:

```bash
sudo apt install -y build-essential
```

Para verificar la instalación y comprobar la versión de GCC, ejecuta:

```bash
g++ --version
```

<h2 align=center>********* POR COMPLETAR Y EXPLICAR *********</h2>

```bash
    1  sudo apt update
    2  sudo apt install -y build-essential
    3  g++ --version
    5  touch hello.cpp
   13  g++ hello.cpp -o hello
   14  ./hello
   15  cd ~/project
   16  touch syntax_errors.cpp
   17  ls
   18  g++ syntax_errors.cpp -o syntax_errors
   19  ./syntax_errors
```


## Resumen

En este laboratorio, aprendiste a instalar el compilador GCC (GNU Compiler Collection) para C++ y a configurar las variables de entorno necesarias en Ubuntu 22.04. Creaste un nuevo archivo de código fuente en C++, escribiste la estructura básica del programa con la función int main() y utilizaste cout para imprimir el mensaje "Hello World". Luego, compilaste el programa usando el comando g++ y lo ejecutaste. Además, aprendiste a añadir comentarios de una y varias líneas, a utilizar endl y \n para saltos de línea, y a corregir errores de sintaxis comunes, como la falta de puntos y coma.

Después de completar estos pasos, tendrás una base sólida para escribir y ejecutar tu primer programa en C++, así como una comprensión de las herramientas y conceptos básicos necesarios para el desarrollo en C++ en Ubuntu 22.04.
