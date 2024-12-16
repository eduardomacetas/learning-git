# Git Pull

## Concepto

Es el comando que se emplea para extraer y descargar contenido desde un repositorio remoto y actualizar al instante el repositorio local para reflejar ese contenido.

## Como funciona

- El comando git pull ejecuta en primer lugar git fetch, que descarga el contenido del repositorio remoto especificado. Después, se ejecuta git merge para fusionar las referencias y los encabezados del contenido remoto en una nueva confirmación de fusión local.

[IMAGEN]

## Comando

+ - git pull <remote> : Recupera la copia del origen remoto especificado de la rama actual y fusiónala de inmediato en la copia local. Esto equivale a git fetch ＜remote＞ seguido de git merge origin/＜current-branch＞.
+ - git pull --no-commit <remote> : De manera similar a la invocación predeterminada, extrae el contenido remoto, pero no crea una nueva confirmación de fusión.

## Buenas practicas

- Revisa el repositorio del que quieres obtener los cambios

## Recurso / Bibliografía
- https://www.datacamp.com/es/tutorial/git-push-pull
