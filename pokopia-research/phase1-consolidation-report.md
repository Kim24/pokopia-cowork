# Reporte de Consolidación — Fase 1 (Domain Research)

> Fecha: 2026-08-15. Alcance: consolidación del Domain Research antes de Gold Dataset / arquitectura.
> Prioridades: gaps P0 (GAP-03) y contradicciones C02/C03; catálogo de 300 Pokémon; revisión de relaciones/reglas.
> Sin commits ni push.

---

## 1. Método

- Verificación contra fuentes canónicas de Serebii (páginas principales) y The Games Wiki.
- Páginas nuevas verificadas: `availablepokemon`, `locations`, `gameplay`, `locations/witheredwastelands`, `environmentlevel`, `importantrequests`, `teaminitiationchallenge` (Serebii) y `pokemon-list`, `requests` (The Games Wiki).
- Ninguna contradicción se eliminó sin evidencia: se documentó la resolución o se mantuvo UNKNOWN.
- Catálogo de Pokémon: extracción íntegra de Serebii + validación cruzada contra The Games Wiki.

---

## 2. Qué quedó CONFIRMADO (nuevo o validado)

1. **Roster: 300 Pokémon** (Pokédex principal). Serebii lista 308 entradas #001–#300 (los extra son duplicados por variantes de forma); The Games Wiki lista 300 numerados + 7 sin número + 4 de evento. **C09 resuelto** (el "423" era un error de marketing).
2. **31 especialidades** exactas (Appraise…Yawn). **C08 resuelto**; "Scrub" se elimina (no aparece en el roster).
3. **7 localizaciones**: Withered Wastelands, Bleak Beach, Rocky Ridges, Sparkling Skylands, Palette Town, Cloud Island y Bubbly Basin (DLC); Dream Islands aparte. **C01 resuelto**.
4. **Lore**: Kanto "long after the events of Pokémon Heart Gold & SoulSilver"; Withered Wastelands = antigua Ciudad Fucsia; el objetivo de la zona inicial es provocar lluvia. Viaje entre áreas volando entre "Homes".
5. **Trainer Ranks: No Rank → Great → Ultra → Master** (Serebii + The Games Wiki). **C03 resuelto** ("Super"/"Hyper" sin evidencia). Great→Bleak Beach+Rocky Ridges, Ultra→Sparkling Skylands, Master→Master Ball en el Huge Building.
6. **Desbloqueo por área** (C02 resuelto): Important Request + reconstruir el Pokémon Center + Environment Level 5; las puertas entre áreas se abren por Trainer Rank.
7. **Environment Level**: 1→10 por área; sube con Comfort, Requests y edificios/kits; **baja al quitar Pokémon** (re-bloquea ítems/Challenges); Lv.5 = regalo de ítems, Lv.10 = recetas. **GAP-01/GAP-02 resueltos a nivel mecánico**.
8. **Comfort Level**: 5 niveles (Iffy→Average→Nice→Great→Awesome); sin hábitat = Comfy 0; hábitat preferido y casas suben más rápido; objetos que disgustan bajan el comfort.
9. **Team Initiation Challenge: 9 retos** (Serebii, tabla completa), etapa 1 = 5 Leppa Berries → Bouldery Badge; el edificio es un cohete de Team Rocket. **C06 resuelto** (TGW cuenta 8 fusionando las etapas 8–9).
10. **Legendarios**: 12 en el juego base; 14 con DLC (Manaphy, Phione). **C07 resuelto con criterio**.
11. **Recursos de Withered Wastelands** (Serebii): Gold Ore (también aquí, no exclusivo de Rocky Ridges), Fresh Carrot, 6 berries, tesoros (Lost Relics, muñecos), fósiles (Shield/Armor/Wing).
12. **Tablas de desbloqueo de tienda/PC por área y Environment Level** extraídas (incluye kits de Cloud Island y Bubbly Basin).

---

## 3. Qué CAMBIÓ respecto a Fase 1

