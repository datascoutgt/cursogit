### Actividad de Proyecto Colaborativo:

## Objetivo general:

Cada equipo trabajará en un proyecto colaborativo, donde deberá seguir un flujo de trabajo ordenado utilizando Git y Github, con roles definidos (Las instrucciones se muestran al final del documento).El objetivo es garantizar la seguridad de la empresa y asegurar que ningún archivo que contenga datos sensibles o credenciales sea compartido en el repositorio. Se espera que los equipos practiquen el uso de gitignore, commits, git rm y la resolución de conflictos, aplicando buenas prácticas de colaboración en Git.

Con base en los siguentes roles, selecciona y asume un rol específico para llevar a cabo las tareas del proyecto:

1.Product Owner (PO)
2.Ingeniero de Datos
3.Desarrollador
4.Data Analyst

### Descripción de roles a trabajar:

 
### Product Owner (PO):

## Responsabilidades:
Levantar los requerimientos del proyecto y definir las funcionalidades clave.
Supervisar el avance del equipo y asegurarse de que los requerimientos se cumplan.

---

### Ingeniero de Datos:

## Responsabilidades:

Recolectar y asegurar que los datos están en un formato adecuado para su análisis.
Limpiar los datos si es necesario y asegurarse de que no haya valores inconsistentes.
Colaborar con el Desarrollador para garantizar que el script de análisis pueda procesar los datos correctamente.

---

### Desarrollador:

## Responsabilidades:

Asegurarse de que el script funcione correctamente y siga los requerimientos del Product Owner.
Optimizar el código para manejar los datos eficientemente.
Colaborar con el Data Analyst para garantizar que los datos procesados estén listos para la visualización.

---

### Data Analyst:

## Responsabilidades:


Crear gráficos y visualizaciones con los datos utilizando bibliotecas como matplotlib o seaborn.
Trabajar en la rama visualizacion-datos en colaboración con el Desarrollador para generar gráficos adecuados (ej., diagramas de barras, líneas, etc.).
Asegurarse de que las visualizaciones cumplan con los requerimientos y representen los datos correctamente.
Revisar la claridad y precisión de las visualizaciones para que sean comprensibles.

---
 
### Instrucciones:

De acuerdo con los roles asignados, coordina con tu equipo para definir claramente las responsabilidades de cada miembro. Luego, revisa el repositorio y asegúrate de que en la carpeta correspondiente a tu rol solo se visualicen los archivos apropiados. A continuación, se detallan los archivos que deben visualizarse o eliminarse según el rol:

Propietario del producto (PO) : Eliminar todos los archivos .csv (Usando comandos de git), ocultar api_keys_4 y el archivo .env.

Ingeniero de Datos : Eliminar todos los archivos .xlsx (Usando comandos de git), ocultar api_keys_3 y el archivo .env.

Desarrollador : Eliminar todos los archivos .csv (Usando comandos de git), ignorar api_keys_2y el archivo .env.

Analista de datos : Eliminar todos los archivos .xlsx, eliminar el archivo .pbix (Usando comandos de git), e ignorar api_keys_1 y el archivo env.


### Criterios de Evaluación:

Correcta implementación de .gitignore y exclusión de archivos sensibles.
Uso adecuado de git rm para eliminar archivos y su correspondiente confirmación.