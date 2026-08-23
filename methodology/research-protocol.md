# Research Protocol

> Parte de `methodology/` — ver `README.md` para el rol de esta carpeta (estado actual del método, independiente del dominio, evolutivo) y su relación con `learning-log/`.

Este documento describe el ciclo general y reutilizable de investigación y validación de conocimiento. Es deliberadamente abstracto: no describe ningún caso concreto de Pokopia. Para ver el protocolo aplicado a un caso real y documentado, ver `learning-log/entries/LL-0001-c05-electric-limits-hardening.md` — ese archivo es la referencia histórica; este archivo es la regla vigente.

El ciclo no es estrictamente lineal: varias etapas pueden repetirse o retroceder (p. ej. una contradicción detectada en la etapa 7 puede obligar a volver a la etapa 3).

## 1. Definición de la pregunta
Se formula explícitamente qué se quiere saber, con el alcance más estrecho posible. Una pregunta vaga ("¿cómo funciona X?") debe descomponerse en preguntas verificables antes de investigar.

## 2. Descubrimiento
Se identifican las fuentes potencialmente relevantes (oficiales, secundarias, comunitarias) sin todavía extraer ni aceptar contenido. El objetivo de esta etapa es solo mapear dónde podría estar la respuesta.

## 3. Investigación
Se examina el contenido de las fuentes identificadas. Toda afirmación recogida en esta etapa se trata inicialmente como *candidate evidence* (ver `source-and-corroboration.md`), nunca como hecho aceptado.

## 4. Extracción
Se registra la afirmación con su proveniencia completa (fuente, fecha de publicación, fecha de recuperación) antes de interpretarla o resumirla. Sin proveniencia registrada en esta etapa, la afirmación no puede avanzar a las etapas siguientes.

## 5. Evaluación
Se evalúa la calidad de cada fuente y de cada afirmación individualmente (ver `source-and-corroboration.md`): tipo de fuente, autoridad, especificidad, fecha.

## 6. Corroboración
Se determina si distintas fuentes que respaldan la misma afirmación son independientes entre sí o si unas derivan de otras. Solo la corroboración entre fuentes independientes incrementa la confianza en un claim (ver `source-and-corroboration.md`).

## 7. Contradicciones
Cuando dos afirmaciones con evidencia propia son mutuamente incompatibles, se registra como contradicción formal en vez de elegir una arbitrariamente (ver `contradiction-and-gap-protocol.md`).

## 8. Gaps
Cuando ninguna fuente disponible cubre la pregunta con evidencia suficiente, se registra como knowledge gap explícito, distinto de una contradicción (ver `contradiction-and-gap-protocol.md`).

## 9. Blind research
Ante un claim ya existente que se va a reforzar o poner a prueba, la investigación se reinicia sin aceptar como punto de partida la conclusión previa. El objetivo es evitar que una conclusión ya registrada sesgue la búsqueda de evidencia nueva.

## 10. Adversarial verification
Se busca activa y deliberadamente evidencia que contradiga o debilite el claim bajo revisión, no solo evidencia que lo confirme. Incluye, cuando es posible, acceder directamente a la fuente primaria en lugar de conformarse con reproducciones de terceros.

## 11. Human-in-the-Loop (HITL)
Ningún cambio de estado epistémico de un claim (de UNKNOWN a un estado más fuerte, o viceversa) se considera definitivo sin un punto de revisión humana. El modelo puede proponer o auditar; la decisión final es humana (ver también `CLAUDE.md`).

## 12. Actualización
Una vez aprobado el cambio, se actualiza el artefacto de conocimiento correspondiente (regla, contradicción, relación, fuente) reflejando el nuevo estado, sin eliminar el registro de lo que existía antes salvo que sea estrictamente incorrecto.

## 13. Propagation analysis
Se evalúa explícitamente si el patrón o aprendizaje detectado en un claim aplica también a otros elementos del corpus. La propagación es selectiva: se extiende solo a los elementos donde existe evidencia de que el mismo patrón está presente, nunca por generalización automática o por uniformidad estética.

## 14. Post-implementation audit
Tras propagar un cambio, se audita el resultado real (no solo lo declarado) contra el estado del control de versiones u otro registro objetivo, para detectar defectos de implementación que la propia narrativa del proceso podría no haber registrado.

## 15. Reproducibilidad
Cada etapa anterior debe quedar registrada de forma suficiente para que un tercero pueda reconstruir qué se hizo, con qué evidencia y con qué decisión, sin depender de memoria no escrita (ver `reproducibility.md`).

## Mantenimiento de este archivo
Este archivo se actualiza cuando una entrada de `learning-log/` demuestra que una etapa falta, sobra o está mal definida — no por reorganización estética. Todo cambio sustantivo a una etapa debe citar la entrada de `learning-log/` que lo motivó, cuando exista.
