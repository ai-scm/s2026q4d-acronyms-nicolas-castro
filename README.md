# IaC, TDD, BDD y ATDD

## Visión general

Estas cuatro prácticas buscan que el software sea **confiable, reproducible y alineado con lo que el negocio necesita**. **IaC** se ocupa de la infraestructura: la define como código para crearla y versionarla de forma automática. **TDD**, **BDD** y **ATDD** son enfoques de desarrollo guiados por pruebas, en los que primero se define cómo se va a verificar algo y después se construye. Cada uno trabaja a un nivel distinto: **TDD** prueba el código, **BDD** el comportamiento del sistema y **ATDD** los criterios de aceptación del negocio.

| Práctica | Pregunta que responde | Nivel |
|---|---|---|
| **IaC** | ¿Dónde y en qué corre la aplicación? | Infraestructura |
| **TDD** | ¿El código funciona correctamente? | Unitario |
| **BDD** | ¿El sistema se comporta como esperamos? | Funcional |
| **ATDD** | ¿Cumple lo necesario para ser aceptado? | Aceptación |

---

### 1. IaC: *Infrastructure as Code* (Infraestructura como Código)

Consiste en definir servidores, redes, bases de datos y demás recursos en **archivos de código**, en lugar de configurarlos a mano. Así la infraestructura queda versionada en Git, se puede revisar y se reproduce de forma idéntica en cualquier entorno. Lo fundamental es que es **declarativa**, porque se describe el estado deseado y la herramienta se encarga de crearlo, e **idempotente**, porque aplicarla varias veces da el mismo resultado. Herramientas comunes: Terraform, Pulumi, CloudFormation, Ansible y archivos como `Dockerfile` o `docker-compose.yml`.

### 2. TDD: *Test-Driven Development* (Desarrollo Guiado por Pruebas)

Es una práctica en la que **se escribe la prueba antes que el código**. Sigue el ciclo **Red → Green → Refactor**: se escribe una prueba que falla, luego el código mínimo para que pase y finalmente se mejora el código sin romper la prueba. Es un enfoque técnico, hecho por y para desarrolladores, que usa pruebas unitarias (pytest, JUnit). Ayuda a evitar regresiones y produce código más limpio y modular.

### 3. BDD: *Behavior-Driven Development* (Desarrollo Guiado por Comportamiento)

Es una evolución de TDD que describe el **comportamiento esperado del sistema en lenguaje natural**, comprensible tanto para negocio como para el equipo técnico. Los escenarios se escriben en **Gherkin** con la estructura **Dado / Cuando / Entonces** (*Given / When / Then*), y herramientas como Cucumber, Behave o pytest-bdd los convierten en pruebas automáticas. Su objetivo es alinear a todos sobre *qué* debe hacer el sistema antes de construirlo.

### 4. ATDD: *Acceptance Test-Driven Development* (Desarrollo Guiado por Pruebas de Aceptación)

Consiste en definir, **antes de desarrollar**, las **pruebas de aceptación**: los criterios que una funcionalidad debe cumplir para que el cliente o el negocio la dé por terminada. Se construye en colaboración entre negocio, QA y desarrollo, y establece una "definición de hecho" clara y medible. Se parece mucho a BDD, pero cambia el énfasis: ATDD se centra en *si cumple lo que el cliente necesita*, mientras que BDD se centra en *cómo se comporta* el sistema. Herramientas comunes: Robot Framework, FitNesse, Cucumber.