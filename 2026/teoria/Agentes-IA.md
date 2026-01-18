# Programación con Agentes en VS Code: Arquitecturas y Roles

Para gestionar eficazmente el desarrollo de software moderno con Inteligencia Artificial, es necesario trascender el concepto de "autocompletado" y comprender la **arquitectura agéntica**. Mientras que un LLM (Modelo de Lenguaje Grande) predice texto, un agente razona, planifica, utiliza herramientas y ejecuta tareas en bucles autónomos.

En el ecosistema de VS Code, esto implica pasar de una interacción pasiva a delegar flujos de trabajo completos, donde la IA actúa como un "empleado" capaz de navegar por el código, ejecutar comandos y corregir sus propios errores.

--------------------------------------------------------------------------------

## 1. Conceptos Fundamentales: Del Prompt al Agente

Antes de programar, es crucial entender la estructura que diferencia a un chat estándar de un sistema agéntico capaz de resolver problemas complejos.

### El Bucle de Razonamiento (ReAct)

La mayoría de los agentes en VS Code operan bajo el patrón **ReAct** (Reason + Act). El modelo no responde de inmediato; entra en un ciclo iterativo:

1. **Pensamiento (Reasoning):** Analiza el estado actual y el objetivo.
2. **Acción (Acting):** Decide usar una herramienta (ej. leer un archivo, ejecutar un test).
3. **Observación (Observation):** Lee el resultado de esa acción (ej. un error de compilación).
4. **Iteración:** Repite el proceso basándose en la observación hasta completar la tarea.

### Tipos de Interacción en VS Code

En VS Code, los agentes se manifiestan en dos modalidades principales:

* **Agente Interactivo (Chat & Inline):** Colaboración síncrona. El desarrollador supervisa en tiempo real dentro del editor. Ideal para exploraciones rápidas o dudas específicas.
* **Agente Autónomo (Coding Agent):** Trabajo asíncrono en segundo plano. Se le delega una tarea (ej. "arreglar este bug"), el agente trabaja en un entorno aislado y devuelve un *Pull Request* (PR) para revisión humana.

--------------------------------------------------------------------------------

## 2. Roles y Arquitectura de Agentes

Al igual que en las organizaciones humanas, los sistemas de IA son más eficientes cuando se especializan. No debemos diseñar un solo agente monolítico, sino orquestar roles específicos.

### El Agente Planificador (Planner)

Es el cerebro estratégico. Su función no es escribir código final, sino descomponer un problema ambiguo en pasos ejecutables.

* **Función:** Interpreta objetivos de alto nivel y genera un plan estructurado (lista de tareas o JSON).
* **Uso:** Fundamental antes de iniciar la codificación para evitar "alucinaciones" o código que no encaja en la arquitectura existente. Utiliza modelos con alta capacidad de razonamiento (ej. modelos o1 o Claude 3.5 Sonnet en modo "thinking").

### El Agente Ejecutor (Executor)

Es la capacidad operativa. Recibe el plan y lo lleva a cabo.

* **Función:** Interactúa con el sistema de archivos, ejecuta comandos de terminal y escribe código.
* **Herramientas Clave:** Debe tener acceso a herramientas de edición (`#editFiles`) y ejecución (`#runTerminal`). En VS Code, esto se ve cuando el agente edita múltiples archivos automáticamente para cumplir un requisito.

### El Agente Crítico/Revisor (Reflection)

El control de calidad. Evalúa la salida del ejecutor antes de darla por buena.

* **Función:** Revisa el código generado buscando errores lógicos, de seguridad o desviaciones del plan.
* **Patrón:** *Review and Critique*. Un agente genera código y otro (o el mismo en un paso posterior) actúa como "auditor" para sugerir mejoras antes de finalizar la tarea.

--------------------------------------------------------------------------------

## 3. Implementación Práctica en VS Code

¿Cómo aplicamos estos roles utilizando las herramientas disponibles en VS Code? Existen dos vías: usar los agentes integrados de GitHub/Microsoft o construir agentes personalizados.