- **`contradictions.json`**: C01, C02, C03, C06, C08 → RESOLVED (con `resolution_detail` y evidencia); C07 → RESOLVED_WITH_CRITERIA; C09 mantenido RESOLVED_FAVORING_A; añadida **C10** (fechas del evento Hoppip, UNKNOWN menor).
- **Comfort Level**: de "6 estados (No Home→Awesome)" a **5 niveles + Comfy 0** (sin hogar). Afecta a `pokemon.md`, `progression.md`, `rules.json` (RULE024).
- **Desbloqueo de áreas**: se añade la condición triple (Important Request + Pokémon Center + Env Level 5) sobre el criterio previo de solo rango. Afecta a `areas.md`, `progression.md`, `rules.json` (RULE025), `relationships.json` (R034).
- **Especialidades**: de "29 (en disputa)" a **31 confirmadas**; eliminado "Scrub". `pokemon.md` §2.
- **Gold Ore**: de "exclusivo de Rocky Ridges" a "Rocky Ridges y Withered Wastelands". `resources.md`, `rules.json` (RULE035), `areas.md` §3.
- **TIC**: de "8 vs 9 en disputa" a **9 retos** (Serebii canónico); etapa 1 = 5 Leppa Berries (no 10). `progression.md` §6, `rules.json` (RULE036).
- **Legendarios**: de "12 vs 14 en disputa" a "12 base / 14 con DLC"; Manaphy pasa a tener método documentado (Ocean Temple). `pokemon.md` §5.
- **Catálogo**: nuevo archivo `entities/pokemon-catalog.md` (308 entradas) — antes no existía una tabla íntegra en el paquete.
- **Fuentes**: `sources.json` pasa de 64 a **69 fuentes** (SRC065–SRC069).
- **Conteo de áreas**: de "6 regiones (prensa)" a **7 localizaciones** canónicas de Serebii.

---

## 4. Qué sigue siendo DESCONOCIDO (con intento documentado)

- **C04 — Tasa Iron Ingot → Tinkagear** (2:1 vs 1:3): sin evidencia nueva; solo dato indirecto (TIC etapa 5 pide 5 Tinkagears).
- **C05 — Límites eléctricos** (64 generadores / 1024 objetos): sin evidencia nueva; dato indirecto (TIC etapa 5 pide 50 Electricity).
- **C10 — Fechas del evento "More Spores for Hoppip"** (Serebii 10–25 mar vs TGW 9–24 mar): diferencia de 1 día, menor; mantener como rango 9–25 mar.
- **GAP-01 — Umbrales numéricos exactos** de puntos de Environment/Comfort por nivel: mecanismo documentado, cifras no publicadas.
- **GAP-04 — Costes exactos de materiales** de los Building Kits (las tablas de desbloqueo ya están extraídas).
- **GAP-05 — Tabla íntegra de las 24 recetas** (nombres e ingredientes exactos).
- **GAP-06 — Tabla de valores de trueque (Trade)**.
- **GAP-07 — Generación/consumo eléctrico exactos** por aparato.
- **Discrepancias de especialidades entre Serebii y TGW** (p. ej. Victreebel, Pidgeot, Porygon-Z): Serebii se adopta como canónico; las diferencias quedan anotadas en `pokemon.md` §7.

---

## 5. Artefactos actualizados en Fase 1

| Artefacto | Cambio |
|---|---|
| `entities/pokemon-catalog.md` | NUEVO — catálogo íntegro (308 entradas) + resumen de duplicados y "???" |
| `sources/sources.json` | +5 fuentes (SRC065–069) |
| `contradictions/contradictions.json` | C01/C02/C03/C06/C08 resueltas; C07 con criterio; +C10; C04/C05 UNKNOWN documentado |
| `knowledge-gaps/gaps.md` | GAP-01/02 resueltos o parciales; GAP-03 resuelto; GAP-04 parcial; prioridades renovadas |
| `entities/pokemon.md` | 31 especialidades, "???", C07 criterio, Manaphy, catálogo referenciado |
| `entities/resources.md` | Gold Ore en Wastelands, Fresh Carrot, berries, tesoros/fósiles |
| `entities/areas.md` | 7 localizaciones, requisitos por área (C01/C02 resueltos), recursos de Wastelands |
| `entities/progression.md` | Trainer Rank/Environment/Comfort/TIC actualizados a la evidencia de Fase 1 |
| `rules/rules.json` | RULE021/22/24/25/35/36 revisadas |
| `relationships/relationships.json` | R013/R033 revisadas; +R034, +R035 |

Pendiente de revisión en próximas fases: `research-notes.md` / `README.md` (logs), `domains.md`, `concepts/glossary.json` (si algún término cambió).
