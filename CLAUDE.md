# CLAUDE.md — Pokopia Intelligence Lab

> Este archivo es el contexto y contrato persistente del proyecto para cualquier sesión de Claude que trabaje sobre este repositorio. No reemplaza el juicio humano; establece reglas que deben respetarse salvo autorización explícita del usuario. Es el Project Operating Model de Pokopia Intelligence Lab.

---

## 1. Identidad y objetivo científico del proyecto

- **Nombre:** Pokopia Intelligence Lab
- **Repositorio:** `pokopia-cowork`

Este proyecto es un **laboratorio experimental**, no un producto de conocimiento sobre un videojuego. *Pokémon Pokopia* es el **dominio experimental**: un mundo lo bastante rico e interconectado (entidades, reglas, relaciones, contradicciones entre fuentes, dependencias temporales) como para servir de banco de pruebas, pero el conocimiento sobre Pokopia no es el objetivo final — es el material con el que se experimenta.

**El objetivo es:**

1. usar Pokémon Pokopia como dominio experimental;
2. construir una capa de domain intelligence / knowledge layer sobre ese dominio;
3. construir un Gold Dataset metodológicamente defendible;
4. construir posteriormente un Researcher / Knowledge Layer / Agent;
5. construir un baseline RAG comparable;
6. evaluar si la representación estructurada del conocimiento, la provenance, las relaciones, las reglas, la temporalidad/versionado, la memoria/case history, el manejo de incertidumbre y el razonamiento/agente aportan ventajas reales frente a un RAG básico basado en retrieval;
7. producir aprendizajes y metodología suficientemente reproducibles como para transferir el enfoque a otros dominios.

**No queremos simplemente "un RAG mejor".** Queremos poder responder, con evidencia experimental y no por intuición, si la inversión en estructura, provenance, razonamiento y memoria se traduce en una ventaja medible frente a retrieval-based RAG — o si no lo hace, lo cual sería en sí mismo un resultado válido del experimento.

La metodología reproducible (`methodology/` + `learning-log/`) es, en sí misma, uno de los productos intelectuales finales del proyecto — no un subproducto incidental de investigar Pokopia.

## 2. Non-goals

El proyecto explícitamente **no** persigue:

- conocimiento exhaustivo perfecto de todo Pokopia;
- resolver todos los `UNKNOWN` por obligación;
- corregir toda contradicción existente antes de avanzar;
- favorecer al Knowledge/Agent artificialmente en el diseño del experimento;
- diseñar Gold Questions para que el RAG falle;
- introducir evidencia solo porque favorece una hipótesis ya sostenida;
- optimizar métricas intermedias desconectadas del experimento final (p. ej. maximizar número de fuentes, de reglas, o de contradicciones resueltas, como fin en sí mismo).

Cuando surja la tentación de hacer algo de esta lista, toda mejora propuesta debe justificarse explícitamente por su impacto en al menos uno de: calidad del conocimiento, validez del Gold Dataset, validez del experimento, aporte de valor al proyecto, reproducibilidad metodológica. Si no puede justificarse así, se documenta como idea futura y no se implementa (ver §19, Seguridad metodológica).

## 3. Roadmap oficial

| Fase | Contenido | Estado |
|---|---|---|
| Fase 1 | Research + Knowledge Baseline | **CLOSED** |
| Fase 1.5 | Knowledge Hardening / Gap Resolution | Primer ciclo **validado mediante C05**. No significa que todos los gaps estén resueltos. |
| Fase 2 | Gold Dataset + representación técnica | **NEXT MAJOR PHASE** |
| Fase 3+ | Researcher / Knowledge Layer / Agent | Posterior a Fase 2 |
| Fase posterior | Baseline RAG + evaluación comparativa RAG vs. Knowledge/Agent | Posterior a Fase 3+ |

Ver §22 para el snapshot estratégico actual (dónde estamos hoy dentro de este roadmap) y §21 para los criterios que debe cumplir una fase antes de darse por cerrada.

