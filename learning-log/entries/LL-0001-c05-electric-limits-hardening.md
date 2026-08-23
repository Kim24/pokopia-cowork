---
id: LL-0001
date: 2026-08-15
phase: "Fase 1.5"
title: "Hardening de C05 (límites eléctricos) y defecto de implementación sobre C10"
status: DOCUMENTED
source: "pokopia-research/research-notes.md §15 (\"Fase 1.5 — Knowledge Hardening (C05) y generalización\")"
evidence:
  - type: primary (dominio)
    description: "Notas oficiales de parche citadas en research-notes.md §15 (referenciadas en el proyecto como SRC070/SRC071), consultadas mediante fetch directo el 2026-08-15."
  - type: secondary/derived (dominio)
    description: ">12 medios que citaron el mismo cambio de límites, identificados en research-notes.md §15 como reproducciones de la misma nota oficial — no como corroboración independiente."
  - type: internal (proyecto)
    description: "Comparación directa entre 'git show HEAD:pokopia-research/contradictions/contradictions.json' y la copia de trabajo, realizada en sesión de auditoría posterior (2026-08-23) — sustenta específicamente el hallazgo sobre C10 (ver 'Error / fallo metodológico')."
tags: [experiment, methodological-change, error, validation, versioning, subclaims, source-independence, adversarial-verification, hitl, propagation-analysis]
---

## Experimento
Fortalecer ("hardening") el claim C05 sobre los límites del sistema eléctrico de Pokopia, aplicando blind research y verificación adversarial, y evaluar si el patrón resultante debía propagarse a otras partes del corpus de conocimiento. Resumen; el relato completo está en `pokopia-research/research-notes.md` §15 — esta entrada no lo reproduce íntegramente.

## Problema observado
C05 llevaba desde Fase 1 en estado `UNKNOWN`, sustentado en guías secundarias con cifras dispares, sin verificación contra una fuente oficial y sin considerar que el objeto de estudio (el juego) podía haber cambiado de comportamiento entre versiones/actualizaciones.

## Hipótesis
Según se relata en `research-notes.md` §15: los límites eléctricos podían ser *version-dependent* (distintos según la versión del juego) en vez de un único valor correcto en disputa entre fuentes.

## Acción
Según `research-notes.md` §15:
1. Blind research: se reconstruyó una línea temporal de versiones sin partir de la conclusión de Fase 1.
2. Verificación adversarial: fetch directo a fuente(s) oficial(es) el 2026-08-15, buscando confirmar o refutar el versionado.
3. Evaluación de independencia: se determinó que los >12 medios que citaban el cambio de límites derivaban todos de la misma nota oficial (dependencia, no corroboración independiente).
4. HITL: el cambio de estado de C05 y el registro del nuevo candidate evidence (posteriormente C11) quedaron pendientes de revisión humana antes de darse por definitivos — la propia sección cierra con "Sin commits ni push".
5. Propagation analysis: se aplicó un criterio P0/P1/P2 para decidir a qué otros artefactos extender el aprendizaje, evitando aplicar la estructura de C05 al resto del corpus sin evidencia de que el mismo patrón existiera ahí.

## Resultado
Según `research-notes.md` §15:
- C05 pasó de `UNKNOWN` a confirmación parcial, descompuesto en subclaims segmentados por versión, dejando explícitamente `UNKNOWN` las partes no resueltas por la verificación adversarial.
- Se detectó una segunda discrepancia no relacionada con el versionado (posteriormente registrada como C11), quedando como `UNKNOWN` nuevo en vez de resolverse por inferencia.
- El aprendizaje se propagó de forma selectiva (P0/P1/P2) a los artefactos con evidencia relacionada, sin tocar artefactos sin evidencia de que el mismo patrón aplicara ahí.

## Error / fallo metodológico
Dos hallazgos de proveniencia distinta, que esta entrada mantiene separados deliberadamente:

**(a) Documentado contemporáneamente en `research-notes.md` §15:** el propio texto no declara ningún error o fallo en el proceso de hardening de C05; se presenta como cierre exitoso de esa fase de trabajo.

