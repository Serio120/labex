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

## Lección 2:  Operaciones Básicas con archivos

Empezado 16/05/2026

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

```bash
    1  pwd #(Imprimir Directorio de Trabajo)
    2  echo ~ (Este comando mostrará la ruta a tu directorio personal)
    3  ls (Este comando enumera el contenido de tu directorio de trabajo actual.)
    4  ls ~ (Este comando enumera el contenido de tu directorio personal, que puede ser diferente de tu directorio de trabajo actual.)
```
### Navegando por el Sistema de Archivos

```bash
    7  pwd
    8  ls
    9  cd ..
   10  cd project
   11  cd ~
   12  cd /home/labex/project
```

### Creación de Archivos y Listado de Contenidos

```bash
       14  pwd
       15  cd /home/labex/project
       16  touch file1.txt
       17  echo "Hello, Linux" > file2.txt
       20  echo "Hidden file" > .hiddenfile
       22  mkdir testdir
       23  ls -la
       24  ls
       25  ls -l
       26  ls -a
       27  ls -l testdir
```

### Copiar Archivos y Directorios

```bash
   32  pwd
   33  cp file1.txt file1_copy.txt
   34  ls -la
   35  ls
   36  cp file2.txt testdir/
   37  ls -la testdir
   38  ls testdir
   39  cp -r testdir testdir_copy
   40  ls testdir_copy
```
### Mover y Renombrar Archivos y Directorios

```bash
       pwd
   45  mv file1.txt newname.txt
   47  mv newname.txt testdir/
   49  mv testdir_copy new_testdir
   51  mv testdir/newname.txt ./original_file1.txt
   52  ls -la testdir
   53  ls -la
```

### Eliminar Archivos y Directorios

```bash
   58  rm original_file1.txt
   60  rm -i file2.txt
   62  ls new_testdir
   63  ls tesdir
   64  ls testdir
   65  rmdir testdir
   66  rmdir -r testdir
   67  rm -r testdir
   69  rm .hiddenfile
   70  ls -a
   71  mkdir temp_dir
   72  touch temp_dir/temp_file.txt
   73  ls -Rtemp_dir
   74  ls -R temp_dir
   75  rm -rf temp_dir
   76  ls
```

### Resumen

¡Felicidades! Has aprendido las operaciones de archivos esenciales en Linux:

-  Navegar por el sistema de archivos con `cd y pwd`
- Crear archivos y directorios con `touch y mkdir`
--  Listar contenidos con ls y sus opciones
- Copiar archivos y directorios con `cp`
- Mover y renombrar con `mv`
- Eliminar archivos y directorios con `rm y rmdir`
Estos comandos forman la base de la gestión de archivos en Linux. Con la práctica, te volverás experto en la administración de tus archivos y directorios desde la línea de comandos.

Recuerda usar estos comandos con cuidado, especialmente rm, ya que elimina permanentemente archivos y directorios sin posibilidad de recuperación.

A medida que continúes tu viaje en Linux, explora las páginas del manual (por ejemplo, `man ls`) para aprender más sobre cada comando y sus opciones. 