## 4. Estado histórico — Fase 1

Fase 1 está **cerrada como baseline**.

Artefactos principales de Fase 1 (en `pokopia-research/`):

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

Fase 1 documentó el conocimiento consolidado y reconoció sus propias limitaciones metodológicas. **Solo se listan aquí las limitaciones que efectivamente están documentadas en `research-notes.md` §14 ("Limitaciones metodológicas conocidas")** — no se atribuye a Fase 1 nada que Fase 1 no haya declarado de sí misma:

- search log incompleto/inexistente (extracción histórica no registrada claim-por-claim);
- queries y búsquedas fallidas no registradas (`UNKNOWN` sin log de intentos);
- provenance claim-level insuficiente (granularidad variable entre reglas, glosario y catálogo);
- reproducibilidad parcial (ausencia de snapshots/quotes por claim);
- actualizabilidad claim-level limitada (clasificación `FACT` todavía gruesa, por sentencia agrupada).

**Nota histórica sobre un ítem retirado:** una versión anterior de este documento incluía "cobertura multilingüe no demostrada" como limitación de Fase 1. Se retira de esta lista: no existe respaldo documental en `research-notes.md`, en `phase1-consolidation-report.md` ni en ningún otro artefacto de `pokopia-research/` que sustente esa afirmación como un hallazgo que Fase 1 haya declarado. Si en el futuro se documenta como observación verificada, se reincorporará con su propia evidencia — no se reintroduce por defecto.

**Estas limitaciones NO deben interpretarse como prueba de que la investigación histórica fue incorrecta.** Significan que el repositorio no permite reconstruir completamente el proceso.

## 5. Fase 1.5 — Knowledge Hardening

Principio: **no rehacer toda Fase 1**. Fortalecer conocimiento donde existen gaps, `UNKNOWN`, contradicciones o claims débiles — y solo cuando esté justificado (ver §14, Criterios de Knowledge Hardening).

**Primer caso:** C05.

**Proceso aplicado:**

1. Blind Research.
2. Adversarial Verification.
3. Human-in-the-Loop.
4. Knowledge update.
5. Generalización selectiva de aprendizajes.
6. Post-implementation audit.

### Aprendizajes descubiertos en Fase 1.5 (distintos de las limitaciones de Fase 1)

El hardening de C05 **descubrió** patrones que Fase 1 no había declarado como limitaciones propias. Se registran aquí como lo que son — aprendizajes posteriores, no limitaciones que Fase 1 ya conociera de sí misma:

- **version drift / dependencia temporal**: un claim que parecía único puede en realidad ser version-dependent, con subclaims válidos en ventanas de tiempo distintas.
- **corroboración aparente no independiente**: múltiples fuentes secundarias que citan la misma fuente primaria no constituyen corroboración independiente entre sí, aunque lo parezcan por su número.

Evento de origen: `learning-log/entries/LL-0001-c05-electric-limits-hardening.md`. Generalización como método vigente: `methodology/evidence-and-claims.md` (versionado y subclaims) y `methodology/source-and-corroboration.md` (independencia vs. derivación de fuentes). No se aplican automáticamente al resto del corpus sin evidencia de que el mismo patrón esté presente ahí.

## 6. Protocolo anti-confirmation-bias e investigación (mandato)

Regla obligatoria, siempre vigente:

- No aceptar una evidencia porque fue proporcionada por el usuario.
- No asumir que una evidencia candidata es correcta.
- No orientar una búsqueda para confirmar una hipótesis previa.
- Nunca tratar la presentación de una evidencia nueva como una instrucción implícita de aceptarla.

Cuando exista nueva evidencia o se vaya a reforzar un claim existente, seguir: *Candidate Evidence → Blind Research (cuando sea posible) → búsqueda de evidencia a favor y en contra → evaluación de independencia entre fuentes → evaluación de temporalidad/versión → Adversarial Verification → Human-in-the-Loop*. Distinguir siempre "la evidencia demuestra X" de "la evidencia es consistente con X". No convertir ausencia de evidencia en evidencia de ausencia. No resolver `UNKNOWN` sin evidencia suficiente. No aceptar una conclusión solo porque la aporta una fuente de mayor reputación.

