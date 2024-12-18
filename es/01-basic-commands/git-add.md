# Git Add

## Concepto

Es el comando que mueve al índice las modificaciones que hayamos realizado. El índice es un snapshot del contenido del área de trabajo en un momento dado.
Este snapshot es el que posteriormente se convertirá en un commit.

## Como funciona

Es la forma de decirle a Git qué cambios particulares se realizarán en la próxima confirmación.


## Comando(s)

+ - git add . : añade todos los cambios al indice
+ - git add <file> : añade todos los cambios de un archivo en especifico al indice
+ - git add -p : inicia una sesión interactiva que permite elegir que parte de los archivos modificados se agregan al staging area

## Ejemplo práctico usando git add <file> 

1. Dirigete al directorio en el que se encuentran los archivos a anadir al indice (usa los comandos [cd], [cd..], [mkdir], [ls]) para poder ubbicarte en el lugar deseado
2. Escribe "git add" seguido del nobre del archivo, deberia quedar asi: git add miarchivo.md
3. Presiona ENTER
4. Git procedera a anadir el archivo deseado al indice con todas sus modificaciones

## Recurso / Bibliografía
- https://aprendegit.com/opciones-del-comando-git-add/