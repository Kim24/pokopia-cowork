# Pokopia — Research Notes (Fase 1)

> Bitácora del proceso de investigación. Metodología, decisiones, limitaciones y próximos pasos.
> Fecha de sesión: 2026-08-15. Repo: `D:\repositorios\pokopia-cowork`.

---

## 1. Contexto del proyecto

Este paquete de investigación es el **entregable de la Fase 1 (Domain Research)** del "Pokopia Intelligence Lab": el objetivo a largo plazo es construir una **capa de conocimiento** y un **agente de IA** capaces de razonar sobre un dominio completo (Pokémon Pokopia), incluyendo la generación de un **Gold Dataset** de preguntas/respuestas para evaluación.

La Fase 1 **no** construye arquitectura técnica (RAG, embeddings, vector DB, agentes, Text-to-SQL, interfaces). Solo produce conocimiento estructurado y trazable.

## 2. Metodología

1. **Inspección del repositorio**: verificar rama, working tree limpio y contenido existente (solo README y .gitignore).
2. **Definición de la estructura de salida** según `instrucciones_research.txt`.
3. **Búsqueda y fetch de fuentes** en 4 niveles:
   - **Oficial** (press.pokemon.com, pokopia.pokemon.com, nintendo.com, Nintendo Support) → SRC001–SRC014, SRC060, SRC064.
   - **Wikis/bases de datos** (Serebii, Bulbapedia, The Games Wiki, Fextralife) → SRC015–SRC041.
   - **Guías/walkthroughs** (Nintendo Life, VGC, Polygon, Eurogamer, Game8, Dexerto, GamesRadar, Pocket Tactics, IGN, GameRant, pokopiaguide, thegamer, rectifygaming, Vandal, popcultdaily, pokopia.center, pokopiamap) → SRC042–SRC058, SRC062, SRC063.
   - **Comunidad** (r/Pokopia vía prensa, Kotaku, Eurogamer, YouTube) → SRC052–SRC055, SRC059.
4. **Consolidación** en: `sources/sources.json` (64 fuentes), `domain-map/`, `entities/`, `concepts/glossary.json`, `relationships/relationships.json`, `rules/rules.json`, `contradictions/contradictions.json`, `knowledge-gaps/gaps.md`, `candidate-questions/questions.md`.

## 3. Jerarquía de evidencia

| Etiqueta | Significado | Uso |
|---|---|---|
| `FACT` | Afirmado explícitamente por una o más fuentes | Mayoría de reglas y relaciones |
| `INFERENCE` | Deducido de otras afirmaciones (p. ej. inspiración de áreas de Kanto) | Marcado en el campo `status` |
| `STRATEGY` | Recomendaciones de la comunidad (p. ej. automatizaciones) | Documentado en domains.md §22 |
| `UNKNOWN` | No hay evidencia suficiente | Contradicciones y gaps |

## 4. Decisiones tomadas

- **Número canónico de Pokédex: 300** (la Pokédex principal). Se documenta la discrepancia C09 (423 de RankedBoost) como error de marketing.
- **Serebii como fuente canónica** para estructuras de juego (movimientos, áreas, progresión, hábitats) porque es la más detallada y post-lanzamiento.
- **Áreas de historia = 4 + Palette Town + Bubbly Basin (DLC)**. Las "6 regiones" de algunas fuentes (C01) probablemente cuentan Palette Town y/o Bubbly Basin; se deja en UNKNOWN.
- **Nombres de Trainer Rank: No Rank → Great → Ultra → Master** (Serebii); se documentan alternativas (C03).
- Las **especialidades se consolidan por unión** de Serebii + Game8 + Serebii (29 vs 31+), etiquetando la fuente por ítem (C08).
- Se **descarta el dato de 423 Pokémon** (C09) por ser de un sitio de marketing sin verificación.

## 5. Limitaciones y advertencias

