# pokopia-research — Fase 1 (Domain Research y Consolidación)

> **Pokopia Intelligence Lab — Domain Research Agent**
> Fase 1 · Domain Research: Mapa de conocimiento del dominio **Pokémon Pokopia** (vida de simulación, Nintendo Switch 2).
> Fase 1 · Consolidación: (catálogo de 300 Pokémon, contradicciones P0, progresión de áreas/rank).
> Fecha: 2026-08-15 · Repo: `D:\repositorios\pokopia-cowork`

---

## Executive Summary

Pokémon Pokopia es el **primer juego de simulación de vida** de la franquicia Pokémon, publicado por The Pokémon Company y Nintendo, desarrollado por **The Pokémon Company, GAME FREAK inc. y KOEI TECMO GAMES**, y lanzado el **5 de marzo de 2026** para **Nintendo Switch 2**.

El jugador interpreta a un **Ditto transformado en humano** que despierta en un Kanto abandonado y marchito (post **HeartGold & SoulSilver**), conoce al **Profesor Tangrowth** (el último habitante) y reconstruye la zona construyendo hábitats, cultivando, cocinando, recolectando y cumpliendo peticiones. **No hay combates**: toda la progresión es de mundo, con un sistema rico de entidades interconectadas que lo convierte en un caso excelente para razonamiento multi-hop.

Este paquete entrega un **mapa de conocimiento trazable y verificable** (hechos con fuente, jerarquía de evidencia FACT/INFERENCE/STRATEGY/UNKNOWN): inventario de **69 fuentes**, **catálogo íntegro de 308 entradas Pokémon** (`entities/pokemon-catalog.md`, validado contra The Games Wiki), catálogo de entidades y sistemas, **36 reglas**, **35 relaciones formales**, **10 contradicciones documentadas (6 resueltas en Fase 1)**, knowledge gaps y **28 preguntas candidatas** para un futuro Gold Dataset.

> 📄 **Reporte de consolidación (Fase 1)**: ver `phase1-consolidation-report.md` (qué quedó confirmado, qué cambió, qué sigue desconocido).

---

## Domain Map

El mundo se compone de **7 localizaciones** (C01 resuelto) — 4 áreas de historia inspiradas en ciudades de Kanto, una zona sandbox (Palette Town), una isla online (Cloud Island) y un pueblo submarino de DLC (Bubbly Basin):

| Área | Inspiración | Hito principal |
|---|---|---|
| Withered Wastelands | Ciudad Fucsia (confirmado) | "Yawn Up a Storm!" |
| Bleak Beach | Ciudad Carmín | "Brighten Things Up!" |
| Rocky Ridges | Ciudad Plateada | "Time to Party!" |
| Sparkling Skylands | Celadon + Saffron | "Rebuild the Huge Building!" |
| Palette Town | Ciudad Paleta | sandbox (Eevee) |
| Cloud Island | — (online) | Virtual Mode / Link Play |
| Bubbly Basin (DLC) | — | pueblo submarino (Dive) |

**Sistemas principales** (detalle en `domain-map/domains.md`):
1. Pokémon y Pokédex (300)
2. Movimientos de Ditto (15)
3. Especialidades (~31)
4. Hábitats (209) y aparecimiento
5. Cocina (24 recetas, 5 sabores)
6. Agricultura (5 cultivos, riego, Grow)
7. Recursos y crafting (cadenas de procesado)
8. Construcción y terraforming
9. Economía (Life Coins + trueque)
10. Electricidad y agua (generadores, límites)
11. Áreas y puertas
12. Requests (misiones)
13. Progresión (Trainer Rank, Environment Level, Comfort, Friendship)
14. NPCs (7 con nombre)
15. Legendarios/míticos (12–14)
16. Dream Islands y Cloud Islands
17. Multiplayer (Link Play, GameShare)
18. Eventos y Mystery Gifts
19. DLC (Expansion Pass de 3 partes)
20. Customización
21. Mini-juegos
22. Sensores y automatización (comunidad)

