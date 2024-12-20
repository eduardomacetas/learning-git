# Rebasing 

El rebasing es una técnica en Git que permite reescribir el historial de commits de una rama para mantener un flujo de trabajo limpio y lineal. Utilizando el comando `git rebase`, puedes aplicar los cambios de una rama sobre otra, lo cual puede ayudar a mejorar la legibilidad del historial del proyecto. Esta práctica es especialmente útil cuando trabajas en un equipo y quieres evitar los "merge commits" innecesarios.

## ¿Qué es el Rebasing?

En términos simples, el **rebasing** mueve toda una rama para que su punto de partida sea otro commit. Esto se logra reescribiendo los commits de esa rama y aplicándolos sobre otro commit base. A diferencia de un **merge**, que crea un commit de fusión adicional, el rebase mantiene un historial más limpio y lineal.

### Diferencia entre Git Merge y Git Rebase

- **Merge:** Combina dos ramas creando un nuevo commit de fusión.
  - Ejemplo: `git merge ramaA`
  - El historial tendrá un "merge commit", lo que puede hacer que el historial sea más complicado de leer.
- **Rebase:** Mueve los commits de una rama sobre otra sin crear un commit adicional
  - Ejemplo: `git rebase ramaA`
  = El historial se mantiene lineal, lo que facilita la navegación y la comprensión del flujo del proyecto.

## ¿Cuándo Utilizar el Rebasing?

El rebasing es útil en los siguientes casos:

1. **Mantener un historial limpio:** Al rebasear tus commits antes de fusionarlos a una rama principal (como main o master), eliminas los commits de fusión y creas un historial más lineal.
2. **Evitar conflictos de fusión:** Rebasear regularmente tu rama local sobre la rama principal ayuda a minimizar los conflictos cuando finalmente hagas el merge.
3. **Simplificar el trabajo con ramas temporales:** Si tienes una rama de características y muchos otros cambios están siendo hechos en la rama principal, el rebasing permite que sigas aplicando tus cambios sin complicar el historial.

## Cómo Realizar un Rebase

### 1. Rebase Interactivo

El **rebase interactivo** (`git rebase -i`) permite modificar el historial de commits de manera más controlada. Puedes editar, eliminar o reordenar commits.

#### Pasos para hacer un rebase interactivo:

1. Entra a la rama que deseas rebasear:
    ```bash
    git checkout mi-rama
    ```

2. Inicia el rebase interactivo:
    ```bash
    git rebase -i HEAD~n
    ```

    Donde `n` es el número de commits que deseas revisar. Por ejemplo, si quieres rebasear los últimos 5 commits, usa `HEAD~5`.

3. Git abrirá un editor donde podrás ver una lista de tus commits recientes. Aquí puedes cambiar el comando al principio de cada línea, como `pick`, `reword`, `edit`, `squash`, entre otros.

    - **pick:** Mantiene el commit tal como está.
    - **reword:** Modifica el mensaje del commit.
    - **edit:** Permite modificar el contenido de un commit.
    - **squash:** Fusiona el commit con el anterior.

4. Después de hacer los cambios, guarda y cierra el editor. Git aplicará los cambios y modificará el historial.

### 2. Rebase Normal

Un **rebase normal** se utiliza para aplicar los cambios de una rama sobre otra sin modificar los commits individuales.

#### Pasos para hacer un rebase normal:

1. Asegúrate de estar en la rama que deseas rebasear:
    ```bash
    git checkout mi-rama
    ```

2. Realiza el rebase sobre la rama principal (por ejemplo, `main`):
    ```bash
    git rebase main
    ```

    Esto tomará tus commits y los aplicará sobre la rama principal.

### 3. Resolución de Conflictos Durante el Rebase

Es posible que encuentres conflictos durante un rebase, especialmente si los mismos archivos han sido modificados en ambas ramas. Git te indicará los archivos en conflicto.

#### Pasos para resolver conflictos:

1. Abre los archivos en conflicto y resuélvelos manualmente.
2. Marca los archivos como resueltos:
    ```bash
    git add archivo_en_conflicto
    ```
3. Continúa con el rebase:
    ```bash
    git rebase --continue
    ```
    Si es necesario, repite estos pasos hasta que el rebase esté completo.

## Ventajas del Rebasing
- **Historial limpio y lineal:** Al rebasear, tu historial se mantiene ordenado, lo que facilita la comprensión del flujo de trabajo.
- **Menos commits de fusión:** Elimina los commits de fusión innecesarios, lo que hace que el historial sea más fácil de seguir.
- **Mayor control sobre el historial:** Con el rebase interactivo, puedes modificar y reorganizar los commits antes de que se fusionen con la rama principal.

## Desventajas del Rebasing

- **Reescritura del historial:** El rebase modifica el historial de commits, lo cual puede ser peligroso si ya has compartido esos commits con otros colaboradores. Por esta razón, es recomendable usar el rebase solo en ramas locales que aún no han sido compartidas.
- **Conflictos recurrentes:** Si no se hace con frecuencia, un rebase puede generar muchos conflictos que requieren ser resueltos manualmente.

## Conclusión

El **rebasing** es una herramienta poderosa que, cuando se usa correctamente, permite mantener un historial limpio y fácil de seguir. Sin embargo, es importante ser consciente de cuándo usarlo y cuándo evitarlo, especialmente cuando se trabaja en colaboración con otros. Si usas el rebasing de manera adecuada, podrás disfrutar de un flujo de trabajo más organizado y eficiente en Git.