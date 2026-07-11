# Technology.md

# Tecnologías del Proyecto

**Proyecto:** Planificash

**Versión:** 1.0.0

**Estado:** Vigente

**Relacionado con:**

* Architecture.md
* ADR/

---

# 1. Objetivo

Este documento describe las tecnologías seleccionadas para implementar la arquitectura de Planificash.

Las tecnologías podrán cambiar durante la evolución del proyecto sin alterar la arquitectura ni el dominio del negocio.

Las razones de cada decisión tecnológica deberán documentarse mediante un ADR.

---

# 2. Principios

La selección de tecnologías seguirá los siguientes principios:

* Priorizar herramientas maduras y ampliamente adoptadas.
* Favorecer tecnologías con buena documentación y comunidad activa.
* Reducir la dependencia de proveedores específicos.
* Elegir herramientas compatibles con una arquitectura modular.
* Mantener la simplicidad del MVP.
* Facilitar el aprendizaje y la mantenibilidad del proyecto.

---

# 3. Stack Tecnológico

| Área                    | Tecnología |
| ----------------------- | ---------- |
| Lenguaje Backend        | TypeScript |
| Lenguaje Frontend       | TypeScript |
| Backend                 | NestJS     |
| Frontend                | React      |
| Base de Datos           | PostgreSQL |
| ORM                     | Prisma     |
| Control de Versiones    | Git        |
| Repositorio             | GitHub     |
| Contenedores            | Docker     |
| Autenticación           | JWT        |
| Gestión de Dependencias | npm        |

---

# 4. Backend

## Framework

NestJS

### Motivo

* Arquitectura modular.
* Soporte para inyección de dependencias.
* Excelente integración con TypeScript.
* Escalable para proyectos empresariales.

---

## Lenguaje

TypeScript

Se utilizará TypeScript en todo el backend.

---

# 5. Frontend

## Framework

React

### Motivo

* Ecosistema maduro.
* Gran comunidad.
* Excelente integración con APIs REST.
* Amplia disponibilidad de librerías.

---

## Estilos

Bootstrap (MVP)

La elección de Bootstrap busca acelerar el desarrollo del producto inicial.

Podrá evaluarse otro enfoque en futuras versiones.

---

# 6. Base de Datos

## Motor

PostgreSQL

### Motivo

* Código abierto.
* Alto rendimiento.
* Escalable.
* Compatible con Prisma.
* Amplio soporte en proveedores cloud.

---

## ORM

Prisma

### Motivo

* Tipado fuerte.
* Migraciones.
* Excelente experiencia de desarrollo.
* Integración con TypeScript.

---

# 7. Infraestructura

## Desarrollo

PostgreSQL Local

Cada desarrollador podrá ejecutar la base de datos en su equipo mediante Docker o instalación local.

---

## MVP

Proveedor recomendado:

Supabase

Supabase será utilizado únicamente como proveedor administrado de PostgreSQL.

La lógica del negocio permanecerá completamente en la API.

---

## Frontend

Proveedor recomendado:

Vercel

---

## Backend

Proveedor recomendado:

Render

---

# 8. Desarrollo

## Editor recomendado

Visual Studio Code

---

## Control de versiones

Git

Modelo de trabajo:

GitHub Flow (MVP)

---

## Formato del código

Prettier

---

## Linter

ESLint

---

# 9. Testing

## Backend

Jest

---

## Frontend

Vitest

---

## End-to-End

Playwright

---

# 10. Calidad del Código

Se utilizarán herramientas automáticas para garantizar la calidad del código.

* ESLint.
* Prettier.
* Husky (futuro).
* lint-staged (futuro).

---

# 11. Seguridad

Las siguientes tecnologías forman parte de la estrategia de seguridad:

* JWT.
* bcrypt.
* Helmet.
* CORS.
* Validación mediante DTOs.
* Variables de entorno.

---

# 12. Herramientas Futuras

se puede evaluar algunas herramientas adicionales cuando el negocio lo requiera, previa indagación al respecto y siempre y cuando no cambie la estructura del proyecto.


---

# 13. Dependencias Prohibidas

Durante el MVP no se utilizarán tecnologías que incrementen innecesariamente la complejidad.

Ejemplos:

* Microservicios.
* Firebase como backend principal.
* Arquitecturas distribuidas.
* Dependencias exclusivas de un proveedor cloud.

---

# 14. Evolución

La tecnología podrá cambiar siempre que:

* No rompa el dominio.
* Respete la arquitectura.
* Exista una justificación documentada mediante un ADR.

La evolución tecnológica deberá responder a necesidades del producto y no únicamente a tendencias del mercado.

---

# Historial de Versiones

| Versión | Fecha      | Descripción                               |
| ------- | ---------- | ----------------------------------------- |
| 1.0.0   | Julio 2026 | Definición inicial del stack tecnológico. |
