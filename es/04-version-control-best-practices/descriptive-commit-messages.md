# Commits con Descripciones Claras

## Concepto

Un mensaje descriptivo de commit es una breve descripción que explica claramente los cambios realizados en el código fuente de un proyecto. Estos mensajes son esenciales para facilitar el seguimiento del historial de cambios, ayudar a otros desarrolladores (o a ti mismo en el futuro) a comprender las razones detrás de una modificación, y mantener un historial ordenado y útil en el repositorio.

## Importancia de los mensajes descriptivos

1. **Colaboración eficiente:** Los mensajes claros permiten que otros desarrolladores comprendan rápidamente el propósito de un cambio sin necesidad de leer todo el código modificado.
2. **Depuración más rápida:** Un historial bien documentado facilita identificar y revertir cambios que introdujeron errores.
3. **Mejora del mantenimiento:** Los proyectos a largo plazo se benefician de un historial legible y organizado, especialmente cuando los desarrolladores cambian con el tiempo.

## Estructura recomendada

Un buen mensaje de commit generalmente incluye:

1. **Título breve (resumen del cambio):** Máximo 50 caracteres.
2. **Cuerpo opcional (detalles del cambio):** Explica por qué se hicieron los cambios o cómo afectan al proyecto. Ejemplo:
    ```vbnet
    feat: Implementar funcionalidad de búsqueda avanzada

    Se añadió soporte para filtros por categorías y rangos de precio.
    La búsqueda ahora utiliza un índice optimizado para mejorar el rendimiento.
    ```
3. **Pie opcional (referencia a tareas o problemas):** Vincula el commit a un ticket, issue o tarea. Ejemplo: `Closes #123`

## Convenciones comunes

- Usa un prefijo que describa el tipo de cambio:
  - **feat:** Nueva funcionalidad.
  - **fix:** Corrección de errores.
  - **refactor:** Reorganización del código sin cambiar funcionalidad.
  - **docs:** Cambios en la documentación.
  - **style:** Cambios de formato o estilo (sin impacto en el código funcional).
  - **test:** Añadir o modificar pruebas.
  - **chore:** Tareas generales como actualizaciones de dependencias.

## Buenas prácticas

1. **Sé claro y específico:** Indica qué cambió y por qué.
    - ✗ Malo: Arreglar cosas
    - ✓ Bueno: fix: Corregir error en la validación de email
2. **Mantén los mensajes cortos:** Resume el cambio en el título y usa el cuerpo para detalles adicionales.
3. **Usa el idioma del proyecto:** Asegúrate de que los mensajes estén en el idioma que todos los colaboradores comprendan (español o inglés, según corresponda).
4. **Evita redundancias:** No repitas información que ya está en el código.

## Ejemplo práctico

Imagina que estás trabajando en una aplicación y necesitas corregir un error donde los usuarios no pueden restablecer su contraseña. Tu mensaje podría ser:

```makefile
fix: Resolver error en el flujo de restablecimiento de contraseña

El problema ocurría porque el token generado expiraba demasiado rápido.  
Se aumentó el tiempo de expiración a 15 minutos y se mejoró la validación del token.
Closes #456
```

Con esta estructura, el commit es claro, profesional y fácil de entender para otros desarrolladores.