# Git Reset: Deshacer cambios restaurando la rama actual a un commit anterior

## Introducción
El comando `git reset` es una herramienta poderosa en Git que permite deshacer cambios en el historial de commits, ya sea eliminando commits, moviendo cambios al área de staging o descartándolos completamente. Este comando se utiliza para restablecer la rama actual a un estado previo, lo que puede ser útil para limpiar el historial o corregir errores.

## Modos de `git reset`

### `--soft`
- Mueve la referencia de la rama (HEAD) al commit objetivo, pero deja los cambios realizados en el área de staging.
- **Útil para:** Reorganizar commits sin perder cambios.
- **Comando:**

  ```bash
  git reset --soft <commit>
  ```

### `--mixed` (opción por defecto)

- Mueve la referencia de la rama al commit objetivo y deja los cambios en el área de trabajo, eliminándolos del staging.
- **Útil para:** Corregir el historial y volver a preparar los cambios manualmente.
- **Comando:**
  
  ```bash
  git reset --mixed <commit>
  ```

### `--hard`

- Restaura el historial, el área de staging y el área de trabajo al estado exacto del commit objetivo. **Todos los cambios no confirmados se pierden**.
- **Útil para:** Descartar completamente los cambios no deseados.
- **Comando:**

  ```bash
  git reset --hard <commit>
  ```

## Ejemplo de uso práctico

1. **Ver el historial de commits:** Antes de usar `git reset`, identifica el commit al que deseas volver con:

  ```bash
  git log --oneline
  ```

  Salida:

  ```bash
  3e1f9b2 Actualización de documentación
  f5a80ab Agregar funcionalidad X
  7c92a19 Corrección de errores
  ```

2. **Restaurar la rama al commit f5a80ab:**
 - Si quieres mantener los cambios en staging:

    ```bash
    git reset --soft f5a80ab
    ```

  - Si quieres conservar los cambios en el área de trabajo pero no en staging:

    ```bash
    git reset --mixed f5a80ab
    ```

  - Si deseas descartar completamente los cambios:

    ```bash
    git reset --hard f5a80ab
    ```

## Precauciones al usar `git reset`

  - **Pérdida de cambios:** Al usar `--hard`, los cambios no confirmados se pierden definitivamente. Asegúrate de que no necesitas esos cambios antes de usar esta opción.
  - **Impacto en el historial compartido:** No uses `git reset` para modificar el historial si ya has compartido los commits con otros colaboradores. En su lugar, considera usar `git revert`.

## Consejo adicional

Si accidentalmente usaste `git reset --hard` y perdiste cambios importantes, puedes intentar recuperarlos si no has hecho más cambios en el repositorio:

  ```bash
  git reflog
  ```

Esto mostrará el historial de referencias, permitiéndote volver al estado anterior.

## Conclusión

`git reset` es una herramienta esencial para manejar errores en commits y limpiar el historial de una rama. Sin embargo, debido a su capacidad para modificar y eliminar cambios, debe usarse con cuidado y entendiendo sus implicaciones.
