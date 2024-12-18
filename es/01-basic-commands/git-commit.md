# Git Commit

## Concepto

Es el comando que captura una instantánea de los cambios preparados en ese momento del proyecto. 

## Como funciona

- Es la forma de confirmarle a Git qué cambios particulares se realizarán en un determinado momento en su repositorio local.
- En vez de hacer un cambio y confirmaro directamente en el repositorio central, los usuarios de Git tienen la oportunidad de acumular confirmaciones en su repositorio local.


## Comando(s)

+ - git commit : confirma la instantánea preparada. El comando abrirá un editor de texto que te pedirá un mensaje para la confirmación. Una vez escrito el mensaje, guarda el archivo y cierra el editor para crear la confirmación.
+ - git commit -a : confirma una instantánea de todos los cambios del directorio de trabajo. Esta acción solo incluye las modificaciones a los archivos con seguimiento (los que se han añadido con git add en algún punto de su historial).
+ - git commit -m "commit message" : un comando de atajo que crea inmediatamente una confirmación con un mensaje de confirmación usado. De manera predeterminada, git commit abrirá el editor de texto configurado localmente y solicitará que se introduzca un mensaje de confirmación. Si se usa la opción -m, se omitirá la solicitud de editor de texto a favor de un mensaje insertado.
+ - git commit --amend : Actualiza (modifica) una confirmacion

## Ejemplo práctico usando git commit 

1. Dirigete al directorio en el que se encuentran los archivos a anadir al indice (usa los comandos [cd], [cd..], [mkdir], [ls]) para poder ubbicarte en el lugar deseado
2. Realiza algun cambio al archivo "miarchivo.md"
3. Escribe "git add" seguido del nobre del archivo, deberia quedar asi: git add miarchivo.md
4. Presiona ENTER
5. Git procedera a anadir el archivo deseado al indice con todas sus modificaciones
6. Escribe "git status"
7. Presiona ENTER
8. Git te mostrara en color verde el nombre del archivo miarchivo.md lo que significa que se guardara en la proxima confirmacion.
9. Escribe "git commit"
10. Se abrira un editor de texto que solicitara un mensaje de registro de confirmacion junto con una lista de lo que se confirmara.

## Buenas practicas

- Git no exige que los mensajes de confirmación sigan ninguna limitación de formato específica, pero el formato canónico consiste en resumir toda la confirmación en la primera línea en menos de 50 caracteres, dejar una línea en blanco y, después, una explicación detallada de lo que ha cambiado.
- El mensaje de confirmacion debe ser directo y entendible para cualquier usuario indicando que cambios se confirmaron.

## Recurso / Bibliografía
- https://www.atlassian.com/es/git/tutorials/saving-changes/git-commit
