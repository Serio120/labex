# Laboratorio llamado: HTML Para Principiantes
Empezado 07/05/2026

## Lección 1: Estructura del documento HTML

### Introducción

Cubriremos los componentes esenciales que toda página HTML debe tener:

- La declaración `<!DOCTYPE html>`
- El elemento raíz `<html>`
- El elemento `<head>` para metadatos
- El elemento `<body>` para contenido visible

## `<!DOCTYPE html>`

Esa línea <!DOCTYPE html> es fundamental porque informa al navegador que estás utilizando el estándar HTML5. Es la instrucción necesaria para que el navegador sepa cómo interpretar y mostrar correctamente el contenido de tu página.


## Añadir el elemento raíz **html** con el atributo **lang**

En este paso, agregarás el elemento `<html>`. Este elemento es el contenedor raíz para todos los demás elementos HTML en la página (excepto la declaración `<!DOCTYPE>`).

También es una buena práctica incluir el atributo lang dentro de la etiqueta de apertura `<html>`. Este atributo especifica el idioma del contenido del documento, lo que ayuda a los motores de búsqueda y a los lectores de pantalla. Para inglés, usamos lang="en".

## Insertar el elemento **head** con la etiqueta **title**

En este paso, agregarás el elemento `<head>`. La sección `<head>` contiene metadatos sobre el documento **HTML**, como su título, conjunto de caracteres, estilos y scripts. Esta información no se muestra en la página web en sí, sino que es utilizada por el navegador.

La pieza de metadatos más importante para un principiante es la etiqueta `<title>`. El texto dentro de la etiqueta `<title>` es lo que aparece en la pestaña del navegador o en la barra de título de la ventana.

Dentro de tu elemento <html>, agrega una sección `<head>`. Dentro de la sección `<head>`, agrega una etiqueta `<title>` con el texto **"My First Web Page"**.

## Añadir el elemento **body** para el contenido

En este paso, agregarás el elemento `<body>`. Aquí es donde va todo el contenido visible de tu página web, como encabezados, párrafos, imágenes, enlaces y más. El elemento `<body>` debe colocarse después del elemento `<head>`, pero aún dentro del elemento `<html>`.

Agreguemos un encabezado principal a nuestra página para que sea visible en el navegador. Usaremos la etiqueta `<h1>`, que significa "Heading 1" (Encabezado 1).

En tu archivo index.html, agrega una sección `<body>`. Dentro del `<body>`, agrega un elemento `<h1>` con el texto "Hello, World!".


### Resumen

¡Felicidades! Has creado con éxito tu primer documento HTML válido. Has aprendido los bloques de construcción fundamentales que forman el esqueleto de cada página web.

En este laboratorio, has aprendido:

`<!DOCTYPE html>`: La declaración que define el documento como HTML5.
- `<html>`: El elemento raíz que envuelve todo el contenido de la página.
- `<head>`: El contenedor de metadatos, como el título de la página, que no es visible en la página en sí.
- `<title>`: La etiqueta que establece el título de la pestaña del navegador.
- `<body>`: El contenedor de todo el contenido visible, como encabezados y párrafos.
Esta estructura básica es la base sobre la cual construirás todos tus futuros proyectos web.

# Lección 2: Formato de texto HTML

Empezado 30/06/2026

## Introducción

En esta sesión práctica, aprenderá a estructurar y formatear texto en una página web utilizando etiquetas HTML fundamentales. El texto formateado correctamente es crucial para crear contenido web legible, accesible y bien organizado.

Trabajará con un único archivo HTML, `index.html`, y aprenderá a utilizar las siguientes etiquetas:

- `<h1>`: Para encabezados principales.
- `<p>`: Para párrafos.
- `<strong>`: Para dar al texto una gran importancia, que normalmente se muestra en negrita.
- `<em>`: Para enfatizar texto, que normalmente se muestra en cursiva.
- `<br>`: Para insertar un salto de línea.

## Añadir etiqueta h1 para el título principal

En este paso, añadirá un título principal a su página web. En HTML, los encabezados se definen con las etiquetas <h1> a <h6>. <h1> define el encabezado más importante y se utiliza típicamente para el título principal de una página.

Primero, abra el archivo index.html ubicado en el directorio `~/project` utilizando el explorador de archivos en el lado izquierdo del WebIDE.

Ahora, añada una etiqueta <h1> dentro de la sección <body> de su archivo `index.html`. Reemplace el comentario <!-- Content will be added here --> con la siguiente línea de código:

```html
<h1>Welcome to My Web Page</h1>
```





