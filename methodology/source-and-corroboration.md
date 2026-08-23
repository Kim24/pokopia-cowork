# Source Evaluation & Corroboration

> Parte de `methodology/` — ver `README.md` para el rol de esta carpeta y su relación con `learning-log/`.

## Evaluación de fuentes
Cada fuente se evalúa, como mínimo, por: tipo (oficial, wiki, guía, prensa, comunidad), autoridad del publicador sobre el objeto de estudio, especificidad (¿describe el caso exacto o algo general?), fecha de publicación y fecha de recuperación, y nivel de confianza declarado explícitamente en vez de asumido.

## Jerarquía de fuentes
De mayor a menor peso evidencial, sin que esto implique que una fuente de menor jerarquía deba descartarse, solo que su peso en la evaluación es distinto:

1. **Fuente primaria**: emitida directamente por quien controla o produce el objeto de estudio (p. ej. notas oficiales de un fabricante o desarrollador).
2. **Fuente secundaria especializada**: analiza o documenta el objeto de estudio con metodología propia, sin ser la fuente primaria (p. ej. una wiki especializada con verificación propia).
3. **Fuente agregadora/terciaria**: recopila o resume lo que otras fuentes ya dijeron, sin verificación propia adicional.
4. **Fuente única sin respaldo**: una única mención, sin corroboración de ningún tipo — se trata como *candidate evidence* débil hasta que se corrobore o se descarte.

## Independencia vs. dependencia/derivación
Dos fuentes son **independientes** cuando llegaron a la misma afirmación por vías de verificación distintas. Una fuente es **dependiente/derivada** de otra cuando simplemente reproduce, traduce o resume lo que la otra ya publicó, sin aportar verificación propia.

**Regla explícita:** un número alto de fuentes secundarias que citan o reproducen la misma fuente primaria **no constituye corroboración independiente**. Cuentan como una sola línea de evidencia, no como N líneas. Tratar reproducciones múltiples de una misma fuente como si fueran confirmaciones independientes es un sesgo de conteo que infla artificialmente la confianza en un claim. Este principio fue generalizado a partir de un caso documentado — ver `learning-log/entries/LL-0001-c05-electric-limits-hardening.md`.

## Corroboración
Un claim se considera corroborado cuando al menos dos fuentes **independientes entre sí** (no derivadas una de otra) respaldan la misma afirmación. La corroboración incrementa el estado epistémico del claim (ver `evidence-and-claims.md`); la mera repetición no lo hace.

## Candidate Evidence
Toda evidencia nueva —incluida la aportada directamente por quien solicita la investigación— se trata inicialmente como *candidate evidence*: no se acepta ni se rechaza de entrada. Debe pasar por evaluación de fuente, búsqueda de evidencia en contra, evaluación de independencia y verificación adversarial antes de poder cambiar el estado epistémico de un claim.

## Protocolo anti-confirmation-bias
Ante evidencia nueva sobre un claim existente o candidato:

1. tratarla como *candidate evidence*, nunca como conclusión;
2. investigar el claim desde cero cuando sea posible (blind research), sin partir de la conclusión previa;
3. buscar evidencia a favor **y en contra** activamente;
4. evaluar independencia entre las fuentes involucradas;
5. evaluar temporalidad/versión del objeto de estudio;
6. realizar una revisión adversarial explícita (intentar refutar, no solo confirmar);
7. solo después, someter el cambio a Human-in-the-Loop.

No se orienta la búsqueda para confirmar una hipótesis previa, no se acepta una conclusión solo porque la aporta una fuente de mayor reputación, y no se resuelve un UNKNOWN sin evidencia suficiente solo por presión de cerrarlo.

## "Consistente con X" vs. "demuestra X"
Estas dos afirmaciones no son intercambiables:

- **"La evidencia es consistente con X"**: los datos disponibles no contradicen X, pero tampoco lo prueban de forma concluyente; pueden ser igualmente consistentes con otras explicaciones.
- **"La evidencia demuestra X"**: existe verificación directa y suficiente (idealmente primaria o corroborada de forma independiente) que soporta X por encima de explicaciones alternativas.

Un claim solo debe marcarse como FACT cuando la evidencia lo demuestra, no cuando simplemente es consistente con él. La ausencia de evidencia en contra tampoco equivale a evidencia a favor: no convertir ausencia de evidencia en evidencia de ausencia.

## Mantenimiento de este archivo
Se actualiza cuando una entrada de `learning-log/` revela un patrón de evaluación de fuentes o de sesgo no cubierto aquí. Todo cambio sustantivo debe citar la entrada que lo motivó, cuando exista.
