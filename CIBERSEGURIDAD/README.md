# Laboratorio llamado: CIBERSEGURIDAD
Empezado 18/05/2026

## Lección 1: Kali Linux para Principiantes

<h2 align=center>********* POR REPASAR Y COMPLETAR *********</h2>

```bash
    2  pwd
    3  docker pull kalilinux/kali-rolling
    4  docker images
    5  docker run -d --name kali-container -it kalilinux/kali-rolling /bin/bash
    6  docker ps
    7  docker exec -it kali-container /bin/bash
```


### Introducción

En este desafío, tendrás que comprobar la versión de Kali Linux que se está ejecutando dentro de un contenedor Docker. Para lograrlo, deberás acceder a la terminal del contenedor, localizar y extraer el valor VERSION_ID del archivo /etc/os-release y, finalmente, guardar dicho dato en un archivo llamado version.txt dentro del directorio ~/project de la máquina host.

El script de configuración descargará la imagen kalilinux/kali-rolling si no está presente e iniciará un contenedor llamado kali-container. Deberás emplear docker exec para entrar al contenedor, ejecutar cat /etc/os-release para identificar la versión y luego generar el archivo version.txt con el VERSION_ID obtenido. El script de verificación validará si el contenedor está activo y si el archivo version.txt contiene la versión correcta.


# Project Title

A brief description of what this project does and who it's for

### Verificar la versión de Kali Linux

Una auditoría de seguridad crítica requiere que identifiques rápidamente la versión de Kali Linux que se ejecuta en un contenedor Docker. Tu equipo necesita esta información para garantizar la compatibilidad con las herramientas de seguridad más recientes y mantener la integridad del sistema.

### Tareas
Acceder a la terminal del contenedor de Kali Linux.
Utilizar el comando cat /etc/os-release para encontrar el VERSION_ID.
Crear un archivo llamado version.txt en el directorio ~/project y escribir el VERSION_ID en él.
Requisitos
Debes acceder al contenedor de Kali Linux utilizando el comando docker exec -it kali-container /bin/bash.
Debes usar el comando cat /etc/os-release dentro del contenedor para localizar el VERSION_ID.
Debes crear un archivo llamado version.txt en el directorio ~/project.
El archivo version.txt debe contener únicamente el valor del VERSION_ID.
Ejemplos
Si el VERSION_ID en /etc/os-release es 2023.3, entonces el archivo version.txt debería contener:

```
2023.3
```

 Explicar Código
Ejemplo del contenido de version.txt

### Consejos
Primero, utiliza docker exec -it kali-container /bin/bash para entrar al contenedor.
Luego, usa cat /etc/os-release para buscar el VERSION_ID.
Finalmente, utiliza echo y la redirección > para crear el archivo version.txt en el directorio ~/project de la máquina host. Es posible que necesites usar docker cp para copiar el archivo desde el contenedor al host. Alternativamente, puedes escribir la versión en un archivo dentro del contenedor y luego usar docker cp para transferirlo al host.
