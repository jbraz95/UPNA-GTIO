# RFI I. Proyecto Votación - Metodologías de Gestión

- [RFI I. Proyecto Votación - Metodologías de Gestión](#rfi-i-proyecto-votación---metodologías-de-gestión)
  - [Contexto](#contexto)
  - [Objetivo](#objetivo)
  - [Preguntas del RFI](#preguntas-del-rfi)
  - [Respuestas a este RFI](#respuestas-a-este-rfi)
  - [Consideraciones](#consideraciones)
  - [Entrega](#entrega)
  - [Evaluación](#evaluación)
  - [Modificaciones sobre este RFI](#modificaciones-sobre-este-rfi)

## Contexto

En un mundo tecnológico en constante cambio, la empresa Bermejo inc. (en adelante el cliente) necesita conocer las bases de las empresas que optan a la venta (en adelante proveedor) a nivel de gestión y sus respectivas herramientas previa la compra de un proyecto de tipo votación para la nueva edición de Operación Triunfo.

Se espera que un proyecto de esta envergadura esté al menos los siguientes diez años en producción por lo que una correcta organización del equipo encargado de su evolución y mantenimiento es vital para asegurarnos su continuidad en el tiempo.

Se quiere también, aplicar las metodologías de gestión, desarrollo y operación llevadas a cabo por la empresa proveedora al resto de áreas tecnológicas de la empresa cliente.

Se espera que un proyecto de esta envergadura sea capaz de desplegarse de forma fácil y sencilla tanto en sistemas locales como en proveedores de infraestructura externos (por ejemplo nubes públicas).

Así el sistema deberá estar adaptado tanto para integración continua como para despliegues con cargas de trabajo masivas en producción.

Para ello el cliente espera propuestas basadas en sistemas distribuidos en microservicios usando Docker como tecnología para la creación y despliegue de esos microservicios en contenedores.

En conclusión, la idea de esta entrega es que se conozca la organización y metodología del proveedor, y que se haga una prueba de concepto bastante completa del sistema votación basado en microservicios y Docker que pueda ser desplegado tanto en local como en la nube.

## Objetivo

El Objetivo de este RFI consiste en conocer el estado del arte dentro de las posibles empresas proveedoras de un proyecto de tipo votación. La fecha límite se encuentra en la sección *Entrega*.

## Preguntas del RFI

La empresa que proveedora deberá dar respuesta justificada a los siguientes puntos:

- ¿Cómo es la organización de un equipo de desarrollo, mantenimiento y operaciones del proyecto votación?
- ¿Quiénes son los miembros del equipo y cuáles son sus roles?
- ¿Cuáles son las herramientas de gestión del proyecto?
- ¿Cuáles son las herramientas de gestión de la configuración del proyecto?
- ¿Cómo se plantea la arquitectura del programa? Se requiere un acercamiento inicial a la arquitectura del sistema.
- ¿Cuáles son los servicios/microservicios de los que consiste el sistema votación?
- ¿Cómo es la metodología y buenas prácticas utilizadas en el desarrollo de un proyecto votación?
- ¿Cómo se despliega el sistema en un entorno de test local? Se requiere una pequeña guía de explicación de como levantar el programa.
- ¿Cómo se prueba la funcionalidad del sistema en un entorno de test local?
- ¿Cuáles son los Dockerfiles utilizados para cada microservicio?
- ¿Cuál es la configuración del Docker Compose para levantar el sistema?
- ¿Por qué es escalable y elástica la solución?

## Respuestas a este RFI

- Se requiere la *justificación* (el ¿por qué?) de las respuestas
- Se requieren pruebas para todas las respuestas. Son válidas, capturas de pantalla, actas de reuniones, conversaciones, e-mail, audios, documentación etc...

## Consideraciones

- Cualquier otro aporte de interés en el ámbito de la gestión de proyectos será bienvenido y considerado para una mayor puntuación en la evaluación
- Cualquier otro aporte de interés en el ámbito de la mejora de la arquitectura del sistema será bienvenida y considerado para una mayor puntuación en la evaluación
- Se valoran las metodologías ágiles por encima de las metodologías tradicionales
- Solo se valorarán arquitecturas basadas en microservicios
- Solo se valorarán microservicios basados en Docker como sistema de contenedores

## Entrega

- La fecha límite para la entrega del RFI será el: *25 de febrero de 2026*
- Se deberá realizar una presentación el mismo día *25 de febrero de 2026* en el horario habitual de la asignatura
- Se puede incluir toda la documentación que el proveedor considere necesaria
- La tarea de MiAulario será previamente anunciada mediante anuncio en miAulario o e-mail.

## Evaluación

| Tema                                              | Puntuación |
| ------------------------------------------------- | ---------: |
| Organización y metodología                        |          5 |
| Herramientas de gestión                           |          5 |
| Herramientas de gestión de configuración          |          5 |
| Arquitectura inicial del sistema y microservicios |          5 |
| Dockerfiles                                       |          5 |
| Docker Compose files                              |          5 |
| Ejecución demostrada de buenas prácticas          |          5 |
| Ejecución en entorno local                        |          5 |
| Presentación/Demo                                 |         10 |
| Total                                             |         50 |

## Modificaciones sobre este RFI

El cliente se guarda el derecho a modificar este RFI en cualquier momento, siendo obligado su aviso mediante anuncio en miAulario o e-mail a partir del día 28 de enero del 2026.
