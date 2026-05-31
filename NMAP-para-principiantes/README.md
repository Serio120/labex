# Laboratorio llamado: NMAP Para Principiantes
Empezado 31/05/2026

## Lección 1: Aprende la Instalación y el Uso Básico de Nmap

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

```bash
curl http://localhost:8000
```
Cuando ejecuta este comando, curl envía una solicitud al servidor HTTP que se ejecuta en localhost (que se refiere a su propia computadora) en el puerto 8000. Si el servidor se está ejecutando correctamente, debería ver el contenido HTML que creamos anteriormente.

```bash
127.0.0.1 - - [13/Sep/2024 15:24:21] "GET / HTTP/1.1" 200 -
<html>
  <body>
    <h1>Welcome to the Nmap Lab</h1>
  </body>
</html>
```
Esta salida muestra que el servidor recibió la solicitud, la procesó con éxito (indicado por el código de estado 200) y devolvió el contenido HTML del archivo index.html.

### Escaneo básico con Nmap

Ahora que hemos instalado Nmap con éxito y configurado un servicio local, es hora de comenzar a realizar algunos escaneos básicos. Esto le ayudará a entender cómo funciona Nmap y qué tipo de información puede proporcionar.

Primero, realizaremos un simple escaneo TCP connect en nuestro servidor HTTP local. Un escaneo TCP connect es un tipo fundamental de escaneo en Nmap. Intenta establecer una conexión TCP completa al puerto de destino. Si la conexión es exitosa, significa que el puerto está abierto.

Aquí está el comando para realizar este escaneo:

```bash
nmap -sT -p 8000 localhost
```

Desglosemos este comando:

-sT es una opción que especifica un escaneo TCP connect. Esto le dice a Nmap que use el método TCP connect para verificar el estado de los puertos.
-p 8000 indica que queremos que Nmap escanee solo el puerto 8000. Puede cambiar este número para escanear otros puertos si es necesario.
localhost es el objetivo de nuestro escaneo. Se refiere a la máquina local donde se está ejecutando el servicio.
Después de ejecutar este comando, debería ver una salida similar a esta:

```bash
Starting Nmap 7.80 ( https://nmap.org ) at 2024-09-13 15:27 CST
Nmap scan report for localhost (127.0.0.1)
Host is up (0.00011s latency).
Other addresses for localhost (not scanned): ::1

PORT     STATE SERVICE
8000/tcp open  http-alt

Nmap done: 1 IP address (1 host up) scanned in 0.06 seconds
```
Esta salida muestra que el puerto 8000 está abierto y está ejecutando un servicio HTTP. La columna STATE indica el estado del puerto, y en este caso, es open. La columna SERVICE da una idea de qué tipo de servicio podría estar ejecutándose en ese puerto.

Ahora, realicemos un escaneo más detallado. A veces, solo saber que un puerto está abierto no es suficiente. Podríamos querer saber más sobre el servicio que se está ejecutando en ese puerto, como su versión.

Aquí está el comando para un escaneo más detallado:

```bash
nmap -sV -p 8000 localhost
```
La opción -sV se utiliza para decirle a Nmap que explore los puertos abiertos para determinar la información del servicio/versión. Esto significa que Nmap intentará averiguar qué software específico y versión se está ejecutando en el puerto abierto.

Después de ejecutar este comando, debería ver una salida similar a esta:

```bash
Starting Nmap 7.80 ( https://nmap.org ) at 2024-09-13 15:27 CST
Nmap scan report for localhost (127.0.0.1)
Host is up (0.00011s latency).
Other addresses for localhost (not scanned): ::1

PORT     STATE SERVICE VERSION
8000/tcp open  http    SimpleHTTPServer 0.6 (Python 3.10.12)

Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 6.48 seconds
```
Esta salida proporciona información más detallada sobre el servicio que se está ejecutando en el puerto 8000. Nos dice que es un SimpleHTTPServer de Python e incluso nos da el número de versión.

Puede ver las solicitudes de Nmap en los registros de la terminal donde inició el servidor HTTP de Python. Esto puede ser útil para la depuración o un análisis más profundo.