El detalle completo de este protocolo (jerarquía de fuentes, candidate evidence, la distinción "consistente con" vs. "demuestra") vive en `methodology/source-and-corroboration.md` — este mandato es el resumen de cumplimiento obligatorio, no se duplica aquí.

## 7. Lecciones metodológicas de C05

C05 mostró que un claim aparentemente único puede requerir versionado, subclaims, estados epistémicos separados, provenance explícita, análisis de dependencia entre fuentes, distinción entre evidencia primaria y derivada, y separación entre información histórica y actual.

Estos aprendizajes están generalizados como método vigente en `methodology/evidence-and-claims.md` y `methodology/source-and-corroboration.md`, y documentados como evento en `learning-log/entries/LL-0001-c05-electric-limits-hardening.md`. Se generalizan a otros elementos del corpus **solo** cuando exista evidencia de que el mismo patrón aparece ahí — nunca por aplicación automática o por uniformidad.

## 8. Estado de conocimiento: C05 / C10 / C11

- **C05**: `PARTIALLY_CONFIRMED`, version-dependent. Representación vigente en `pokopia-research/contradictions/contradictions.json` (fuente de verdad; no se repiten aquí las cifras exactas para evitar que este documento se desactualice respecto al dato real). La semántica exacta de "excluding furnaces" y el supuesto límite de transmisores permanecen `UNKNOWN` — mantener ese `UNKNOWN` explícito, no forzar resolución.
- **C11**: `UNKNOWN`. Contradicción adicional (output del Furnace) detectada durante el hardening de C05. No asumir ninguna resolución.
- **C10**: **restaurado y preservado** en su estado previo a Fase 1.5, tras haber sido sobrescrito por error durante la inserción de C11. Esta restauración es un **defecto de implementación corregido y un aprendizaje metodológico** (verificar el diff real contra el historial de git antes de aceptar una afirmación de "no tocado") — **no es conocimiento nuevo del dominio** ni una resolución de C10. Ver `learning-log/entries/LL-0001-c05-electric-limits-hardening.md` para el registro completo del incidente.

## 9. Q13

Q13 depende de C05 y tiene una nota explícita de versión (`version_note`) en `pokopia-research/candidate-questions/questions.md`. No convertir Q13 en una pregunta Gold ni introducir respuestas Gold implícitas sin HITL posterior.

## 10. Methodology & Learning Log

El repositorio distingue tres capas que no deben mezclarse:

- **Knowledge** (`pokopia-research/`) responde *"¿qué sabemos sobre Pokopia?"*
- **Method** (`methodology/`) responde *"¿cómo decidimos qué sabemos?"* — es el estado **actual** del método: normativo, independiente del dominio, reutilizable, evolutivo. No es un registro histórico.
- **Learning Log** (`learning-log/`) responde *"¿qué eventos nos hicieron cambiar el método?"* — es la capa histórica; nada se sobrescribe ahí.

El detalle de cada capa (mapa de cobertura de conceptos, esquema de entradas, reglas de mantenimiento) vive en `methodology/README.md` y `learning-log/README.md` respectivamente — no se duplica aquí. Regla de flujo: un evento se registra primero en `learning-log/`; solo si ese evento demuestra que el método actual es insuficiente, se actualiza `methodology/`, citando la entrada que lo motivó. No se inventan eventos retrospectivamente.

## 11. Modelo de trabajo permanente

Todo trabajo significativo sigue este ciclo:

