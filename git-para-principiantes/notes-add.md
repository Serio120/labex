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
-------------------------------------------------------------------------------------
```
## Para **borrar el usuario y el email global en Git**, solo necesitas eliminar esas claves de la configuración global.
```diff
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
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

## GGG

```bash
git branch -m master main
```
