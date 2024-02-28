---
marp: true
class: invert
footer: Herramientas para la Gestión de Proyectos y Gestión de La Configuración
paginate: true
theme: my-theme
---

# Diferentes Arquitecturas de Nube

Como hemos hablado en cloud hay múltiples proveedores de servicios en la nube, cada uno con sus propias características y ventajas. Cada uno de ellos tendrá diferentes servicios y con ellos podremos crear diferentes arquitecturas. En esta sesión vamos a ver las diferentes arquitecturas de nube que podemos crear.

---

- [Diferentes Arquitecturas de Nube](#diferentes-arquitecturas-de-nube)
  - [Arquitecturas Principales](#arquitecturas-principales)
    - [Arquitectura de Nube Pública](#arquitectura-de-nube-pública)
    - [Arquitectura de Nube Privada](#arquitectura-de-nube-privada)
    - [Arquitectura de Nube Híbrida](#arquitectura-de-nube-híbrida)
    - [Multicloud](#multicloud)
    - [Arquitectura Serverless (Sin Servidor)](#arquitectura-serverless-sin-servidor)
  - [Otras arquitecturas o patrones](#otras-arquitecturas-o-patrones)
    - [Usar Contenedores](#usar-contenedores)
    - [Arquitectura por microservicios](#arquitectura-por-microservicios)
    - [Arquitectura IoT](#arquitectura-iot)

---

## Arquitecturas Principales

Cuando trabajamos en cloud podemos decir que hay 5 arquitecturas principales. Estas arquitecturas son las que más se usan y las que más se ven en la vida real.

---

### Arquitectura de Nube Pública

La arquitectura de nube pública es la más común. En esta arquitectura los servicios de la nube son proporcionados por un tercero, que es el proveedor de servicios en la nube. Este proveedor es el que se encarga de mantener los servidores, de mantener parte de la seguridad, de mantener la disponibilidad, etc. En esta arquitectura el cliente no tiene que preocuparse de una gran mayoría, simplemente paga por los servicios que usa. El cliente montará ahí su servicio y podrá usar los servicios de la nube que necesite.

---
<!-- _header: Nube Pública -->

Lo más común es que poco a poco el cliente vaya implementando servicios que ofrezca su nube pública y vaya construyéndose sobre ella. Será cada vez más dificil migrar a otra nube pública, ya que el cliente tendrá que migrar todos sus servicios a la nueva nube.

---
<!-- _header: Nube Pública -->

Pero esto también hace que su uso sea más sencillo ya que muchos servicios simplificarán las tareas. Por ejemplo, si tenemos un servicio de base de datos, este servicio nos proporcionará una base de datos con un usuario y contraseña, y nos proporcionará un puerto para conectarnos a ella. No nos tendremos que preocupar de escalar, gestionar la bbdd o como realizar el backup. Todo esto lo hará el proveedor de servicios en la nube.

---

### Arquitectura de Nube Privada

En una nube privada, los recursos de infraestructura, como servidores, almacenamiento y redes, se utilizan exclusivamente para la organización que los implementa. Esto significa que la organización tiene un mayor control sobre la seguridad, la privacidad y la personalización de la nube.

---
<!-- _header: Nube Privada -->

A diferencia de una nube pública, donde los recursos son compartidos por varios usuarios, una nube privada se utiliza solo por una organización y se encuentra detrás del firewall de la empresa. Esto hace que la nube privada sea una opción popular para organizaciones que necesitan un alto nivel de control sobre sus datos y aplicaciones, como empresas grandes y organizaciones gubernamentales.

---
<!-- _header: Nube Privada -->

Algunas de las ventajas de una nube privada incluyen:

- Mayor control y personalización: La organización tiene un mayor control sobre los recursos y datos de la nube, lo que le permite personalizar la configuración y ajustar la infraestructura según sus necesidades.
- Mayor seguridad: Al estar detrás de un firewall, la nube privada es más segura que la nube pública, ya que se minimiza el riesgo de acceso no autorizado a los datos y aplicaciones de la organización.
- Mayor flexibilidad: La organización puede utilizar la nube privada para alojar una amplia variedad de aplicaciones y servicios de TI, lo que le permite adaptarse rápidamente a las necesidades cambiantes del negocio.

---
<!-- _header: Nube Privada -->

Sin embargo, la implementación de una nube privada puede requerir una inversión inicial significativa en infraestructura y recursos de TI, lo que puede ser una desventaja para algunas organizaciones. Además, la gestión de una nube privada puede ser más compleja que la gestión de una infraestructura "on-premises", ya que requiere conocimientos especializados en la arquitectura de nube y en el uso de herramientas de gestión de la nube.

---

### Arquitectura de Nube Híbrida

Una arquitectura híbrida es un modelo de implementación de servicios de computación en la nube que combina una nube pública y una nube privada. Otra opción es una nube pública y una infraestructura onpremise, la idea es que cierto cómputo se haga en la nube pública y otra en onpremise/nube privada.

---
<!-- _header: Nube Híbrida -->

En una arquitectura híbrida, algunos servicios y aplicaciones se ejecutan en una nube pública, mientras que otros se ejecutan en una nube privada. Los dos entornos de nube están conectados a través de una red segura que permite la transferencia de datos entre ellos.

---
<!-- _header: Nube Híbrida -->

Por ejemplo, una organización puede utilizar una nube pública para alojar aplicaciones web que requieren una gran cantidad de recursos informáticos, como procesamiento de datos intensivo. Al mismo tiempo, puede utilizar una nube privada para alojar aplicaciones empresariales críticas que requieren un mayor nivel de control y seguridad, como aplicaciones de finanzas y recursos humanos.

---
<!-- _header: Nube Híbrida -->

Esta arquitectura tambien es la más compleja de las 3 mencionadas hasta ahora. Requiere gestionar 2 nubes diferentes a la vez y con permisos diferentes. Además, requiere de una gran cantidad de conocimientos en la gestión de ambas nubes.

---

### Multicloud

Una arquitectura multicloud es un modelo de implementación de servicios de computación en la nube que utiliza dos o más proveedores de nube pública diferentes para alojar aplicaciones y servicios. En una arquitectura multicloud, una organización puede utilizar diferentes proveedores de nube pública, como Amazon Web Services (AWS), Microsoft Azure, Google Cloud Platform (GCP), entre otros.

---
<!-- _header: Multicloud -->

La arquitectura multicloud se diferencia de la arquitectura híbrida en que la arquitectura híbrida combina una nube pública y una nube privada, mientras que la arquitectura multicloud utiliza múltiples nubes públicas. Al utilizar múltiples proveedores de nube pública, las organizaciones pueden aprovechar las fortalezas de cada proveedor y minimizar las limitaciones y debilidades.

---
<!-- _header: Nube Híbrida -->

Además estarán menos atados a un proveedor, ya que si este deja de ofrecer un servicio, la organización podrá migrar a otro proveedor que sí lo ofrezca.

---
<!-- _header: Nube Híbrida -->

Sin embargo, la implementación y gestión de una arquitectura multicloud puede ser compleja, ya que requiere la integración de diferentes proveedores de nube pública y la gestión de diferentes herramientas y plataformas.

---

### Arquitectura Serverless (Sin Servidor)

Una arquitectura serverless es un modelo de implementación de servicios en la nube en el que el proveedor de la nube se encarga de administrar la infraestructura subyacente necesaria para ejecutar y escalar aplicaciones y servicios sin que el usuario tenga que preocuparse de nada más que no sea su código. Esto permite a los desarrolladores centrarse en escribir código y no preocuparse por la administración de servidores o infraestructura.

---
<!-- _header: Serverless -->

Algunas de las características y ventajas de una arquitectura serverless son:

- Escalabilidad automática: El proveedor de la nube se encarga de escalar automáticamente los recursos necesarios para ejecutar la aplicación o función en función de la demanda, lo que permite una mayor escalabilidad y flexibilidad.
- Pago por uso: El modelo de precios en una arquitectura serverless se basa en el uso real de los recursos, lo que permite a los usuarios pagar solo por lo que utilizan y reducir los costos generales.
- Tiempo de ejecución eficiente: Al no tener que preocuparse por la gestión de la infraestructura, los desarrolladores pueden centrarse en escribir código y mejorar el tiempo de ejecución de las aplicaciones y funciones.

---
<!-- _header: Serverless -->

Algunos ejemplos de servicios serverless son AWS Lambda, Google Cloud Functions y Azure Functions. En estos servicios, el usuario solo tiene que proporcionar el código y configurar algunos parámetros, y el proveedor de la nube se encarga del resto, incluyendo la escalabilidad, el rendimiento y la gestión de la infraestructura subyacente.

---
<!-- _header: Serverless -->

El problema de esta arquitectura es su complejidad y lo atado que te quedas a un proveedor. Es una arquitectura muy nueva y muy barata, pero eso significa que está muy verde y puede traer complejidades a la hora de gestionarla. Además, si el proveedor deja de ofrecer el servicio o aumenta su precio, la organización tendrá que migrar a otro proveedor. Por lo que es una arquitectura que no se recomienda para organizaciones grandes, si no para pequeños equipos o proyectos.

---

## Otras arquitecturas o patrones

Despues de ver las arquitecturas más comunes, vamos a ver otras arquitecturas o patrones que se pueden utilizar en la nube. No son como tal "arquitecturas", pero si que son ideas que se pueden integrar en ellas. Además, estas ideas no están atadas a la nube y son más genéricas, por lo que se pueden utilizar en cualquier tipo de infraestructura.

---

### Usar Contenedores

Ya hemos visto anteriormente los beneficios de usar contenedores para entregar y desplegar aplicaciones: es más facil de entregar, se reducen errores, el despliegue es más sencillo, etc. Pero además, los contenedores también nos permiten crear arquitecturas más escalables y flexibles.

---
<!-- _header: Contenedores -->

Por ejemplo, podemos usar contenedores para crear un cluster de contenedores que se encargue de escalar automáticamente la aplicación en función de la demanda. Otra ventaja es que podemos crear unidades lógicas a la hora de levantar máquinas: un conjunto de contenedores que se encarguen de una misma aplicación y que sean interdependientes entre ellos pueden ir en una máquina, mientras que otro conjunto de contenedores que se encarguen de otra aplicación pueden ir en otra máquina. Te permite crear crear tu máquina como si fuese un lego, metiendo las piezas que te interesan.

---
<!-- _header: Contenedores -->

Además usar contenedores para desplegar servicios a día de hoy se considera una buena práctica. Esto no solo significa que tu sistema será más limpio, robusto y escalable, si no que tambien se acoplará mejor a la nube o a otros servicios de terceros. Al fin y al cabo, si utilizas una tecnología que muchos usan será más probable que tengas herramientas para gestionarla.

---

### Arquitectura por microservicios

Aunque explicar en profundidad lo que es la arquitectura de microservicios se va del alcance de este curso, vamos a ver brevemente que es y porque es importante.

También es importante entender que nosotros solemos hablar de que hacemos "microservicios" pero en realidad lo que hacemos es una arquitectura de servicios, que son servicios algo más grandes y dependientes que los microservicios.

---
<!-- _header: Microservicios -->

Una arquitectura por microservicios es una forma de diseño de software en la que las aplicaciones se dividen en pequeños servicios independientes que se comunican entre sí a través de interfaces bien definidas. Cada microservicio se enfoca en un conjunto específico de funcionalidades de la aplicación y puede ser implementado, escalado y actualizado de manera independiente. Algunos de los beneficios de una arquitectura por microservicios son:

---
<!-- _header: Microservicios -->

- Flexibilidad y agilidad: al dividir la aplicación en pequeños servicios independientes, se puede desarrollar, probar e implementar cada uno de manera más rápida y ágil.
- Escalabilidad y disponibilidad: cada servicio puede ser escalado y desplegado de manera independiente, lo que permite una mayor disponibilidad y escalabilidad de la aplicación en general.
- Resiliencia: en caso de fallos en uno o varios servicios, los demás servicios pueden seguir funcionando normalmente, lo que mejora la resiliencia de la aplicación.
- Facilidad de mantenimiento: cada servicio puede ser actualizado y mantenido de manera independiente, lo que facilita el mantenimiento de la aplicación en general.
- Mejora del rendimiento: al dividir la aplicación en pequeños servicios, se puede optimizar el rendimiento de cada uno de manera individual.
- Facilidad de integración: los servicios pueden ser implementados en diferentes lenguajes de programación y tecnologías, lo que facilita la integración con otras aplicaciones y sistemas.

---
<!-- _header: Microservicios -->

Una arquitectura por microservicios ofrece una serie de beneficios importantes para el diseño de software, incluyendo flexibilidad, agilidad, escalabilidad, disponibilidad, resiliencia, facilidad de mantenimiento y mejora del rendimiento. Estos beneficios hacen que las arquitecturas por microservicios sean populares en la implementación de aplicaciones modernas.

---

### Arquitectura IoT

Una arquitectura IoT se asemeja a una cloud en cuanto a que tiene muchos dispositivos conectados entre sí. Estos hay que saber gestionarlos y lanzar sus actualizaciones, al igual que saber monitorizarlos y automatizalos. La diferencia es que en una arquitectura IoT los dispositivos no son máquinas virtuales, si no que son dispositivos físicos. Por ejemplo, un sensor de temperatura, un sensor de humedad, un sensor de movimiento, etc.

---
<!-- _header: IoT -->

Una arquitectura muy común en IoT es la de un sensor que se conecta a una red de sensores y que se encarga de recoger datos de los sensores y enviarlos a un servidor. El servidor se encarga de procesar los datos y enviarlos a un servidor. Ese servidor puede estar en un servidor local o en la nube.

Compañias de nube pública como AWS o Azure tienen servicios específicos para IoT, como por ejemplo AWS IoT o Azure IoT Hub.

---
<!-- _header: IoT -->

Los dispositivos IoT utilizan protocolos de comunicación diferentes a los habituales. El más famoso y extendido es MQTT, pero últimamente también se está utilizando CoAP. Estos protocolos son más ligeros y están pensados para dispositivos con poca capacidad de procesamiento y de batería.

Además hay que tener en cuenta que muchos de ellos utilizan redes de baja potencia, como LoRaWAN, sigfox, NB-IoT y, a veces si tenemos suerte, 4G o 5G.

Es por eso que una nube que se comunique con IoT será ligeramente diferente, ya que necesitará servicios específicos de IoT, nuevos protocolos de comunicación y piezas de IaaS de más bajo nivel. Por ejemplo, si utilizamos MQTT, no podremos utilizar ALB y tendremos que utilizar NLB. Esto sucede porque el primero es un balanceador de capa 7 y el segundo de capa 4, y MQTT es un protocolo que funciona sobre capa 4.