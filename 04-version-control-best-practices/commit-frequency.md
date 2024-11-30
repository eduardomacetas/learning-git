# Frecuencia de Commits

La práctica de realizar **commits pequeños y frecuentes** con mensajes significativos es fundamental para mantener un historial de cambios claro y útil en Git. Esta metodología facilita la colaboración en equipo, simplifica la depuración de errores y asegura que cada cambio esté documentado adecuadamente.

En este documento, exploraremos por qué esta práctica es importante, cuándo realizar un commit y cómo escribir mensajes efectivos que describan claramente los cambios realizados.

## ¿Por qué es importante realizar commits pequeños y frecuentes?

1. **Facilita la depuración:**  Los commits pequeños permiten identificar rápidamente qué cambio específico introdujo un error. Usar herramientas como git bisect es mucho más efectivo cuando los commits son granulares.

2. **Historial más claro:** Un historial con cambios pequeños y bien descritos es más fácil de entender para los colaboradores actuales y futuros del proyecto.

3. **Mejor colaboración:** En equipos, los commits frecuentes reducen la probabilidad de conflictos al integrar cambios, ya que los desarrolladores están trabajando sobre bases de código más actualizadas.

4. **Evita la pérdida de progreso:** Realizar commits frecuentes asegura que no se pierda mucho trabajo en caso de errores, como fallos del sistema o problemas con tu entorno de desarrollo.

## ¿Cuándo realizar un commit?

1. **Después de completar un cambio lógico:** Cada commit debe representar un cambio independiente y funcional. Por ejemplo:
    - Añadir una nueva función.
    - Corregir un error.
    - Actualizar la documentación.

2. **Antes de realizar pruebas grandes:** Si estás por hacer pruebas importantes, realiza un commit previo para guardar el estado actual.

3. **Cuando alcances un punto de control significativo:** Si terminas un paso clave en tu tarea, realiza un commit para consolidar tu avance.

4. **Evita commits demasiado grandes:** Si tu commit incluye múltiples cambios no relacionados, divídelos en commits más pequeños y específicos.

## Buenas prácticas para la frecuencia de commits

1. **Divide el trabajo en tareas pequeñas:** Trabaja en unidades pequeñas y manejables para que cada commit represente un paso claro hacia el objetivo.

2. **Evita los "WIP commits" en ramas principales:** Si necesitas guardar progreso incompleto, hazlo en una rama separada y luego combina los commits cuando estén listos.

3. **Usa ramas para organizar tus cambios:** Mantén tus cambios separados del código principal trabajando en ramas específicas para cada tarea o corrección.

4. **Realiza commits frecuentemente mientras desarrollas:** No esperes a que todo esté terminado. Guarda tu progreso regularmente.

## Ejemplo práctico: Frecuencia de commits en una tarea

Supongamos que estás trabajando en una funcionalidad para agregar un formulario de registro en una aplicación web. Aquí hay una posible secuencia de commits:

1. **Estructura inicial del formulario:**

    ```bash
    git commit -m "feat: agregar estructura HTML inicial para el formulario de registro"
    ```

2. **Estilos básicos para el formulario:**

    ```bash
    git commit -m "style: añadir estilos básicos al formulario de registro"
    ```

3. **Corrección de un error en la validación:**

    ```bash
    git commit -m "fix: corregir validación del campo de correo electrónico"
    ```