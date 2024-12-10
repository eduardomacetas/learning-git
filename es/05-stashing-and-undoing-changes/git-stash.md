# Git Stash: Guardar Cambios Temporalmente

## Introducción

En Git, el comando `git stash` es una herramienta poderosa que te permite guardar temporalmente los cambios no confirmados en tu trabajo para que puedas cambiar de rama o realizar otras tareas sin perder esos cambios. Una vez que termines con la tarea temporal, puedes recuperar tus cambios y continuar trabajando en ellos. Esta es una forma práctica de evitar que los cambios no terminados interfieran con otros flujos de trabajo.

Este documento explica qué es `git stash`, cómo utilizarlo, y algunos casos de uso comunes.

## ¿Qué es `git stash`?

El comando `git stash` guarda los cambios actuales en tu área de trabajo (modificaciones no confirmadas y archivos sin seguimiento) en una "pila" para que puedas limpiar tu directorio de trabajo y cambiar de contexto sin perder esos cambios. Posteriormente, puedes aplicar esos cambios cuando lo desees.

Básicamente, git stash te permite:

- Guardar cambios que no están listos para ser comprometidos (commits).
- Cambiar de rama sin perder el trabajo en progreso.
- Recuperar esos cambios más tarde.

## Cómo usar `git stash`

### 1. Guardar los cambios

Para guardar los cambios actuales en tu área de trabajo, simplemente ejecuta:

```bash
git stash
```

Esto guarda tanto los cambios en archivos rastreados como los cambios en el área de preparación (staging area), y luego revierte el área de trabajo a su último commit.

### 2. Guardar solo los cambios no añadidos al área de staging

Si solo deseas guardar los cambios en los archivos que has modificado, pero no los que están en staging, usa la opción `--keep-index`:

```bash
git stash --keep-index
```

Esto guarda solo los cambios no añadidos al área de staging y deja los archivos en staging.

### 3. Guardar cambios con un mensaje

Es útil ponerle un nombre o mensaje a tu "stash" para saber qué cambios estás guardando. Puedes hacerlo con la opción `-m`:

```bash
git stash push -m "Trabajo en la nueva funcionalidad"
```

### 4. Ver el contenido de tu pila de stashes

Puedes ver los stashes guardados con el siguiente comando:

```bash
git stash list
```

Esto muestra una lista de los stashes guardados, como por ejemplo:

```less
stash@{0}: WIP on main: 1234abcd Completada la estructura del formulario
stash@{1}: WIP on feature-branch: 5678efgh Ajuste de diseño de la página
```

## Aplicar y eliminar cambios guardados

### 1. Aplicar los cambios de un stash

Para aplicar un stash y recuperar los cambios guardados, usa:

```bash
git stash apply
```

Esto aplica el último stash guardado sin eliminarlo de la pila. Si deseas aplicar un stash específico, usa el nombre del stash:

```bash
git stash apply stash@{1}
```

### 2. Eliminar un stash después de aplicarlo
Si ya no necesitas un stash después de haberlo aplicado, puedes eliminarlo con:

```bash
git stash drop stash@{0}
```

### 3. Aplicar y eliminar el stash simultáneamente
Si deseas aplicar y eliminar el stash al mismo tiempo, puedes usar:

```bash
git stash pop
```

Esto aplicará el último stash y lo eliminará de la pila.

## Otras opciones útiles de git stash

### 1. Guardar cambios sin archivos no rastreados

Si no quieres guardar los archivos no rastreados (archivos nuevos), usa la opción `--keep-index` y `--include-untracked`:

```bash
git stash --include-untracked
```

### 2. Recuperar un stash y los archivos no rastreados

Si guardaste archivos no rastreados, puedes recuperarlos con:

```bash
git stash apply --index
```

### 3. Ver el contenido de un stash específico

```bash
git stash show stash@{0}
```

Para obtener una vista más detallada de los cambios, usa la opción `-p`:

```bash
git stash show -p stash@{0}
```

## Cuándo usar `git stash`

- **Cambiar de rama temporalmente:** Si estás trabajando en algo y necesitas cambiar de rama, pero no deseas hacer un commit de tus cambios incompletos.
- **Guardar progreso sin comprometer:** Si necesitas guardar tu progreso de manera temporal sin hacer un commit.
- **Revertir cambios rápidamente:** Si necesitas limpiar tu espacio de trabajo y empezar de nuevo, pero quieres guardar los cambios en curso por si acaso.

## Consideraciones y mejores prácticas

1. **No depende del stash para cambios importantes:** Aunque el stash es útil, no es una herramienta para almacenar cambios permanentes. Usa commits regulares para guardar el trabajo importante.
2. **Usar mensajes claros:** Cuando usas `git stash`, siempre que sea posible, añade un mensaje descriptivo que explique por qué estás guardando los cambios.
3. **No confíes solo en el stash para cambios largos:** Si estás trabajando en algo que tomará tiempo, es mejor realizar un commit en una rama separada en lugar de depender solo de `git stash`.

## Conclusión

`git stash` es una herramienta invaluable para gestionar cambios temporales en tu flujo de trabajo sin comprometer el código incompleto. Con su capacidad para guardar, aplicar y gestionar cambios rápidamente, puedes cambiar de contexto sin perder tu progreso.

Recuerda que el uso de `git stash` está diseñado para ser una solución temporal, así que es importante organizar tu trabajo de manera que los cambios importantes se almacenen mediante commits regulares.

