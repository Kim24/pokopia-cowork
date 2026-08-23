# learning-log/ — Índice cronológico

## Rol de esta carpeta

`learning-log/` registra eventos discretos del propio proceso de investigación: experimentos, errores, decisiones, cambios metodológicos y validaciones. Es la capa histórica del proyecto — a diferencia de `methodology/` (el estado actual del método) o `pokopia-research/` (el estado actual del conocimiento sobre Pokopia), aquí nada se sobrescribe: una entrada, una vez creada, no se reescribe para reflejar aprendizajes posteriores; si algo cambia, se añade una entrada nueva que referencia a la anterior.

Cada entrada distingue explícitamente dos campos que no deben mezclarse:

- **`source`** → el origen documental *interno del proyecto* del aprendizaje (p. ej. una sección de `research-notes.md`). Es dónde se registró que esto pasó, no la prueba de que sea cierto.
- **`evidence`** → la evidencia que sustenta la afirmación o el aprendizaje en sí, clasificada como primaria del dominio, secundaria/derivada, o documentación interna del proyecto (ver `../methodology/evidence-and-claims.md`).

Un documento interno del proyecto (como `research-notes.md`) puede aparecer en `source`, pero llamarlo "evidencia primaria" solo porque es un documento no es correcto — la evidencia primaria es la que proviene del propio objeto de estudio (o de quien lo controla oficialmente), no la nota que describe el proceso de investigación.

## Índice

| ID | Fecha | Título | Fase | Categoría | Status | Entrada |
|---|---|---|---|---|---|---|
| LL-0001 | 2026-08-15 | Hardening de C05 (límites eléctricos) y defecto de implementación sobre C10 | Fase 1.5 | experiment / methodological-change | DOCUMENTED | [`entries/LL-0001-c05-electric-limits-hardening.md`](entries/LL-0001-c05-electric-limits-hardening.md) |

## Categorías (vocabulario)

- **experiment** — se ejecutó un proceso de investigación/verificación sobre un claim existente o candidato.
- **error** — se detectó un defecto (de investigación o de implementación) en un artefacto o en el propio proceso.
- **decision** — se tomó una decisión de alcance (qué hacer con un hallazgo), sin que medie necesariamente un experimento nuevo.
- **methodological-change** — el evento motivó un cambio en `methodology/`.
- **validation** — se verificó (auditó) el estado real de un artefacto contra lo que la documentación afirmaba.

Una entrada puede pertenecer a más de una categoría; la columna "Categoría" de este índice muestra las principales, y el campo `tags` de cada entrada lleva el detalle completo.

## Por qué no hay entradas de Fase 1

Fase 1 (previa a Fase 1.5) no cuenta con un registro de proceso con el nivel de detalle necesario para reformatearse como entrada de `learning-log/` sin fabricar narrativa. El propio `pokopia-research/research-notes.md` y `pokopia-research/phase1-consolidation-report.md` documentan explícitamente esta limitación (search log incompleto, queries fallidas no registradas, etc.). En vez de reconstruir retrospectivamente un proceso que no quedó anotado, este índice deja Fase 1 sin entradas y remite a esos dos documentos como el registro honesto de sus propios límites. Esto es una aplicación directa del principio: no reconstruir procesos no documentados presentándolos como si lo estuvieran.

## Mantenimiento
Ver `../CLAUDE.md` y `../methodology/README.md` para las reglas de cuándo se crea una entrada nueva, cuándo eso motiva un cambio en `methodology/`, y cuándo motiva un cambio en `../CLAUDE.md`.
