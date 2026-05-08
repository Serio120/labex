# Laboratorio llamado: Docker para principiantes

Empezado 08/05/2026

## Lección 1: Tu primer laboratorio Docker

Antes de empezar a usar Docker, familiaricémonos con algunos conceptos clave. No te preocupes si parecen complejos al principio, ¡pronto los veremos en acción!

**1.- Contenedor** (Container): Un paquete ligero, independiente y ejecutable que incluye todo lo necesario para ejecutar una pieza de software.

**2.- Imagen (Image)**: Piensa en esto como una plantilla o un plano para los contenedores. Contiene todas las instrucciones necesarias para crear un contenedor.

**3.- Docker Hub**: Es como GitHub pero para imágenes de Docker; es el lugar donde puedes encontrar y compartir imágenes de contenedores.

**4.- Docker Engine**: La tecnología central que ejecuta y gestiona los contenedores en tu máquina.

Aquí tienes un diagrama sencillo para visualizar cómo interactúan estos conceptos:

    runs
    create
    stores
    pulls
    pushes
    Docker Engine
    Containers
    Images
    Docker Hub

Este diagrama muestra que:

- El Docker Engine ejecuta los contenedores.
- Las imágenes se utilizan para crear los contenedores.
- Docker Hub almacena las imágenes.
- El Docker Engine puede descargar (pull) imágenes desde Docker Hub y subir (push) imágenes a Docker Hub.

Comprender estas relaciones te ayudará a entender cómo funciona Docker a medida que avancemos.

### Ejecutando tu primer contenedor

Ahora que entendemos los conceptos básicos, vamos a ejecutar nuestro primer contenedor Docker utilizando la imagen **hello-world**. Esta imagen sencilla está diseñada para verificar que tu instalación de Docker funciona correctamente y para introducirte en los fundamentos de Docker.

```bash

docker run hello-world

```

Analicemos qué hace este comando:

`docker:` Es el comando para interactuar con el Docker Engine.

`run:` Este subcomando le indica a Docker que cree e inicie un nuevo contenedor.

`hello-world:` Es el nombre de la imagen que queremos ejecutar.

Cuando ejecutas este comando, suceden varias cosas entre bastidores:

1. Docker comprueba si la imagen hello-world está disponible localmente.

2. Si no es así, la descarga automáticamente (hace un "pull") desde Docker Hub.

3. Docker crea un nuevo contenedor basado en esta imagen.

4. El contenedor se ejecuta, muestra un mensaje y luego finaliza.

### Mas

Como puedes ver en la salida, el comando `docker run hello-world` realizó los pasos fundamentales para verificar que tu instalación de Docker funciona correctamente:

**1. Contacto con el demonio:** Tu cliente de Docker se comunicó con el servicio de Docker en segundo plano.

**2. Descarga de imagen:** Al no estar presente localmente, Docker la descargó de `Docker Hub`.

**3. Creación y ejecución:** Se creó un contenedor nuevo, se ejecutó el programa dentro de él y envió el mensaje de bienvenida a tu terminal.

Esta es la base de todo: utilizas una imagen **(el "molde")** para crear un contenedor **(la "instancia")** que ejecuta una tarea específica

### Entendiendo las imágenes de Docker

Ahora que hemos ejecutado nuestro primer contenedor, exploremos las imágenes de Docker con más detalle. Recuerda, una imagen es como un plano o una plantilla para un contenedor. Contiene todas las instrucciones necesarias para crearlo.

Para ver las imágenes disponibles en tu sistema local, utiliza el siguiente comando:

```bash

docker images

```
Veamos qué significa cada columna:

- REPOSITORY: El nombre de la imagen. En este caso, es "hello-world".
- TAG: La versión de la imagen. "latest" es la etiqueta por defecto si no especificas una.
- IMAGE ID: Un identificador único para la imagen. Es útil cuando necesitas referirte a una imagen específica.
- CREATED: Cuándo se creó la imagen. Esto te ayuda a saber si tienes la versión más reciente.
- SIZE: El tamaño de la imagen en el disco. Las imágenes de Docker están diseñadas para ser ligeras, por eso la imagen hello-world solo ocupa 13.3kB.

La imagen `hello-world` ahora está almacenada localmente en tu sistema. Esto significa que si vuelves a ejecutar docker run `hello-world`, Docker no necesitará descargar la imagen de Docker Hub. Usará la copia local, lo que hará que el proceso sea más rápido.

Si no ves la imagen`hello-world`, ¡no te preocupes! Es posible que se haya eliminado automáticamente para ahorrar espacio. Siempre puedes volver a descargarla ejecutando **`docker pull hello-world`**

<h2 align=center>********* POR MAQUETAR *********</h2>

Explorando Docker Hub
Docker Hub es un servicio de registro basado en la nube donde los usuarios y organizaciones de Docker pueden almacenar y distribuir sus imágenes. Es como un GitHub para imágenes de Docker, funcionando como un repositorio central donde puedes encontrar, compartir y gestionar imágenes.

Exploremos Docker Hub:

Abre tu navegador web local y ve a https://hub.docker.com
En la barra de búsqueda superior, escribe "hello-world" y presiona Enter.
Verás una lista de imágenes. Busca la imagen oficial "hello-world" (debería tener una insignia de "Official Image").
Haz clic en la imagen "hello-world" para ver sus detalles.
Resultados de búsqueda de imágenes en Docker Hub
En la página de la imagen, puedes ver:

Una descripción de la imagen.
Instrucciones de uso.
El número de descargas (pulls) que tiene la imagen.
Las etiquetas (tags) o versiones disponibles.
Docker Hub es el lugar donde Docker busca las imágenes cuando ejecutas un comando docker run y la imagen no está disponible localmente. Por eso pudiste ejecutar el contenedor hello-world aunque no hubieras descargado la imagen explícitamente de antemano.

Puntos clave sobre Docker Hub:

Imágenes Oficiales (Official Images): Son seleccionadas por Docker y suelen estar bien mantenidas y documentadas. Son una excelente opción para principiantes.
Etiquetas (Tags): Las imágenes pueden tener múltiples versiones, llamadas etiquetas. Por ejemplo, podrías ver etiquetas como "latest", "1.0", "2.1", etc. Cuando no especificas una etiqueta (como hicimos con docker run hello-world), Docker asume que quieres la etiqueta "latest".
Comando Pull: En la página de cada imagen, verás un "Pull Command". Esto es lo que usarías para descargar manualmente la imagen sin ejecutar un contenedor. Por ejemplo: docker pull hello-world.
Dockerfile: Muchas imágenes en Docker Hub tienen un enlace a su Dockerfile, que es el script utilizado para construir la imagen. Esto puede ser útil si quieres entender cómo se creó la imagen.
Explorar Docker Hub y entender cómo encontrar y usar imágenes es una habilidad crucial al trabajar con Docker. A medida que progreses, probablemente te encontrarás buscando con frecuencia en Docker Hub imágenes que se adapten a tus necesidades.

¡Este es el paso final de tu primer laboratorio de Docker! Haz clic en Continue para verificar todas tus habilidades.

### Resumen

¡Felicidades! ¡Has completado tu primer laboratorio de Docker y has dado tus primeros pasos en el mundo de la contenerización! Has aprendido a:

Comprender los conceptos básicos de Docker.
Ejecutar tu primer contenedor usando la imagen hello-world.
Ver y entender las imágenes de Docker en tu sistema.
Navegar por Docker Hub para encontrar e informarte sobre las imágenes.

<h2 align=center>********* POR MAQUETAR *********</h2>
