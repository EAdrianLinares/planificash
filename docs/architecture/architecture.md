# Architecture.md

# Arquitectura de Software

**Proyecto:** Planificash

**Versión:** 1.0.0

**Estado:** Aprobado

**Documentos relacionados:**

* Vision.md
* Domain.md
* Technology.md
* ADR/

---

# 1. Objetivo

Este documento define la arquitectura de software de Planificash.

Su propósito es establecer la organización del sistema, los principios arquitectónicos y las reglas que deberán respetarse durante todo el ciclo de vida del producto.

La arquitectura debe permitir que el sistema evolucione sin comprometer el dominio del negocio.

---

# 2. Objetivos Arquitectónicos

La arquitectura de Planificash busca garantizar:

* Mantenibilidad.
* Escalabilidad.
* Bajo acoplamiento.
* Alta cohesión.
* Seguridad.
* Testabilidad.
* Facilidad de evolución.
* Independencia tecnológica.

---

# 3. Principios Arquitectónicos

## 3.1 El dominio es el centro

El modelo del negocio es el activo más importante del sistema.

Toda decisión arquitectónica deberá proteger el dominio.

---

## 3.2 Independencia tecnológica

Las reglas del negocio nunca dependerán de frameworks, motores de bases de datos o proveedores cloud.

Las tecnologías podrán cambiar sin modificar el dominio.

---

## 3.3 Dependencias dirigidas al dominio

Todas las dependencias apuntarán hacia el dominio.

El dominio nunca conocerá detalles de infraestructura.

---

## 3.4 Responsabilidad única

Cada módulo y cada componente deberán tener una única responsabilidad claramente definida.

---

## 3.5 Modularidad

El sistema crecerá mediante módulos independientes.

La incorporación de nuevas funcionalidades no deberá afectar módulos existentes.

---

## 3.6 Seguridad por diseño

La seguridad deberá formar parte de la arquitectura desde el inicio del proyecto.

Nunca será considerada una etapa posterior.

---

## 3.7 Especificaciones antes que implementación

Toda funcionalidad deberá comenzar con una SPEC aprobada.

No se implementará código sin una especificación previamente definida.

---

# 4. Estilo Arquitectónico

Planificash adoptará una arquitectura basada en:

* Monolito Modular.
* Clean Architecture.
* Domain Driven Design (DDD).
* Arquitectura por Capas.

Esta combinación permite un desarrollo ágil para el MVP y una evolución controlada conforme el producto crezca.

---

# 5. Arquitectura General

```text
Usuario
      │
      ▼
Aplicación Web
      │
HTTPS / REST
      │
      ▼
API
      │
┌────────────────────────────┐
│ Presentation               │
├────────────────────────────┤
│ Application                │
├────────────────────────────┤
│ Domain                     │
├────────────────────────────┤
│ Infrastructure             │
└────────────────────────────┘
      │
Persistencia
```

La infraestructura nunca podrá modificar directamente el dominio.

---

# 6. Organización del Repositorio

```text
Planificash/

apps/
packages/
docs/
scripts/
.github/
```

## Responsabilidad de cada carpeta

### apps/

Contiene las aplicaciones ejecutables del producto.

Ejemplo:

* API.
* Web.
* Mobile (futuro).

---

### packages/

Contiene componentes compartidos entre aplicaciones.

Ejemplo:

* utilidades;
* configuraciones;
* tipos;
* librerías comunes.

---

### docs/

Documentación oficial del proyecto.

Representa la fuente de verdad para las decisiones funcionales y arquitectónicas.

---

### scripts/

Automatizaciones del proyecto.

---

### .github/

Configuración de integración continua y flujos de trabajo.

---

# 7. Organización Interna

Cada aplicación podrá organizarse por módulos de negocio.

Cada módulo respetará la separación entre:

* Presentación.
* Aplicación.
* Dominio.
* Infraestructura.

Cada capa tendrá responsabilidades claramente definidas.

---

# 8. Flujo de Dependencias

```text
Presentation
      │
      ▼
Application
      │
      ▼
Domain
      ▲
      │
Infrastructure
```

## Reglas

* Presentation conoce Application.
* Application conoce Domain.
* Infrastructure implementa contratos definidos por Domain.
* Domain no conoce ninguna otra capa.

---

# 9. Comunicación

Durante el MVP:

* Comunicación síncrona.
* API REST.
* HTTPS.
* JSON.

No se implementarán mecanismos de mensajería o eventos distribuidos mientras el negocio no lo requiera.

---

# 10. Calidad Arquitectónica

La arquitectura prioriza los siguientes atributos:

## Mantenibilidad

El código deberá ser fácil de comprender y modificar.

---

## Escalabilidad

La incorporación de nuevos módulos no deberá requerir cambios significativos en la arquitectura.

---

## Seguridad

La protección de la información del usuario es un requisito fundamental.

---

## Testabilidad

Cada componente deberá poder probarse de forma aislada.

---

## Observabilidad

El sistema deberá permitir registrar errores y eventos relevantes para facilitar el diagnóstico y la operación.

---

# 11. Restricciones Arquitectónicas

Durante el MVP no se implementarán:

* Microservicios.
* CQRS.
* Event Sourcing.
* Comunicación distribuida.
* Dependencias circulares.
* Lógica de negocio en controladores.
* Acceso directo a persistencia desde la capa de presentación.

Estas restricciones buscan reducir la complejidad inicial y favorecer un desarrollo incremental.

---

# 12. Convenciones Generales

## Idioma

* Código: Inglés.
* Documentación: Español.

---

## Organización

Cada carpeta deberá tener una única responsabilidad.

No se permitirá mezclar lógica de negocio con infraestructura.

---

## Cambios Arquitectónicos

Toda modificación importante deberá registrarse mediante un ADR antes de su implementación.

---

# 13. Testing

La arquitectura está diseñada para favorecer la automatización de pruebas.

Se utilizará la siguiente estrategia:

1. Pruebas unitarias.
2. Pruebas de integración.
3. Pruebas End-to-End.

Cada nueva funcionalidad deberá definir su estrategia de pruebas dentro de su SPEC correspondiente.

---

# 14. Evolución

La arquitectura de Planificash fue diseñada para evolucionar sin modificar el dominio del negocio.

Las nuevas funcionalidades deberán incorporarse mediante módulos o extensiones del modelo existente, evitando reescrituras innecesarias.

El crecimiento del sistema deberá respetar los principios definidos en este documento.

---

# Historial de Versiones

| Versión | Fecha      | Descripción                                         |
| ------- | ---------- | --------------------------------------------------- |
| 1.0.0   | Julio 2026 | Definición inicial de la arquitectura del proyecto. |
