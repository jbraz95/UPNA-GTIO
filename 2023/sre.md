# SRE: Site Reliability Engineer

Hoy vamos a ver cual es la labor del Site Reliability Engineer (SRE) y/o Cloud Engineer.

- [SRE: Site Reliability Engineer](#sre-site-reliability-engineer)
  - [¿Qué es un SRE? ¿Y un Cloud Engineer? Y entonces, ¿que es un DevOps?](#qué-es-un-sre-y-un-cloud-engineer-y-entonces-que-es-un-devops)
  - [Responsabilidades de un SRE](#responsabilidades-de-un-sre)
  - [Habilidades necesarias](#habilidades-necesarias)
  - [Herramientas y tecnologías más comunes para un SRE](#herramientas-y-tecnologías-más-comunes-para-un-sre)
  - [Nuevas tendencias de un SRE](#nuevas-tendencias-de-un-sre)

## ¿Qué es un SRE? ¿Y un Cloud Engineer? Y entonces, ¿que es un DevOps?

Un SRE es un ingeniero de software que se encarga de la disponibilidad, escalabilidad y rendimiento de las aplicaciones. La idea es que el SRE se preocupe de que las aplicaciones funcionen correctamente y que el equipo de desarrollo se pueda centrar en desarrollar nuevas funcionalidades. Sus tareas más comunes serán crear la infraestructura, monitorizarla, mantenerla, pequeños desarrolllos o automatizar tareas.

Entonces... que es un Cloud Engineer? Pues la verdad que no hay muchas diferencias entre un SRE y un Cloud Engineer. Se podría decir que un Cloud Engineer es experto en un IaaS (o varios) mientras que el SRE sería más agnóstico, buscando soluciones que funcionen en cualquier IaaS, pero también yendo un paso más allá y definiendo mejor las operaciones. Cada empresa tiene una visión, y según [Google](https://sre.google/in-conversation/) un SRE piensa en las operaciones que se van a tener que realizar y busca la forma de automatizarlas. "Fundamentally, it's what happens when you ask a software engineer to design an operations function"

¿Y un DevOps? Bueno, pues es que un DevOps no existe como tal, ya que DevOps es una cultura/metodología. Una organización que incluye prácticas DevOps haces cosas como continuous integration y continuous delivery (ci/cd) o automatización de tareas. Pero no es que haya un rol de DevOps, sino que todos los miembros de la organización deben tener un poco de DevOps en su ADN. Aunque la realidad es que os encontrareis cientos de puestos que se llamen DevOps engineers.

Pero es que luego están los Platform Engineers, que se enfocan en la creación y mantenimiento de una plataforma de tecnología que permita a los equipos de desarrollo crear, implementar y escalar aplicaciones de manera eficiente. Pero es que esto al final es un poco lo mismo... ¿no?

Al final todos estos roles hacen tareas muy muy parecidas, que es desplegar servicios y mantenerlos funcionando. ¿Y como conseguimos eso? Monitorizando, haciendo mejor la infraestructura, analizando resultados para ver mejoras, etc. En este texto vamos a seguir hablando de SRE porque es la denominación que más caché tiene ahora, pero realmente cualquiera de las anteriores encajaría sin problemas.

## Responsabilidades de un SRE

Un SRE va a tener que:

- Diseñar, implementar y mantener la infraestructura Cloud de la empresa
- Realizar tareas de operaciones como escalar instancias o hacer despliegues
- Automatizar tareas y procesos, desde limpiezas o migraciones hasta despliegues de aplicaciones automáticos. Generalmente estas automatizaciones se hacen despues de que se hayan hecho manualmente (en las operativas anteriores) varias veces.
- Monitorizar la infraestructura y las aplicaciones. Esto puede ser con paneles de control (como visualización de gráficos o lectura de logs) o con Alertas (que se disparan cuando se detecta un problema)
- Investigación de problemas. Cuando se detecta un problema, el SRE tiene que investigar el problema y solucionarlo. Esto puede implicar hacer cambios en la infraestructura, en la aplicación o en la configuración de la misma. Muchas veces trabajará mano a mano con un desarrollador para encontrar la solución.

## Habilidades necesarias

Los requisitos para ser un SRE son diferentes al resto. Cuando uno quiere ser desarrollador de Front o de Back, suele trabajar con un stack y esos suelen ser los requisitos para hacer ese trabajo. Dependerá de tu conocimiento en ese área pero generalmente los requisitos suelen ser unas herramientas concretas. Se pueden hacer exámenes técnicos para comprobar el dominio del stack y con una charla técnica se puede revisar las buenas prácticas o conocimientos de arquitectura. Pero en el caso de un SRE, no hay un stack concreto, y por lo tanto no hay un examen técnico que te pueda comprobar si eres un buen SRE o no. Por lo tanto, los requisitos para ser un SRE suelen más genéricos y se basan en habilidades y conocimientos. Es dificil medir si alguien va a ser un buen SRE, y la actitud y sus "batallitas" pueden ser muy importantes. Las habilidades serían las siguientes:

- Conocimientos de programación. No hace falta ser un experto, pero si que sepa programar. Es importante saber programar porque muchas veces se tendrá que hacer pequeños desarrollos para automatizar tareas o para solucionar problemas.
- Arquitecturas: Hay que saber como montar diferentes sistemas y sus herramientas más comunes. Una buena arquitectura es clave para tener un sistema que se pueda mantener y que sea escalable.
- Seguridad: Es importante saber como proteger la infraestructura y las aplicaciones. Hay que saber como protegerse de ataques, como hacer backups, como hacer que la infraestructura sea segura, etc. Aunque no es la labor propia de un SRE, si que generalmente va a caer mucho de su lado.
- Comunicación: Un SRE va a ser una persona que se comunique constantemente con otros equipos, ya sea para resolver problemas o para coordinar despliegues. También hay que entender los requisitos de los equipos y saber exáctamente que quieren para poder darles lo que necesitan. Pero sobretodo hay que saber comunicarse bien con tu propio equipo, ya que cuando haya una incidencia tendremos que ser muy rápidos y una buena comunicación es clave en estos momentos

## Herramientas y tecnologías más comunes para un SRE

Hemos hablado de que no hay un stack claro como tal cuando uno es un SRE, pero eso no es del todo verdad. Si que hay una serie de herramientas que se suelen usar mucho, y que son las que se suelen pedir en las entrevistas. El tema es que no son herramientas super complejas, y todo dependerá de la empresa y como esté montada su infraestructura. Pero vamos a ver las más comunes:

- El propio IaaS: AWS, Azure, GCP. Cada proveedor tiene sus propias herramientas, y aunque son parecidas si que tienen ciertas diferencias
- Infraestructura como código: Terraform, CloudFormation, Ansible, Chef, Puppet, etc. Estas herramientas nos permiten definir la infraestructura como código, y luego desplegarla en el IaaS. Esto nos permite tener un control total de la infraestructura, y además nos permite automatizar despliegues y hacer cambios de forma rápida y sencilla.
- Herramientas de monitorización: Grafana, Prometheus, Datadog, etc. Estas herramientas nos permiten monitorizar la infraestructura y las aplicaciones. Nos permiten ver métricas, logs, etc. y nos permiten tener un control total de la infraestructura y las aplicaciones.
- Scripting: Bash, Python, etc. Estos lenguajes nos permiten automatizar tareas y hacer pequeños desarrollos.

## Nuevas tendencias de un SRE

Poco a poco (como pasó con la informática) se está viendo como este rol es MUY amplio y hay muchísimas zonas en las que uno se puede especializar. Poco a poco el rol de SRE irá mutando en varios subroles, y cada uno de ellos tendrá sus propias herramientas y tecnologías. Algunos ejemplos que podemos ver (o que veremos):

- Roles de Data: Desde montar un dataware house/data lake hasta hacer análisis de datos. La infraestructura para trabajar con datos es muy importante y poco a poco habrá más y más roles de este tipo.
- MLOps: Es el rol de SRE para Machine Learning. Es un rol que está creciendo mucho y que va a seguir creciendo. En este caso, el SRE tiene que montar la infraestructura para entrenar los modelos de ML, y luego tiene que montar la infraestructura para desplegar los modelos de ML. Es una práctica como es la de DevOps, pero bueno... habrá roles de esto.
- Platform Engineering: SRE que se centren en hacer una plataforma de despliegues para los equipos. Aquí el SRE hará muchas automatizaciones y hara que los despliegues sean muy rápidos y sencillos. Esto es muy importante para que los equipos puedan desplegar sus aplicaciones de forma rápida y sencilla.
- Monitorización: SRE que se centren en la monitorización de la infraestructura y las aplicaciones. En este caso, el SRE se centrará en hacer que la monitorización sea lo más eficiente posible, y que los equipos puedan monitorizar sus aplicaciones de forma sencilla.
