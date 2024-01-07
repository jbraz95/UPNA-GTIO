---
marp: true
class: invert
footer: Modelos de Dirección y Roles en las Organizaciones
paginate: true
theme: my-theme
---

# Modelos de Gestión de Proyectos y Buenas Prácticas

---
<!-- _header: Modelos de Gestión de Proyectos y Buenas Prácticas -->

- [Modelos de Gestión de Proyectos y Buenas Prácticas](#modelos-de-gestión-de-proyectos-y-buenas-prácticas)
  - [Modelos de Gestión](#modelos-de-gestión)
    - [Tradicional](#tradicional)
    - [Waterfall/Cascada](#waterfallcascada)
    - [Agile](#agile)
      - [Scrum](#scrum)
      - [Kanban](#kanban)
      - [Lean](#lean)
    - [Resumen](#resumen)
  - [Buenas Prácticas. CMMI, ITIL](#buenas-prácticas-cmmi-itil)
    - [CMMI (Capability Maturity Model Integration)](#cmmi-capability-maturity-model-integration)
    - [ITIL](#itil)
    - [Buenas prácticas en Software](#buenas-prácticas-en-software)

---
<!-- _header: Modelos de Gestión de Proyectos y Buenas Prácticas -->

Es necesario decidir cuál es el modelo de gestión de proyectos para cada equipo/proyecto. **Las herramientas tecnológicas corporativas deberán permitir cierta flexibilidad para adaptarse a distintos tipos de proyectos.**

---

## Modelos de Gestión

Los más conocidos/utilizados en empresas tecnológicas son los siguientes:

- Tradicional
- Waterfall o Desarrollo en cascada
- Agile
  - Kanban
  - Scrum
- Lean
- RUP
- CMMI

---
<!-- _header: Modelos de Gestión de Proyectos -->

### Tradicional

_Autor: José Javier Astráin Escola._

Consiste en dividir el proyecto en diferentes procesos que se ejecutan de forma secuencial. Típico del ámbito industrial

---
<!-- _header: Modelos de Gestión de Proyectos: Tradicional -->

Procesos:

- Inicialización: definición inicial del proyecto y fases, junto con la aprobación de su inicio.
- Planificación: desarrollo de los diferentes planes de gestión.
- Ejecución: realización de las tareas planificadas en la fase anterior con objeto de completar los entregables.
- Seguimiento y control: supervisión de las tareas ejecutadas, comparación con la planificación (líneas base), y definición y aplicación de correcciones en caso de desviaciones.
- Cierre: finalización de la fase o proyecto
  - por haber conseguido la aprobación del conjunto de entregables
  - por no ser posible conseguir alcanzar los entregables,
  - porque el proyecto ha dejado de tener motivo de ser.

---
<!-- _header: Modelos de Gestión de Proyectos: Tradicional -->

Puntos a tener en cuenta:

- Integración: Incluye los procesos y actividades requeridos para identificar, definir, combinar, unificar y coordinar los mismo a realizar por los grupos de trabajo.
- Alcance:  Incluye los procesos requeridos para asegurar la realización de todo el trabajo a aplicar en el proyecto, y no solo realizar aquellos que completen el proyecto.
- Tiempo: Incluye los procesos requeridos para la correcta administración de tiempo.
- Costes: Incluye los procesos involucrados en la planificación, estimación, presupuesto, financiamiento, costeo, administración y control de costos; con el objetivo de que el proyecto sea realizado con un presupuesto apropiado

---
<!-- _header: Modelos de Gestión de Proyectos: Tradicional -->

- Recursos Humanos
- Comunicación: Incluye los procesos requeridos para asegurar en tiempo y forma la planificación, recolección, creación, distribución, almacenaje, recuperación, administración, control, monitoreo y disposición de la información del proyecto.
- Riesgo: Incluye los procesos que planean, identifican, analizan, y controlan los posibles o actuales riesgos del proyecto.
- Adquisición: Incluye todos los procesos necesarios para la adquisición y compra de productos, bienes, servicios o resultados requeridos del exterior por el equipo de trabajo.
- Interesados: Incluye todos los procesos requeridos para identificar los grupos u organización que impacta el proyecto; analizando sus expectativas y desarrollar las estrategias necesarias para impactar positivamente en la ejecución y decisiones de los interesados.

 ---
<!-- _header: Modelos de Gestión de Proyectos: Tradicional -->

Recurso interesante : [Guía PMBOK](https://uacm123.weebly.com/index.html): colección completa de procesos, prácticas recomendadas, terminologías y directrices que se acepta como estándar dentro del sector de la gestión de proyectos.

PMBOK: Project Management Body of Knowledge

---
<!-- _header: Modelos de Gestión de Proyectos -->

### Waterfall/Cascada

Está basado en el desarrollo secuencial de las siguientes fases:

1. Análisis de requisitos
1. Diseño
1. Implementación
1. Verificación
1. Mantenimiento

---
<!-- _header: Modelos de Gestión de Proyectos: Waterfall -->

Es una metodología fácil de seguir y de llevar a cabo, no obstante, en proyectos de requisitos cambiantes es necesario volver al diseño del proyecto por completo antes de avanzar, por lo que lo hace muy poco flexible.

---
<!-- _header: Modelos de Gestión de Proyectos -->

Es necesario esperar a que el software esté terminado para probarlo, a menudo esto hace que se encuentren errores muy difíciles de resolver que retrasan en gran medida los proyectos.

>**En nuestro proyecto puede que los requisitos sean cambiantes**

---
<!-- _header: Modelos de Gestión de Proyectos -->

### Agile

[Agile Manifesto](https://agilemanifesto.org)

El objetivo principal de las metodologías Ágiles consiste en ofrecer entregas continuas incrementando gradualmente la funcionalidad. De esta forma se es más reactivo ante el cambio en los requisitos.

> Ejercicio: ¿Cómo construiríamos un coche usando una metodología Ágil? ¿Y una App de Android?

---
<!-- _header: Modelos de Gestión de Proyectos: Agile -->

#### Scrum

Es un marco de trabajo para ayudar a los equipos a realizar un proyecto de forma ágil.

[Guía en Inglés](https://www.scrumguides.org/scrum-guide.html)

[Scrum Cheatsheet](PDF/scrum.pdf) ([fuente](https://www.agile42.com/en/agile-info-center/scrum/scrum-cheat-sheet/))

> Ejercicio por grupos: Sin mirar todavía la guía de Scrum. ¿Qué sabemos de Scrum?. Anotad los roles, eventos y artefactos que recordéis.

---
<!-- _header: Modelos de Gestión de Proyectos: Agile -->

Scrum no es una metodología, es un marco de desarrollo. Pero habitualmente nos referimos a Scrum de cualquiera de las dos maneras.

> Ejercicio por grupos: Ventajas y Desventajas de Scrum para la gestión de un proyecto de software

---
<!-- _header: Modelos de Gestión de Proyectos: Agile -->

#### Kanban

Es un flujo de trabajo que sirve para maximizar la eficiencia en un contexto de numerosas interrupciones o cambios en los requisitos. Se integra muy fácilmente en organizaciones que ya tienen otros flujos implementados. Básicamente es el tablero de tareas que se puede ver en muchas empresas.

1. Visualizar el flujo de trabajo mediante paneles o boards
2. Limitar el número de tareas que están en proceso
3. Se gestiona el trabajo no a las personas

> Ejercicio por grupos: Sin investigar ni mirar en internet, desarrollad un board de kanban

---
<!-- _header: Modelos de Gestión de Proyectos: Agile -->

#### Lean

[Web Oficial](http://theleanstartup.com/principles)

Es una forma de trabajar pensada en salir al mercado lo más rápido posible. Para ello lo imprescindible es trabajar hacia el MVP o _Minimum Viable Product_. Está enfocado a los emprendedores o startups. Es compatible con otras metodologías ágiles para la gestión del equipo de desarrollo. Es preferible que sean meotodologías ágiles, ya que de lo que una startup tiene en mente como producto a lo que finalmente acaba llevando al mercado puede haber grandes diferencias (o incluso ser productos de ámbitos totalmente distintos)

> Ejercicio por grupos: 5 Ventajas y desventajas de Agile

---
<!-- _header: Modelos de Gestión de Proyectos -->

### Resumen

Como os podeis imaginar la mayoría de metodologías no se llevan al completo a la práctica. Generalmente se cogen las partes que más nos interesan de cada una de ellas y se adaptan a las necesidades de cada proyecto. Generalmente no es una mala idea, ya que llevar estos procesos de forma muy estricta puede ser muy costoso y no aportar valor al proyecto. Pero a veces es importante tener en cuenta que no se debe perder de vista el objetivo de cada una de las metodologías y ser serio con ellas. Hay una razón detrás de cada una de ellas, y lo importante es mantener estas razones en mente. Si solo cogemos lo que nos interesa de cada proceso, podemos acabar con un Frankenstein que no nos aporte nada.

---
<!-- _header: Modelos de Gestión de Proyectos -->

> ¿Cual es la idea principal detras de la metodología...
>
> - tradicional?
> - waterfall?
> - agile?
> - lean?

---
<!-- _header: Modelos de Gestión de Proyectos -->

> ¿Que desventaja principal tiene la metodología...
>
> - tradicional?
> - waterfall?
> - agile?
> - lean?

---
<!-- _header: Modelos de Gestión de Proyectos -->

> Ahora intentad retirar la desventaja principal de cada una de ellas. ¿Que os queda? ¿Es posible? ¿Mantiene la esencia esta metodología?

---
<!-- _header: Modelos de Gestión de Proyectos -->

## Buenas Prácticas. CMMI, ITIL

Para una buena gestión de proyecto, se generan marcos de trabajo y prácticas que se consideran positivas para la gestión de proyectos. Estas prácticas se pueden agrupar en modelos de gestión.

---
<!-- _header: Buenas Prácticas. CMMI, ITIL -->

### CMMI (Capability Maturity Model Integration)

[Web Oficial](https://cmmiinstitute.com)

Es un modelo para la mejora y evaluación de procesos para el desarrollo, mantenimiento y operación de software.

[CMMI en Tutorialspoint](https://www.tutorialspoint.com/cmmi/cmmi_quick_guide.htm)

---
<!-- _header: Buenas Prácticas. CMMI, ITIL -->

### ITIL

Guía de buenas prácticas para empresas que proveen servicios de IT.

ITIL es un marco donde se proporcionan pautas de buenas prácticas en todos los aspectos de la gestión de servicios de un extremo a otro. Cubre un espectro completo de personas, procesos, productos y uso de partners.

Hoy en día, casi todas las empresas que ofrecen servicios de TI a sus clientes practican ITIL.

[Itil en Tutorialspoint](https://www.tutorialspoint.com/itil/index.htm)

---
<!-- _header: Buenas Prácticas. CMMI, ITIL -->

### Buenas prácticas en Software

Aqui hemos hablado de buenas prácticas en la organización, que no es lo mismo que buenas prácticas en el desarrollo de software. Las ideas son las mismas: hacer las cosas bien para luego poder reaccionar correctamente ante los cambios