1. Define objective
2. Inspect current state
3. Analyze
4. Research / investigate *(cuando aplica: seguir el ciclo detallado de `methodology/research-protocol.md`, no repetirlo aquí)*
5. Validate
6. Human-in-the-Loop
7. Implement
8. Audit implementation
9. Validate repository
10. Human approval for staging
11. Human approval for commit
12. Human approval for push
13. Record learning when applicable, and re-evaluate the next step against the project objective (§20)

No saltar directamente de investigación a implementación cuando exista incertidumbre relevante. Los pasos 10-12 son checkpoints humanos explícitos y no se colapsan entre sí ni se saltan (ver §18, Git Workflow).

## 12. Cuándo hacer adversarial verification (obligatorio)

La verificación adversarial es obligatoria — no opcional — cuando el resultado de una investigación pueda:

- cambiar un `UNKNOWN`;
- resolver una contradicción;
- cambiar una regla importante;
- afectar una Gold Question;
- alterar una dependencia relevante entre artefactos;
- cambiar una conclusión experimental.

La revisión adversarial debe buscar activamente evidencia que contradiga la conclusión propuesta, no solo evidencia que la confirme (ver `methodology/source-and-corroboration.md` para el procedimiento).

## 13. Human-in-the-Loop (HITL)

Claude puede investigar, proponer, analizar e implementar. **El humano decide sobre cambios importantes de conocimiento.** Ningún cambio de estado epistémico, resolución de contradicción, o generalización a otros artefactos se da por definitivo sin este checkpoint.

Vocabulario de decisión disponible para el humano:

- **ACCEPT**
- **REJECT**
- **ACCEPT WITH CAVEATS**
- **INVESTIGATE MORE**
- **KEEP UNKNOWN**

No convertir automáticamente un resultado o propuesta del modelo en conocimiento Gold ni en un cambio de estado epistémico aceptado.

## 14. Criterios de Knowledge Hardening

**No hacer Knowledge Hardening por volumen. No intentar resolver todos los gaps.** Un candidato (gap o contradicción) merece hardening solo cuando exista justificación por al menos uno de:

- impacto sobre el Gold Dataset;
- impacto experimental (afecta la comparación RAG vs. Knowledge/Agent);
- incertidumbre relevante para una pregunta o decisión activa;
- dependencia downstream (otros artefactos dependen de resolverlo);
- riesgo temporal/versionado significativo;
- valor metodológico (el caso enseña algo generalizable sobre el método).

Antes de elegir un gap para endurecer, verificar explícitamente si contribuye al objetivo global (§1) — no asumir que "existe" es razón suficiente.

## 15. Gold Dataset

El objetivo de Fase 2 **no** es simplemente convertir preguntas interesantes en Gold. Una Gold Question debe poder tener, como mínimo:

- respuesta esperada;
- claims que la soportan;
- evidencia que sustenta esos claims;
- provenance;
- estado epistemológico;
- aplicabilidad temporal/versionada, cuando corresponda;
- tratamiento explícito de contradicciones relevantes;
- un criterio de corrección reproducible (que no dependa de quién evalúa).

Además, debe aportar valor al experimento RAG vs. Knowledge/Agent. Estas son **dos dimensiones independientes** y ambas deben evaluarse:

- **Goldability**: ¿podemos construir para esta pregunta una respuesta Gold reproducible, con la evidencia y provenance mínimas de arriba?
- **Evaluation Value**: ¿la pregunta es útil para diferenciar capacidades entre un RAG básico y un Knowledge/Agent (factual retrieval, multi-hop, structured reasoning, rules, relationships, temporal/version-aware reasoning, contradictions, uncertainty, case/history memory)?

Una pregunta puede ser Gold-ready pero de bajo valor experimental; otra puede tener alto valor experimental pero requerir Knowledge Hardening antes de ser Gold-ready. Ninguna de las dos dimensiones sustituye a la otra.

Human-in-the-Loop es obligatorio para toda Gold Question: Claude propone o audita, el humano decide, el Gold Dataset es el resultado validado. Nunca convertir automáticamente una clasificación del modelo en Gold.

## 16. Evaluación RAG vs. Knowledge/Agent

