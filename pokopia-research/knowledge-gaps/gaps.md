# Pokopia — Knowledge Gaps

> Lagunas de conocimiento detectadas durante la Fase 1 (investigación y consolidación). Se clasifican por impacto y por el tipo de acción necesaria.

---

## 1. Gaps de datos estructurales (se necesita una fuente de datos completa)

| ID | Gap | Por qué importa | Estado |
|---|---|---|---|
| GAP-01 | Umbrales numéricos del Environment Level (puntos de Comfort por Pokémon/nivel) | No publicados por fuentes oficiales; necesarios para razonar cuantitativamente sobre progresión | PARTIAL — mecanismo documentado (1→10 por área, sube con Comfort/Requests/edificios, baja al quitar Pokémon) [SRC023, SRC066]; los puntos exactos por nivel siguen sin publicarse |
| GAP-02 | Mecánica exacta de bajada del Environment Level | Descrita cualitativamente ("puede bajar") sin detalle de condiciones | RESOLVED — quitar Pokémon baja la puntuación del área y puede bajar el Environment Level, re-bloqueando ítems no comprados y Challenges [SRC023] |
| GAP-03 | Lista completa de los 300 Pokémon con atributos (tipos, especialidades, hábitats, flavors) | Serebii tiene un Habitat Dex, pero no se había consolidado una tabla íntegra en este paquete | RESOLVED — `entities/pokemon-catalog.md` con 308 entradas Serebii (#001–#300, 31 especialidades) y validación cruzada contra The Games Wiki (300 numerados + 7 sin número + 4 de evento) |
| GAP-04 | Lista completa de Building Kits y sus costes de materiales | Solo se conocen ejemplos (Freezing Chamber, Abandoned Power Plant, Altar of Flame) | PARTIAL — tablas de desbloqueo por área y nivel de Environment extraídas (incluye los kits); los costes exactos de materiales siguen sin consolidar |
| GAP-05 | Lista completa de las 24 recetas (nombres e ingredientes exactos) | Las fuentes describen el sistema (4 tipos × 6 variantes) pero no la tabla íntegra | OPEN — nuevos ingredientes conocidos en Fase 1 (15 Leppa Berry, 15 Wheat, 15 Beans, 5 Honey para 'Time to Party'; curry cocinado en 6 min reales) |
| GAP-06 | Valores de trueque (Trade) de cada objeto | Se sabe que es un sistema de puntos de valor, pero no se conoce la tabla | OPEN |
| GAP-07 | Puntos exactos de energía de cada generador y consumo de cada objeto eléctrico | Cifras parciales (Mini Gen 5, Windmill 10/20, Waterwheel 20, Furnace 30); falta el consumo por aparato; el output del Furnace está en disputa (C11) | OPEN — nuevo dato indirecto: etapa 5 del TIC requiere 50 Electricity + 10 Crystal Fragments + 5 Tinkagears |

## 2. Gaps de cobertura temática (aspectos poco documentados)

| ID | Gap | Por qué importa | Estado |
|---|---|---|---|
| GAP-08 | Mecánica completa de los Mystery Gifts por Internet (frecuencia, caducidad, contenidos) | Solo se conocen ejemplos (Ditto Rug) | OPEN |
| GAP-09 | Contenido exacto de las partes 2 y 3 del Expansion Pass | Anunciado genéricamente (finales 2026 / 2027) | OPEN |
| GAP-10 | Lista completa de eventos 2026 y sus fechas/pokémon | Documentados 7; es probable que haya más a lo largo del año | OPEN |
| GAP-11 | Requisitos detallados de los legendarios (Building Kits, campanas, slates) | Se conocen los métodos generales, no los pasos exactos | OPEN |
| GAP-12 | Detalle de los Challenge del PC (lista completa, recompensas) | Solo se sabe que dan Life Coins | OPEN |

## 3. Gaps de confianza (contradicciones sin resolver — detalle en contradictions.json)

| ID | Contradicción | Estado |
|---|---|---|
| C01 | Nº de áreas (4 vs 6) | RESOLVED — 7 localizaciones (Serebii) |
| C02 | Mecánica de desbloqueo de áreas (Trainer Rank vs % de restauración / 'Hyper' rank) | RESOLVED — Trainer Rank + Important Request + Pokémon Center + Env Level 5 |
| C03 | Nombres de Trainer Ranks (Great/Ultra/Master vs Super/Hyper) | RESOLVED — No Rank → Great → Ultra → Master |
| C04 | Tasa Iron Ingot → Tinkagear (2:1 vs 1:3) | UNKNOWN |
| C05 | Límites eléctricos (64 gen/1024 items vs otros) | PARTIALLY CONFIRMED (Fase 1.5) — versionado: 1.0.x=64 gen/512 items; 1.1.0–1.1.1=64 gen/1.024 items; 2.0.0+=128 gen excl. furnaces/1.024 items. Semántica de furnaces y tope de 256 transmisores: UNKNOWN |
| C06 | Etapas del Team Initiation Challenge (8 vs 9; 5 vs 10 Leppa Berries) | RESOLVED — 9 retos (Serebii); etapa 1 = 5 Leppa |
| C07 | Nº de legendarios (12 vs 14) | RESOLVED_WITH_CRITERIA — 12 base; 14 con DLC (Manaphy, Phione) |
| C08 | Nº de especialidades (29 vs 31+) | RESOLVED — 31 (sin 'Scrub') |
| C09 | Roster (300 vs 423) | RESOLVED_FAVORING_A — 300 |
| C10 | Fechas evento 'More Spores for Hoppip' (10–25 vs 9–24 mar 2026) | UNKNOWN (diferencia de 1 día; menor) |

## 4. Gaps de acceso a fuentes

| ID | Gap | Estado |
|---|---|---|
| GAP-13 | Reddit r/Pokopia bloqueado directamente (solo accesible vía prensa) | OPEN — usar prensa (Kotaku, Eurogamer) y añadir confianza baja |
| GAP-14 | La wiki oficial de Pokopia (pokopia.wiki/wiki) requiere suscripción/pago para contenido completo | OPEN |
| GAP-15 | Fechas de publicación de algunas guías no verificadas; el juego se lanza el 5 mar 2026 y puede que alguna información sea de pre-release (cambiable) | OPEN — priorizar fuentes post-lanzamiento |

## 5. Prioridades para próximas fases (tras consolidación Fase 1)

Resueltos en Fase 1: GAP-02, GAP-03, C01, C02, C03, C06, C07 (con criterio), C08, C09. Parciales: GAP-01, GAP-04. **Fase 1.5: C05 → PARTIALLY CONFIRMED (versionado; restos UNKNOWN: semántica de furnaces, tope de 256 transmisores).**

1. **P1 — GAP-05**: tabla de recetas completa (los ingredientes exactos de las 24 recetas siguen sin consolidar).
2. **P1 — GAP-04**: costes de materiales de todos los Building Kits (las tablas de desbloqueo ya están extraídas).
3. **P1 — GAP-07**: tabla de electricidad (generación/consumo exactos; incluye resolver C11).
4. **P2 — C04, C10**: resolver contradicciones restantes con capturas de partida o guías canónicas.
5. **P2 — C05 (restos)**: verificar en partida la semántica de 'excl. furnaces' (¿dentro de los 128, tope propio o exentos?) y el tope de 256 transmisores.
6. **P2 — C11**: output exacto del Furnace (30 vs 15–25).
7. **P2 — GAP-01**: umbrales numéricos de Environment/Comfort (probablemente requieran experimentación en partida).
