# Specifications (SPEC)

## Objetivo

La carpeta **specs/** contiene las especificaciones funcionales del proyecto Planificash.

Una **Specification (SPEC)** describe de forma precisa una funcionalidad antes de que sea implementada.

Su propósito es garantizar que todas las funcionalidades:

- Sean comprendidas por todo el equipo.
- Respondan a una necesidad del negocio.
- Sean implementadas de forma consistente.
- Puedan ser validadas mediante criterios objetivos.
- Sirvan como fuente de verdad durante el desarrollo.

Ninguna funcionalidad deberá implementarse sin una SPEC aprobada.

---

# Flujo de trabajo

Toda nueva funcionalidad seguirá el siguiente proceso:

Idea

↓

Discusión

↓

Epic

↓

User Story

↓

SPEC

↓

Revisión

↓

Aprobación

↓

Implementación

↓

Testing

↓

Documentación

Cada etapa debe completarse antes de avanzar a la siguiente.

---

# Organización

La carpeta **specs/** se organiza por funcionalidades del negocio.

Ejemplo:

specs/

authentication/

login/

spec.md

register/

spec.md

movements/

create/

spec.md

update/

spec.md

dashboard/

overview/

spec.md

Cada carpeta representa una funcionalidad independiente.

---

# Relación con otros documentos

Las SPEC no son documentos aislados.

Cada SPEC debe estar alineada con:

- Vision.md
- Domain.md
- Architecture.md
- Technology.md
- docs/specs/quality-ux.md
- ADR relacionados

Si existe alguna contradicción entre la SPEC y estos documentos, deberá resolverse antes de iniciar la implementación.

---

# Contenido mínimo de una SPEC

Toda SPEC deberá incluir como mínimo:

- Objetivo
- Contexto
- Alcance
- Requisitos funcionales
- Requisitos no funcionales
- Reglas de negocio
- Casos de uso
- Criterios de aceptación
- Riesgos
- Dependencias
- Estrategia de pruebas

Se recomienda utilizar siempre la plantilla oficial del proyecto.

templates/SPEC_TEMPLATE.md

---

# Reglas

Una SPEC:

Debe describir el comportamiento esperado.

No debe describir la implementación.

No debe contener código.

No debe depender de tecnologías específicas.

Debe estar escrita utilizando el Lenguaje Ubicuo definido en Domain.md.

---

# Criterios de calidad

Antes de aprobar una SPEC se deberá verificar que:

- Existe una necesidad del negocio.
- El objetivo es claro.
- El alcance está definido.
- Los criterios de aceptación son verificables.
- Las reglas de negocio son completas.
- No existen ambigüedades.
- Se identificaron riesgos.
- Existe una estrategia de pruebas.

---

# Responsabilidades

Product Owner

- Define la necesidad del negocio.
- Valida el alcance.

Software Architect

- Revisa la coherencia con la arquitectura.

Development Team

- Evalúa la viabilidad técnica.
- Propone mejoras.

QA

- Define la estrategia de validación.

Agentes IA

- Pueden colaborar en la creación y revisión de SPEC.
- Nunca deben aprobar una SPEC por sí mismos.

---

# Estados de una SPEC

Toda SPEC deberá tener uno de los siguientes estados:

Draft

La funcionalidad está siendo definida.

Review

La funcionalidad está en revisión.

Approved

Puede comenzar la implementación.

Implemented

La funcionalidad fue desarrollada.

Deprecated

La funcionalidad dejó de utilizarse.

---

# Trazabilidad

Toda SPEC deberá poder responder las siguientes preguntas:

¿Por qué existe?

→ Vision.md

¿Qué representa?

→ Domain.md

¿Cómo se integra?

→ Architecture.md

¿Con qué tecnologías se implementará?

→ Technology.md

¿Qué decisiones afectan esta funcionalidad?

→ ADR

¿Qué historia de usuario implementa?

→ User Story

¿Qué Epic pertenece?

→ Epic

---

# Convenciones

- Una SPEC describe una única funcionalidad.
- El nombre debe ser claro y descriptivo.
- Se utilizará Markdown.
- El contenido funcional se redactará en español.
- Los nombres técnicos podrán mantenerse en inglés cuando sea conveniente.

---

# Evolución

Las SPEC evolucionan junto con el producto.

Toda modificación importante deberá conservar el historial correspondiente y actualizar los documentos relacionados cuando sea necesario.

Las SPEC representan el contrato funcional entre el negocio y el equipo de desarrollo.