# Merging: Fusionar ramas en la base de código principal

## Introducción
En Git, fusionar (merge) es una operación clave que permite combinar los cambios de una rama con otra. Generalmente, este proceso se utiliza para incorporar cambios de una rama de trabajo (por ejemplo, `feature/nueva-funcionalidad`) en la rama principal (`main` o `master`). Este documento explica cómo funciona el merge, los tipos de fusiones disponibles y cómo manejar conflictos que puedan surgir.

## ¿Qué es un merge en Git?

Un merge combina el historial de commits de dos ramas en una sola rama. Esto es útil para integrar nuevas características, corregir errores o unificar ramas de desarrollo colaborativo.

El comando principal para realizar una fusión es:

```bash
git merge <rama_a_fusionar>
```

Por ejemplo, si estás en la rama `main` y deseas fusionar los cambios de `feature/nueva-funcionalidad`:

```bash
git checkout main
git merge feature/nueva-funcionalidad
```

## Tipos de Merge

1. **Fast-forward Merge:** Ocurre cuando la rama principal no tiene commits adicionales desde que se creó la rama de trabajo. En este caso, Git simplemente avanza el puntero de la rama principal al último commit de la rama de trabajo.

    ```bash
    git merge feature/nueva-funcionalidad
    ```

    Este tipo de merge no crea un nuevo commit de fusión.

2. **Recursive Merge (Three-Way Merge):** Se utiliza cuando ambas ramas tienen commits adicionales. Git combinará los cambios de ambas ramas creando un nuevo commit de fusión. Ejemplo:

    ```bash
    git merge feature/nueva-funcionalidad
    ```

    El resultado será un commit de merge que une ambos historiales.

## Cómo Fusionar Ramas

1. **Cambiar a la rama donde deseas fusionar los cambios:** 

    ```bash
    git checkout main
    ```

2. **Ejecutar el merge:**

    ```bash
    git merge <rama_a_fusionar>
    ```

3. **Verificar el estado después de la fusión:**

    ```bash
    git status
    ```

4. **Confirmar los cambios fusionados:**

    ```bash
    git log --oneline
    ```

## Manejo de Conflictos

En algunos casos, Git no puede fusionar automáticamente los cambios, lo que genera un conflicto. Esto suele suceder si los mismos archivos o líneas fueron modificados en ambas ramas.

### Cómo resolver conflictos:

1. **Identificar los archivos con conflictos:** Git mostrará los archivos problemáticos después de intentar una fusión.

2. **Editar los archivos manualmente:** Los archivos con conflictos tendrán marcas como estas:

    ```text
    <<<<<<< HEAD
    Versión de la rama actual
    =======
    Versión de la rama fusionada
    >>>>>>> feature/nueva-funcionalidad
    ```

    Resuelve el conflicto eligiendo o combinando las versiones.

3. **Marcar los conflictos como resueltos:** Una vez editados, añade los archivos al área de preparación:

    ```bash
    git add <archivo_con_conflicto>
    ```

4. **Completar la fusión:** Finalmente, confirma los cambios:

    ```bash
    git commit
    ```

## Opciones Avanzadas

- **Abortar una fusión en curso:** Si deseas deshacer una fusión que no fue completada:

    ```bash
    git merge --abort
    ```

- **Hacer un merge sin fast-forward:** Esto siempre crea un commit de fusión, incluso si un fast-forward sería posible:

    ```bash
    git merge --no-ff <rama_a_fusionar>
    ```

- **Fusionar una rama remota:** Antes de fusionar, asegúrate de obtener los últimos cambios del remoto:

    ```bash
    git fetch origin
    git merge origin/<rama_a_fusionar>
    ```

## Mejores Prácticas

1. **Fusiona frecuentemente:** Realiza fusiones regulares para minimizar conflictos.
2. **Usa nombres descriptivos para los commits de fusión:** Esto facilita entender el historial del proyecto.
3. **Prueba antes de fusionar:** Asegúrate de que los cambios de la rama a fusionar sean estables y estén probados.
4. **Mantén tu rama principal limpia:** Solo fusiona ramas que hayan sido revisadas y aprobadas.

## Conclusión
La operación de fusión en Git es una herramienta esencial para gestionar proyectos colaborativos. Comprender cómo realizar merges correctamente, resolver conflictos y emplear buenas prácticas ayuda a mantener un historial de commits claro y un flujo de trabajo eficiente.