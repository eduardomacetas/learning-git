# Git Revert: Crear un commit para deshacer cambios introducidos por un commit previo

## Introducción

El comando `git revert` es una herramienta de Git diseñada para deshacer cambios realizados en un commit específico, creando un nuevo commit que invierte los cambios introducidos. A diferencia de `git reset`, no altera el historial existente, lo que lo convierte en una opción segura para corregir errores en repositorios compartidos.

## ¿Qué hace `git revert`?
  - Crea un **nuevo commit** que deshace los cambios de un commit anterior.
  - Mantiene el historial del proyecto limpio y lineal.
  - Es ideal para colaborar en equipos, ya que no reescribe el historial.

## Uso básico de `git revert`

1. **Identificar el commit a revertir:** Utiliza el comando git log para encontrar el hash del commit que deseas revertir.

    ```bash
    git log --oneline
    ```

    Salida:

    ```bash
    3e1f9b2 Agregar nueva funcionalidad
    f5a80ab Actualización de la documentación
    7c92a19 Corrección de errores menores
    ```

2. **Revertir un commit:** Una vez identificado el hash, usa el comando:

    ```bash
    git revert <commit_hash>
    ```

    Por ejemplo, para revertir el commit `3e1f9b2`:

    ```bash
    git revert 3e1f9b2
    ```

    Esto abrirá un editor de texto para confirmar el mensaje del nuevo commit. Puedes editarlo o aceptar el mensaje predeterminado.

## Opciones comunes de `git revert`

1. **Revertir sin abrir el editor de mensajes:** Usa la opción `--no-edit` para revertir y aceptar automáticamente el mensaje de commit:

    ```bash
    git revert <commit_hash> --no-edit
    ```

2. **Revertir múltiples commits:** Si necesitas revertir varios commits a la vez, usa el rango de commits:

    ```bash
    git revert <start_commit>..<end_commit>
    ```

    Nota: Esto revierte los commits en orden inverso.

3. **Revertir sin aplicar los cambios directamente:** Usa la opción `--no-commit` para preparar los cambios pero sin crear un nuevo commit automáticamente:

    ```bash
    git revert <commit_hash> --no-commit
    ```

    Luego, puedes revisar los cambios y confirmar con:

    ```bash
    git commit
    ```

## Casos de uso

1. **Deshacer un cambio específico sin afectar otros:** Cuando un commit introduce un error y quieres eliminar sus efectos sin tocar otros commits.

2. **Revertir cambios en un entorno compartido:** Si ya has compartido el commit con tu equipo y necesitas revertirlo sin modificar el historial existente.

3. **Revertir un merge commit:** Usa `-m` para especificar el padre del merge que deseas conservar. Por ejemplo:

    ```bash
    git revert -m 1 <merge_commit_hash>
    ```

## Ejemplo práctico

Supongamos que tienes el siguiente historial:

```bash
3e1f9b2 Agregar nueva funcionalidad
f5a80ab Actualización de la documentación
7c92a19 Corrección de errores menores
```

El commit `3e1f9b2` introdujo un error. Para revertirlo:

1. Ejecuta:

    ```bash
    git revert 3e1f9b2
    ```

2. Esto crea un nuevo commit con un mensaje como:

    ```bash
    Revert "Agregar nueva funcionalidad"
    ```

    Ahora, el historial se ve así:

    ```bash
    d12a4f8 Revert "Agregar nueva funcionalidad"
    3e1f9b2 Agregar nueva funcionalidad
    f5a80ab Actualización de la documentación
    7c92a19 Corrección de errores menores
    ```

## Diferencias entre `git revert` y `git reset`

## Conclusión
`git revert` es una herramienta esencial para mantener un historial limpio y seguro en proyectos colaborativos. Es ideal para corregir errores sin alterar commits existentes, asegurando que todos los miembros del equipo puedan trabajar con un historial consistente y confiable.

|Característica  | `git revert`                           |`git reset`                                 |
|----------------|----------------------------------------|--------------------------------------------|
|Historial       |Mantiene el historial completo          |Puede reescribir el historial               |
|Colaboración    |Seguro para repositorios compartidos    |No es seguro si otros ya han clonado la rama|
|Efecto          |Crea un nuevo commit que deshace cambios|Deshace commits moviendo HEAD hacia atrás   |

## Conclusión
`git revert` es una herramienta esencial para mantener un historial limpio y seguro en proyectos colaborativos. Es ideal para corregir errores sin alterar commits existentes, asegurando que todos los miembros del equipo puedan trabajar con un historial consistente y confiable.

