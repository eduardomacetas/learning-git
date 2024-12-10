# Git Status

## Concepto

Es el comando que permite ver los cambios que se han preparado, los que no y los archivos en los que Git no va a realizar el seguimiento.

## Como funciona

- Enumera los archivos que se han preparado, los que están sin preparar y los archivos sin seguimiento.
- Muestra lo que ha ocurrido con los comandos git add y git commit.

[IMAGEN]

## Comando

+ - git status

## Ejemplo práctico usando git add <file> 

1. Dirigete al directorio en el que se encuentran los archivos a anadir al indice (usa los comandos [cd], [cd..], [mkdir], [ls]) para poder ubbicarte en el lugar deseado
2. Escribe "git add" seguido del nobre del archivo, deberia quedar asi: git add miarchivo.md
3. Presiona ENTER
4. Git procedera a anadir el archivo deseado al indice con todas sus modificaciones
5. Escribe "git status"
6. Presiona ENTER
7. Git te mostrara en color verde el nombre del archivo miarchivo.md

## Recurso / Bibliografía
- https://www.atlassian.com/es/git/tutorials/inspecting-a-repository#:~:text=El%20comando%20git%20status%20muestra,relativa%20al%20historial%20del%20proyecto.