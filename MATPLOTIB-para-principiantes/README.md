[Matplotlib es una biblioteca completa para crear estáticos, animados, y visualizaciones interactivas en Python. Matplotlib hace cosas fáciles Cosas fáciles y difíciles posibles](https://matplotlib.org/)

# Laboratorio llamado: Matplotib Para Principiantes
Empezado 28/05/2026

# Lección 1: Instalación e Importación de Matplotlib

## Instalar Matplotlib usando pip

En este paso, aprenderás cómo instalar Matplotlib. Como biblioteca de terceros, no viene incluida con una instalación estándar de Python. Debe instalarse usando `pip`, el instalador de paquetes para Python.

El comando estándar para instalarlo es `pip install matplotlib`. Sin embargo, para tu conveniencia, Matplotlib ya ha sido instalado en este entorno de laboratorio. Tu tarea es verificar la instalación.

Puedes verificar los detalles de un paquete instalado usando el comando `pip show`. Ejecuta el siguiente comando en la terminal para confirmar que `matplotlib` está instalado.

```bash
pip show matplotlib
```

## Importar matplotlib.pyplot como plt

En este paso, importarás el módulo necesario de Matplotlib en tu script de Python. El núcleo de la funcionalidad de trazado de Matplotlib está contenido dentro del módulo pyplot.

Por convención, matplotlib.pyplot se importa con el alias plt. Este alias, estándar en la industria, hace que tu código sea más conciso y legible, ya que puedes escribir plt.function() en lugar de matplotlib.pyplot.function().

Primero, localiza el archivo main.py en el explorador de archivos en el lado izquierdo de tu IDE. Haz doble clic en él para abrirlo en el editor.

Ahora, añade la siguiente línea de código a main.py:

```python
import matplotlib.pyplot as plt
```
Esta línea le indica a Python que busque la biblioteca matplotlib.pyplot y ponga sus funciones a disposición en tu script bajo el nombre más corto plt.

## Verificar importación con comprobación de versión

En este paso, verificarás que la biblioteca se importó correctamente comprobando su versión desde el script. Acceder al atributo __version__ es una forma común y sencilla de confirmar que una biblioteca de Python se ha cargado y es accesible correctamente.

Modifica tu archivo main.py para añadir una sentencia print. Esto ejecutará el código y mostrará la versión de Matplotlib en la terminal.

Tu archivo main.py debería verse ahora así

```python
import matplotlib
import matplotlib.pyplot as plt

print(matplotlib.__version__)
```

Ahora, guarda el archivo y ejecútalo desde la terminal usando el comando python3:

```bash
python3 main.py
```
Después de ejecutar el script, verás el número de versión instalado impreso en la terminal.

```plaintext
3.10.0
```
Esto confirma que tu script de Python puede importar y utilizar correctamente la biblioteca Matplotlib.

## Crear un objeto figure simple

En este paso, crearás los objetos fundamentales para cualquier gráfico: una Figure y un Axes.

Una Figure es el contenedor de nivel superior para todos los elementos del gráfico. Puedes pensar en ella como el lienzo o ventana completa.
Un Axes es el área donde se grafican los datos con los ejes x e y. Una figura puede contener uno o más axes.
La forma más común de crear una figura y un conjunto de subplots (axes) es con la función plt.subplots(). Esta función devuelve una tupla que contiene un objeto Figure y un objeto Axes (o un array de objetos Axes).

Modifica tu archivo main.py. Puedes eliminar la sentencia print y añadir el código para crear un gráfico y guardarlo.

```python
import matplotlib.pyplot as plt

# Create a Figure and an Axes object
fig, ax = plt.subplots()

# Save the figure to a file
plt.savefig('empty_plot.png')
```

En este código, fig, ax = plt.subplots() crea una figura y un único axes. Dado que estamos en un entorno basado en web que no puede mostrar una ventana GUI, usamos plt.savefig('empty_plot.png') para guardar el contenido de la figura en un archivo de imagen llamado empty_plot.png.

Ahora, ejecuta el script desde la terminal:

```bash
python3 main.py
```

Este comando no producirá ninguna salida en la terminal. En su lugar, creará un nuevo archivo llamado empty_plot.png en tu directorio /home/labex/project.

## Mostrar un gráfico vacío usando plt.show()

En el paso anterior, generaste un archivo de imagen de tu gráfico. En este paso, aprenderás cómo verlo dentro del entorno de LabEx.

Como se mencionó, no podemos usar plt.show() para abrir una ventana emergente. La función plt.savefig() es nuestro método para "mostrar" el gráfico escribiéndolo en un archivo.

Para ver tu creación, mira el panel del explorador de archivos en el lado izquierdo del IDE. Deberías ver el archivo `empty_plot.png` que fue generado por tu script.

### Haz doble clic en **empty_plot.png**. (Se creó en Máquina Virtual)

Esto abrirá la imagen en una nueva pestaña dentro del IDE. Deberías ver un gráfico simple y en blanco con un eje x y un eje y. ¡Esta es tu primera figura de Matplotlib generada con éxito!

Este paso no requiere que escribas ningún código nuevo ni que ejecutes ningún comando. Es puramente para observar el resultado de tu trabajo del paso anterior.

## Resumen

En este laboratorio, has aprendido los primeros pasos esenciales para trabajar con esta potente biblioteca de visualización. Has cubierto:

- Cómo verificar la instalación de Matplotlib usando pip.
- La convención estándar para importar la biblioteca: import matplotlib.pyplot as plt.
- Cómo crear un objeto básico Figure y Axes, los bloques de construcción de todos los gráficos, usando plt.subplots().
- Cómo guardar un gráfico en un archivo de imagen con plt.savefig(), una habilidad crucial para entornos sin GUI.

Ahora estás preparado para pasar a laboratorios más interesantes donde aprenderás a graficar datos reales y a personalizar tus visualizaciones.

# Lección 2: Gráficos de Líneas Básicos con Matplotlib

Empezado 29/05/2026

## Introducción

Matplotlib es una biblioteca completa para crear visualizaciones estáticas, animadas e interactivas en Python. Es una de las bibliotecas de visualización de datos más populares y es esencial para cualquier científico o analista de datos que trabaje con Python.

Un gráfico de líneas es uno de los tipos de gráficos más básicos y ampliamente utilizados. Muestra información como una serie de puntos de datos llamados 'marcadores' conectados por segmentos de línea recta. A menudo se utiliza para visualizar una tendencia en los datos a lo largo de intervalos de tiempo (una serie temporal), por lo tanto, la línea a menudo se dibuja cronológicamente.

En este laboratorio, aprenderá a crear un gráfico de líneas simple desde cero. Cubriremos todo el proceso: preparar los datos, graficarlos, agregar etiquetas descriptivas a los ejes y, finalmente, guardar el gráfico como un archivo de imagen que puede ver directamente.

## Preparar listas de datos x e y

En este paso, prepararemos los datos para nuestro gráfico. Antes de poder visualizar algo, necesita datos. Para un gráfico de líneas 2D simple, necesita dos conjuntos de datos: uno para el eje x (el eje horizontal) y otro para el eje y (el eje vertical).

Usaremos listas de Python para almacenar nuestros datos. Crearemos un conjunto de datos simple que represente el crecimiento de la población durante algunos años.

Primero, abra el archivo main.py ubicado en el directorio ~/project desde el explorador de archivos a la izquierda. El archivo ya contiene la declaración de importación necesaria.

Ahora, agregue el siguiente código a main.py para crear dos listas, x e y.

```python
import matplotlib.pyplot as plt

# Data for plotting
x = [2018, 2019, 2020, 2021, 2022]
y = [10, 12, 15, 18, 22]
```

Aquí, x representa los años y y representa la población en millones para cada año correspondiente. Estas dos listas servirán como las coordenadas para nuestro gráfico de líneas.

## Graficar la línea usando plt.plot(x, y)

En este paso, utilizaremos los datos que preparamos para crear el gráfico real. El módulo pyplot de Matplotlib, que importamos como plt, proporciona una función llamada plot() que es perfecta para esta tarea.

La función plt.plot() toma dos argumentos principales: los datos para el eje x y los datos para el eje y. Luego dibujará una línea que conecta los puntos definidos por estas coordenadas.

Agregue la siguiente línea a su script main.py, justo después de las listas de datos que creó en el paso anterior.

```python
import matplotlib.pyplot as plt

# Data for plotting
x = [2018, 2019, 2020, 2021, 2022]
y = [10, 12, 15, 18, 22]

# Create the plot
plt.plot(x, y)
```
Esta única línea de código le indica a Matplotlib que cree un gráfico de líneas utilizando las listas x e y como coordenadas. Sin embargo, si ejecuta el script ahora, aún no verá nada. Todavía necesitamos agregar etiquetas y guardar explícitamente el gráfico en un archivo.

## Añadir etiqueta al eje x con plt.xlabel()

En este paso, añadiremos una etiqueta al eje x. Un gráfico sin etiquetas a menudo carece de sentido porque el espectador no sabe qué representan los ejes. Es una parte crucial para crear visualizaciones claras e informativas.

Matplotlib proporciona la función plt.xlabel() para añadir una etiqueta al eje x. Simplemente pasa la etiqueta deseada como una cadena de texto a esta función.

Añadamos una etiqueta para el 'Año' a nuestro gráfico. Agrega la siguiente línea a tu script main.py después de la llamada a plt.plot().

```python
import matplotlib.pyplot as plt

# Data for plotting
x = [2018, 2019, 2020, 2021, 2022]
y = [10, 12, 15, 18, 22]

# Create the plot
plt.plot(x, y)

# Add x-axis label
plt.xlabel("Year")
```

Ahora, el eje horizontal de nuestro gráfico estará claramente marcado como 'Year'.

## Añadir etiqueta al eje y con plt.ylabel()

En este paso, añadiremos una etiqueta al eje y, completando el etiquetado básico de nuestro gráfico. Al igual que el eje x, el eje y necesita una etiqueta descriptiva para que los espectadores puedan entender los datos.

La función para esto es plt.ylabel(), que funciona exactamente igual que plt.xlabel(). Pasas el texto de la etiqueta como una cadena de texto.

Añadamos una etiqueta para 'Population' a nuestro gráfico. Agrega la siguiente línea a tu script main.py, justo después de la llamada a plt.xlabel().

```python
import matplotlib.pyplot as plt

# Data for plotting
x = [2018, 2019, 2020, 2021, 2022]
y = [10, 12, 15, 18, 22]

# Create the plot
plt.plot(x, y)

# Add x-axis label
plt.xlabel("Year")

# Add y-axis label
plt.ylabel("Population (in millions)")
```

Con ambos ejes etiquetados, nuestro gráfico es ahora mucho más comprensible.

## Mostrar gráfico con plt.show()

En este paso final, generaremos y visualizaremos nuestro gráfico. En un entorno de escritorio típico, podrías usar plt.show() para mostrar el gráfico en una nueva ventana. Sin embargo, en un entorno basado en web como LabEx, no podemos abrir ventanas GUI.

En su lugar, guardaremos el gráfico en un archivo de imagen utilizando la función plt.savefig(). Esta función guarda la figura actual en un archivo en tu directorio de proyecto.

Agrega la siguiente línea al final de tu script main.py. Esto guardará el gráfico como una imagen PNG llamada `line_plot.png`.

```python
import matplotlib.pyplot as plt

# Data for plotting
x = [2018, 2019, 2020, 2021, 2022]
y = [10, 12, 15, 18, 22]

# Create the plot
plt.plot(x, y)

# Add x-axis label
plt.xlabel("Year")

# Add y-axis label
plt.ylabel("Population (in millions)")

# Save the plot to a file
plt.savefig("line_plot.png")
```

Ahora, abre una terminal en el WebIDE (puedes usar el icono + en el panel de terminal o el menú Terminal > New Terminal). Ejecuta tu script con el siguiente comando:

```bash
python3 main.py
```

Después de que el comando termine, verás un nuevo archivo llamado `line_plot.png` aparecer en el explorador de archivos de la izquierda. Haz doble clic en line_plot.png para abrirlo y ver tu gráfico de líneas completado.

## Resumen

¡Felicitaciones! Has creado y guardado con éxito tu primer gráfico de líneas utilizando Matplotlib.

En este laboratorio, aprendiste el flujo de trabajo fundamental para crear un gráfico básico:

- **1. Preparar Datos:** Creaste listas de Python para contener los datos de tus ejes x e y.
- **2. Graficar Datos:** Usaste plt.plot() para generar el gráfico de líneas a partir de tus datos.
- **3. Añadir Etiquetas:** Hiciste el gráfico informativo añadiendo etiquetas con plt.xlabel() y plt.ylabel().
- **4. Guardar el Gráfico:** Aprendiste a usar plt.savefig() para guardar tu visualización en un archivo, lo cual es esencial en entornos sin GUI.

Esto es solo el comienzo de lo que puedes hacer con Matplotlib. Ahora puedes basarte en estas habilidades para crear visualizaciones más complejas y personalizadas. ¡Sigue explorando!

