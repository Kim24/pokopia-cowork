# Evidence & Claims Model

> Parte de `methodology/` — ver `README.md` para el rol de esta carpeta y su relación con `learning-log/`.

## Claim
Un *claim* es una afirmación puntual sobre el dominio que puede evaluarse como verdadera, falsa o indeterminada dado un conjunto de evidencia. Un claim debe poder enunciarse en una sola oración verificable; si una afirmación mezcla varias condiciones independientes, es candidata a descomponerse (ver "Subclaims" abajo).

## Subclaim
Un *subclaim* es una parte de un claim mayor que puede tener su propio estado epistémico, su propia evidencia y su propia validez temporal, distintos de los del claim del que proviene. Un claim debe descomponerse en subclaims cuando se detecta cualquiera de estas condiciones:

- distintas partes de la afirmación están respaldadas por evidencia de calidad o independencia distintas;
- distintas partes de la afirmación son válidas en momentos o versiones distintas del objeto de estudio;
- resolver una parte de la afirmación no resuelve el resto.

Forzar un claim compuesto a un único estado epistémico oculta la incertidumbre real de las partes que no se han verificado. Este criterio de descomposición fue generalizado a partir de un caso documentado — ver `learning-log/entries/LL-0001-c05-electric-limits-hardening.md`.

## Evidencia
La evidencia es cualquier dato verificable (fuente, observación, medición) que respalda o refuta un claim o subclaim. La evidencia se clasifica, como mínimo, en:

- **primaria del dominio**: proviene directamente del objeto de estudio o de quien lo controla oficialmente;
- **secundaria/derivada**: reproduce, resume o cita evidencia primaria sin aportar verificación independiente;
- **documentación interna del proyecto**: registros del propio proceso de investigación (notas, bitácoras, reportes) — describe *cómo se investigó*, no es en sí misma evidencia sobre el dominio.

Ver `source-and-corroboration.md` para el detalle de esta distinción y sus implicaciones.

## Estados epistémicos: FACT / INFERENCE / STRATEGY / UNKNOWN
Definiciones de trabajo actualmente en uso en este proyecto:

- **FACT**: el claim cuenta con evidencia suficiente y verificada — idealmente incluyendo al menos una fuente primaria o una corroboración genuinamente independiente — para afirmarse sin reservas dentro del alcance (y versión, si aplica) declarado.
- **INFERENCE**: el claim se deduce razonablemente de evidencia indirecta o parcial, pero no ha sido confirmado de forma directa.
- **STRATEGY**: no es una afirmación sobre el dominio sino una recomendación operativa (qué hacer dado el conocimiento parcial disponible); no debe confundirse con FACT.
- **UNKNOWN**: la evidencia disponible es insuficiente para afirmar o descartar el claim. Un claim permanece en UNKNOWN mientras esa condición se mantenga — no se fuerza una resolución para "cerrar" el estado (ver `contradiction-and-gap-protocol.md`).

Un claim puede cambiar de estado únicamente como resultado de nueva evidencia evaluada según el protocolo de `research-protocol.md`, nunca por antigüedad, consenso no verificado o presión por reducir el número de UNKNOWN.

## Provenance
Todo claim debe poder rastrearse hasta su origen. Como mínimo, cada fuente citada debe registrar: un identificador único, el tipo de fuente, el publicador/autor, la fecha de publicación (si se conoce), la fecha en que fue consultada, y un nivel de confianza declarado. Un claim sin esta información asociada se trata como insuficientemente sustentado, independientemente de lo plausible que parezca.

## Versionado y validez temporal
Cuando el objeto de estudio puede cambiar a lo largo del tiempo (actualizaciones, versiones, ediciones), un claim debe declarar explícitamente a qué versión o período aplica. Un claim sin alcance temporal declarado, sobre un objeto de estudio que sí cambia con el tiempo, debe tratarse como un gap implícito (ver `contradiction-and-gap-protocol.md`), no como un hecho universal. Este principio, junto con el de subclaims, fue generalizado a partir de un caso documentado — ver `learning-log/entries/LL-0001-c05-electric-limits-hardening.md`.

## Mantenimiento de este archivo
Se actualiza cuando una entrada de `learning-log/` revela que el modelo de evidencia/claims actual no distingue algo que debería distinguir. Todo cambio sustantivo debe citar la entrada que lo motivó, cuando exista.
