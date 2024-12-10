# Forking: Trabajar con Forks de Repositorios para Desarrollo Independiente y Contribuciones

## Introducción
El concepto de *forking* (o bifurcación) permite a los desarrolladores crear una copia independiente de un repositorio existente. Este enfoque es ampliamente utilizado para colaborar en proyectos de código abierto o trabajar en un repositorio sin afectar directamente el original. Este documento describe cómo trabajar con forks de repositorios y cómo contribuir de vuelta mediante Pull Requests.

## ¿Qué es un Fork?
Un fork es una copia completa de un repositorio alojado en tu propia cuenta de usuario, en una plataforma como GitHub, GitLab o Bitbucket. Con esta copia, puedes:

- Experimentar: Realizar cambios sin riesgo de modificar el proyecto original.
- Colaborar: Probar ideas o solucionar errores y luego contribuir esas mejoras al proyecto principal.
- Trabajar Independientemente: Mantener una versión personalizada del proyecto

## Flujo de Trabajo con Forks

### 1. Realizar un Fork de un Repositorio
Desde la plataforma de Git de tu elección (GitHub, GitLab, etc.):

1. Navega al repositorio original.
2. Haz clic en el botón **Fork**.
3. Selecciona tu cuenta personal o de organización para crear el fork.

Esto crea una copia completa del repositorio bajo tu control.

### 2. Clonar el Fork en tu Máquina Local
Una vez que tengas el fork en tu cuenta, clónalo localmente para trabajar en él:

```bash
git clone https://github.com/tu-usuario/nombre-del-repositorio.git
cd nombre-del-repositorio
```

### 3. Configurar el Remoto del Proyecto Original
Es buena práctica agregar un remoto adicional para sincronizar con el repositorio original (*upstream*):

```bash
# Agregar el remoto del repositorio original
git remote add upstream https://github.com/autor-original/nombre-del-repositorio.git

# Verificar remotos
git remote -v
```

Esto configurará dos remotos:

- origin: Tu fork.
- upstream: El repositorio original.

### 4. Trabajar en el Fork

1. Crea una rama para los cambios que planeas realizar:

    ```bash
    git checkout -b nombre-de-la-rama
    ```

2. Realiza tus cambios y realiza commits regularmente:

    ```bash
    git add .
    git commit -m "feat: implementar nueva funcionalidad"
    ```

3. Envía tus cambios a tu fork:
  
    ```bash
    git push origin nombre-de-la-rama
    ```

### 5. Mantener el Fork Sincronizado con el Proyecto Original
Si el repositorio original recibe actualizaciones, sincroniza tu fork regularmente:

```bash
# Obtener actualizaciones del repositorio original
git fetch upstream

# Fusionar cambios en tu rama principal
git checkout main
git merge upstream/main

# Subir cambios sincronizados a tu fork
git push origin main
```

### 6. Contribuir al Proyecto Original (Pull Request)
Cuando tus cambios estén listos, crea un Pull Request (PR) para contribuir de vuelta al repositorio original:

1. Navega a tu fork en la plataforma.
2. Selecciona la rama que contiene tus cambios.
3. Haz clic en Compare & pull request.
4. Proporciona un título y descripción detallados.
5. Envía el PR para revisión.

## Buenas Prácticas al Trabajar con Forks

1. **Mantén tu Fork Actualizado:** Sincroniza regularmente con el repositorio original para evitar conflictos al enviar un PR.

2. **Haz Cambios en Ramas Separadas:** Usa ramas específicas para cada conjunto de cambios.

3. **Proporciona PRs Detallados:** Explica claramente los cambios realizados, el problema que resuelven y cómo probarlos.

4. **Sigue las Normas del Proyecto:** Revisa las guías de contribución del repositorio original.

5. **Evita Realizar Cambios en la Rama Principal (main):** Trabaja siempre en ramas dedicadas para mantener un historial limpio.

## Ejemplo de Flujo de Trabajo
1. Realizas un fork de un proyecto de GitHub.
2. Clonas el fork y creas una rama llamada `fix/typo-in-readme`.
3. Corriges un error tipográfico en el archivo `README.md` y realizas un commit:

    ```bash
    git add README.md
    git commit -m "fix: corregir error tipográfico en README.md"
    ```

4. Subes los cambios a tu fork:

    ```bash
    git push origin fix/typo-in-readme
    ```

5. Envías un Pull Request al repositorio original para que revisen y fusionen tus cambios.

## Conclusión

Trabajar con forks es una técnica poderosa para colaborar en proyectos de código abierto o realizar cambios independientes sin riesgo de afectar el repositorio original. Al dominar este flujo de trabajo, puedes contribuir efectivamente a proyectos externos y mantener un historial limpio y organizado para tu desarrollo.
