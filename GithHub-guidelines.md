# Como es el workflow de GitHub?

Vease toda la documentación en este [link](https://blog.mergify.com/understanding-the-github-pull-request-workflow/)

### 1. Creación de características locales

Aquí es donde comienza la ramificación. A diferencia de otros flujos de trabajo, el modelo de flujo de GitHub depende de que la rama principal de tu proyecto [sea desplegable](https://www.varonis.com/blog/git-branching/) en todo momento. Esto significa que todas y cada una de las funcionalidades que pretendas desarrollar deben ser trabajadas en sus propias ramas y posteriormente integradas de nuevo en la principal cuando estén listas.

![](https://blog.mergify.com/content/images/2021/09/Screenshot-2021-09-22-at-17.53.55.png)

Hay múltiples formas de generar nuevas ramas para las características de tu proyecto en desarrollo activo, pero generalmente necesitarás realizar una operación `git branch` con el nombre deseado para tu nueva rama, y luego cambiar manualmente a esta rama recién creada usando el comando `git checkout` con su nombre. También puede optar por crear simplemente una nueva rama y cambiar a ella inmediatamente [usando el comando checkout](https://www.freecodecamp.org/news/git-switch-branch/) con `-b` seguido del nombre de su nueva rama.

### 2. Empujar características

Una vez que haya hecho una serie de confirmaciones que sospecha que están listas para ser expuestas a otros desarrolladores que trabajan en su proyecto, puede empujarlas a su repositorio remoto, donde pueden ser vistas por otros que interactúan con su rama de características.

![img](https://blog.mergify.com/content/images/2021/09/Screenshot-2021-09-22-at-18.32.48.png)

Enviar actualizaciones desde tu rama local a un repositorio remoto es tan fácil como usar el comando "git push" con el nombre de la rama local [y un nombre remoto](https://docs.github.com/en/get-started/using-git/pushing-commits-to-a-remote-repository) también.

### 3. Creación de pull request

Con una característica completada, estás listo para emitir un pull request. Esto permite a tu equipo de proyecto saber que [tus commits están listos](https://docs.github.com/en/github/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-pull-requests) para su posterior revisión y (con suerte) fusión. Además de alertar a los colaboradores de la finalización de tu función, una solicitud de extracción también facilita la discusión de los detalles que rodean los cambios propuestos, así como la modificación de esos cambios antes de que se fusionen.

![](https://blog.mergify.com/content/images/2021/09/Screenshot-2021-09-22-at-18.33.22.png)

Las pull requests también pueden activarse y gestionarse en GitHub. Esta es también la etapa en la que el código se somete generalmente a una revisión formal para garantizar que se ajusta a las normas del proyecto y que es seguro incluirlo en un despliegue determinado. En este punto del modelo de flujo de GitHub se suelen realizar todo tipo de pruebas, a diferencia de lo que ocurre en el modelo de Gitflow, en el que las funciones se envían primero a una rama de desarrollo para su posterior evaluación.

### 4. Revisión

Este es el punto en el que los colaboradores del repositorio discuten tu código y hacen sugerencias, o simplemente lo aprueban. Espera hacer algunas idas y venidas para cumplir con las pruebas automatizadas del sistema de integración continua y la opinión de los demás sobre tu código.

![](https://blog.mergify.com/content/images/2021/09/Screenshot-2021-09-22-at-18.34.25.png)

### 5. Fusión de características con main

Una vez que todos los pasos anteriores se han completado, los administradores del proyecto pueden dar el paso final y fusionar el código de la característica completada con el principal.

![](https://blog.mergify.com/content/images/2021/09/Screenshot-2021-09-22-at-18.35.46.png)


## Elección de un flujo de trabajo Git pull request

Además del modelo de flujo de GitHub descrito anteriormente, puedes elegir entre varios flujos de trabajo de solicitudes pull de Git, y cada uno de ellos ofrece ventajas únicas que pueden ser adecuadas para tu equipo. Sin embargo, al menos uno de ellos -el flujo de trabajo centralizado- no puede acomodar pull requests y debería evitarse si prefieres aprovechar dichas peticiones en el historial de tu propio proyecto.

Hay algunos modelos de flujo de trabajo Git adicionales que podrías considerar probar si estás planeando usar pull requests, como el modelo Gitflow antes mencionado, el modelo de flujo de trabajo de rama de características, y el modelo de flujo de trabajo de bifurcación. Cada uno de ellos es ideal para ciertas aplicaciones y no tanto para otras. El modelo de bifurcación es particularmente adecuado para proyectos abiertos con muchos colaboradores diferentes, por ejemplo, ya que los repositorios [se copian cuidadosamente](https://reflectoring.io/github-fork-and-pull/) cada vez que se bifurcan.

## Automatiza las pull requests con Mergify

El flujo de trabajo de solicitudes de extracción de GitHub del que depende tu equipo puede funcionar mucho mejor con la adición de las utilidades de automatización de Mergify. Gestiona fusiones, comentarios, asignación de revisiones y mucho más sin redundancias manuales mundanas ni pérdidas de tiempo. Descubra cómo Mergify puede hacer que su [proceso de desarrollo sea pan comido](https://dashboard.mergify.io/) hoy mismo.
