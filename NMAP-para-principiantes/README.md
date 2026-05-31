# Laboratorio llamado: HTML Para Principiantes
Empezado 31/05/2026

## Lección 1: 

### Introducción
En este laboratorio, aprenderá sobre la instalación y el uso básico de Nmap, una poderosa herramienta de escaneo de redes y auditoría de seguridad. Nmap, también conocido como Network Mapper, es una utilidad de código abierto ampliamente utilizada por administradores de sistemas y expertos en seguridad para encontrar hosts, servicios y vulnerabilidades en una red.

Este laboratorio lo guiará a través del proceso de instalación de Nmap, la configuración de un servicio local para el escaneo y la realización de escaneos básicos para comprender las capacidades de Nmap.

### Instalando Nmap
En este paso, lo guiaremos a través del proceso de instalación de Nmap en su sistema Ubuntu Linux. Nmap es una poderosa herramienta de escaneo de redes que se utiliza ampliamente en ciberseguridad para tareas como la detección de redes y la auditoría de seguridad. Está disponible en los repositorios predeterminados de Ubuntu, lo que significa que el proceso de instalación es bastante sencillo.

Primero, debe abrir su terminal. La terminal es una interfaz basada en texto que le permite interactuar con su sistema ingresando comandos. Por defecto, debe estar en el directorio /home/labex/project. Si no está en este directorio, puede navegar hasta allí utilizando el siguiente comando. Este comando cambia su directorio de trabajo actual a /home/labex/project.

```bash
cd /home/labex/project
```

Ahora que está en el directorio correcto, es hora de actualizar la lista de paquetes e instalar Nmap. La lista de paquetes contiene información sobre todo el software disponible en los repositorios de Ubuntu. Actualizarla asegura que está obteniendo la última versión de Nmap.

```bash
sudo apt update
sudo apt install nmap -y
```

El comando sudo se utiliza para ejecutar comandos con privilegios administrativos. Dado que la instalación de software requiere acceso administrativo, debe utilizar sudo. La opción -y se utiliza con el comando apt install. Responde automáticamente "sí" a cualquier solicitud durante el proceso de instalación, por lo que no tiene que confirmar manualmente cada paso.

Después de que la instalación se complete, es importante verificar que Nmap se haya instalado correctamente. Puede hacer esto comprobando su versión. La opción --version del comando nmap muestra la información de la versión de Nmap.

```bash
nmap --version
```
Esta salida confirma que Nmap está instalado en su sistema. También proporciona información sobre la versión de Nmap y las opciones de compilación utilizadas, lo cual puede ser útil para solucionar problemas o entender las capacidades de su instalación de Nmap.

### Configuración de un Servicio Local para Escaneo

Antes de comenzar a usar Nmap para escanear, es esencial tener un servicio objetivo en ejecución. De esta manera, podemos probar las capacidades de escaneo de Nmap de manera efectiva. En este paso, configuraremos un servidor HTTP simple utilizando el módulo http.server integrado de Python. El módulo http.server de Python es una herramienta conveniente que nos permite iniciar rápidamente un servidor HTTP sin la necesidad de configuraciones complejas.

Primero, creemos un nuevo directorio para nuestro servidor HTTP. Un directorio es como una carpeta en su computadora donde podemos almacenar todos los archivos relacionados con nuestro servidor.

```bash
mkdir -p /home/labex/project/http-server
cd /home/labex/project/http-server
```
El comando mkdir -p crea un directorio llamado http-server en la ruta especificada. La opción -p asegura que si algún directorio intermedio no existe, también se creará. El comando cd luego cambia nuestro directorio de trabajo actual al directorio http-server recién creado.

Ahora, creemos un archivo HTML simple que nuestro servidor servirá. HTML es el lenguaje de marcado estándar para crear páginas web.

```bash
echo "<html><body><h1>Welcome to the Nmap Lab</h1></body></html>" > index.html
```
Este comando usa el comando echo para imprimir el código HTML en la terminal y luego redirige esa salida a un archivo llamado index.html. Entonces, hemos creado un archivo con una estructura HTML básica y un mensaje de bienvenida.

A continuación, iniciaremos el servidor HTTP de Python.

```bash
python3 -m http.server 8000
```
Este comando usa el intérprete python3 para ejecutar el módulo http.server como un script. La opción -m le dice a Python que ejecute el módulo como un script. Especificamos el puerto 8000, lo que significa que nuestro servidor escuchará las solicitudes entrantes en este puerto.

**Importante:*** Abra una nueva pestaña o ventana de terminal para continuar. Mantenga el servidor HTTP en ejecución en esta terminal y use la nueva terminal para todos los comandos Nmap posteriores en este laboratorio. Esto asegura que el servidor HTTP permanezca activo mientras realiza los escaneos.

Para verificar que el servidor se está ejecutando, puede usar el comando curl en la nueva terminal. curl es una herramienta de línea de comandos que se utiliza para transferir datos desde o hacia un servidor.

