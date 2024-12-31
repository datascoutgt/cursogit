# Buenas Prácticas de Ramificación, Fusión y Push en Git

Este documento describe las **buenas prácticas** para trabajar con ramas en Git, cómo fusionarlas y cómo subir los cambios al repositorio remoto. Además, incluye **ejercicios prácticos** para aplicar lo aprendido.

---

## **1. ¿Qué son las ramas en Git?**
**Ventajas:**
- Permite trabajar en paralelo.
- Facilita la colaboración.
- Ayuda a mantener limpio el historial de cambios.

### **Gráfico conceptual de ramas:**
```markdown
main (rama principal) ────●──────●───────●───
                             \ 
                              feature1 ─●────●───
```

---   

## **2. Crear y Cambiar a una Nueva Rama**
Para crear y cambiar a una nueva rama:

```bash
git checkout -b NombreDeRama
```

### **Ejercicio 1: Crear y Fusionar una Rama (Nivel Fácil)**
1. Crea una nueva rama llamada `feature1`:
   ```bash
   git checkout -b feature1
   ```
2. Crea o edita un archivo, por ejemplo:
   ```bash
   echo "# Este es un archivo nuevo" > archivo1.md
   git add archivo1.md
   git commit -m "Agregado archivo1.md"
   ```
3. Cambia a la rama principal (`master`):
   ```bash
   git checkout master
   ```
4. Fusiona los cambios de `feature1`:
   ```bash
   git merge feature1
   ```
5. Elimina la rama después de fusionarla:
   ```bash
   git branch -d feature1
   ```

---

## **3. Resolver Conflictos al Fusionar Ramas**
Cuando dos ramas modifican el mismo archivo de manera diferente, se produce un conflicto. Es necesario resolverlos manualmente antes de fusionar.

### **Ejercicio 2: Resolver un Conflicto (Nivel Intermedio)**
1. Crea dos ramas: `featureA` y `featureB`:
   ```bash
   git checkout -b featureA
   git checkout -b featureB
   ```
2. Edita el archivo `archivo_conflicto.md` en ambas ramas con contenido diferente.
   - En `featureA`:
     ```bash
     echo "Línea editada por featureA" > archivo_conflicto.md
     git add archivo_conflicto.md
     git commit -m "Cambio realizado por featureA"
     ```
   - En `featureB`:
     ```bash
     git checkout featureB
     echo "Línea editada por featureB" > archivo_conflicto.md
     git add archivo_conflicto.md
     git commit -m "Cambio realizado por featureB"
     ```
3. Cambia a la rama `master` y fusiona `featureA`:
   ```bash
   git checkout master
   git merge featureA
   ```
4. Intenta fusionar `featureB`, generando un conflicto:
   ```bash
   git merge featureB
   ```
5. Resuelve el conflicto editando manualmente el archivo:
   ```bash
   vim archivo_conflicto.md  # Edita y guarda el archivo
   git add archivo_conflicto.md
   git commit -m "Conflicto resuelto entre featureA y featureB"
   ```
6. Elimina las ramas una vez resueltas:
   ```bash
   git branch -d featureA
   git branch -d featureB
   ```

### **Gráfico de conflicto y resolución:**
```markdown
main ───────●───────●───┬───● (resuelto)
              \         / 
           featureA   featureB
```

---

## **4. Manejo de Hotfix (Corrección de Problemas Críticos)**
En un entorno real, a menudo se necesita corregir errores críticos rápidamente sin afectar el desarrollo en curso.

### **Ejercicio 3: Crear una Rama de Hotfix (Nivel Avanzado)**
1. Crea una rama `hotfix1` desde `master` para solucionar el problema:
   ```bash
   git checkout -b hotfix1
   ```
2. Realiza la corrección en el archivo correspondiente:
   ```bash
   echo "Corrección aplicada" > archivo_critico.md
   git add archivo_critico.md
   git commit -m "Hotfix: corregido el error crítico"
   ```
3. Fusiona `hotfix1` con `master` y sube los cambios:
   ```bash
   git checkout master
   git merge hotfix1
   git push origin master
   ```
4. Fusiona `hotfix1` también con `develop` para mantener ambos entornos sincronizados:
   ```bash
   git checkout develop
   git merge hotfix1
   git push origin develop
   ```
5. Elimina la rama después de resolver el problema:
   ```bash
   git branch -d hotfix1
   ```

---

## **5. Subir los Cambios al Repositorio Remoto**
Después de fusionar ramas, recuerda subir los cambios al repositorio remoto con:

```bash
git push origin master
```

Esto asegura que los demás colaboradores tengan acceso a los últimos cambios.

---

## **Resumen Final**
### Conceptos Clave:
- Crear ramas para nuevas funcionalidades o correcciones.
- Resolver conflictos durante la fusión.
- Eliminar ramas después de fusionarlas para mantener el repositorio limpio.

### **Gráfico General del Flujo de Trabajo:**
```markdown
master ────────●──────────●───────────────●───────
                 \        / \           /
              feature1  hotfix1      featureA
```