El futuro benchmark **no** debe construirse para favorecer de antemano al Agent. Las Gold Questions, en conjunto, deben representar capacidades relevantes del problema — no solo las que el Agent maneja mejor:

- factual retrieval;
- multi-hop reasoning;
- structured reasoning;
- rules;
- relationships;
- temporal/version-aware reasoning;
- contradictions;
- uncertainty;
- case/history memory.

El baseline RAG y el Knowledge/Agent deben evaluarse sobre un conjunto de preguntas comparable, y las reglas de evaluación deben definirse **sin conocer de antemano cuál sistema ganará**. Diseñar una pregunta para que el RAG falle es un non-goal explícito (§2).

## 17. Validación y auditoría

Después de cualquier cambio significativo de conocimiento o de estructura del repositorio:

- revisar `git status`;
- revisar el diff completo (no solo el resumen `--stat`);
- validar la estructura de los artefactos tocados;
- validar referencias internas (rutas, IDs citados);
- validar estados epistemológicos (`FACT`/`INFERENCE`/`STRATEGY`/`UNKNOWN`) tras el cambio;
- buscar cambios accidentales (archivos que no debían tocarse);
- revisar provenance;
- revisar consistencia con el resto del corpus.

No aceptar una implementación solamente porque Claude declare que terminó. Para cambios de conocimiento relevantes, debe existir una auditoría post-implementación explícita antes de considerar el cambio cerrado (ver también la etapa 14, "Post-implementation audit", de `methodology/research-protocol.md`).

## 18. Git Workflow

**Regla central, sin excepciones:** Claude puede inspeccionar, investigar, analizar, modificar archivos, ejecutar validaciones, preparar el diff y dejar archivos listos para `staging` — pero **`git add`, `git commit` y `git push` requieren cada uno autorización humana explícita**, dada dentro de la tarea en curso. La publicación a GitHub permanece como checkpoint humano en cada una de sus tres etapas.

Flujo permanente:

```text
Research / Analysis
→ Validation
→ HITL
→ Implementation
→ Post-implementation Audit
→ Repository Validation
→ Human approval for staging
→ Human approval for commit
→ Human approval for push
```

Antes de modificar: inspeccionar el estado de git. Durante investigación: no hacer commits — ni siquiera locales de "checkpoint". Antes de proponer un commit (nunca antes de que el humano lo apruebe):

- revisar el diff completo;
- revisar qué archivos quedarían staged;
- ejecutar `git diff --check` (o equivalente) para detectar problemas obvios de formato;
- comprobar que no hay archivos accidentales en el conjunto propuesto;
- comprobar explícitamente que `git_github_guia_pokopia.md` permanece fuera.

Nunca usar `git add -A` sin inspección previa del conjunto de archivos que incluiría. Un commit solo se ejecuta (por el humano, o por Claude con autorización explícita para ese commit puntual) cuando: la decisión conceptual está cerrada, el diff fue auditado, las validaciones pasaron, y el conjunto de archivos staged es intencional — nunca el resultado de un comando amplio sin revisar. Push solo después de validar el commit local. Usar branches/PR cuando se entre a cambios arquitectónicos mayores (Researcher, Knowledge Layer, Agent, RAG baseline, infraestructura experimental).

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

## 19. Seguridad metodológica

No modificar archivos solamente para hacerlos más uniformes. Toda modificación debe responder a una de estas razones:

- nueva evidencia;
- corrección de inconsistencia demostrada;
- impacto directo de una actualización;
- mejora metodológica explícitamente justificada.

Si una recomendación todavía no tiene suficiente evidencia: documentarla, no implementarla.

## 20. Comportamiento esperado y regla de decisión del siguiente paso

Cuando recibas una tarea:

1. identifica qué parte es investigación, qué parte es decisión y qué parte es implementación;
2. no mezcles descubrimiento de evidencia con aceptación de evidencia;
3. separa hechos, inferencias y `UNKNOWN`;
4. explica impactos antes de cambios grandes;
5. no hagas cambios fuera del alcance solicitado;
6. conserva trazabilidad.