- **El juego se lanzó el 5 de marzo de 2026**; la mayor parte de la información es post-lanzamiento, pero la situación cambia con updates y DLC (Bubbly Basin salió el 5 ago 2026).
- **Reddit r/Pokopia está bloqueado** para fetch directo → la información comunitaria se tomó de artículos de prensa que citan a la comunidad (Kotaku, Eurogamer) → **confianza baja-media**.
- **La wiki oficial de Pokopia es de pago** → no se usó directamente.
- Algunas **fechas de publicación de guías** no están verificadas; puede haber contenido pre-release desactualizado en sitios menores.
- Las **tablas numéricas** (umbrales de Environment Level, tabla de recetas, tabla de trueque, consumo eléctrico) no están publicadas por fuentes oficiales → **GAP-01/02/05/06/07**.

## 6. Próximos pasos

1. ✅ **Resolver contradicciones P0 (C02/C03)** y **consolidar GAP-03** (catálogo de 300 Pokémon) — completado en la **Fase 1** (2026-08-15), ver `phase1-consolidation-report.md`.
2. **Definir el formato del Gold Dataset** (pregunta/respuesta esperada/scoring) usando `candidate-questions/questions.md` como semilla.
3. **Decidir la representación técnica**: JSON/SQL/CSV/Markdown/vector/GraphDB. Este paquete es agnóstico y servirá de input en cualquiera de ellos.

## 7. Checklist de entregables de la Fase 1

| Entregable | Ruta | Estado |
|---|---|---|
| Inventario de fuentes | `sources/sources.json` | ✅ |
| Overview del dominio | `domain-map/overview.md` | ✅ |
| Mapa de sistemas | `domain-map/domains.md` | ✅ |
| Mapa de relaciones | `domain-map/relationships.md` | ✅ |
| Entidades: Pokémon | `entities/pokemon.md` | ✅ |
| Entidades: áreas | `entities/areas.md` | ✅ |
| Entidades: NPCs | `entities/npcs.md` | ✅ |
| Entidades: comida | `entities/food.md` | ✅ |
| Entidades: recursos | `entities/resources.md` | ✅ |
| Entidades: progresión | `entities/progression.md` | ✅ |
| Glosario de conceptos | `concepts/glossary.json` | ✅ |
| Relaciones formales | `relationships/relationships.json` | ✅ |
| Reglas del juego | `rules/rules.json` | ✅ |
| Contradicciones | `contradictions/contradictions.json` | ✅ |
| Knowledge gaps | `knowledge-gaps/gaps.md` | ✅ |
| Preguntas candidatas | `candidate-questions/questions.md` | ✅ |
| Notas de investigación | `research-notes.md` | ✅ |
| Reporte final | `README.md` (raíz del paquete) | ✅ |

---

## 8. Fase 1 — Consolidación (2026-08-15)

**Objetivo (Opción A del usuario):** priorizar gaps P0 y contradicciones C02/C03; completar y validar el catálogo de 300 Pokémon; revisar relaciones/reglas; actualizar artefactos; reportar confirmado/cambiado/desconocido. Sin commits ni push.

**Decisiones tomadas en Fase 1:**

