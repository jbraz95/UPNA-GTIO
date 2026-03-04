# RFI II. Proyecto Votación - CI/CD & Arquitectura Cloud

## Contexto

En un mundo tecnológico en constante cambio, la empresa Bermejo inc. (en adelante el cliente) necesita conocer la arquitectura técnica, documentación del código, seguridad y despliegue de un sistema de tipo votación.

Se espera que un proyecto de esta envergadura cuente con una documentación clara y accesible del código desarrollado, así como mecanismos robustos de autenticación, autorización y auditoría que garanticen la seguridad del sistema.

Además, se espera que el sistema incluya un sistema de integración continua (CI) que asegure después de cada cambio el correcto funcionamiento del proyecto votación, y se espera conocer la arquitectura de despliegue en la nube de AWS. Queremos asegurarnos que el sistema funciona en la nube, así que se pedirá ver una demostración avanzada del sistema funcionando en AWS.

En conclusión, la idea de esta entrega es que se implemente una forma agil y rápida de desplegar el sistema de votación en AWS.

## Objetivo

El Objetivo de este RFI consiste en conocer el estado del arte dentro de la documentación técnica, seguridad, integración continua y despliegue en AWS de las posibles empresas proveedoras de un proyecto de tipo votación. La fecha límite se encuentra en la sección *Entrega*.

## Preguntas del RFI

La empresa proveedora deberá dar respuesta justificada a los siguientes puntos:

* ¿Cómo se lleva a cabo la autenticación, autorización y auditoria del sistema?
* ¿Cuál es la documentación técnica del código desarrollado?
* ¿Cómo es la documentación de la arquitectura de la solución?
* ¿Cuáles son los procesos de CI?
* ¿Cuáles son las herramientas CI?
* ¿Cuál es la arquitectura en AWS de la solución?
* ¿Qué servicios de AWS requiere el sistema?
* ¿Cuál es el plan de despliegue?
* ¿Teneis alguna prueba del sistema funcionando?
* ¿Por qué es escalable y elástica la solución?
* ¿Cuáles serán los costes de la solución?

## Respuestas a este RFI

* Se requiere la *justificación* (el ¿por qué?) de las respuestas
* Se requieren pruebas para todas las respuestas. Son válidas, código, documentación, capturas de pantalla, vídeos, actas de reuniones, conversaciones, e-mail, audios

## Consideraciones

* Cualquier otro aporte de interés en el ámbito de la mejora de la arquitectura del sistema será bienvenida y considerado para una mayor puntuación en la evaluación
* Cualquier otro aporte de interés en el ámbito de la integración continua o despliegue continuo del sistema será bienvenido y considerado para una mayor puntuación en la evaluación
* Cualquier otro aporte de interés en el ámbito de la seguridad y auditoría del sistema será bienvenido y considerado para una mayor puntuación en la evaluación
* Solo se valorarán arquitecturas basadas en microservicios
* Solo se valorarán arquitecturas basadas en AWS
* Solo se valorarán microservicios basados en Docker como sistema de contenedores
* Durante la presentación se espera una demostración del sistema funcionando en AWS

## Entrega

* La fecha límite para la entrega del RFI será el: *15 de abril de 2026*
* Se deberá realizar una presentación el mismo día *15 de abril de 2026* en el horario habitual de la asignatura
* La entrega será realizada mediante ficheros `.pdf`, o ficheros `.zip` con el código o documentación necesarias. No se admiten enlaces a recursos externos al `.zip`, salvo en el caso que se quiera enviar una tag de un repositorio git público. En todo caso esto se hará para demostrar el uso de varias funcionalidades del repositorio de git público (issues, milestones, etc.) y no para compartir el código del proyecto (este deberá estar si o si en el `.zip`).
* Se puede incluir todo el código y documentación que el proveedor considere necesaria
* La tarea de MiAulario será previamente anunciada mediante anuncio en miAulario o e-mail.

## Evaluación

| Tema                                     | Puntuación |
| ---------------------------------------- | ---------: |
| Autenticación Autorización Auditoria     |         10 |
| Herramienta CI                           |          5 |
| Proceso CI                               |          5 |
| Documentación código/ejecución           |          5 |
| Documentación Arquitectura (local y aws) |          5 |
| Despliegue Parcial en AWS                |         10 |
| Presentación/Demo                        |         10 |
| Total                                    |         50 |

## Modificaciones sobre este RFI

El cliente se guarda el derecho a modificar este RFI en cualquier momento, siendo obligado su aviso mediante anuncio en miAulario o e-mail a partir del día 26 de marzo del 2026.
