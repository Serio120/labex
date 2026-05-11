# Laboratorio llamado: Redis para principiantes
Empezado 11/05/2026

## Lección 1: Instalación y configuración inicial de Redis

Instalar Redis y conectar al servidor.

En este paso, instalaremos Redis en la máquina virtual de LabEx y nos conectaremos al servidor Redis utilizando la herramienta de línea de comandos `redis-cli`. Redis es un almacén de estructuras de datos en memoria de código abierto, utilizado frecuentemente como base de datos, caché y agente de mensajes.

Primero, actualicemos las listas de paquetes para asegurarnos de tener las versiones más recientes del software. Abre una terminal en la máquina virtual de LabEx.

Ejecuta el siguiente comando:

```bash
sudo apt update
```

```
# Este comando actualiza la lista de paquetes disponibles. Deberías ver una salida que indica que las listas de paquetes se están actualizando
```

A continuación, instala Redis utilizando el comando `apt install`:

```bash
sudo apt install redis-server
```
Una vez completada la instalación, inicia el servidor Redis:

Este comando instalará el servidor Redis y sus dependencias. Es posible que se te solicite confirmar la instalación escribiendo `y` y presionando Enter.

Una vez completada la instalación, inicia el servidor Redis:

```bash
sudo service redis-server start
```

Ahora, conectémonos al servidor Redis utilizando el comando `redis-cli`. Este comando abre la interfaz de línea de comandos de Redis, permitiéndote interactuar con el servidor.

```bash
redis-cli
```
Deberías ver un prompt que se ve así:

```bash
127.0.0.1:6379>
```
Esto indica que ahora estás conectado al servidor Redis y puedes comenzar a ejecutar comandos. Mantén esta conexión abierta para el siguiente paso.