### A. Uso del GitHub Copilot Coding Agent (Integrado)

Este es un agente autónomo "llave en mano" proporcionado por GitHub. Funciona de manera asíncrona en la nube.

* **Flujo de trabajo:**
    1. **Asignación:** Se asigna una *issue* de GitHub a `@copilot` o se delega desde el chat.
    2. **Desarrollo:** El agente analiza el repositorio, planifica y ejecuta cambios en un entorno aislado (GitHub Actions).
    3. **Revisión:** El agente crea un *Pull Request* (PR) detallando los cambios.
    4. **Iteración:** El humano revisa el PR; si hay fallos, deja comentarios y el agente vuelve a iterar.

### B. Creación de Agentes Personalizados (Chat Participant API)

Si necesitas un experto en un dominio específico (ej. "Experto en la base de datos legacy de la empresa"), puedes crear tu propio participante de chat mediante una extensión de VS Code.

* **Estructura básica (`package.json`):**
    Se define un `id`, `name` (para invocarlo con `@nombre`), y una descripción.

    ```json
        "id": "chat-sample.mi-agente",
        "name": "mi-agente",
        "description": "Experto en migración de bases de datos"
    ```

* **Manejador de Peticiones (Request Handler):**
    Es la función que procesa el *prompt* del usuario. Aquí defines la lógica: ¿Debe llamar a una API externa? ¿Debe usar un modelo de lenguaje específico?.

--------------------------------------------------------------------------------

## 4. Contexto y Herramientas: La "Fontanería" del Agente

Un agente es tan bueno como la información (contexto) y las herramientas que tiene a su disposición. La diferencia entre un agente mediocre y uno excelente suele estar en la integración de herramientas, no en el modelo.

### Gestión del Contexto: LSP vs. Grep

Para que el agente no "adivine", debemos darle herramientas de precisión.

* **LSP (Language Server Protocol):** Es vital. Permite al agente "saber" y no solo "buscar". A través de LSP, el agente puede ir a la definición exacta de una función o encontrar todas sus referencias con precisión absoluta, en lugar de hacer una búsqueda de texto (`grep`) que puede fallar por ambigüedad.
* **Archivos de Instrucciones (`.github/copilot-instructions.md` o `CLAUDE.md`):** Úsalos para dar contexto permanente al agente sobre reglas de negocio, estilo de código o comandos comunes. Es como el "manual del empleado" para el agente.

### Model Context Protocol (MCP)

Es el estándar para conectar agentes con datos externos y herramientas personalizadas.

* **Función:** Permite que tu agente en VS Code se conecte a GitHub, Slack, bases de datos (Postgres) o Google Drive sin tener que programar la integración desde cero cada vez.
* **Uso:** Puedes configurar servidores MCP para que el agente tenga herramientas específicas (ej. "buscar en la documentación interna" o "consultar logs de Sentry").

--------------------------------------------------------------------------------

## 5. Patrones de Colaboración (Estrategias Multi-Agente)

Cuando un solo agente no es suficiente, utilizamos patrones de colaboración para tareas complejas.

### Secuencial (Sequential)

Como una línea de montaje. La salida de un agente es la entrada del siguiente.

* **Ejemplo:** Agente A escribe el código -> Agente B escribe los tests -> Agente C escribe la documentación.
* **Uso:** Procesos deterministas y repetibles.

### Orquestador / Coordinador

Un agente central decide quién hace qué.

* **Ejemplo:** El usuario pide "Arreglar el error de login". El Coordinador analiza el error y decide enviarlo al Agente de Base de Datos o al Agente de Frontend según corresponda.
* **Ventaja:** Maneja flujos dinámicos donde no siempre se ejecutan los mismos pasos.

### Bucle de Mejora (Iterative Refinement)

El agente itera sobre su propio trabajo hasta cumplir una condición.

