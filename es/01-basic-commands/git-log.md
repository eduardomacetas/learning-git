# Git Log

## Concepto

Es el comando que te muestra todos los commits en el historial del repositorio.
Por defecto, el comando muestra los datos de cada commit:
- Secure Hash Algorithm (SHA).
- Autor.
- Fecha.
- Mensaje del commit.

## Como funciona

- Git utiliza el visualizador de archivos less para navegar por el historial de los commit's. Tu puedes navegar por él, con los siguientes comandos:

    - Para bajar una línea, utilice j o ↓.
    - Para desplazarse una línea hacia arriba, utilice k o ↑.
    - Para bajar una página, utilice la barra espaciadora o el botón Page Down.
    - Para avanzar una página, utilice b o el botón de avance de página.
    - Para salir del registro, utilice q.

[IMAGEN]

## Comando

+ - git log : Muestra el historial completo.
+ - git log -n <LIMITE> : Muestra solo el numero indicado de commit.
+ - git log --oneline : Condensa cada commit en una sola línea, lo que es útil para obtener una descripción general de los cambios.
+ - git log --stat : Agrega información sobre qué archivos han cambiado para cada commit y la cantidad de filas agregadas/modificadas.


## Ejemplo práctico usando git log 

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
13. Escribe "git log"
14. Podras ver los commits que se realizaron


## Recurso / Bibliografía
- https://aulab.es/articulos-guias-avanzadas/76/el-comando-git-log-en-git 