**Mapa de conexiones** (resumen): Pokémon → (aprende movimiento) → Ditto → (movimientos) → Mundo · Pokémon → (especialidad) → Materiales → Crafting → Hábitats/Edificios · Cultivos → Ingredientes → Recetas → Comida → (flavor) → Comfort → Environment Level → Desbloqueos · Requests → Trainer Rank → Puertas/Áreas.

---

## Entities

Catálogos por tipo (detalle en `entities/`):

- **Pokémon** (`entities/pokemon.md`): identidad, especialidades (**31 confirmadas**, C08), movimientos que Ditto aprende (15), legendarios/míticos (**12 base / 14 con DLC**, C07), Pokémon de evento. Catálogo íntegro en `entities/pokemon-catalog.md` (308 entradas, validado).
- **Áreas** (`entities/areas.md`): las 7 localizaciones con inspiración Kanto, requisitos de acceso (**Important Request + Pokémon Center + Env Level 5**, C02) y contenido.
- **NPCs** (`entities/npcs.md`): Profesor Tangrowth, Peakychu, Chef Dente, Mosslax, Smearguru, DJ Rotom, Tinkmaster + otros singulares (Eevee, Drifloon, Manaphy, Porygon).
- **Food & Cooking** (`entities/food.md`): 4 estaciones, 4 tipos × 6 variantes = 24 recetas (+ smoothies DLC), 5 sabores, efectos sobre movimientos y Comfort.
- **Resources** (`entities/resources.md`): materiales base, cadenas de procesado (INPUT→OUTPUT con especialidad/equipo), regionalidad, agricultura.
- **Progression** (`entities/progression.md`): Trainer Rank (No Rank → Great → Ultra → Master, C03), Environment Level (1–10), Comfort (**5 niveles + Comfy 0**), Friendship, PP, Team Initiation Challenge (**9 retos**, C06), economía.

**Glosario de conceptos**: `concepts/glossary.json` (45 términos).

---

## Relationships

- Mapa conceptual de alto nivel: `domain-map/relationships.md`.
- **35 relaciones formales** (triplas sujeto/predicado/objeto con fuente y estado FACT/INFERENCE): `relationships/relationships.json`.
- Relaciones clave: `aprende_de` (Ditto↔Pokémon), `potencia` (comida↔movimientos), `influye_en` (Comfort→Environment Level), `desbloquea` (Trainer Rank→áreas), `requiere` (área→Request+Centro+Env Lv.5), `procesa` (especialidad→materiales), `exclusiva_de` (especialidades de NPC), `lleva_a` (Drifloon→Dream Islands), `gate_de` (Bubbly Basin).

---

## Rules

**36 reglas del juego** documentadas en `rules/rules.json` (estado FACT/INFERENCE), categorizadas en: mundo/estructura, jugador, Pokédex, reclutamiento, aparición, movimientos, especialidades, comida/cocina, agricultura, economía, electricidad, progresión, áreas, multiplayer, eventos, Dream Islands, DLC, crafting.

Ejemplos destacados:
- No hay combates; la progresión es de mundo (RULE001).
- Los Pokémon se reclutan con hábitats, no con Poké Balls (RULE005).
- La aparición depende de hora/clima/luz (RULE006).
- Cada tipo de comida potencia un movimiento y restaura PP (RULE010).
- Semillas desbloqueables con Environment Level 3 (RULE014).
- Límite eléctrico: 64 generadores y 1024 objetos eléctricos (RULE019, INFERENCE).
- Trainer Rank sube solo con Important Requests (RULE021).

---

## Sources

Inventario completo con esquema (source_id, title, url, publisher, source_type, publication_date, retrieved_at, topics, entities, confidence) en **`sources/sources.json`**: **64 fuentes (SRC001–SRC064)**.

| Nivel | Tipo | Fuentes | Confianza |
|---|---|---|---|
| 1 | Oficial | press.pokemon.com, pokopia.pokemon.com, nintendo.com, Nintendo Support | Alta |
| 2 | Wikis/BD | Serebii, Bulbapedia, The Games Wiki, Fextralife | Alta |
| 3 | Guías | Nintendo Life, VGC, Polygon, Eurogamer, Game8, Dexerto, GamesRadar, Pocket Tactics, IGN, GameRant, pokopiaguide, thegamer, rectifygaming, Vandal, popcultdaily, pokopia.center, pokopiamap | Media-Alta |
| 4 | Comunidad | r/Pokopia (vía prensa), Kotaku, Eurogamer, YouTube | Baja-Media |

