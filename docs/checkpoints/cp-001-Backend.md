# CHECKPOINT.md

# Planificash

**Versión:** 1.0.0  
**Fecha:** Julio 2026  
**Estado:** Entorno de Desarrollo Completamente Configurado  
**Checkpoint:** CP-002 - Preparación del Backend Finalizada

---

# 1. Estado General

La fase de preparación del entorno de desarrollo ha sido completada exitosamente.

El proyecto ya cuenta con una base sólida para comenzar el desarrollo del dominio del negocio.

A partir del siguiente checkpoint comenzará la construcción de los primeros módulos de la aplicación.

---

# 2. Backend

## Finalizado

### Proyecto

- ✅ NestJS 11 instalado.
- ✅ Proyecto ubicado en `backend/`.
- ✅ Estructura del framework comprendida.

---

### Arquitectura comprendida

Se estudió el flujo completo de una petición HTTP:

Cliente

↓

main.ts

↓

AppModule

↓

Controller

↓

Service

↓

(Repositorio / Base de datos en el futuro)

↓

Controller

↓

Cliente

---

### Conceptos dominados

- Responsabilidad de `main.ts`.
- Responsabilidad de `AppModule`.
- Responsabilidad de los Controllers.
- Responsabilidad de los Services.
- Arquitectura Modular de NestJS.
- Flujo completo de una petición.

---

# 3. Calidad del Código

## ESLint

Configurado y comprendido.

Se decidió permitir temporalmente el uso de `any` durante el aprendizaje del MVP.

---

## Prettier

Configuración adoptada:

```json
{
  "singleQuote": true,
  "trailingComma": "all",
  "semi": true,
  "printWidth": 100
}
```

---

## VS Code

Configurado para:

- Formatear automáticamente.
- Ejecutar ESLint al guardar.
- Mantener un estilo consistente.

---

# 4. Variables de Entorno

Configurado:

- ✅ `.env`
- ✅ `.env.example`
- ✅ `.gitignore`
- ✅ `@nestjs/config`
- ✅ `ConfigModule`
- ✅ `ConfigService`

---

# 5. Conceptos Aprendidos

Durante esta fase se comprendieron:

## Variables de entorno

- Qué son.
- Para qué sirven.
- Por qué nunca deben almacenarse en el código.
- Diferencia entre `.env` y `.env.example`.

---

## ConfigModule

Se comprendió que:

- Es el responsable de cargar el archivo `.env`.
- Debe inicializarse una única vez.
- Se configuró como módulo global (`isGlobal: true`).

---

## ConfigService

Se aprendió:

- Inyección mediante el constructor.
- Lectura de variables de entorno.
- Uso de `get()`.
- Uso de genéricos (`get<string>()`).

---

## Inyección de Dependencias (Dependency Injection)

Concepto comprendido:

Los objetos no deben crearse manualmente.

NestJS utiliza un contenedor de dependencias que suministra automáticamente las instancias necesarias.

Frase acordada:

> "Los Controllers coordinan. Los Services resuelven el negocio. El contenedor entrega las dependencias."

---

# 6. Git

Durante esta fase se detectó un problema importante.

## Problema encontrado

Existían dos repositorios Git:

```

Planificash/
│
├── .git
└── backend/
└── .git

```

Esto provocaba trabajar sobre ramas distintas (`main` y `master`).

---

## Solución

Se eliminó el repositorio Git interno de `backend`.

El proyecto quedó con una única estructura:

```

Planificash/
│
├── .git
├── docs/
├── backend/
└── frontend/

```

A partir de este momento todo el proyecto comparte:

- un único historial
- una única rama principal
- una única estrategia de ramas

---

# 7. Estrategia Git Adoptada

Se acordó trabajar bajo un flujo simplificado inspirado en Git Flow.

```

main

↓

develop

↓

feature/\*

```

Reglas:

- Nunca desarrollar directamente sobre `main`.
- Crear una rama `feature/*` por funcionalidad.
- Integrar en `develop`.
- Fusionar en `main` únicamente versiones estables.

---

# 8. Convención de Commits

Se utilizarán Conventional Commits.

Ejemplos:

```

feat(users): create users module

fix(auth): validate jwt expiration

docs: update architecture

refactor(database): simplify repository

chore: configure development environment

```

---

# 9. Estado del Roadmap

## Fase 0

- ✅ Documentación

---

## Fase 1

Preparación del entorno

- ✅ Proyecto NestJS
- ✅ Comprender estructura
- ✅ Main
- ✅ Module
- ✅ Controller
- ✅ Service
- ✅ ESLint
- ✅ Prettier
- ✅ VS Code
- ✅ Variables de entorno
- ✅ ConfigModule
- ✅ ConfigService
- ✅ Inyección de dependencias

**Estado:** COMPLETADA

---

# 10. Próxima Fase

Fase 2

Arquitectura del dominio.

Próximas tareas:


- ⬜ Crear rama `develop`.
- ⬜ Crear `UsersModule`.
- ⬜ Comprender el código generado por el CLI de NestJS.
- ⬜ Diseñar la arquitectura del módulo de usuarios.

---

# 11. Forma de Trabajo

Se mantiene la metodología acordada.

Para cada tema:

1. Comprender el concepto.
2. Justificar la decisión técnica.
3. Implementar.
4. Realizar revisión de código.
5. Continuar.

No avanzar sin comprender el paso anterior.

---

# 12. Estado General

La infraestructura base del proyecto se considera terminada.

