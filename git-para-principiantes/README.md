# Laboratorio llamado: Git Para Principiantes
Empezado 20/04/2026

## Lección 1: Tu Primer Laboratorio GIT

  Aprendido:
  Resumen
  ¡Felicidades, viajero del tiempo! Acabas de completar tu primera aventura con Git. Repasemos las cosas increíbles que has aprendido:
  
    1. Cómo crear un repositorio Git (tu máquina del tiempo) usando git init.
    2. Cómo comprobar el estado de tu repositorio con git status.
    3. Cómo crear archivos y prepararlos para un commit usando git add.
    4. Cómo crear un commit (un punto de guardado en el tiempo) con git commit.
    5. Cómo ver el historial de tu proyecto usando git log.
    
  Tal vez te preguntes: "¿Por qué tomarse tantas molestias solo para guardar archivos?". ¡Excelente pregunta! He aquí por qué Git es tan poderoso:
  
    1. Historial detallado: Con Git, tienes un historial completo de tu proyecto. Puedes ver qué cambió, cuándo cambió y por qué.
    2. Experimentación: Git te permite experimentar libremente. Puedes crear diferentes versiones de tu proyecto sin miedo a perder tu trabajo original.
    3. Colaboración: Al trabajar en equipo, Git facilita ver quién hizo qué cambios y por qué.
    4. Copia de seguridad: Cada repositorio de Git es una copia de seguridad completa de tu proyecto, incluyendo todo su historial.
    
  Estos son los pilares fundamentales que los desarrolladores utilizan cada día para crear software asombroso. A medida que continúes tu camino, te basarás en estos conceptos básicos para gestionar proyectos más     complejos y colaborar con otros.
  
  Recuerda, todo el mundo empieza como principiante. Incluso los desarrolladores más experimentados estuvieron alguna vez donde tú estás ahora. ¡Sigue practicando, sigue experimentando y, lo más importante, diviértete!
  Si quieres aprender más sobre LabEx y cómo usarlo, puedes visitar nuestro Centro de Soporte. O puedes ver este vídeo para conocer más sobre LabEx.
  Tu viaje en el mundo de la programación y el control de versiones no ha hecho más que empezar. El Siguiente Laboratorio está a solo un clic de distancia. ¡Sigamos explorando y haciendo crecer tus habilidades! ¿Quién     sabe qué proyectos increíbles crearás con tus nuevos superpoderes de Git?

21/04/2026

## Lección 2: Operación Salto Cuántico

Initializing and Committing to Your Secret Repository Tasks
Create a new directory called quantum-leap in the ~/project folder.

```bash
mkdir quantum-lead
```

Initialize a new Git repository in the quantum-leap directory.

```bash
cd quantum-lead
git init
```
Create a file named classified.txt with the content "The flux capacitor requires 1.21 gigawatts of power."

```bash
echo "The flux capacitor requires 1.21 gigawatts of power." > classified.txt
```
Stage the classified.txt file for commit.

```bash
git add .
```
Commit the staged file with the message "Add top-secret flux capacitor information".

```bash
git commit -m "Add top-secret flux capacitor information"
```
Requirements
All operations must be performed in the ~/project/quantum-leap directory.
Use Git commands to complete the tasks.
The commit message must be exactly "Add top-secret flux capacitor information".
Example
After completing the challenge, running git log should show output similar to this:

```bash
git log
#q >> EXIT
```
22/04/2026 

## Lección 3: Gestión de la configuración de GIT

(ESTA LECCION LA TIENES QUE REPASAR)

```bash
    1  cd ~/project   # Pulsar ~ [ Alt Gr + 4 + espacio ]
    2  mkdir git-config-lab
    3  cd git-config-lab
    4  git init
    5  git config --list
    6  git config user.name

    9   git config --global user.name "MiNombre"
    10  git config --global user.email "minombre@example.com"
    11  git config --global user.name \n git config --global user.email


    13  git config --global color.ui auto
    14  git config --global color.ui
    15  git config --global core.editor nano
    16  git config --global core.editor


    18  git config --global core.autocrlf input
    19  git config --global core.autocrlf

    22  git config --global alias.st status
    23  git config --global alias.lg "log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit"
    24  git config --global alias.st\ngit config --global alias.lg

    26  cd ~/project/git-config-lab
    27  git config user.name "Lab User"
    28  git config user.name
    29  git config --global user.name
```
23/04/2026 

## Lección 4: Configuración de Identidad en la Máquina del Tiempo

(ESTA LECCION LA TIENES QUE DETALLAR)

