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

