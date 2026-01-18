---
marp: true
class: invert
footer: Herramientas para la Gestión de Proyectos y Gestión de La Configuración
paginate: true
theme: my-theme
---

# Herramientas para la Gestión de Proyectos y Gestión de La Configuración

---
<!-- _header: Herramientas para la Gestión de Proyectos y Gestión de La Configuración-->

- [Herramientas para la Gestión de Proyectos y Gestión de La configuración](#herramientas-para-la-gestión-de-proyectos-y-gestión-de-la-configuración)
  - [Artefactos de la gestión de Proyectos](#artefactos-de-la-gestión-de-proyectos)
  - [Gestión de la configuración y Control de Versiones](#gestión-de-la-configuración-y-control-de-versiones)
  - [Herramientas sugeridas](#herramientas-sugeridas)
    - [Qué tener en cuenta a la hora de elegir](#qué-tener-en-cuenta-a-la-hora-de-elegir)
      - [Ejercicio por grupos](#ejercicio-por-grupos)

---

## Artefactos de la gestión de Proyectos

Una vez decidido el sistema para gestionar un proyecto, es necesario conocer los artefactos que nos van a ayudar a realizar la gestión del proyecto, y posteriormente evaluar el estado del mismo.

Una vez decididos los artefactos con los que queremos trabajar, es necesario disponer de las herramientas que nos permitan disponer de estos artefactos.

---
<!-- _header: Artefactos de la gestión de Proyectos-->

Una práctica habitual general es disponer de una herramienta en la que se puedan incluir *tareas* o *historas de usuario*, y asignarlas a un miembro del equipo, que pasará a ser el responsable de realizar o hacer que se realice esa tarea.

---
<!-- _header: Artefactos de la gestión de Proyectos-->

En *Scrum* estas tareas se organizan en objetivos tácticos o estrátegicos denominados *épicas*. El conjunto de épicas y tareas que no se están realizando en un Sprint se denomina *backlog* y es responsabilidad del *Product Owner* priorizar ese *backlog*, no obstante es responsabilidad de todo el equipo que las historias estén debidamente actualizadas, con las descripciones oportunas, y sus estimaciones.

También es responsabilidad de los miembros del equipo llevar la contabilidad del tiempo dedicado a cada una de las *historias de usuario*

---
<!-- _header: Artefactos de la gestión de Proyectos-->

En *Kanban* por ejemplo el backlog solo consiste en tareas que se priorizan, no obstante se pueden tener etiquetas dependiendo del ámbito.

---
<!-- _header: Artefactos de la gestión de Proyectos-->

En *Scrum* una de las métricas más importantes es el *Burndown Chart* o gráfico de velocidad, que indica la cantidad de puntos de historia que es capaz de realizar un equipo por *Sprint*, y cómo esa velocidad cambia a lo largo del tiempo.

---
<!-- _header: Artefactos de la gestión de Proyectos-->

![Burndown](../img/burndown.png)

---
<!-- _header: Artefactos de la gestión de Proyectos-->

En waterfall los artefactos más habituales para conocer los estados de los proyectos son los diagramas de Gantt o Cronogramas.

---
<!-- _header: Artefactos de la gestión de Proyectos-->

![Cronograma](../img/cronograma.png)

---
<!-- _header: Artefactos de la gestión de Proyectos-->

Lo ideal es que la herramienta elegida sea común para toda una organización y se adapte a todas estas necesidades.  

---

## Gestión de la configuración y Control de Versiones

La gestión de la configuración es el conjunto de procesos destinados a asegurar la calidad de todo producto obtenido durante cualquiera de las etapas del desarrollo de un sistema de información, a través del estricto control de los cambios realizados sobre los mismos y de la disponibilidad constante de una versión estable de cada elemento para toda persona involucrada en el citado desarrollo.

---
<!-- _header: Gestión de la configuración y Control de Versiones-->

Estos dos elementos, el control de cambios y control de versiones de todos los elementos del SI, facilitan también el mantenimiento de los sistemas al proporcionar una imagen detallada del sistema en cada etapa del desarrollo. La gestión de la configuración se realiza durante todas las fases del desarrollo de un sistema de información, incluyendo el mantenimiento y control de cambios, una vez realizada la puesta en producción.

---
<!-- _header: Gestión de la configuración y Control de Versiones-->

Ejemplos de configuración de software:

- Ejecutables/ artefactos
- Código Fuente
- Modelos de datos
- Modelos de procesos
- Especificaciones de requisitos
- Pruebas
[De Wikipedia](https://es.wikipedia.org/wiki/Gestión_de_la_configuración)

---

## Herramientas sugeridas

- Github
- Gitlab
- Microsoft teams
- Jira
- Trello
- Gsuite
- Excel o similares
- ClickUp
- Asana
- OpenProject
- ProjectLibre
- Zentao

---

### Focus: Notion como Espacio de Trabajo Unificado

A diferencia de herramientas verticales (solo gestión o solo documentos), Notion actúa como un **hub centralizado** que elimina los silos de información entre equipos técnicos y de producto.

- **Wiki de Ingeniería:** Centraliza guías de estilo, *onboarding* y documentación de infraestructura junto a las tareas, evitando la dispersión del conocimiento.
- **Gestión de Sprints:** Permite gestionar Épicas, Historias de Usuario y Bugs en la misma plataforma mediante bases de datos vinculadas y vistas personalizables (Tablero, Cronograma, Lista).

---

### Notion: Integraciones y Automatización

Su valor diferencial reside en conectar la ejecución técnica con la documentación de negocio:

- **Sincronización con GitHub:** Vincula *Pull Requests* directamente a tareas de Notion. El estado de la tarea se actualiza automáticamente cuando el PR se fusiona, dando visibilidad a los PMs sin entrar al repositorio.
- **Sincronización con Jira:** Permite visualizar tickets de Jira dentro de Notion para equipos no técnicos.
- **Potenciado por IA:** Automatiza la redacción de historias de usuario a partir de especificaciones técnicas o resume reuniones de *dailys*.

---

### Notion: Problema

El principal problema de Notion es el tiempo que se "pierde" en mantener todo en orden.

Si lo usamos como documentación hay que dedicar tiempo a mantenerlo integrado. Y si usamos IA para programar, los cambios tienden a ser tan rápidos que la documentación se queda obsoleta. Se pueden usar servidores MCP para mantener la documentación actualizada, pero requiere tiempo y esfuerzo.

Luego si lo utilizamos como herramienta de gestión de proyectos, hay que dedicar un tiempo a montar los automatismos y flujos de trabajo. No es solo crear tareas como en otras plataformas, es utilizar sus bases de datos y automatizaciones para sacarle el máximo partido.

---

### Plan B: GitHub Projects + Wiki (El Ecosistema Nativo)

Si buscamos reducir la fricción del desarrollador o nuestra empresa no requiere que el conocimiento se comparta con, por ejemplo, financiero, la alternativa es vivir dentro de GitHub.

- **GitHub Projects:** Es la capa de gestión visual sobre el código.
  - **Automatización Nativa:** Al cerrar una *Issue* mediante un commit, la tarjeta se mueve sola en el tablero Kanban. Sin webhooks ni configuraciones complejas.
- **Documentación (Wiki vs. Docs/):**
  - **GitHub Wiki:** Útil para documentación de alto nivel (Onboarding, normas).
  - **Carpeta `/docs`:** Para documentación técnica viva. Al estar junto al código, evoluciona con él en el mismo *commit* ("Docs-as-code"), evitando la obsolescencia.

### Comparativa: Fricción vs. Visibilidad

- Básicamente se basa en elegir entre:
  - **Notion:** Mayor visibilidad y colaboración interdepartamental, pero con mayor fricción para desarrolladores.
  - **GitHub Nativo:** Menor fricción para desarrolladores, pero menos visibilidad para otros departamentos.
- Además otro punto importante es el coste de mantenimiento y el tamaño del equipo.
  - En un equipo pequeño no hay necesidad de un sistema complejo y tu herramienta puede ser github projects.
  - Pero en equipos grandes con varios departamentos y roles, puede ser beneficioso compartir información de forma interdepartamental
- Pero como siempre, es una decisión que debe tomar cada equipo en función de sus necesidades. Es un tema de gustos y se debe priorizar inicialmente la productividad del equipo y donde se sienta más cómodo.

---

### Qué tener en cuenta a la hora de elegir

- Precio
- Disponibilidad
- Esfuerzo de instalación/registro
- Curva de aprendizaje
- Funcionalidades que incluyen
- SaaS VS On-premise

---

#### Ejercicio por grupos

> Pensar en los artefactos necesarios para la gestión del proyecto. Este ejercicio
está incluido en la primera entrega. [RFI I](RFI/RFI-I.md). Es necesario documenta la decisión en un [ADR](ADR/README.md) o similar.

> Decidid las herramientas necesarias para la gestión del proyecto. Este ejercicio
está incluido en la primera entrega. [RFI I](RFI/RFI-I.md). Es necesario documenta la decisión en un [ADR](ADR/README.md) o similar.

>Cada equipo deberá demostrar que ha utilizado la herramienta elegida a lo largodel desarrollo del proyecto.
