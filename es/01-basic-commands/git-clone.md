# Git Clone

## Concepto

Es un comando de Git usado para clonar (copiar) un repositorio existente.

## Como funciona

- La clonacion crea automaticamente una conexion remtoa llamada "origin" que apunta al repositorio original.
- Cuando se hace git clone de igual forma se obtiene el historial de commits.

## Comando

+ - git clone

## Ejemplo práctico

1. Ingresa a un repositorio existente en Git con tu cuenta personal o de Ravn, por ejemplo:

- https://github.com/eduardomacetas/learning-git

2. Selecciona el boton verde "<> Code"
3. Nota que se desplegan opciones entre ellas "Clone"
4. Selecciona una de las 3 opciones existentes, por ejemplo: HTTPS
5. Copia el link
6. Abre una consola de comandos
7. Dirigete al directorio en el que quieras tener la copia de repositorio (usa los comandos [cd], [cd..], [mkdir], [ls]) para poder ubbicarte en el lugar deseado
8. Escribe "git clone" seguido del link que copiaste en el paso 5, deberia quedar asi: git clone https://github.com/eduardomacetas/learning-git
9. Presiona ENTER
10. Git procedera con el clonado de repositorio
11. Una vez termine, podras ver el contenido del repositorio clonado (copiado) en la ubicacion que elegiste en el paso 7
12. Listo! ya ejecutaste tu primer git clone!

## Recurso / Bibliografía
- https://www.atlassian.com/es/git/tutorials/setting-up-a-repository/git-clone