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


```





