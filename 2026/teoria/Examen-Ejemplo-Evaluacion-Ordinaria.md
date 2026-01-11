# Examen Ejemplo Evaluación Ordinaria

**Gestión de Tecnologías Informáticas en las Organizaciones**

Máster en Ingeniería Informática. Curso 2024/2025

---

**NOMBRE:**

_**Puntuación**_:

> **IMPORTANTE:**
>
> - Puedes usar tus apuntes y cualquier recurso de internet, pero está prohibido el uso de chats o asistentes de IA (tipo ChatGPT, Copilot, Gemini, etc.).
> - Las preguntas no buscan que memorices definiciones, sino que comprendas, analices y apliques los conceptos.
> - RECUERDA LEER TODO EL EXAMEN ANTES DE EMPEZAR A RESPONDER. Fíjate bien en los puntos que vale cada pregunta, el tiempo que tienes y donde vas a estar seguro de puntuar más.
> - Responde a las preguntas dentro del documento word y súbelo en pdf a miaulario.
> - El examen se entrega en formato PDF. **No se aceptan otros formatos.**
> - La puntuación máxima es de 10 puntos. Para aprobar, necesitas al menos 5 puntos.
> - La duración del examen es de 2 horas.

---

## Parte 1: Preguntas tipo test (20%)

**Responde a las siguientes preguntas. Solo una respuesta es correcta.**

1. ¿Cuál de las siguientes opciones describe mejor el propósito de un API Gateway en una arquitectura de microservicios?
   - a) Almacenar datos de los microservicios
   - b) Gestionar la comunicación y seguridad entre clientes y microservicios
   - c) Ejecutar pruebas automáticas
   - d) Monitorizar el uso de CPU

**Respuesta:** b) Gestionar la comunicación y seguridad entre clientes y microservicios

---

2. ¿Qué herramienta se utiliza principalmente para la gestión de la configuración del código fuente?
   - a) Jira
   - b) Docker
   - c) Git
   - d) Postman

**Respuesta:** c) Git

---

3. ¿Cuál es la principal ventaja de utilizar contenedores Docker frente a máquinas virtuales tradicionales?
   - a) Mayor consumo de recursos
   - b) Menor portabilidad
   - c) Despliegue más rápido y eficiente
   - d) Requiere más hardware

**Respuesta:** c) Despliegue más rápido y eficiente

---

4. ¿Qué significa el término "escalabilidad" en el contexto de sistemas en la nube?
   - a) Capacidad de reducir costes
   - b) Capacidad de aumentar recursos según la demanda
   - c) Capacidad de crear interfaces de usuario
   - d) Capacidad de almacenar datos en local

**Respuesta:** b) Capacidad de aumentar recursos según la demanda

---

## Parte 2: Casos prácticos (80%)

### Caso 1: Análisis de prácticas y propuesta de mejora

1.1. Realiza un gráfico (puede ser un esquema simple) que represente la arquitectura de microservicios que implementasteis en las prácticas. Explica brevemente cada componente.

**Respuesta:**
- El gráfico debe mostrar al menos: API Gateway, microservicios principales (por ejemplo, autenticación, votación, resultados), base de datos y los logs.

1.2. Da tu opinión sobre la arquitectura elegida en las prácticas y propón una mejora concreta para la próxima vez.

**Respuesta:**
- Buscar un problema a largo plazo en la arquitectura y ver como solucionarlo.
- Evitad arreglar cosas que deberían estar bien. Si no pudisteis hacer funcionar X y ahora lo proponeis... eso no es una mejora.

---

### Caso 2: Estrategias y aplicación práctica

1. Explica una estrategia para asegurar la integración continua (CI) en el desarrollo de microservicios. ¿Qué herramientas y pasos utilizarías?

**Respuesta:**
- Estrategia ejemplo:
  - Usar un repositorio Git para el código.
  - Configurar un pipeline de CI (por ejemplo, con GitHub Actions o GitLab CI) que ejecute tests automáticos y despliegue en un entorno de pruebas con Docker.
  - Revisar los resultados y corregir errores antes de hacer merge a la rama principal.

2. ¿Cómo se podría monitorizar el funcionamiento de los microservicios en producción? Nombra una herramienta y explica brevemente cómo se usaría.

**Respuesta:**
- Herramienta ejemplo: Elastic Stack (ELK: Elasticsearch, Logstash, Kibana). Vuestra experiencia con Cloudwatch vale, pero estaría bien conocer algo más complejo.
- Uso: Los microservicios envían logs a Logstash, que los almacena en Elasticsearch. Kibana permite visualizar métricas y detectar incidencias en tiempo real.

---

## Fin del examen ejemplo

Recuerda que este examen es solo una guía para practicar y entender la estructura y tipo de preguntas que pueden aparecer en la evaluación ordinaria.
