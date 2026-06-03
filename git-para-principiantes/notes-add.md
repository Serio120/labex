### ✅ **1. Ver el usuario y email globales (configuración general del equipo)**

Estos valores se aplican a *todos* los repositorios del sistema:

```bash
git config --global user.name
git config --global user.email
```

Para verlos juntos:

```bash
git config --global --list
```

---

### ✅ **2. Ver el usuario y email locales (solo para un repositorio concreto)**

Dentro del repositorio:

```bash
git config user.name
git config user.email
```

O toda la configuración local:

```bash
git config --local --list
```

---

### ✅ **3. Ver la configuración completa (global + local + sistema)**

```bash
git config --list
```

Git mostrará la configuración en este orden de prioridad:

1. **Local** (del repo)
2. **Global** (del usuario)
3. **Sistema**

---

### 🧩 **4. Ver quién hizo un commit concreto**

Si quieres saber qué usuario y email se usaron en un commit:

```bash
git log --pretty=format:"%h - %an <%ae>"
```

O para un commit específico:

```bash
git show <commit-id>
```
```diff
-----------------------------------------------------------------------------------------------------------------------
```
## Para **borrar el usuario y el email global en Git**, solo necesitas eliminar esas claves de la configuración global.
```diff
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
```
---

### 🧹 **1. Borrar usuario y email global**

Ejecuta:

```bash
git config --global --unset user.name
git config --global --unset user.email
```

---

### 🧹 **2. Verificar que se borraron**

```bash
git config --global --list
```

Si ya no aparecen `user.name` ni `user.email`, está limpio.

---

### 🔄 **3. (Opcional) Borrar toda la configuración global**

Si quieres dejar el archivo global vacío:

```bash
git config --global --edit
```

Se abrirá en tu editor (normalmente Vim o Nano). Puedes borrar las líneas manualmente y guardar.

---

### 🧩 **4. Recordatorio importante**

Si un repositorio tiene configurado un usuario **local**, Git seguirá usando ese:

```bash
git config --local --list
```

Si quieres borrarlo también:

```bash
git config --unset user.name
git config --unset user.email
```

---

```diff
-----------------------------------------------------------------------------------------------------------------------
```
## Para **Que el sistema de Reconozca o Iniciar tu GIT en el equipo nuevo**.
```diff
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
```

Vincular el repositorio local con un repositorio **remoto** y hacer el push inicial.

Flujo **completo y claro**, sin rodeos:

---

### 🚀 1. Crea el repositorio vacío en GitHub
En GitHub → **New Repository**  
No añadas README, .gitignore ni licencia (para evitar conflictos).

---

### 🔗 2. Conecta tu repo local con GitHub
En tu terminal, dentro de tu proyecto:

```bash
git remote add origin https://github.com/TU_USUARIO/NOMBRE_REPO.git
```

Puedes comprobar que quedó bien:

```bash
git remote -v
```

---

### 📤 3. Sube tu rama principal
Si tu rama se llama `main`:

#### Antes:

```bash
git branch -m master main
```

```bash
git push -u origin main
```

Si tu rama se llama `master`: (Esto nunca lo has utilizado)

```bash
git push -u origin master
```

---

### 🧩 Si GitHub te pide autenticación
GitHub ya no acepta contraseña. Necesitas un **Personal Access Token**.

Lo generas aquí:  
[https://github.com/settings/tokens](https://github.com/settings/tokens)

Y cuando Git te pida contraseña, pegas el token.

---

### 🎉 Listo
Tu repositorio local ya está publicado en GitHub.  
A partir de ahora solo usas:

```bash
git add .
git commit -m "mensaje"
git push
```

