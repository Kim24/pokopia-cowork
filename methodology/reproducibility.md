# Reproducibility — Seed / Checklist

> Parte de `methodology/` — ver `README.md` para el rol de esta carpeta y su relación con `learning-log/`.

Este archivo **no es** la guía "Cómo construir una Domain Intelligence / Knowledge Layer reproducible". Es el esqueleto/checklist de qué necesitaría cubrir esa guía cuando se escriba, y sirve mientras tanto como criterio de auto-evaluación: para cada punto, ¿el proyecto actual lo cubre de forma reutilizable, o solo de forma específica a Pokopia?

## Inputs
Qué se necesita antes de empezar a investigar un dominio nuevo: alcance de las preguntas iniciales, lista de fuentes candidatas, y una declaración explícita de qué NO se sabe todavía. *Pendiente de generalizar*: la plantilla de "pregunta inicial" no está formalizada como artefacto reutilizable todavía.

## Outputs
Qué artefactos debe producir el proceso al final de una fase: un mapa de conocimiento con proveniencia, un inventario de contradicciones, un inventario de gaps, un banco de preguntas candidatas. *Cubierto en este proyecto*: la estructura de `pokopia-research/` ya instancia este patrón (sources/domain-map/entities/relationships/rules/contradictions/knowledge-gaps/candidate-questions), y ese patrón de carpetas es en sí mismo portable a otro dominio.

## Provenance
Todo output debe ser trazable a una fuente concreta con fecha de publicación y de recuperación (ver `evidence-and-claims.md`). *Cubierto en este proyecto* como esquema de datos (`sources.json`); *pendiente de generalizar* como checklist explícito de campos obligatorios independiente del formato JSON usado aquí.

## Logs
Todo intento de investigación —incluidas las búsquedas que no dieron resultado— debería quedar registrado, no solo los hallazgos positivos. *No cubierto de forma completa*: el propio proyecto documenta como limitación conocida de Fase 1 que el registro de búsquedas fallidas es incompleto (ver `pokopia-research/research-notes.md`). Esta guía futura debería exigir explícitamente lo que Fase 1 no pudo garantizar.

## Versionado
Cuando el objeto de estudio cambia con el tiempo, el proceso debe capturar en qué versión/momento se investigó cada claim (ver `evidence-and-claims.md`). *Parcialmente cubierto*: existe el campo `applicable_versions` y la práctica de notas de versión, pero no se aplica todavía de forma universal a todo el corpus.

## Reproducibilidad (en sentido estricto)
Un tercero con acceso a las mismas fuentes debería poder llegar a una conclusión equivalente siguiendo el mismo protocolo. *Pendiente de generalizar*: esto requeriría snapshots o citas textuales por claim, no solo un enlace a la fuente (la fuente puede cambiar o desaparecer) — señalado como mejora futura no implementada en `pokopia-research/research-notes.md`.

## Trazabilidad
Cada decisión de investigación (aceptar, rechazar, mantener UNKNOWN, versionar) debe poder rastrearse hasta quién/qué la tomó y con qué evidencia. *Cubierto en este proyecto* a nivel de diseño mediante `learning-log/` (este mismo directorio); *pendiente* de aplicarse retroactivamente a todo el historial de Fase 1, lo cual el proyecto ha decidido explícitamente no hacer para evitar reconstrucción retrospectiva no evidenciada.

## HITL
El proceso debe declarar en qué puntos exactos se requiere intervención humana antes de dar un cambio por definitivo (ver `research-protocol.md`, etapa 11). *Cubierto en este proyecto* como regla (`CLAUDE.md`, `research-protocol.md`); *pendiente de generalizar* como checklist independiente de quién ejecuta el proceso (humano o modelo).

## Evaluación
Debe existir un criterio explícito para juzgar si el conocimiento producido es correcto y útil (no solo "se ve completo"). *Parcialmente cubierto*: los estados epistémicos (`evidence-and-claims.md`) cumplen esta función a nivel de claim individual; falta un criterio de evaluación a nivel de corpus completo (p. ej. cobertura, tasa de UNKNOWN, tasa de contradicciones sin resolver).

## Portability
Qué partes del método dependen de herramientas, modelos o proveedores concretos, y cuáles no. *Cubierto por diseño*: todo el contenido de `methodology/` está escrito en términos de roles y procedimientos, sin mencionar ningún modelo o proveedor concreto (ver `CLAUDE.md` §24 sobre la migración de OpenCode/DeepSeek a Claude, que motiva este requisito).

## Mantenimiento de este archivo
Se actualiza cuando se identifica un punto adicional necesario para la futura guía portable, o cuando uno de los puntos "pendientes" se resuelve y pasa a "cubierto". No se convierte en la guía completa hasta que exista una decisión explícita de escribirla.
