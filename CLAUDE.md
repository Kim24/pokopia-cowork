# CLAUDE.md — Pokopia Intelligence Lab

> Este archivo es el contexto y contrato persistente del proyecto para cualquier sesión de Claude que trabaje sobre este repositorio. No reemplaza el juicio humano; establece reglas que deben respetarse salvo autorización explícita del usuario.

---

## 1. Identidad del proyecto

- **Nombre:** Pokopia Intelligence Lab
- **Repositorio:** `pokopia-cowork`
- **Objetivo:** construir una capa de conocimiento / domain intelligence sobre *Pokémon Pokopia*, y posteriormente comparar un sistema basado en conocimiento/agente contra un baseline RAG.
- **Roadmap:**
  - Fase 1 → Research + Consolidación del conocimiento
  - Fase 1.5 → Knowledge Hardening / Gap Resolution
  - Fase 2 → Gold Dataset + representación técnica
  - Fases posteriores → Researcher / Knowledge Layer / Agent y experimento RAG vs Agent

---

## 2. Estado histórico (Fase 1)

Fase 1 está **cerrada como baseline**.

Artefactos principales de Fase 1:

- `sources/sources.json`
- `domain-map/*`
- `entities/*`
- `concepts/glossary.json`
- `relationships/relationships.json`
- `rules/rules.json`
- `contradictions/contradictions.json`
- `knowledge-gaps/gaps.md`
- `candidate-questions/questions.md`
- `research-notes.md`
- `phase1-consolidation-report.md`
- `pokemon-catalog.md`

La Fase 1 documentó el conocimiento consolidado y reconoció limitaciones metodológicas. Principales limitaciones de Fase 1:

- search log incompleto/inexistente;
- queries y búsquedas fallidas no registradas;
- cobertura multilingüe no demostrada;
- provenance claim-level insuficiente;
- dependencia temporal/versionado incompleto;
- corroboración no siempre independiente;
- reproducibilidad parcial;
- actualizabilidad claim-level limitada.

**Estas limitaciones NO deben interpretarse como prueba de que la investigación histórica fue incorrecta.** Significan que el repositorio no permite reconstruir completamente el proceso.

---

## 3. Fase 1.5 — Knowledge Hardening

Principio: **no rehacer toda Fase 1**. Fortalecer conocimiento donde existen gaps, UNKNOWN, contradicciones o claims débiles.

**Primer caso:** C05.

**Proceso aplicado:**

1. Blind Research.
2. Adversarial Verification.
3. Human-in-the-Loop.
4. Knowledge update.
5. Generalización de aprendizajes.
6. Post-implementation audit.

---

## 4. Protocolo anti-confirmation-bias (obligatorio)

- No aceptar una evidencia porque fue proporcionada por el usuario.
- No asumir que una evidencia candidata es correcta.
- No orientar una búsqueda para confirmar una hipótesis previa.

Cuando exista nueva evidencia:

1. tratarla inicialmente como *Candidate Evidence*;
2. investigar el claim desde cero cuando sea posible;
3. buscar evidencia a favor y en contra;
4. evaluar independencia entre fuentes;
5. evaluar temporalidad y versión;
6. realizar revisión adversarial;
7. solo después hacer Human-in-the-Loop.

Distinguir siempre:

- "la evidencia demuestra X" **de**
- "la evidencia es consistente con X"

No convertir ausencia de evidencia en evidencia de ausencia. No resolver UNKNOWN sin evidencia suficiente. No aceptar una conclusión solamente porque una fuente de mayor reputación la afirma.

---

## 5. Lecciones metodológicas de C05

C05 mostró que un claim aparentemente único puede requerir:

- versionado;
- subclaims;
- estados epistémicos separados;
- provenance;
- análisis de dependencia entre fuentes;
- distinción entre evidencia primaria y derivada;
- separación entre información histórica y actual.

Estos aprendizajes deben generalizarse **solo** cuando exista evidencia de que el mismo patrón aparece en otros elementos del corpus. No aplicar automáticamente una estructura de C05 a todo el conocimiento.

---

## 6. Estado de C05

C05 está actualmente: **PARTIALLY_CONFIRMED**.

Representación actual:

- Lanzamiento / 1.0.x: 64 generadores / 512 ítems
- 1.1.0–1.1.1: 64 generadores / 1.024 ítems
- 2.0.0+: 128 generadores / 1.024 ítems

La semántica exacta de "excluding furnaces" permanece **UNKNOWN**. El supuesto límite de 256 transmisores permanece **UNKNOWN**. C05 debe considerarse *version-dependent*.

---

## 7. C11

Existe C11 como contradicción adicional: **output del Furnace: 30 vs 15–25**. Su estado permanece **UNKNOWN**. No asumir ninguna resolución.

---

## 8. Q13

Q13 depende de C05 y ahora tiene una nota explícita de versión (`version_note`). No convertir Q13 en una pregunta Gold ni introducir respuestas Gold implícitas sin HITL posterior.

---

## 9. Gold Dataset

Todavía **NO** está construido. Human-in-the-Loop es obligatorio:

- DeepSeek/Claude = propuesta o auditoría
- Humano = decisión final
- Gold Dataset = resultado validado

Nunca convertir automáticamente una clasificación de modelo en Gold.

---

## 10. Git

**Regla general:** NO hacer commit, push, PR, merge ni cambios de rama salvo autorización explícita.

Antes de modificaciones importantes:

- inspeccionar estado Git;
- revisar diff;
- mantener trazabilidad.

Antes de publicar:

- revisar cambios;
- verificar consistencia;
- mantener cambios pequeños y explicables.

### Archivo protegido

`git_github_guia_pokopia.md` es un archivo **untracked preexistente**. NO:

- abrirlo para modificarlo;
- editarlo;
- eliminarlo;
- moverlo;
- renombrarlo;
- agregarlo a Git;
- incluirlo en commits;
- cambiar su contenido;

salvo autorización explícita del usuario.

---

## 11. Estado actual del workspace

El workspace contiene cambios locales de Fase 1.5 aún no publicados. No asumir que GitHub refleja este estado. **La copia local es la fuente de verdad de trabajo actual.** Antes de cualquier publicación a GitHub debe revisarse el diff local.

---

## 12. Seguridad metodológica

No modificar archivos solamente para hacerlos más uniformes. Toda modificación debe responder a una de estas razones:

- nueva evidencia;
- corrección de inconsistencia demostrada;
- impacto directo de una actualización;
- mejora metodológica explícitamente justificada.

Si una recomendación todavía no tiene suficiente evidencia:

- documentarla;
- no implementarla.

---

## 13. Comportamiento esperado

Cuando recibas una tarea:

1. identifica qué parte es investigación, qué parte es decisión y qué parte es implementación;
2. no mezcles descubrimiento de evidencia con aceptación de evidencia;
3. separa hechos, inferencias y UNKNOWN;
4. explica impactos antes de cambios grandes;
5. no hagas cambios fuera del alcance solicitado;
6. conserva trazabilidad.

No borres información histórica simplemente porque exista una versión más nueva. Cuando una actualización supersede una afirmación anterior, conservar la información histórica cuando sea relevante.

---

## 14. Estado específico de la migración

Este proyecto está migrando de un flujo anterior basado en OpenCode/DeepSeek a Claude. Los aprendizajes metodológicos del flujo anterior deben conservarse. No asumir que Claude tiene acceso a conversaciones previas fuera de este repositorio. **El repositorio y este `CLAUDE.md` deben ser la base persistente del contexto.**
