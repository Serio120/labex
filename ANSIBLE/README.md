<h2 align=center>******** POR MAQUETAR Y COMPLETAR ********</h2>

# Ansible

A brief description of what this project does and who it's for

En este laboratorio, aprenderá a instalar Ansible Core en un sistema Red Hat Enterprise Linux (RHEL). Ansible es una poderosa herramienta de automatización que le permite gestionar y configurar sistemas, desplegar aplicaciones y orquestar flujos de trabajo de TI complejos.

Utilizará el gestor de paquetes dnf con privilegios sudo para instalar el paquete ansible-core, que proporciona el motor central de Ansible y las herramientas de línea de comandos. Después de la instalación, verificará que Ansible funciona correctamente comprobando su versión y ejecutando comandos básicos.

Esta es una habilidad fundamental para los administradores de sistemas e ingenieros de DevOps que trabajan con sistemas Red Hat Enterprise Linux.

## Instalar Ansible Core usando dnf

En este paso, instalará el paquete ansible-core utilizando el gestor de paquetes dnf. Ansible Core proporciona el motor esencial de Ansible, incluyendo ansible, ansible-playbook, y otras herramientas de línea de comandos fundamentales necesarias para las tareas de automatización.

dnf (Dandified YUM) es la herramienta estándar para gestionar paquetes de software en Red Hat Enterprise Linux. Dado que la instalación de software requiere privilegios administrativos, debe usar el comando sudo.

Ejecute el siguiente comando para instalar Ansible Core con confirmación automática:
## Deployment

To deploy this project run

```bash
  sudo dnf install ansible-core -y
```

La opción -y responde automáticamente "sí" a todas las indicaciones, haciendo que la instalación sea no interactiva. El sistema descargará e instalará ansible-core junto con sus dependencias de Python, incluyendo Jinja2 para plantillas y PyYAML para el procesamiento de YAML.

Debería ver una salida similar a esta, mostrando la resolución de paquetes y el progreso de la instalación:



## Verificar la Instalación de Ansible

Ahora que ha instalado Ansible Core, verifiquemos que la instalación fue exitosa comprobando la versión y confirmando que las herramientas esenciales de línea de comandos están disponibles.

Primero, compruebe la versión de Ansible ejecutando:
## Entendamos qué significa cada línea:

- ansible [core 2.14.18]: Muestra la versión instalada de Ansible Core
- config file: Apunta al archivo de configuración principal de Ansible que contiene la configuración predeterminada
- configured module search path: Directorios donde Ansible busca módulos personalizados
- ansible python module location: Dónde está instalado el código Python central de Ansible
- ansible collection location: Directorios donde se almacenan las colecciones de Ansible (módulos y plugins empaquetados)
- executable location: La ubicación real del binario del comando ansible
- python version: La versión del intérprete de Python que Ansible utiliza
jinja version: La versión del motor de plantillas utilizado por Ansible para contenido dinámico
- libyaml = True: Confirma que el analizador YAML rápido está disponible para un mejor rendimiento

Esto confirma que Ansible está correctamente instalado y listo para usar. A continuación, comprobemos también que el comando ansible-playbook está disponible:



```bash
  ansible-playbook --version
```

```
[labex@host ~]$ cd /home/labex/project
[labex@host project]$ ansible localhost -m ping
```

<h2 align=center>********* POR MAQUETAR Y COMPLETAR *********</h2>
