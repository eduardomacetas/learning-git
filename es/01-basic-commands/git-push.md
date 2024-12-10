# Git Push

## Concepto

Es el comando que te permite subit los commits desde tu rama local en tu repositorio git local al repositorio remoto.

## Como funciona

- Dado que este comando sobrescribe los cambios, solo debe ejecutarse con una rama vacía como objetivo.
- Git push sobrescribe otros cambios, por lo que el comando debe utilizarse con cuidado.
- Es la contraparte del git pull.

[IMAGEN]

## Comando

+ - git push <nombre del repositorio> <nombre de la rama> : sube los cambios del repositorio y rama indicados al repositorio remoto
+ - git push --all <NOMBRE-REMOTO> : --all es la bandera que señala que quieres subir todas las ramas al repositorio remoto, NOMBRE-REMOTO es el nombre del repositorio remoto al cual las quieres subir.
+ - git push --force <NOMBRE-REMOTO> <RAMA-REMOTA> : ignora los cambios locales hechos al repositorio Git en Github(Lo cual hacen la mayoría de desarrolladores para dar una solución rápida al servidor de desarrollo) luego puedes usar el comando —force para subir ignorando esos cambios.

## Ejemplo práctico usando git push 

1. Dirigete al directorio en el que se encuentran los archivos a anadir al indice (usa los comandos [cd], [cd..], [mkdir], [ls]) para poder ubbicarte en el lugar deseado
2. Realiza algun cambio al archivo "miarchivo.md"
3. Escribe "git add" seguido del nobre del archivo, deberia quedar asi: git add miarchivo.md
4. Presiona ENTER
5. Git procedera a anadir el archivo deseado al indice con todas sus modificaciones
6. Escribe "git status"
7. Presiona ENTER
8. Git te mostrara en color verde el nombre del archivo miarchivo.md lo que significa que se guardara en la proxima confirmacion
9. Escribe "git commit"
10. Se abrira un editor de texto que solicitara un mensaje de registro de confirmacion junto con una lista de lo que se confirmara
11. Escribe "git push -u origin miarchivo.md"
12. Los cambios hechos al archivo ya fueron subidos al repositorio remoto

## Buenas practicas

- Revisa el arhivo, rama que quieres subir al repositorio remoto antes de ejecutar el comando git push.

## Recurso / Bibliografía
- https://www.freecodecamp.org/espanol/news/el-comando-git-push-explicado/ 
