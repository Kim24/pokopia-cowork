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