No borres información histórica simplemente porque exista una versión más nueva. Cuando una actualización supersede una afirmación anterior, conservar la información histórica cuando sea relevante.

**Regla crítica sobre el siguiente paso:** al terminar una tarea, no asumas automáticamente que el siguiente paso es resolver el siguiente gap, hacer otra mejora, o investigar más. Primero pregunta: *"¿qué acción maximiza el progreso hacia el objetivo global del proyecto (§1)?"* Si la respuesta no está clara, hacer análisis/planificación antes de implementar. Evitar ciclos de trabajo infinitos y la optimización de problemas intermedios desconectados del objetivo (ver §2, Non-goals).

## 21. Criterios de cierre de fase

Una fase no termina porque "ya trabajamos bastante". Antes de declarar una fase cerrada debe existir, documentado: objective, inputs, outputs, validation, remaining uncertainty, exit criteria. Esta regla aplica de forma prospectiva a partir de Fase 2 en adelante — no reabre retroactivamente el cierre ya declarado de Fase 1.

## 22. Estado estratégico inmediato (snapshot — actualizar cuando cambie)

> Esta sección es un snapshot fechado del estado estratégico, no una regla permanente. Debe actualizarse o retirarse cuando el análisis que describe se complete.

- Fase 1 = **CLOSED**.
- Fase 1.5 = primer ciclo **validado mediante C05** (no todos los gaps están resueltos; no se persigue resolverlos todos — ver §14).
- Fase 2 = **NEXT MAJOR PHASE**. Estamos en transición hacia ella.
- **Próxima tarea prioritaria:** Gold Dataset Readiness Analysis de las 28 Candidate Questions (Q01–Q28, en `pokopia-research/candidate-questions/questions.md`).
- Ese análisis debe ser de **solo lectura**: sin investigación externa, sin modificar Candidate Questions, sin resolver gaps. Evalúa dos dimensiones independientes por pregunta: **Goldability** y **Evaluation Value** (ver §15). Su resultado alimentará una clasificación en: listas para Gold / bloqueadas por gaps / requieren Knowledge Hardening / demasiado ambiguas o débiles / alto valor para evaluar razonamiento.
- Solo después de ese análisis se decide qué Knowledge Hardening (si alguno) tiene sentido priorizar — nunca antes, y nunca por defecto (§14).

## 23. Autonomía operativa de Claude

A partir de este documento, cuando Claude reciba una nueva tarea de proyecto:

1. verificarla contra este Project Operating Model;
2. determinar si la tarea es research, analysis, decision, implementation o audit;
3. identificar si requiere Human-in-the-Loop (§13);
4. determinar si corresponde modificar Knowledge (`pokopia-research/`), Method (`methodology/`) o Learning (`learning-log/`) — y confirmar que no se está duplicando contenido de `methodology/` en otro lugar;
5. ejecutar solo el alcance autorizado por la tarea;
6. validar antes de considerar el trabajo terminado (§17);
7. proponer el siguiente paso solo si está justificado por el roadmap y el objetivo global (§20) — no por defecto.

Esta autonomía cubre investigación, análisis, decisión propuesta e implementación de archivos. **No se extiende nunca a `git add`, `commit`, `push`, PR, merge ni cambios de rama** (§18): esas operaciones requieren autorización humana explícita en cada caso, sin excepción, independientemente de cuán trivial parezca la operación o cuán claro parezca el siguiente paso.

## 24. Estado específico de la migración

Este proyecto está migrando de un flujo anterior basado en OpenCode/DeepSeek a Claude. Los aprendizajes metodológicos del flujo anterior deben conservarse. No asumir que Claude tiene acceso a conversaciones previas fuera de este repositorio. **El repositorio y este `CLAUDE.md` deben ser la base persistente del contexto.**
