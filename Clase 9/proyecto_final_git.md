
# **Actividad: Proyecto Final en Git (Individual)**

## **Objetivo**  
Aplicar conocimientos avanzados de Git y GitHub en un proyecto individual paso a paso, simulando tareas profesionales como gestión de ramas, resolución de conflictos y exploración del historial.

---

## **Instrucciones**

### **Paso 1: Crear un nuevo repositorio**
1. Ve a [GitHub](https://github.com) y crea un nuevo repositorio llamado `proyecto-final-git`.  
   - Agrega una breve descripción: *"Repositorio para el proyecto final del curso de Git y GitHub."*
   - Inicializa el repositorio con un archivo `README.md`.

---

### **Paso 2: Clonar el repositorio**
1. Copia el enlace del repositorio (HTTPS).  
2. En tu terminal, clona el repositorio:  
   ```bash
   git clone <URL_DEL_REPOSITORIO>
   ```
3. Navega al directorio del repositorio:  
   ```bash
   cd proyecto-final-git
   ```

---

### **Paso 3: Crear un archivo con datos personales**
1. Crea un archivo de texto llamado `datos_personales.txt`.  
2. En este archivo, agrega tu información personal:  
   ```
   Nombre: [Tu nombre completo]  
   Residencia: [Tu lugar de residencia]  
   Teléfono: [Tu número de teléfono]  
   ```

---

### **Paso 4: Configurar un archivo `.gitignore`**
1. Crea un archivo `.gitignore` en la raíz del repositorio.  
2. Agrega la siguiente línea para ignorar el archivo `datos_personales.txt`:  
   ```
   datos_personales.txt
   ```
3. Guarda los cambios.

---

### **Paso 5: Hacer el primer commit**
1. Verifica los cambios en tu repositorio:  
   ```bash
   git status
   ```
2. Agrega los archivos al área de preparación, exceptuando el archivo ignorado:  
   ```bash
   git add .
   ```
3. Haz el primer commit:  
   ```bash
   git commit -m "Primer commit: Agregado README.md y .gitignore"
   ```

---

### **Paso 6: Crear y trabajar en una nueva rama**
1. Crea una nueva rama para agregar una funcionalidad adicional:  
   ```bash
   git checkout -b feature/proyecto-futuro
   ```
2. Crea un archivo llamado `proyecto_futuro.txt`.  
3. En este archivo, describe un proyecto personal o profesional que te gustaría realizar:  
   ```
  Como por ejemplo:
   Proyecto: Sistema de seguimiento de tareas  
   Descripción: Una aplicación que permita gestionar tareas de manera colaborativa con opciones de análisis y reportes.  
   ```

4. Haz un commit en esta rama:  
   ```bash
   git add proyecto_futuro.txt
   git commit -m "Añadido proyecto_futuro.txt con descripción de un proyecto futuro"
   ```

5. Envía esta rama al repositorio remoto:  
   ```bash
   git push origin feature/proyecto-futuro
   ```

---

### **Paso 7: Modificar el archivo en la rama principal y generar un conflicto**
1. Cambia a la rama principal (`main`):  
   ```bash
   git checkout main
   ```
2. Edita el archivo `proyecto_futuro.txt` (si aún no está en la rama principal, crea un archivo con el mismo nombre) y agrega:  
   ```
   Este es un archivo base para proyectos futuros.
   ```

3. Haz un commit:  
   ```bash
   git add proyecto_futuro.txt
   git commit -m "Creado archivo base de proyecto_futuro.txt en la rama principal"
   ```

---

### **Paso 8: Hacer un merge y resolver conflictos**
1. Intenta hacer un merge de la rama `feature/proyecto-futuro` en la rama principal:  
   ```bash
   git merge feature/proyecto-futuro
   ```
2. Si hay un conflicto, Git marcará las líneas conflictivas. Resuélvelo manualmente editando el archivo.  
   Ejemplo de contenido final:  
   ```
   Este es un archivo base para proyectos futuros.
   Proyecto: Sistema de seguimiento de tareas  
   Descripción: Una aplicación que permita gestionar tareas de manera colaborativa con opciones de análisis y reportes.  
   ```

3. Marca el conflicto como resuelto y haz un commit:  
   ```bash
   git add proyecto_futuro.txt
   git commit -m "Conflicto resuelto: Integración de proyecto_futuro.txt"
   ```

---

### **Paso 9: Explorar el historial de cambios**
1. Utiliza `git log` para revisar el historial de commits:  
   ```bash
   git log --oneline
   ```
2. Usa `git blame` para identificar quién realizó cada cambio en el archivo `proyecto_futuro.txt`:  
   ```bash
   git blame proyecto_futuro.txt
   ```

---

### **Paso 10: Crear un archivo de documentación**
1. Crea un archivo llamado `documentacion.txt`.  
2. En este archivo, escribe los pasos realizados durante la actividad, incluyendo desafíos encontrados y cómo los resolviste.  

3. Haz un commit y realiza un push:  
   ```bash
   git add documentacion.txt
   git commit -m "Añadida documentación del proyecto"
   git push origin main
   ```

---

### **Entrega Final**
1. Asegúrate de que tu repositorio en GitHub contenga:  
   - El archivo `README.md`.  
   - El archivo `.gitignore`.  
   - El archivo `proyecto_futuro.txt` con los cambios integrados.  
   - El archivo `documentacion.txt` completo.  

2. Comparte el enlace del repositorio para su revisión.

---

