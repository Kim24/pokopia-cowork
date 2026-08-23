# methodology/ — Índice del método

## Rol de esta carpeta

`methodology/` documenta el **estado actual** del método general de investigación y validación de conocimiento usado en Pokopia Intelligence Lab.

No es un registro histórico ni un documento fijo: es **normativo/procedimental** (dice cómo se debe investigar y validar hoy), **independiente del dominio** (no contiene hechos sobre Pokémon Pokopia; podría copiarse a un proyecto sobre cualquier otro dominio sin cambiar una palabra), y **evolutivo** — el método puede y debe cambiar a medida que se aprende. Lo que no hace esta carpeta es narrar *cómo* llegó a su forma actual: esa historia — los experimentos, errores y decisiones que motivaron cada regla — vive en [`../learning-log/`](../learning-log/README.md).

Regla de trazabilidad: cuando un principio de este directorio nació o cambió a raíz de un evento documentado, el archivo correspondiente lo indica con una referencia explícita a la entrada de `learning-log/` que lo originó. Si no existe esa referencia en un principio dado, es porque su origen no está documentado como evento discreto (p. ej. es una convención que ya existía en Fase 1) — no se inventa una genealogía donde no hay evidencia de ella.

## Mapa de cobertura

| Concepto | Vive en | Se aplica actualmente en (artefacto) | Genealogía documentada |
|---|---|---|---|
| Research protocol (ciclo general) | `research-protocol.md` | `pokopia-research/research-notes.md` (bitácora de ejecución) | Etapas de blind research / adversarial verification / HITL / propagation analysis: primera instancia documentada en el proyecto vía `learning-log/entries/LL-0001-c05-electric-limits-hardening.md` |
| Evidence model (estados epistémicos) | `evidence-and-claims.md` | Campo `status` en `pokopia-research/rules/rules.json` | Sin origen de evento único documentado (uso ya presente desde Fase 1) |
| Claim model | `evidence-and-claims.md` | Estructura de objetos en `pokopia-research/contradictions/contradictions.json` | — |
| Subclaims (descomposición de claims) | `evidence-and-claims.md` | `pokopia-research/contradictions/contradictions.json`, `pokopia-research/rules/rules.json` | `learning-log/entries/LL-0001-c05-electric-limits-hardening.md` |
| Provenance | `evidence-and-claims.md` | Esquema de `pokopia-research/sources/sources.json` | — |
| Versioning / temporal validity | `evidence-and-claims.md` | Campo `applicable_versions` en `pokopia-research/rules/rules.json`; nota de versión en `pokopia-research/candidate-questions/questions.md` | `learning-log/entries/LL-0001-c05-electric-limits-hardening.md` |
| Contradiction handling | `contradiction-and-gap-protocol.md` | `pokopia-research/contradictions/contradictions.json` | Sin origen de evento único documentado; el patrón específico "resolución explicada por versionado" sí referencia `LL-0001` |
| Knowledge gaps | `contradiction-and-gap-protocol.md` | `pokopia-research/knowledge-gaps/gaps.md` | — |
| Source evaluation | `source-and-corroboration.md` | Campos `source_type`/`confidence` en `pokopia-research/sources/sources.json` | — |
| Corroboration / source independence | `source-and-corroboration.md` | Campo `aggregation_note` en `pokopia-research/sources/sources.json` | `learning-log/entries/LL-0001-c05-electric-limits-hardening.md` |
| Blind research | `research-protocol.md` | Proceso de investigación, no un artefacto de datos | `learning-log/entries/LL-0001-c05-electric-limits-hardening.md` |
| Adversarial verification | `research-protocol.md` | Ídem | `learning-log/entries/LL-0001-c05-electric-limits-hardening.md` |
| HITL | `research-protocol.md` | Ídem; también normado en `CLAUDE.md` §9-10 | `learning-log/entries/LL-0001-c05-electric-limits-hardening.md` |
| Anti-confirmation-bias | `source-and-corroboration.md` | Ídem; mandato corto en `CLAUDE.md` §4 | — |
| Update / propagation analysis | `research-protocol.md` | Criterio P0/P1/P2 aplicado en `pokopia-research/research-notes.md` §15 | `learning-log/entries/LL-0001-c05-electric-limits-hardening.md` |
| Reproducibility | `reproducibility.md` | Aún sin aplicación fuera de Pokopia | — |

## Qué NO contiene esta carpeta

Ningún hecho específico del dominio Pokopia: sin cifras de generadores, sin identificadores de contradicciones (C01…C11), sin identificadores de reglas (RULE0xx) o de fuentes (SRC0xx), sin nombres de Pokémon, áreas o mecánicas del juego. Cuando un principio necesita un ejemplo concreto, este directorio referencia la entrada correspondiente de `learning-log/` en vez de embeber el ejemplo aquí.
