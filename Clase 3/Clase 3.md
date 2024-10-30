# Buenas Prácticas de Ramificación, Fusión y Push en Git

Este documento describe cómo realizar buenas prácticas de ramificación, fusión y push en Git, incluyendo cómo reflejar estos cambios en Github.

# 1. Crear una nueva rama y cambiar a ella
git checkout -b Nombre de la rama

# 2. Realizar cambios en la nueva rama y confirmarlos
vim archivo_modificado.md  # Edita el archivo (puedes usar cualquier editor)
git commit -a -m 'Nombre de commit'

# 3. Cambiar a la rama principal (master)
git checkout master

# 4. Crear una rama para resolver un problema crítico
git checkout -b Rama3

# 5. Realizar cambios en la rama Rama3 y confirmarlos
vim archivo_modificado.md  # Edita el archivo para corregir el problema
git commit -a -m 'Nombre de commit'

# 6. Fusionar la rama Rama3 en la rama principal
git checkout master
git merge Rama3

# 7. Subir los cambios urgentes a repositorio remoto
git push 
 
# 8. Eliminar la rama Rama3 después de fusionarla
git branch -d Rama3

# 9. Terminar los cambios en la Rama2, agregarlos, realizar el commit y fusionar la rama Rama2 en la rama principal
git add . 
git commit -m "Nombre de commit"
git checkout master
git merge Rama2

=======
# 10. Subir las modificaciones
git push

# 11. Eliminar la rama Rama2 después de fusionarla
git branch -d Rama2
