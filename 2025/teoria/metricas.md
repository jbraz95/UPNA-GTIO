# Métricas: Rendimiento y KPIs. Agentes beats, Elastic, Kibana

- [Métricas: Rendimiento y KPIs. Agentes beats, Elastic, Kibana](#métricas-rendimiento-y-kpis-agentes-beats-elastic-kibana)
  - [¿Que son las métricas y los KPI's?](#que-son-las-métricas-y-los-kpis)
  - [Métricas comunes en el software](#métricas-comunes-en-el-software)
  - [Definición y generación de KPIs](#definición-y-generación-de-kpis)
  - [Links interesantes sobre KPIs en móviles](#links-interesantes-sobre-kpis-en-móviles)
  - [Aplicación práctica](#aplicación-práctica)
    - [Elastic Stack](#elastic-stack)
    - [Sustitución de Elastic Stack por otras herramientas](#sustitución-de-elastic-stack-por-otras-herramientas)
    - [Nuestro Stack con CloudWatch](#nuestro-stack-con-cloudwatch)

## ¿Que son las métricas y los KPI's?

En el contexto del software, una métrica es una medida cuantitativa utilizada para evaluar la calidad, el rendimiento o el progreso de un sistema o proceso. Para simplificar nos referiremos a métricas cuando indiquen el rendimiento de un sistema en ese momento (cpu, memoria, etc), y a las que midan el progreso de un proceso o la calidad de un producto las llamaremos KPI's

Las métricas son fundamentales para la monitorización y optimización del rendimiento de nuestras aplicaciones. Con estas podremos ver que carga tienen nuestras instancias, si hay cuellos de botella, si hay problemas de memoria, etc. Cuando tenemos una sola máquina eso suele ser más facil de ver, pero cuando tenemos varias tenemos que recurrir a las métricas para poder ver como se comporta el sistema. Generalmente las métricas se recopilan en un sistema de monitorización, como puede ser [Grafana](https://www.grafana.com), [Zabbix](https://www.zabbix.com/), [Nagios](https://www.nagios.org/), [Prometheus](https://prometheus.io/), [Elastic Stack](https://www.elastic.co/elastic-stack), etc. Incluso algunos IaaS como [AWS](https://aws.amazon.com/es/) tienen sistemas de monitorización integrados como [CloudWatch](https://aws.amazon.com/es/cloudwatch/).

Entonces... ¿Que son los KPI's? Los KPIs son los indicadores clave de rendimiento que se utilizan para medir el éxito de un software o proceso. Son métricas que engloban un conjunto de métricas con el objetivo de medir el rendimiento de un proceso o sistema en relación con los objetivos específicos de la organización. Lo veremos más adelante, pero los podemos entender como una métrica más abstracta y orientada a objetivos.

## Métricas comunes en el software

Así que visto que ya existen las KPI's cuando hablemos de métricas nos referiremos a métricas generales que nos permiten evaluar el rendimiento de un sistema o proceso. Algunas métricas importantes en el software son:

- CPU: Utilización, carga, espera, etc.
- Memoria: Uso, paginación, intercambio, etc.
- Acceso: Tiempos de respuesta, latencia, etc.
- Otros: Ancho de banda, errores, etc.

Estas métricas se extraen de los sistemas usando herramientas como metricbeat o OpenTelemetry. Estas herramientas se llaman "herramientas de instrumentación", se instalan en los servidores y recopilan métricas de los sistemas operativos y aplicaciones. Estas métricas se envían a un sistema de monitorización y nos permiten visualizar y analizar las métricas de manera efectiva.

Para poder aprovechar estas métricas sería interesante añadirles un sistema de trazabilidad, como puede ser [Metricbeat](https://www.elastic.co/es/beats/metricbeat), [Jaeger](https://www.jaegertracing.io/), [Zipkin](https://zipkin.io/), [OpenTracing](https://opentracing.io/), etc. Estos sistemas nos permiten añadir trazabilidad a nuestras aplicaciones y así poder ver como una acción en una aplicación afecta a otra. Por ejemplo, si tenemos una aplicación web que hace una petición a una API, podemos añadir trazabilidad a ambas aplicaciones y ver como afecta la petición a la API y a la aplicación web y de esta manera podemos ver donde hay cuellos de botella y donde podemos mejorar el rendimiento.

## Definición y generación de KPIs

KPI significa Key Performance Indicator. Los KPIs son los indicadores clave de rendimiento que se utilizan para medir el éxito de un software o proceso. Son un tipo de métrica que se utilizan para medir el rendimiento de un proceso o sistema en relación con los objetivos específicos de la organización. Se utilizan comúnmente en los negocios para evaluar el rendimiento financiero, pero también se pueden utilizar en el software para medir el rendimiento en relación con objetivos específicos, como la satisfacción del usuario o como de eficientes estamos siendo en el desarrollo.

Estos se crean para tomar decisiones informadas: Fijamos un objetivo, lo cuantificamos en un número y así podemos hacer una progresión de los resultados. Vamos a poner un ejemplo; Nuestra empresa decide que uno de nuestros objetivos principales es dar una experiencia fluida en nuestra web, así que vamos a definir un KPI para ello. El tiempo de respuesta de la web no debe ser superior a 2 segundos y medirlo será facil ya que tenemos herramientas de instrumentación. Ahora podemos llevar un control de este objetivo y tomar decisiones correctamente, y si llega una nueva funcionalidad que afecta al rendimiento de la web, veremos este KPI y tomaremos decisiones en base a él. Quizás tengamos que optimizar el código, aumentar las instancias o incluso crear un UX que de la sensación de que la web es más rápida. Otros ejemplos podrían ser número de errores en la web o el número de registros. Este último ejemplo está mas centrado en el negocio y no en el software, pero es un ejemplo de como podemos definir KPIs para medir el rendimiento de un proceso o sistema en relación con los objetivos específicos de la organización.

Además tendremos un histórico de como el KPI ha ido evolucionando durante todo este tiempo. Esto nos permitirá ver que acciones han tenido más impacto en el rendimiento de la web y así hacer una mejor planificación de futuras acciones.

Pero para poder hacer todo esto tendremos que monitorizar constantemente nuestro sistema, así que vamos a ver como podemos hacerlo.

## Links interesantes sobre KPIs en móviles

- [Monopoly GO KPIs](https://naavik.co/digest/monopoly-go-kpis/)
- [Brawl stars](https://naavik.co/digest/brawl-stars-moba-reimagined/)

## Aplicación práctica

Nosotros para este proyecto vamos a usar CloudWatch de AWS, que tiene una integración mucho más simple y rápida. Pero si fuese un proyecto mucho más grande deberíamos utilizar un stack más completo como Elastic Stack. Vamos a ver de que se compone y como podemos utilizarlo.

### Elastic Stack

Elastic Stack está compuesto por:

- Agentes Beats: Son pequeños programas que recopilan métricas/logs y las envían a Logstash o Elasticsearch.
- Logstash: Es un servidor de procesamiento de datos que recibe, transforma y envía datos a Elasticsearch. Esto es muy util cuando tenemos que transformar los datos antes de enviarlos, o si queremos duplicarlos en varios sistemas. No es necesario y suele ser un "extra", pero según las necesidades de cada proyecto puede ser muy útil.
- Elasticsearch: Es un motor de búsqueda y análisis de datos escalable y distribuido. Es una base de datos NoSQL que nos permite almacenar y buscar datos de manera muy eficiente. Es bastante complejo de configurar y mantener pero es muy potente (es por eso que nosotros no vamos a utilizarlo en este proyecto).
- Kibana: Es una herramienta de visualización y análisis de datos que se conecta a Elasticsearch. Es muy fácil de configurar y nos permite visualizar y analizar los datos de manera muy eficiente. Generalmente se utiliza para visualizar logs también se puede utilizar para visualizar métricas, aunque generalmente se usa Grafana para esto.

### Sustitución de Elastic Stack por otras herramientas

Como hemos dicho antes, Elastic Stack es un stack muy completo y potente, pero es bastante complejo de configurar y mantener. Además puede tener un alto coste o quizás queremos utilizar otras herramientas. Veamos que posibilidades tenemos:

- Recolectores de métricas (Agentes Beats): Podemos utilizar cualquier agente que nos permita recopilar métricas y enviarlas a un sistema de monitorización. Por ejemplo, podemos utilizar [Prometheus](https://prometheus.io/) o [OpenTelemetry](https://opentelemetry.io/).
- Transformadores de logs (Logstash): La verdad que aquí no hay muchas opciones, pero si no queremos utilizar Logstash podemos utilizar alguna herramienta que nos permita transformar los datos antes de enviarlos a Elasticsearch. Por ejemplo Filebeat tiene un módulo de transformación de datos que nos permite transformar los datos antes de enviarlos a Elasticsearch, pero no es muy flexible. Podemos utilizar [Apache NiFi](https://nifi.apache.org/) o [Apache Airflow](https://airflow.apache.org/), que son herramientas de ETL (Extract, Transform, Load) que nos permiten transformar los datos antes de enviarlos a Elasticsearch.
- Almacenamiento de métricas (Elasticsearch): Realmente Elasticsearch es la herramienta más utilizada en estos casos. Otra opción que tenemos es utilizar herramientas de pago como [Datadog](https://www.datadoghq.com/) o [New Relic](https://newrelic.com/) (¡O incluso CloudWatch, que es lo que vamos a usar!). Pero si no queremos utilizar ninguna de estas herramientas podemos utilizar cualquier base de datos NoSQL que nos permita almacenar y buscar datos de manera eficiente, como por ejemplo [MongoDB](https://www.mongodb.com/). No recomendamos utilizar bases de datos relacionales como MySQL o PostgreSQL ya que no están diseñadas para almacenar y buscar datos de manera eficiente.
- Visualización (Kibana): Aquí es donde más opciones tenemos, pero la más famosa y recomendada es [Grafana](https://grafana.com/). Luego hay otras herramientas para BI como [Tableau](https://www.tableau.com/) o [Power BI](https://powerbi.microsoft.com/es-es/). Aunque el problema de estas es que requieren bases de datos relacionales así que solo las usaremos si tenemos unos procesos ETL que nos permitan transformar los datos antes de enviarlos a la base de datos.

Otra novedad que está surgiendo poco a poco es el uso de ficheros [parquet](https://parquet.apache.org). Vienen a ser sqlite's pero para datos no relacionados. Se pueden utilizar para almacenar estos datos en bases de datos no muy grandes, o para reducir su carga. Están muy bien optimizados, y tiene pinta de que va a ser muy utilizado en el futuro.

### Nuestro Stack con CloudWatch

Nosotros tenemos menos tiempo y vamos a hacer algo bastante más simple. Vamos a utilizar el siguiente stack:

- Recolectores de métricas: Aquí teneis múltiples opciones:
  - Podéis utilizar [CloudWatch Agent](https://docs.aws.amazon.com/es_es/AmazonCloudWatch/latest/monitoring/Install-CloudWatch-Agent.html) que es un agente que recopila métricas de los servicios de AWS y las envía a CloudWatch.
  - Usar Beats para recopilar métricas de los servicios de AWS. Por ejemplo, podemos utilizar [Metricbeat](https://www.elastic.co/guide/en/beats/metricbeat/current/metricbeat-module-aws.html) para recopilar métricas de los servicios de AWS.
  - Otra opción similar a beats es usar [Telegraf](https://www.influxdata.com/time-series-platform/telegraf/) que es un agente de recopilación de métricas. Técnicamente está preparado para influxDB, pero se puede utilizar para cualquier otro sistema. 
  - La opción final es usar OpenTelemetry, que parece que va a ser el estandard de la industria. La mala noticia es que no está del todo pulido y no es muy fácil de configurar. Más información [aquí](https://aws.amazon.com/blogs/opensource/collecting-aws-metrics-using-opentelemetry/).
- Transformadores de logs: No vamos a utilizar ninguno.
- Almacenamiento de métricas: Como ya hemos dicho, vamos a utilizar CloudWatch.
- Visualización: Aquí teneis dos opciones.
  - O bien utilizar CloudWatch para visualizar las métricas.
  - O bien utilizar Grafana. Para esto tenemos que utilizar un plugin de Grafana que se llama [CloudWatch](https://grafana.com/docs/grafana/latest/datasources/aws-cloudwatch/). Este plugin nos permite visualizar las métricas de CloudWatch en Grafana. Podeis utilizar [Grafana Cloud](https://grafana.com/products/cloud/) que es un servicio de Grafana en la nube, o bien instalar Grafana en vuestro propio servidor.

Obviamente, sois libres de utilizar vuestro propio stack! Pero acordaos de preguntar antes :) 