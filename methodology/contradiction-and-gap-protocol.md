# Contradiction & Knowledge Gap Protocol

> Parte de `methodology/` — ver `README.md` para el rol de esta carpeta y su relación con `learning-log/`.
> Este archivo define el *procedimiento* general. No enumera contradicciones ni gaps concretos de Pokopia — esos viven en `pokopia-research/contradictions/contradictions.json` y `pokopia-research/knowledge-gaps/gaps.md`.

## Contradiction
Una **contradicción** existe cuando dos o más claims mutuamente incompatibles cuentan, cada uno, con evidencia propia que los respalda. No es una contradicción si una de las dos afirmaciones carece por completo de evidencia — en ese caso se trata simplemente de un claim débil o descartable, no de una contradicción formal.

## Knowledge Gap
Un **knowledge gap** existe cuando, para una pregunta dada, ninguna fuente disponible aporta evidencia suficiente para afirmar nada — no hay dos lados en disputa, simplemente falta información. Un gap se registra explícitamente en vez de dejarse implícito, y en vez de completarse con una suposición razonable no verificada.

## Cómo distinguirlos
La pregunta clave es si existen dos (o más) afirmaciones específicas con evidencia propia enfrentadas (→ contradicción) o si simplemente no hay afirmación verificable disponible (→ gap). Un gap puede convertirse en contradicción si aparece evidencia nueva que introduce una segunda afirmación en disputa; una contradicción no se reclasifica como gap solo porque sea difícil de resolver.

## Registro de UNKNOWN
Cuando la evidencia disponible —para una contradicción o para un gap— no permite decidir, el estado se registra explícitamente como **UNKNOWN**, junto con la razón concreta de por qué no se pudo decidir (evidencia insuficiente, fuente inaccesible, evidencia contradictoria sin forma de arbitrar, ambigüedad de redacción en la fuente, etc.). Un UNKNOWN sin razón registrada es una forma más débil de documentación que un UNKNOWN con razón explícita, y debe mejorarse cuando sea posible.

**Prohibición explícita:** la ausencia de evidencia sobre X nunca se trata como evidencia de que no-X. Mantener UNKNOWN es preferible a forzar una resolución sin sustento.

## Estados de resolución
Vocabulario mínimo de estados para una contradicción, de menor a mayor certeza:

- **UNKNOWN**: sin evidencia suficiente para decidir.
- **PARTIALLY_CONFIRMED**: parte de la afirmación original se confirma bajo condiciones específicas (p. ej. una ventana temporal o versión), mientras otras partes (subclaims) permanecen sin resolver. Requiere haber aplicado la descomposición en subclaims (ver `evidence-and-claims.md`).
- **RESOLVED_FAVORING_X**: la evidencia respalda claramente una de las afirmaciones en disputa por encima de la otra, con un motivo explícito de por qué la afirmación alternativa se descarta (no simplemente se ignora).
- **RESOLVED_WITH_CRITERIA**: ambas afirmaciones en disputa resultan ciertas bajo criterios de alcance distintos (no es que una esté equivocada, sino que miden o incluyen cosas distintas).
- **RESOLVED**: la evidencia es suficiente y no queda ambigüedad relevante sobre ningún subclaim conocido.

## Evidencia mínima para resolver
Ninguna contradicción se resuelve (en cualquier dirección) sin al menos: identificar las fuentes en conflicto, evaluar su independencia (ver `source-and-corroboration.md`), y —cuando sea posible— intentar una verificación adversarial antes de aceptar la resolución. Resolver sin este mínimo es indistinguible de adivinar.

## Resolución parcial y explicación por temporalidad/versión
Una aparente contradicción puede en realidad ser dos afirmaciones distintas, cada una cierta en un momento o versión distinta del objeto de estudio ("version drift"), en vez de un error de alguna de las fuentes. Cuando esto se sospecha, el protocolo correcto es: (a) reconstruir la línea temporal/de versiones, (b) verificar cada tramo con evidencia propia, y (c) representar el resultado como subclaims versionados en vez de forzar un único valor. Este patrón fue documentado como caso real — ver `learning-log/entries/LL-0001-c05-electric-limits-hardening.md`.

## Mantenimiento de este archivo
Se actualiza cuando una entrada de `learning-log/` revela un caso de contradicción o gap que el protocolo actual no cubre bien. Todo cambio sustantivo debe citar la entrada que lo motivó, cuando exista.