**Fuentes canónicas recomendadas**: Serebii (estructuras de juego), press.pokemon.com (oficial), The Games Wiki (datos de juego).

---

## Contradictions

**10 contradicciones** documentadas en `contradictions/contradictions.json` (6 resueltas en Fase 1; resolución con evidencia en `phase1-consolidation-report.md`):

| ID | Tema | A vs B | Estado |
|---|---|---|---|
| C01 | Nº de áreas | 4 vs 6 | RESUELTA — 7 localizaciones |
| C02 | Desbloqueo de áreas | Trainer Rank vs % de restauración / 'Hyper' | RESUELTA — Request + Centro + Env Lv.5 |
| C03 | Nombres de Trainer Rank | Great/Ultra/Master vs Super/Hyper | RESUELTA — No Rank→Great→Ultra→Master |
| C04 | Tasa Tinkagear | 2:1 vs 1:3 | UNKNOWN |
| C05 | Límites eléctricos | 64/1024 vs otros | UNKNOWN |
| C06 | Etapas del TIC | 8 vs 9 (5 vs 10 Leppa) | RESUELTA — 9 retos; etapa 1 = 5 Leppa |
| C07 | Nº de legendarios | 12 vs 14 | RESUELTA CON CRITERIO — 12 base / 14 con DLC |
| C08 | Nº de especialidades | 29 vs 31+ | RESUELTA — 31 |
| C09 | Roster | 300 vs 423 | RESUELTA — 300 |
| C10 | Fechas evento Hoppip | 10–25 vs 9–24 mar 2026 | UNKNOWN (menor) |

---

## Knowledge Gaps

Gaps en `knowledge-gaps/gaps.md`, priorizados tras la consolidación de Fase 1:
- **Resueltos/parciales en Fase 1**: GAP-02 (mecánica de bajada del Env Level), GAP-03 (catálogo 300 ✅ `pokemon-catalog.md`), GAP-01 (mecánica Env Level, faltan cifras), GAP-04 (tablas de desbloqueo ✅, faltan costes).
- **P1**: tabla de 24 recetas (GAP-05); costes de Building Kits (GAP-04); tabla de electricidad (GAP-07).
- **P2**: umbrales numéricos de Environment Level (GAP-01), tabla de trueque (GAP-06), contenido de DLC 2/3 (GAP-09), C04/C05/C10.

---

## Candidate Questions

**28 preguntas candidatas** en `candidate-questions/questions.md` con metadatos completos (concepts_required, entities_required, relationships_required, sources_required, requires_multi_hop, requires_structured_data, requires_case_memory, expected_difficulty, why_this_question_is_interesting).

Distribución por categoría:
- Direct Lookup: Q01–Q05 (5)
- Multi-hop: Q06–Q11 (6)
- Constraint: Q12–Q15 (4)
- Comparison: Q16–Q18 (3)
- Contradiction: Q19–Q22 (4)
- Novel/Creative: Q23–Q26 (4)
- Meta: Q27–Q28 (2)

---

## Recommended Next Step

**Fase 1 (consolidación) completada.** Opciones a discutir:

1. ✅ **Consolidar el catálogo completo de 300 Pokémon** (GAP-03) y **resolver las contradicciones P0** (C02/C03) — hecho en Fase 1 (ver `phase1-consolidation-report.md`).
2. **Definir el formato del Gold Dataset** (semilla: `candidate-questions/questions.md`) y su método de scoring.
3. **Elegir la representación técnica** del conocimiento (JSON/SQL/CSV/Markdown/vector/GraphDB) — este paquete es agnóstico y compatible con cualquiera.
4. **Decidir el alcance de la siguiente fase**: solo datos, o ya diseñar el agente/el gold dataset.

No se ha realizado ningún commit ni push (el usuario revisa antes).
