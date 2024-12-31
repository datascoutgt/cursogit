# Actividad de Git: Clonar, Crear Ramas y Manejar Errores con Git

## Objetivo
Practicar el uso de comandos esenciales de Git: clonar un repositorio, crear ramas, realizar cambios y manejar errores con `git restore`, `git reset` y `git rm`, además de reforzar conceptos previos como `git revert` y la fusión de ramas.

### Objetivos adicionales:
- **Exploración del Historial:** Uso de `git log` y `git blame`.
- **Manejo de Cambios No Confirmados:** Revertir y descartar cambios en curso.
- **Ejercicio Práctico:** Gestión avanzada de cambios y exploración del historial en proyectos reales.

---

## Diferencias entre git restore, git reset y git revert

### 1. git restore
- **Función principal:** Descartar cambios en archivos del directorio de trabajo (antes del staging).
- **Uso típico:** Cuando quieres eliminar modificaciones locales y restaurar el archivo a su última versión confirmada.
- **No afecta:** El historial de commits.

**Ejemplo:**
```bash
git restore archivo.txt
```

### 2. git reset
- **Función principal:** Deshacer commits y mover archivos fuera del área de staging.
- **Uso típico:** Cuando quieres eliminar un commit, pero mantener o descartar los cambios.
- **Tipos:**
  - `--soft`: Mantiene los cambios en el staging area.
  - `--hard`: Elimina el commit y todos los cambios del directorio de trabajo.

**Ejemplo:**
```bash
git reset --soft HEAD~1
```

### 3. git revert
- **Función principal:** Deshacer un commit creando uno nuevo que revierte los cambios previos.
- **Uso típico:** Cuando necesitas mantener un historial limpio y mostrar explícitamente la corrección de un error.
- **Afecta:** El historial de commits (crea uno nuevo).

**Ejemplo:**
```bash
git revert HEAD
```

---

## Explicación de `HEAD~1`
- **`HEAD`**: Representa el último commit en la rama actual.
- **`HEAD~1`**: Significa "un commit antes de HEAD". Se puede extender (`HEAD~2`, `HEAD~3`) para referirse a commits más antiguos.
- **`--soft` y `--hard`** afectan de diferente manera:
  - **`--soft`**: Deshace el commit pero mantiene los archivos modificados en el staging area.
  - **`--hard`**: Deshace el commit y elimina los cambios del directorio de trabajo.

---

## Creación de un Archivo para la Actividad
Antes de comenzar la actividad, crea un archivo llamado `README.md` y escribe tu nombre de manera intencionalmente incorrecta:

```bash
echo "Nombre erroneo" > README.md
```

Confirma el archivo:
```bash
git add README.md
git commit -m "Agrega README con nombre mal escrito"
```

---

## Pasos de la Actividad

### 1. Clonar el Repositorio
Clona el repositorio de Git en tu máquina local utilizando el siguiente comando:

```bash
git clone [URL_DEL_REPOSITORIO]
```

---

### 2. Crear una Rama Propia
Crea una nueva rama con tu nombre para trabajar en tu propia copia del repositorio:

```bash
git checkout -b nombre-de-tu-rama
```

---

### 3. Realizar un Cambio
Edita el archivo `README.md` y escribe tu nombre, pero introduce un error intencionalmente.

```bash
echo "Nombre erroneo" > README.md
```

Guarda el archivo y verifica los cambios:

```bash
git status
```

---

### 4. Deshacer Cambios (git restore)
Si deseas **descartar los cambios no guardados** en el archivo antes de agregarlo al staging area, utiliza `git restore`.

```bash
git restore README.md
```
Esto restaurará el archivo a su estado original antes de ser modificado.

---

### 5. Agregar el Cambio y Hacer un Commit
Si decides conservar el cambio, agrégalo al staging area y confirma el commit:

```bash
git add README.md
git commit -m "Corrige nombre mal escrito"
```

---

### 6. Deshacer Commits (git reset)
Si te das cuenta de que el commit fue un error, puedes deshacerlo con `git reset`.

**Reset Suave (mantiene los cambios en el directorio de trabajo):**
```bash
git reset --soft HEAD~1
```
Esto deshace el commit pero deja el archivo modificado en el staging area.

Corrige el archivo:
```bash
echo "Nombre correcto" > README.md
```

Realiza un nuevo commit con los cambios corregidos:
```bash
git add README.md
git commit -m "Nombre corregido"
```

---

### 7. Eliminar Archivos del Repositorio (git rm)
Si decides eliminar un archivo del repositorio (por ejemplo, un archivo innecesario), usa `git rm`.

```bash
git rm archivo_innecesario.md
```
Esto elimina el archivo del repositorio y del directorio de trabajo. Para confirmar, haz un commit:

```bash
git commit -m "Elimina archivo_innecesario.md"
```

---

### 8. Fusión de Ramas
Una vez que hayas corregido los errores y estés satisfecho con los cambios, fusiónalos en la rama principal.

```bash
git checkout main
git merge nombre-de-tu-rama
git push origin main
```

---

### 9. Revertir Cambios en un Commit (git revert)
Para revertir un commit específico (por ejemplo, si escribiste el nombre de otro alumno de forma incorrecta):

1. Modifica el archivo y realiza un commit:
```bash
echo "Nombre equivocado" > README.md
git add README.md
git commit -m "Nombre equivocado de alumno"
```

2. Usa `git revert` para deshacer el último commit:
```bash
git revert HEAD
```
Esto crea un nuevo commit que revierte el cambio anterior.

---

### 10. Hacer un Push
Sube todos los cambios al repositorio remoto:

```bash
git push origin main
```

---

## Conclusión
Esta actividad te proporciona práctica en el manejo de errores y gestión de cambios en Git. Aprender a usar `git restore`, `git reset` y `git rm` te permitirá mantener un repositorio limpio y organizado, mientras que `git revert` te ayuda a mantener un historial claro y recuperable.