* **Ejemplo:** "Escribe el código, corre los tests. Si fallan, corrige el código y repite hasta que pasen todos los tests".
* **Nota:** Es fundamental en estrategias de TDD (Test Driven Development) con agentes.

--------------------------------------------------------------------------------

Aquí tienes la ampliación de los apuntes. He añadido una sección crítica sobre la gestión del contexto y los riesgos de la sobrecarga de herramientas (MCP), así como un ejemplo técnico detallado para implementar un agente en VS Code.

--------------------------------------------------------------------------------

## 6. Gestión del Contexto y Riesgos del "Over-tooling" (MCP)

Aunque el **Model Context Protocol (MCP)** permite conectar agentes a fuentes de datos externas (Slack, GitHub, Bases de Datos), conectar demasiados servidores indiscriminadamente es un antipatrón arquitectónico conocido como **"Over-tooling"**.

### El Peligro de la Contaminación del Contexto

El contexto de un LLM es un recurso finito y costoso. Cargar definiciones de herramientas consume tokens antes de que empiece la conversación.

* **Coste Oculto de las Definiciones:** Un servidor MCP de GitHub con 35 herramientas puede consumir ~26,000 tokens solo en definiciones. Si sumas Slack (~21k) y Jira (~17k), puedes saturar 100k tokens sin haber procesado ninguna petición del usuario.
* **Degradación del Rendimiento:** Cuando el contexto se llena de herramientas irrelevantes ("ruido"), el modelo pierde capacidad de razonamiento ("needle in the haystack problem"). Esto aumenta la latencia y la probabilidad de que el agente elija la herramienta equivocada o alucine parámetros.

### Estrategias de Mitigación

Para evitar que el agente se ahogue en herramientas, debemos aplicar patrones de filtrado:

1. **Carga Diferida (Tool Search / Deferred Loading):**
    En lugar de inyectar todas las herramientas en el *prompt* del sistema, el agente debe tener una herramienta de "búsqueda". El agente busca "herramientas de git" y solo entonces se cargan las definiciones relevantes en el contexto. Esto puede reducir el uso de tokens hasta un 85%.

2. **Llamadas Programáticas (Programmatic Tool Calling):**
    En flujos complejos (ej. analizar 100 logs), no devuelvas cada resultado al chat (contexto). En su lugar, haz que el agente escriba un script (Python/JS) que ejecute las herramientas en un entorno aislado y solo devuelva el resultado final o resumen al contexto principal. Esto evita la "contaminación por resultados intermedios".

3. **Acceso Curado:**
    No instales todos los plugins del marketplace. Define un set mínimo de servidores MCP aprobados y necesarios para la tarea específica. Cada herramienta adicional añade carga cognitiva al modelo. Al final se debería usar un 60/80% de los tokens/contexto como máximo

--------------------------------------------------------------------------------

Aquí tienes la reescritura del **Punto 7**, actualizada según la documentación oficial más reciente sobre **Custom Agents** (disponible desde la versión 1.106).

A diferencia del método anterior que requería programar una extensión en TypeScript, la forma oficial y práctica de crear agentes personalizados ahora es mediante **archivos de configuración Markdown (`.agent.md`)**. Esto permite definir "personas", herramientas y flujos de trabajo sin escribir código complejo.

--------------------------------------------------------------------------------

## 7. Ejemplo Técnico: Creación de un Agente Declarativo (`.agent.md`)

Para crear un agente nativo en VS Code, ya no necesitas compilar una extensión. Ahora defines el comportamiento en un archivo Markdown que puede vivir en tu espacio de trabajo (para compartirlo con el equipo) o en tu perfil de usuario (para uso personal).

### A. Creación del Archivo

1. **Ubicación:** Crea una carpeta `.github/agents` en la raíz de tu proyecto. VS Code detectará automáticamente cualquier archivo `.md` en esta carpeta como un agente.
2. **Comando Rápido:** También puedes usar `Ctrl+Shift+P` > **"Chat: New Custom Agent"** para generar la plantilla.

