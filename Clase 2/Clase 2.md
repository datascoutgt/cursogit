# Clonar un Repositorio de Github a un Ordenador Local

Este tutorial te guiará en el proceso de clonar un repositorio desde Github a tu máquina local. 

## Pasos para Clonar un Repositorio

### 1. Obtener la URL del Repositorio

1. Inicia sesión en [Github](https://github.com/).
2. Navega al proyecto que contiene el repositorio que deseas clonar.
3. En la sección **Repositorios**, selecciona el repositorio que quieres clonar.
4. Haz clic en el botón **Clonar** y copia la URL. Asegúrate de elegir el protocolo adecuado (HTTPS o SSH).

### 2. Abrir la Terminal o Consola

Abre la terminal o consola de tu sistema operativo (puede ser Git Bash, Terminal, CMD, o PowerShell).

### 3. Usar el Comando `git clone`

En la terminal, navega a la carpeta donde deseas clonar el repositorio. Luego, ejecuta el siguiente comando:


git clone <URL-del-repositorio>

### 4. Comprobar el Estado del Repositorio

git status

### 5. Agrega los archivos si es necesario. 

git add . 

### 6. Realiza tu primer commit. 

git commit -m "mi primer commit"

### 7. Realiza un push al repositorio remoto. 
 
git push 
