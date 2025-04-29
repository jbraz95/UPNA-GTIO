---
marp: true
class: invert
footer: Entornos y Costes
paginate: true
theme: my-theme
---
# Entornos y costes

---
<!-- _header: Entornos y costes -->

## ¿Qué es un entorno?

Un entorno es un espacio aislado donde se ejecuta una aplicación o servicio, con una configuración concreta de software, datos y recursos. Los entornos permiten separar fases del ciclo de vida del software y reducir riesgos.

---
<!-- _header: Tipos de entornos -->

### Entorno de desarrollo

- Donde los desarrolladores prueban y crean nuevas funcionalidades.
- Suele ser el entorno más flexible y menos controlado.

---
<!-- _header: Tipos de entornos -->

### Entorno de producción

- Donde los usuarios finales utilizan la aplicación.
- Máxima estabilidad y seguridad.
- No siempre existe en proyectos pequeños, pero es imprescindible en proyectos reales.

---
<!-- _header: Tipos de entornos -->

### Entorno de preproducción/integración

- Réplica de producción para validar cambios antes de publicarlos.
- Permite pruebas de integración, rendimiento, etc.
- Suele ser el siguiente entorno que se crea cuando el proyecto crece.

---
<!-- _header: Platform engineering y entornos bajo demanda -->

### Platform engineering

- Consiste en automatizar la creación y gestión de entornos.
- Permite crear varios entornos de desarrollo, preproducción, etc., bajo demanda.
- Ejemplo: cada rama de un repositorio puede desplegar su propio entorno temporal.
- Herramientas como Terraform, Kubernetes, AWS CloudFormation, etc.
- El problema es que automatizar todo esto puede ser complicado y costoso.

---
<!-- _header: Relación entre entornos y costes -->

## Costes asociados a los entornos

- Cada entorno consume recursos (máquinas, almacenamiento, bases de datos, licencias, etc.).
- A más entornos, más costes y más complejidad de gestión.
- Es fácil perder el control de los gastos si no se monitoriza.

---
<!-- _header: Control y estimación de costes -->

## ¿Cómo controlar y estimar los costes?

- Es fundamental saber cuánto cuesta cada entorno para poder dimensionar y planificar el crecimiento.
- Herramientas como AWS Cost Explorer permiten analizar el gasto real y estimar el impacto de nuevos entornos.
- Revisar las tarifas de los proveedores cloud ayuda a prever gastos futuros.
- Ejemplo: si un entorno de desarrollo cuesta 20€/mes, ¿cuánto costará tener 10 entornos simultáneos?
  - Probablemente más de 200€, ya que los precios no son lineales.

---
<!-- _header: Resumen y recomendaciones -->

## Resumen

- Mínimo: desarrollo y producción. Lo habitual: añadir preproducción/integración.
- Platform engineering permite escalar y automatizar la gestión de entornos.
- Controlar los costes es clave para evitar sorpresas y poder escalar de forma sostenible.

---
<!-- _header: Ejercicio -->

> Calcula el coste mensual de tus entornos usando la calculadora de precios de AWS o el Cost Explorer. ¿Qué impacto tendría duplicar el número de entornos?