### B. Estructura del Agente (Frontmatter + Instrucciones)

El archivo se divide en dos partes: la configuración (YAML en la cabecera) y el comportamiento (Markdown en el cuerpo).

Vamos a crear un **Agente Planificador** que diseña la solución pero tiene prohibido editar código, utilizando el patrón de **Handoffs** (traspaso de tareas) para derivar el trabajo a un agente implementador.

**Archivo:** `.github/agents/planner.agent.md`

```markdown
---
name: Arquitecto           # Nombre que aparecerá en el chat (@arquitecto)
description: Diseña planes de implementación técnica sin modificar código.
model: o1-preview          # Puedes forzar un modelo específico con alto razonamiento
tools:                     # Lista blanca de herramientas permitidas
  - 'search'               # Buscar en la web/docs
  - 'githubRepo'           # Leer el repositorio
  - 'fetch'                # Leer contenido de URLs
handoffs:                  # Flujo de trabajo sugerido al terminar
  - label: Implementar Plan
    agent: @copilot        # Agente al que se le pasa la pelota
    prompt: Toma este plan y genera el código necesario.
    send: false            # false = permite al humano editar el prompt antes de enviar
---

# Instrucciones del Sistema

Eres el Arquitecto de Software del equipo. Tu objetivo es **analizar y planificar**, nunca ejecutar.

## Reglas de Comportamiento

1. **Solo Lectura:** Utiliza las herramientas de búsqueda para entender el contexto, pero NO generes bloques de código final ni intentes editar archivos.
2. **Formato del Plan:** Tus respuestas deben seguir estrictamente esta estructura:
    - **Diagnóstico:** ¿Cuál es el problema actual?
    - **Estrategia:** Resumen técnico de la solución propuesta.
    - **Pasos de Implementación:** Lista numerada detallada de qué archivos crear o modificar.
    - **Riesgos:** Posibles efectos secundarios.

## Uso de Herramientas
Si necesitas verificar una librería externa, usa `#tool:search`. Si necesitas contexto del proyecto actual, usa `#tool:githubRepo`.
```

### C. Explicación Práctica de los Componentes

1. **Definición de Herramientas (`tools`):**
    Aquí es donde evitas el "over-tooling". Al listar explícitamente solo `'search'` y `'githubRepo'`, impides que este agente tenga acceso a herramientas de escritura o despliegue, haciéndolo más seguro y enfocado. Si usas servidores MCP, puedes dar acceso a todas sus herramientas con el formato `<server-name>/*`.

2. **Instrucciones (Body):**
    Todo lo que escribas debajo del bloque YAML se inyectará como "System Prompt". Puedes referenciar otros archivos de documentación usando enlaces Markdown para reutilizar instrucciones comunes.

3. **Flujos de Trabajo (Handoffs):**
    Esta es la característica más potente. Permite encadenar agentes. En el ejemplo anterior, cuando el "Arquitecto" termina de hablar, aparecerá un botón interactivo en el chat llamado **"Implementar Plan"**.
    * Al hacer clic, VS Code cambia automáticamente al agente `@copilot` (o a tu agente "Developer").
    * Pega el contexto del plan generado.
    * Pre-rellena el prompt con "Toma este plan y genera el código...", listo para que el usuario apruebe e inicie la fase de codificación.

--------------------------------------------------------------------------------

### Resumen Rápido para Empezar

1. **Define el objetivo:** ¿Es una tarea interactiva (Chat) o de fondo (Coding Agent)?.
2. **Prepara el terreno:** Crea archivos de instrucciones (`.md`) y asegúrate de que el agente tenga acceso a las definiciones del lenguaje (LSP).
3. **Elige el patrón:**
    * *Simple:* Un solo agente (ReAct).
    * *Calidad:* Agente Generador + Agente Crítico.
    * *Complejo:* Orquestador delegando a sub-agentes especializados.
4. **Supervisión:** Mantén siempre al "Humano en el Bucle" para revisar PRs y decisiones críticas.