- **C01 RESUELTA**: 7 localizaciones canónicas (Serebii `locations`): Withered Wastelands, Bleak Beach, Rocky Ridges, Sparkling Skylands, Palette Town, Cloud Island, Bubbly Basin (DLC). Dream Islands = sistema aparte.
- **C02 RESUELTA**: cada área de historia requiere su Important Request + Pokémon Center reconstruido + Environment Level 5; las puertas entre áreas se abren por Trainer Rank. Descartado el "40%/Hyper" de PokopiaCenter (sin apoyo).
- **C03 RESUELTA**: No Rank → Great → Ultra → Master (Serebii + The Games Wiki, tabla completa). "Super"/"Hyper" sin evidencia.
- **C06 RESUELTA**: Team Initiation Challenge = 9 retos (Serebii, canónico; TGW fusiona 8–9 contando 8); etapa 1 = 5 Leppa Berries; cohete de Team Rocket.
- **C08 RESUELTA**: 31 especialidades exactas (roster Serebii); "Scrub" eliminado.
- **C07 RESUELTA con criterio**: 12 legendarios/míticos en el juego base; 14 contando DLC (Manaphy, Phione).
- **C09 mantenida**: 300 (Serebii 308 entradas #001–#300; TGW 300+7+4 de evento).
- **C10 (nueva)**: fechas del evento Hoppip (Serebii 10–25 vs TGW 9–24 mar 2026) — UNKNOWN, menor.
- **Comfort**: 5 niveles (Iffy→Awesome) + Comfy 0 sin hogar (corrige los "6 estados" de Fase 1).
- **Environment Level**: mecánica completa documentada (sube con Comfort/Requests/edificios; baja al quitar Pokémon; Lv.5 regalo, Lv.10 recetas).
- **Recursos**: Gold Ore también en Withered Wastelands (no exclusivo de Rocky Ridges); Fresh Carrot; tesoros y fósiles de Wastelands.

**Nuevos artefactos:** `entities/pokemon-catalog.md` (308 entradas, validado contra The Games Wiki) y `phase1-consolidation-report.md` (reporte formal).

**Fuentes añadidas:** SRC065–SRC069 (Serebii `availablepokemon`, `locations`, `gameplay`, `locations/witheredwastelands`; The Games Wiki `pokemon-list`). Total: 69.

**Sigue UNKNOWN (documentado):** C04 (Tinkagear), C05 (límites eléctricos), C10, umbrales numéricos de Env/Comfort (GAP-01), costes de Building Kits (GAP-04), tabla de recetas (GAP-05), tabla de trueque (GAP-06), tabla eléctrica exacta (GAP-07).

---

# II. Documentación metodológica (cierre de Fase 1)

> Esta sección documenta **retrospectivamente** el método con el que se produjo y consolidó el conocimiento de Fase 1, a partir únicamente de lo que puede reconstruirse del repositorio. No existió un protocolo formal escrito previamente; por eso esta documentación es una **reconstrucción honesta** del proceso real y, donde no es posible reconstruir con confianza, la limitación se señala explícitamente en lugar de inventarse.

---

## 9. Método de extracción y filtrado

### 9.1 Cómo se identificaba información relevante en una fuente

Según lo registrado, la búsqueda se organizó en **4 niveles de fuentes** (§2.3, `overview.md` §4):

1. **Oficial** (press.pokemon.com, pokopia.pokemon.com, nintendo.com, Nintendo Support) → SRC001–SRC014, SRC060, SRC064.
2. **Wikis/bases de datos** (Serebii, Bulbapedia, The Games Wiki, Fextralife) → SRC015–SRC041.
3. **Guías/walkthroughs** (Nintendo Life, VGC, Polygon, Eurogamer, Game8, etc.) → SRC042–SRC058, SRC062, SRC063.
4. **Comunidad** (r/Pokopia vía prensa, Kotaku, Eurogamer, YouTube) → SRC052–SRC055, SRC059.

Cada fuente se registró en `sources/sources.json` con `source_id`, URL, editor, tipo de fuente, fecha de publicación, `retrieved_at` (todas recuperadas el 2026-08-15), temas cubiertos, entidades mencionadas y un nivel de `confidence` (high/medium/low).

Se consideró información relevante aquella que describía **sistemas, entidades, mecánicas, valores numéricos, progresión, requisitos de desbloqueo y relaciones entre elementos** del juego — es decir, aquello que alimenta los artefactos del paquete (dominios, entidades, reglas, relaciones, contradicciones, gaps).

### 9.2 Cómo se transformaba un hallazgo en conocimiento estructurado

Reconstrucción a partir de §2.4: tras recuperar las fuentes, la información se consolidó por tipo de artefacto:

- **Hechos generales del dominio** → `domain-map/overview.md` y `domain-map/domains.md`.
- **Mapa conceptual de relaciones** → `domain-map/relationships.md` y `relationships/relationships.json`.
- **Catálogos por entidad** (pokémon, áreas, NPCs, comida, recursos, progresión) → `entities/*.md`.
- **Términos del dominio** → `concepts/glossary.json`.
- **Normas de juego** → `rules/rules.json` (cada regla con `sources[]` y `status`).
- **Desacuerdos entre fuentes** → `contradictions/contradictions.json`.
- **Lagunas de conocimiento** → `knowledge-gaps/gaps.md`.
- **Preguntas candidatas** → `candidate-questions/questions.md`.

Cada afirmación estructurada se acompañó de su(s) fuente(s) citada(s) como `[SRC0xx]` (en markdown) o en el campo `sources[]` (en JSON). El caso más detallado es el catálogo de Pokémon (`entities/pokemon-catalog.md`), que incluye una **nota de extracción** (`pokemon-catalog.md:7`) explicando cómo se transcribió la tabla del volcado de la página de Serebii.

### 9.3 Tipos de información considerados relevantes

- Sistemas del juego y su funcionamiento.
- Entidades y sus atributos (tipos, especialidades, hábitats, condiciones de aparición, flavors, comfort).
- Mecánicas de progresión (Trainer Rank, Environment Level, Comfort, Friendship, PP).
- Requisitos de desbloqueo y condiciones de acceso por área.
- Valores numéricos publicados (límites, conteos, recetas, monedas).
- Relaciones entre entidades (aprende, potencia, requiere, desbloquea, procesa, etc.).

### 9.4 Información excluida

A partir de los ejemplos documentados de descarte:

- **Datos de marketing sin verificación**: el conteo "423 Pokémon" de RankedBoost se descartó como error de marketing (C09, §4).
- **Rangos/afirmaciones sin apoyo canónico**: "Super"/"Hyper" Trainer Rank (C03) y el desbloqueo por "40% de restauración" de PokopiaCenter (C02) se descartaron por no tener apoyo en Serebii ni The Games Wiki.
- **Roles sin respaldo en el roster**: la especialidad "Scrub" se eliminó por no aparecer en ninguna entrada (C08).
- **Recomendaciones subjetivas de comunidad** se marcaron como `STRATEGY` (p. ej. automatizaciones, `domains.md` §22) en lugar de tratarse como hechos.

### 9.5 Cómo se evitaba inventar información

Regla de oro explícita en `overview.md:5`: **"no inventar"**. Todo lo que no está confirmado se marca explícitamente: las afirmaciones llevan `FACT`/`INFERENCE`/`STRATEGY`/`UNKNOWN` (§3, cabecera de `domains.md`), y lo no confirmado se registra como contradicción o gap en lugar de darse por cierto.

### 9.6 Cómo se manejaban datos ambiguos o incompletos

- **Ambiguos (con evidencia en pugna)** → se registraron como **contradicción** con `claim_a`/`claim_b`, evidencia por lado y estado de resolución (`contradictions.json`).
- **Incompletos (sin evidencia suficiente)** → se registraron como **knowledge gap** con estado OPEN/PARTIAL/RESOLVED (`gaps.md`).
- **Limitaciones de acceso** se documentaron en §5 (subreddit r/Pokopia bloqueado, wiki oficial de pago, fechas de guías no verificadas, tablas numéricas no publicadas).

### 9.7 Destino de un hallazgo (regla de clasificación observada)

Según el patrón real del repositorio:

- **Entidad**: un elemento nombrado con atributos propios (pokémon, área, NPC, recurso, sistema) → `entities/*.md` (y, si aplica, `pokemon-catalog.md`).
- **Relación**: una conexión entre dos entidades con predicado y fuente → `relationships/relationships.json` y `domain-map/relationships.md`.
- **Regla**: una norma de juego o negocio → `rules/rules.json`.
- **Concepto**: un término del dominio → `concepts/glossary.json`.
- **Contradicción**: dos afirmaciones incompatibles con evidencia por ambos lados → `contradictions/contradictions.json`.
- **Knowledge gap**: falta de información que no es contradictoria sino ausente → `knowledge-gaps/gaps.md`.
- **Evidencia/documentación**: material de soporte o contexto (lo que alimenta `overview.md`, `domains.md`, `research-notes.md`, `phase1-consolidation-report.md`).

> Esta clasificación se presenta como la **regla que se observa** en los artefactos; no se registró explícitamente como decisión en el momento.

### 9.8 Plantilla conceptual de extracción *(recomendación para futuras fases, no registro histórico)*

No hay evidencia de que se usara una plantilla formal en Fase 1. Para fases futuras se sugiere, de forma alineada con la estructura actual del repositorio:

```text
Fuente: SRC0xx · URL · sección/pasaje · retrieved_at
  Hallazgo (afirmación literal, sin interpretar)
    → ¿Es relevante para el dominio?  (sí/no)
        si no  → DESCARTE
    → ¿Hay evidencia contradictoria? → CONTRADICTION (claim_a/claim_b + evidencia)
    → ¿Falta evidencia?               → KNOWLEDGE GAP (estado)
    → ¿Es un hecho/regla/relación/concepto/entidad?
        → artefacto destino + status (FACT/INFERENCE/STRATEGY/UNKNOWN) + sources[]
```

Esta plantilla **no existió históricamente**; es una formalización propuesta para homologar futuras extracciones.

---

## 10. Rúbrica de evaluación y prioridad de fuentes

La priorización que se observa en el repositorio es **cualitativa** (no existió un scoring numérico en Fase 1; no se documenta ninguno retrospectivamente para no inventar una precisión que no hubo).

Criterios inferidos de las decisiones registradas (§4, `overview.md` §4, `sources.json`):

1. **Oficialidad** — las fuentes oficiales (The Pokémon Company, Nintendo) priman para anuncios, lore, fechas de lanzamiento y mecánicas declaradas.
2. **Especialización/detalle** — Serebii se declaró **fuente canónica para estructuras de juego** (movimientos, áreas, progresión, hábitats) por ser la más detallada y post-lanzamiento (§4).
3. **Corroboración independiente** — se privilegian los datos que coinciden en **dos fuentes independientes** (p. ej. Serebii + The Games Wiki para Trainer Rank C03 y desbloqueo de áreas C02).
4. **Proximidad al lanzamiento** — se prefiere información post-lanzamiento; la de pre-release se marca como cambiable (§5, GAP-15).
5. **Confianza declarada** — `sources.json` etiqueta cada fuente con `confidence` (high/medium/low), correlacionada con el nivel (oficial/wikis = alta, guías = media, comunidad = baja-media).
6. **Especificidad respecto al dato** — para un dato concreto (p. ej. conteo de etapas del TIC), la fuente que lo documenta explícitamente (Serebii `teaminitiationchallenge`) prima sobre recuentos implícitos (The Games Wiki fusionando etapas, C06).
7. **Verificabilidad/estado de publicación** — los datos de sitios de marketing sin verificación (RankedBoost) o fan sin apoyo (PokopiaCenter, pokopiawiki.site) se tratan como baja confianza y se descartan cuando contradicen a las canónicas.

**Uso de la jerarquía ante contradicción:** cuando dos fuentes se contradicen, el patrón real fue:
- preferir la fuente canónica/especializada (Serebii) corroborada por otra independiente;
- descartar la afirmación sin apoyo o de pre-release/marketing;
- si la evidencia disponible no permite decidir, **mantener `UNKNOWN`** en lugar de forzar una resolución (C04, C05, C10).

---

## 11. Procedimiento: contradicción vs GAP vs descarte

El siguiente esquema **formaliza retrospectivamente** el patrón observado en los artefactos; no se registró como una regla explícita durante Fase 1:

```text
Hallazgo ambiguo / incompleto
      │
      ├── Existe evidencia contradictoria de fuentes distintas
      │       ↓
      │   CONTRADICTION  (contradictions.json: claim_a vs claim_b, evidencia por lado,
      │                    fuentes[], estado, resolution_detail, impacto, recomendación)
      │
      ├── No existe evidencia suficiente (información ausente o tablas no publicadas)
      │       ↓
      │   KNOWLEDGE GAP  (gaps.md: categoría, por qué importa, estado OPEN/PARTIAL/RESOLVED)
      │
      └── Información irrelevante, fuera de alcance o sin respaldo verificable
              ↓
           DESCARTE  (p. ej. "423" RankedBoost C09, "Super/Hyper" C03, "Scrub" C08,
                      "40% restauración" PokopiaCenter C02; se documenta el descarte)
```

En la práctica de Fase 1:
- **A contradicción** iba lo que tenía afirmaciones incompatibles **con evidencia por ambos lados** (C01–C10).
- **A gap** iba lo que faltaba **por ausencia** (tablas numéricas no publicadas, contenido de DLC no anunciado, etc.).
- **A descarte** iba lo **irrelevante, sin respaldo verificable o claramente erróneo**; el descarte se anotó como parte de la resolución (p. ej. en C03/C08/C09).

---

## 12. Criterios generales utilizados para resolver contradicciones

Reconstrucción de los criterios a partir de las resoluciones ya registradas (C01–C10) y de §4. **No se reabren ni se cambian las resoluciones; solo se documenta el criterio subyacente:**

1. **Preferir la fuente canónica/especializada** corroborada (Serebii como canónica para estructuras de juego; validación cruzada con The Games Wiki).
2. **Preferir el acuerdo entre fuentes independientes** sobre una afirmación aislada (C03, C02).
3. **Descartar afirmaciones de marketing o pre-release sin corroboración** (C09 "423", C03 "Super/Hyper", C02 "40%").
4. **Distinguir contradicción de dato vs diferencia de criterio de inclusión** (C07: "12 base vs 14 con DLC" se resuelve como `RESOLVED_WITH_CRITERIA`, no como dato en pugna).
5. **Explicar el error de fuente cuando es identificable** (C06: TGW cuenta 8 por fusionar etapas; C09: RankedBoost).
6. **No forzar resolución**: cuando la evidencia no permite decidir, se mantiene `UNKNOWN` y se documenta (C04, C05, C10).
7. Cada resolución registra `resolution_detail` con la evidencia y el porqué, e `impact` + `recommendation`.

---

## 13. UNKNOWN: qué significa (C04, C05, C10)

Una contradicción queda `UNKNOWN` cuando la evidencia disponible en el momento no permitió decidir entre las afirmaciones. Es importante distinguir cuatro situaciones que **no son lo mismo**, y qué puede reconstruirse del repo para cada una:

- **"No encontramos evidencia"**: el `resolution_detail` de C04 y C05 dice literalmente *"Sin evidencia nueva"* y solo aporta datos indirectos (p. ej. la etapa 5 del TIC pide 5 Tinkagears / 50 Electricity). Esto indica que **se buscó y no se encontró** una tabla canónica publicada (§5: las tablas numéricas no están publicadas por fuentes oficiales).
- **"No se investigó"**: no hay constancia en el repo de que cada UNKNOWN se intentara resolver exhaustivamente; la búsqueda exacta por contradicción **no está logueada claim-por-claim**. Se declara esta limitación: no se puede afirmar con certeza qué páginas concretas se consultaron para C04/C05.
- **"La fuente no era accesible"**: sí está documentado para ciertos casos (§5): r/Pokopia bloqueado, wiki oficial de pago. Esto limita el acceso, pero no es la causa registrada específica de C04/C05/C10.
- **"La evidencia disponible no permitía decidir"**: C10 (diferencia de 1 día en fechas del evento Hoppip) se mantiene UNKNOWN por ambigüedad menor (posible zona horaria o diferencia de versión), no por falta de acceso.

**Conclusión documentada:** C04 y C05 son el caso "buscado y ausente" (tablas numéricas no publicadas), con la salvedad de que el detalle exacto de los intentos no se registró; C10 es el caso "evidencia insuficiente para decidir" (discrepancia menor). No se modifican sus resoluciones.

---

## 14. Limitaciones metodológicas conocidas

Tras este cierre documental siguen existiendo los siguientes límites del **proceso de Fase 1** (no son errores del dataset, sino limitaciones de trazabilidad del proceso):

- **Extracción histórica no registrada claim-por-claim**: el método real no se logueó paso a paso; §9 es una reconstrucción, no un registro contemporáneo.
- **Ausencia de snapshots/quotes**: no hay cita textual ni copia del pasaje fuente que sustenta cada afirmación; re-verificar exige re-fetchear las URLs.
- **Provenance de granularidad variable**: reglas y relaciones traen `sources[]` + `status`; el glosario solo `sources[]`; el catálogo de Pokémon tiene **provenance global** (una única fuente por tabla) sin trazabilidad por fila.
- **Clasificación FACT todavía gruesa**: el `status` es por sentencia agrupada, no por claim; `FACT` se usa de forma amplia y no distingue hechos de consolidaciones/decisiones.
- **UNKNOWN sin log de intentos**: no se documentó exactamente qué se buscó para cada contradicción no resuelta.

Estas limitaciones quedan **registradas como posibles mejoras futuras** (provenance por fila, quotes/snapshots, jerarquía fina de evidencia, `status` en glosario, rediseño del catálogo), no como pendientes obligatorios de esta fase.
