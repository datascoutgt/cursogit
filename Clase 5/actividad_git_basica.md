

# Actividad de Git: Clonar, Crear Ramas y Revertir Cambios

## Objetivo
Practicar el uso de comandos básicos de Git: clonar un repositorio, crear ramas, realizar cambios y manejar errores con `git reset` y `git revert`.

---

## Pasos de la Actividad

# 1. Clonar el Repositorio
Clona el repositorio de Git en tu máquina local utilizando el siguiente comando:

    ```bash
    git clone [URL_DEL_REPOSITORIO]
    ```

# 2. Crear una Rama Propia
Crea una nueva rama con tu nombre para trabajar en tu propia copia del repositorio:

    ```bash
    git checkout -b nombre-de-tu-rama
    ```

# 3. Hacer un Cambio  
Realiza un cambio con un pequeño error que luego tendrás que corregir en uno de los archivos del proyecto. Por ejemplo, edita el archivo `toma de asistencia.md` escribiendo tu nombre de forma incorrecta.

# 4. Agregar el Cambio y Hacer un Commit  
Agrega el archivo modificado al área de preparación (`staging area`) y confirma los cambios:

    ```bash
    git add toma\ de\ asistencia.md
    git commit -m "Corrige nombre mal escrito"
    ```

# 5. Uso de `git reset`  
Si decides que el último commit fue un error, usa `git reset` para deshacerlo.

    **Ejemplo de Reset Suave:**

    ```bash
    git reset --soft HEAD~1
    ```

    Después de esto, modifica el archivo corrigiendo tu nombre y realiza un nuevo commit con los cambios corregidos.

# 6. Fusión de Ramas 
Para fusionar tus cambios con la rama principal, usa:

    ```bash
    git checkout main
    git merge nombre-de-tu-rama
    git push origin main
    ```

# 7. Uso de `git revert`  
Modifica el archivo nuevamente, escribiendo el nombre de otro alumno de forma incorrecta. Agrega los cambios, realiza un commit, seguido de un push. Luego, revierte este commit usando `git revert`.

    - Revertir el último Commit:

    ```bash
    git revert HEAD
    ```

    Esto creará un nuevo commit que deshace los cambios del commit anterior.

---

# 8. Hacer un push
Realiza un push para subir los cambios a el repositorio.

## Conclusión  
Esta actividad te ayudará a familiarizarte con el uso de `git reset` y `git revert` para manejar errores y mantener un historial limpio y manejable en tus proyectos de Git.