```bash
    2  mkdir chrono-lab
    3  git config --global user.name "Chrononaut Alice"
    4  git config --global user.email "alice@timestream.com"
    5  git config --list

    7  cd chrono-lab
    8  git status
    9  git init
   10  git config user.name "Temporal Agent Bob"
   11  git config --list
   12  git config --local --list
   13  git config --global --list
```

23/04/2026 

## Lección 5: Trabajando con Archivos y el Área de Preparación

(EN ESTA LECCION HAY COSAS NUEVAS)

```bash

    1  cd ~/project
    2  mkdir git-staging-lab
    3  cd git-staging-lab
    4  git init
    5  echo "print('Hello, Git!')" > hello.py

    8  git add hello.py
    9  git status

   11  echo "*.log" > .gitignore
   12  echo "This is a log file" > debug.log
   13  git status
   14  git add .gitignore\ngit commit -m "Initial commit with hello.py and .gitignore"
   #   git add .gitignore
   #   git commit -m "Initial commit with hello.py and .gitignore"

   18  echo "print('Hello, Git! Welcome to the staging area.')" > hello.py
   19  git diff

   22  git add hello.py
   23  git restore --staged hello.py # Aquí esta otra novedad
   24  git status

```
#### Resumen

¡Felicidades, explorador de Git! Acabas de subir de nivel tus habilidades de control de versiones. Recapitulemos lo que has aprendido en este laboratorio:

Cómo añadir archivos al área de preparación usando `git add.`

Cómo ignorar archivos que no deseas rastrear mediante `.gitignore`.

Cómo visualizar los cambios en tus archivos antes de confirmarlos con `git diff`.

Cómo deshacer la preparación de los cambios usando `git restore --staged`.

Estas habilidades te brindan mucho más control sobre tu flujo de trabajo en Git.

El área de preparación, en particular, es una característica poderosa que te permite elaborar confirmaciones más significativas al seleccionar cuidadosamente qué cambios incluir.

**He aquí por qué estas habilidades son tan importantes:**

*Confirmaciones Selectivas:*
 El área de preparación te permite confirmar solo una parte de tus cambios, ayudándote a crear commits más pequeños y enfocados.

*Ignorar Archivos:*
 `.gitignore` ayuda a mantener tu repositorio limpio al excluir archivos que no necesitan control de versiones.

*Revisión de Cambios:*
 `git diff` te permite verificar tus cambios antes de confirmarlos, ayudándote a detectar errores a tiempo.

*Flexibilidad:*
 La capacidad de deshacer la preparación de los cambios te da la libertad de cambiar de opinión, haciendo que Git sea mucho menos intimidante.

A medida que continúes tu viaje con Git, descubrirás que estas habilidades son invaluables. Forman la base de un flujo de trabajo avanzado, permitiéndote gestionar proyectos complejos con facilidad.

Recuerda que dominar Git requiere práctica. No temas experimentar y cometer errores; ¡así es como aprendemos! Sigue explorando, sigue confirmando cambios y observa cómo evolucionan tus proyectos con el tiempo.

---

26/04/2026  ---> NECESARIO OTRO INTENTO

## Lección 6: La Maleta del Viajero del Tiempo

```bash

    1  cd ~/project\n
    2  mkdir time-travel-pack
    3  cd time-travel-pack
    # ERROR el archivo python no se llama crono_gadget, sa llama chrono_gadget
    4  echo "print('Initializing Chrono-Gadget...')" >> crono_gadget.py
    5  echo "print('Warning: Temporal flux detected!')" >> "crono_gadget.py"
    6  echo "print('Calibrating time circuits...')" >> "crono_gadget.py"
    7  echo "print('Ready for time travel!')" >> "crono_gadget.py"
    8  cat crono_gadget.py
    9  git init
   10  git add crono_gadget.py
# Aquí termina el primer ejercicio, bueno falta el git diff --staged

# SOLUCION mv crono_gadget.py chrono_gadget.py (Cambio de nombre del archivo )

# Esto de aquí parece que te sobra
   11  git commit -m "File in Staging Area to Local Repository"
   12  git status
   13  git diff --staged

```
##### Añadimos una explicación Aclaratoria

```markdown
## Git Diff

`git diff` compara el **working tree** con el **staging area** (cambios sin `add`).
`git diff --staged` compara el **staging area** con el **último commit** (cambios listos para commit).

```
[Último commit] → [Staging area] → [Working tree]
                ↑                 ↑
        git diff --staged      git diff
```

Para ver todos los cambios a la vez: `git diff HEAD`
```
