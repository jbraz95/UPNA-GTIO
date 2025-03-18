# RFI III. Proyecto Votación - CI/CD & Arquitectura Cloud

## Contexto

En un mundo tecnológico en constante cambio, la empresa Bermejo inc. (en adelante el cliente) necesita conocer la arquitectura de despliegue y de integración de un sistema de tipo votación para OT.

Se espera que un proyecto de estas características incluya un sistema de integración continua (CI). De forma que los desarrolladores conozcan el resultado y la calidad de sus desarrollos sin necesidad de hacer un despliegue en un entorno de producción.

Así el sistema deberá incluir un sistema de integración continua que asegure después de cada cambio el correcto funcionamiento del proyecto votación.

Además, se espera conocer la arquitecura de despliegue en la nube de AWS. Queremos asegurarnos que el sistema funciona en la nube, así que se pedirá ver una demostración bastante avanzada del sistema funcionando en AWS. Puede que haya algún fallo y se permitirán ciertos errores, pero la mayoría de la solución debería funcionar.

## Objetivo

El Objetivo de este RFI consiste en conocer el estado del arte dentro de la integración continua y arquitectura y despliegue en AWS de las posibles empresas proveedoras de un proyecto de tipo votación. La fecha límite se encuentra en la sección *Entrega*.

## Preguntas del RFI

La empresa proveedora deberá dar respuesta justificada a los siguientes puntos:

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

* Cualquier otro aporte de interés en el ámbito de la mejora de la arquitectura del sistema
será bienvenida y considerado para una mayor puntuación en la evaluación
* Cualquier otro aporte de interés en el ámbito de la integración continua o despliegue continuo del sistema
será bienvenido y considerado para una mayor puntuación en la evaluación
* Solo se valorarán arquitecturas basadas en microservicios
* Solo se valorarán arquitecturas basadas en AWS
* Solo se valorarán microservicios basados en Docker como sistema de contenedores
* Durante la presentación se espera una demostración del sistema funcionando en AWS

## Entrega

* La fecha límite para la entrega del RFI será el: *7 de mayo de 2025*
* Se deberá realizar una presentación el mismo día *7 de mayo de 2025* en el horario habitual de la asignatura
* La entrega será realizada mediante ficheros `.pdf`, o ficheros `.zip` con el código o documentación necesarias. No se admiten enlaces a recursos externos al `.zip`, salvo en el caso que se quiera enviar una tag de un repositorio git público. En todo caso esto se hará para demostrar el uso de varias funcionalidades del repositorio de git público (issues, milestones, etc.) y no para compartir el código del proyecto (este deberá estar si o si en el `.zip`).
* Se puede incluir todo el código y documentación que el proveedor considere necesaria
* La tarea de MiAulario será previamente anunciada mediante anuncio en miAulario o e-mail.

## Evaluación

| Tema                           | Puntuación |
| ------------------------------ | ---------: |
| Herramienta CI                 |          5 |
| Proceso CI                     |         10 |
| Documentación Arquitectura AWS |          5 |
| Despliegue Parcial en AWS      |         10 |
| Presentación/Demo              |         20 |
| Total                          |         50 |

## Modificaciones sobre este RFI

El cliente se guarda el derecho a modificar este RFI en cualquier momento, siendo obligado su aviso mediante anuncio en miAulario o e-mail a partir del día 20 de marzo del 2025.
