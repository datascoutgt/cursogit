    # Guía para Crear un Archivo .gitignore

## Introducción
El archivo `.gitignore` permite a Git ignorar ciertos archivos o directorios que no deseas incluir en tu repositorio, como archivos de configuración locales, archivos generados automáticamente, o archivos temporales.

# Clonar el Repositorio
Clona el repositorio de Git en tu máquina local utilizando el siguiente comando:

    ```bash
    git clone [URL_DEL_REPOSITORIO]
    ```

## Paso a Paso para Crear un Archivo .gitignore

### 1. Abre tu Terminal o Consola de Comandos
Abre la terminal o consola de comandos en tu sistema operativo. Asegúrate de estar en el directorio raíz de tu repositorio Git.

### 2. Crea un Archivo .gitignore
Utiliza el comando `touch` para crear un archivo `.gitignore` en la raíz de tu proyecto.

```bash
touch .gitignore
```

### 3. Edita el archivo .gitignore
Abre el archivo .gitignore en su editor de texto preferido (por ejemplo, Visual Studio Code, Sublime Text, etc.) o edítelo directamente desde la terminal con un editor como nano o vim.

```bash
nano .gitignore
```

### 4. Añade las reglas para ignorar archivos. 
Escribe los nombres de los archivos o directorios que deseas que Git ignore. Utiliza las siguientes reglas básicas:

Ignorar archivos específicos: Escribe el nombre del archivo.
Ejemplo: config.local

Ignorar directorios completos: Agregue una barra inclinada / después del nombre del directorio.
Ejemplo: node_modules/

Ignorar todos los archivos de un tipo específico: Utiliza un asterisco * como comodín.
Ejemplo: *.log(Ignora todos los archivos con extensión .log)

Agrega los archivos y directorios a ignorar. 

```bash
informacion_confidencial.xlsx
documentos/
.env
```

### 5. Guarda y cierra el Archivo
Guarde el archivo .gitignore y ciérralo. En nano, puedes hacer esto presionando "Ctrl + X", luego "Y" para confirmar los cambios y "Enter" para salir.

```bash
    Ctrl + X
    +  Y
    +  Enter
```

### 6. Verifica que los Archivos se Están Ignorando
Para comprobar que los archivos o directorios están siendo ignorados, utilice el comando:

```bash
git status
```

### 7.Verificación del .gitignore y estado del archivo rastreado. 
Modifica el archivo .gitignore, eliminando la entrada del archivo informacion_confidencial.xlsx. Realiza un cambio en el archivo informacion_confidencial.xlsx, guárdalo, y luego utiliza git status para verificar si Git está rastreando el archivo.

```bash
git status
```

Después, vuelve a agregar el nombre del archivo al .gitignore y utiliza git status nuevamente para confirmar que Git ya no lo está rastreando.

### 8.Verificación del .gitignore y estado del archivo rastreado.

Si el archivo informacion_confidencial.xlsx sigue apareciendo en Git incluso después de haberlo agregado al archivo .gitignore, esto se debe a que el archivo ya fue rastreado. Para dejar de rastrearlo, debes eliminarlo del índice de Git sin borrar el archivo en tu sistema de archivos con este comando:

```bash
git rm --cached informacion_confidencial.xlsx
```
Luego, haz commit de estos cambios:

```bash
git commit -m "Dejar de rastrear informacion_confidencial.xlsx"
```

### 9. Eliminamos archivo CSV. 

Para eliminar archivos en Git, puedes usar el comando git rm.
```bash
git rm <nombre-del-archivo>
```

### 10. Confirma los cambios en Git
Agrega el archivo .gitignore a tu repositorio y realiza un commit para que se guarde en el historial de Git.

```bash
git add .gitignore
git commit -m "Añadir .gitignore para ignorar archivos innecesarios y eliminar archivos no deseados"
```
### 11. Haz push de los cambios. 

```bash
git push
```

