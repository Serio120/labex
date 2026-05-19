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