**(b) No documentado en `research-notes.md`; detectado en sesión de auditoría posterior (2026-08-23), evidencia = comparación directa de git (ver campo `evidence` arriba):** `research-notes.md` §15 afirma explícitamente que la contradicción C10 (preexistente, sin relación con C05) "no fue tocada" durante Fase 1.5. La comparación contra el commit `HEAD` mostró que, en realidad, el objeto JSON de C10 en `pokopia-research/contradictions/contradictions.json` había sido **reemplazado en el mismo lugar del arreglo** por el nuevo objeto C11, en vez de añadirse C11 como elemento adicional. La afirmación de "no tocado" no se correspondía con el estado real del archivo. Es un defecto de implementación (edición manual/asistida al insertar C11), no un error de investigación de dominio.

Nota de status: el hallazgo (b) se marca aquí como parte de una entrada `DOCUMENTED` porque está respaldado por evidencia directa y verificable (el propio historial de git), no porque estuviera anticipado por ningún artefacto interno previo al momento de esta auditoría. No se marca como `RECONSTRUCTED` porque no hubo que inferir ni suponer contenido: el commit `HEAD` es la evidencia directa del estado anterior.

## Decisión
- C05: aceptar la confirmación parcial versionada, manteniendo explícitos los `UNKNOWN` residuales en vez de forzar una resolución.
- C11: registrar como contradicción nueva en `UNKNOWN`, sin resolución automática.
- C10: restaurar el objeto exactamente desde `HEAD` (sin reconstruir su contenido de memoria), verificar identidad byte a byte contra el commit, y dejar C11 como elemento adicional distinto en el arreglo.

## Aprendizaje
1. Un claim aparentemente único puede estar formado por subclaims con distinto estado epistémico y distinta validez temporal; forzarlos a una sola resolución oculta incertidumbre real.
2. Múltiples fuentes que citan la misma nota oficial no constituyen corroboración independiente entre sí.
3. Una afirmación de "no tocado" dentro de un registro de proceso no sustituye la verificación del artefacto real: debe contrastarse contra el control de versiones, no solo confiarse en la narrativa del propio proceso.
4. La propagación de un aprendizaje debe ser selectiva y basada en evidencia, nunca automática ni por uniformidad.

## Cambio metodológico derivado
El componente C05 de este episodio es el origen documentado de los principios generales recogidos en:
- `methodology/evidence-and-claims.md` — criterio de descomposición en subclaims y de versionado/validez temporal.
- `methodology/source-and-corroboration.md` — criterio de independencia vs. derivación entre fuentes.
- `methodology/research-protocol.md` — las etapas de blind research, adversarial verification, HITL y propagation analysis del ciclo general.

El componente C10 (defecto de implementación) no originó una regla metodológica nueva en esta iteración; queda registrado aquí como caso de auditoría, y como recordatorio operativo del principio ya presente en `../../CLAUDE.md` de verificar el diff real antes de dar por válida una afirmación de "no tocado".

## Impacto en el proyecto
- `pokopia-research/contradictions/contradictions.json`: C05 reescrito (versionado); C11 añadido; C10 restaurado a su estado previo a Fase 1.5 tras haber sido sobrescrito por error.
- `pokopia-research/rules/rules.json`: RULE019 reescrita como regla versionada; RULE020 recibió una nota aclaratoria relacionada.
- `pokopia-research/candidate-questions/questions.md`: Q13 recibió una nota de versión explícita (`version_note`).
- `pokopia-research/sources/sources.json`: dos fuentes oficiales nuevas incorporadas; nueve entradas existentes marcadas con `aggregation_note` para evitar doble conteo de corroboración.
- `pokopia-research/knowledge-gaps/gaps.md`, `pokopia-research/domain-map/domains.md`, `pokopia-research/domain-map/relationships.md`, `pokopia-research/relationships/relationships.json`, `pokopia-research/concepts/glossary.json`, `pokopia-research/README.md` y `README.md` (raíz): propagación documentada en `research-notes.md` §15.

## Aplicabilidad a otros dominios
El patrón "claim único con subclaims versionados, corroboración aparente pero derivada de una sola fuente" es genérico a cualquier dominio donde el objeto de estudio cambie de versión con el tiempo (software, juegos con parches, normativa, productos con revisiones sucesivas). El criterio de verificar el estado real del artefacto (vía control de versiones) en vez de confiar en la narrativa del propio proceso de investigación es aplicable a cualquier proyecto que use un sistema de versiones como fuente de verdad, independientemente del dominio.
