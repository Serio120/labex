# Laboratorio llamado: Inicio Rápido Con Linux
Empezado 25/04/2026

## Lección 1: Tu primer laboratorio de Linux

```bash

    1  echo "Hello LabEx"
    2  whoami # solo usuario
    3  id  # usuario, grupo, ....
    4  id root
    5  id -un # solo usuario

```
Resumen

¡Felicidades! Has aprendido a:

Abrir y utilizar la terminal.

Usar comandos básicos: `echo`, `whoami`, `id`.

Extraer un detalle de identidad específico con `id -un`.

Empezado 25/04/2026

## Lección 2:  Operaciones Básicas con archivos


### Introducción
¡Bienvenido al laboratorio de Operaciones Básicas con Archivos en Linux! En Linux, casi todo se trata como un archivo, lo que convierte a las operaciones de archivos en algo fundamental para usar el sistema. Esta práctica te guiará a través de los comandos más comunes para administrar archivos y directorios, ayudándote a ser más hábil al navegar y organizar tu sistema Linux.

### Entendiendo tu Entorno de Trabajo
En Linux, cada usuario suele tener un "directorio personal" (home), representado por el símbolo ~. Sin embargo, en este entorno de laboratorio, comenzaremos en el directorio `/home/labex/project`, que es nuestro directorio de trabajo predeterminado.

Primero, abre una terminal en el Escritorio O cambia a la pestaña de la terminal en el entorno del laboratorio.

Captura de pantalla de la interfaz de la terminal
Comencemos por entender nuestra ubicación actual:

```bash
pwd
```



 Explicar Código
pwd significa "print working directory" (imprimir directorio de trabajo). Muestra tu ubicación actual en el sistema de archivos. Este comando es crucial para orientarte dentro de la estructura de archivos de Linux. Deberías ver /home/labex/project como resultado.

Ahora, exploremos la relación entre el directorio actual y el directorio personal:`

```bash
echo ~
```

 Explicar Código
Nota: Si no puedes escribir el símbolo ~ en la terminal del Escritorio debido a diferencias en la distribución del teclado de ciertos países, puedes intentar cambiar a la pestaña de Terminal independiente en la esquina superior izquierda de la interfaz de la VM.

Este comando mostrará la ruta a tu directorio personal, que debería ser /home/labex.

Para ver el contenido de tu directorio actual, usa:
```bash
ls
```
 Explicar Código
Esto listará los archivos y directorios en tu directorio de trabajo actual (/home/labex/project).

También verifiquemos el contenido de tu directorio personal:
```bash
ls ~
```
 Explicar Código
Este comando enumera el contenido de tu directorio personal, que puede ser diferente de tu directorio de trabajo actual.

Comprender la distinción entre tu directorio de trabajo actual y tu directorio personal es importante para navegar por el sistema de archivos de Linux de manera efectiva.




