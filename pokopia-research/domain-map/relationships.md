# Pokopia — Domain Map: Mapa de relaciones (alto nivel)

> Este documento describe el **grafo conceptual** del dominio tal como se entiende tras la Fase 1.
> Las relaciones formales con tipos e IDs se encuentran en `relationships/relationships.json`.
> Legibilidad: `A --relación--> B` (con la fuente que la soporta).

---

## 1. Núcleo entidad-relación

```
DITTO (jugador)
 ├─ interpreta_a ──▶ Pokémon (Ditto es una especie de la Pokédex) [SRC043]
 ├─ se_transforma_en ──▶ Humano (premisa) [SRC001]
 ├─ conoce ──▶ Profesor Tangrowth [SRC003]
 └─ usa ──▶ Movimientos (aprendidos de Pokémon) [SRC016]

POKÉMON
 ├─ posee ──▶ Tipos (hasta 2) [SRC043]
 ├─ posee ──▶ Especialidad(es) (1-2) [SRC042]
 ├─ requiere ──▶ Hábitat específico para aparecer [SRC017]
 ├─ atrae_a ──▶ Otros Pokémon (Hábitats atraen especies) [SRC017]
 ├─ realiza ──▶ Requests [SRC034]
 ├─ tiene ──▶ Comfort Level ──▶ influye ──▶ Environment Level [SRC023]
 ├─ tiene ──▶ Friendship (vínculo con Ditto) [SRC024]
 └─ tiene ──▶ Flavor favorito [SRC033]

HÁBITAT
 ├─ se_construye_con ──▶ Objetos/materiales (crafting) [SRC017]
 ├─ ubicado_en ──▶ Área [SRC017]
 ├─ activo_por ──▶ Hora del día / clima [SRC017]
 └─ a veces requiere ──▶ Electricidad [SRC043]

MOVIMIENTO
 ├─ aprendido_de ──▶ Pokémon concreto [SRC016]
 ├─ consume ──▶ PP [SRC016]
 ├─ potencia_por ──▶ Comida (tipo de receta) [SRC016, SRC033]
 └─ aplica_efecto ──▶ Mundo (terreno, agua, rocas, aire) [SRC040]
```

## 2. Relaciones entre sistemas

| Relación | Detalle | Fuente |
|---|---|---|
| Agricultura → Ingredientes | Cultivos (Beans, Wheat, Tomatoes, Potatoes, Leafy Greens) alimentan recetas | [SRC032, SRC045] |
| Ingredientes → Recetas → Comida | 24 recetas en 4 tipos; 5 sabores | [SRC033, SRC045] |
| Comida → Movimientos | Tipo de comida potencia un movimiento (PP) | [SRC016] |
| Comida → Comfort | Comida del flavor favorito sube Comfort | [SRC033, SRC023] |
| Comfort → Environment Level | Suma de Comfort de Pokémon del área sube el nivel | [SRC023] |
| Environment Level → Desbloqueos | PC Shop recipes, semillas, Building Kits, área final | [SRC023, SRC032] |
| Requests → Trainer Rank | Important Requests suben el rango | [SRC034, SRC019] |
| Trainer Rank → Áreas | Puertas verdes requieren rango + requests | [SRC034] |
| Especialidades → Materiales | Cada especialidad procesa ciertos materiales | [SRC037, SRC042] |
| Materiales → Crafting → Objetos | Cadenas de fabricación (ingot, lumber, glass…) | [SRC037] |
| Crafting → Hábitats/Edificios | Building Kits consumen materiales | [SRC037] |
| Electricidad → Máquinas/Hábitats | Generadores alimentan items eléctricos | [SRC028] |
| Especialidad Generate → Energía | Pokémon energizan temporalmente objetos | [SRC057] |
| Legendarios → Environment Level | Suben el nivel más rápido (al subir su Comfort) | [SRC023, SRC045] |
| Dream Islands → Recursos raros | Stardust, Pokemetal, plumas, legendarios | [SRC022, SRC047] |
| Dream Islands → Eventos | Moneda de evento se obtiene allí | [SRC029] |
| DLC (Bubbly Basin) → Movimientos | Dive (aprendido de Manaphy, update 2.0.0) | [SRC013] |
| DLC → Cocina | Smoothies potencian Surf | [SRC013] |

## 3. Relaciones narrativas / de lore

| Relación | Detalle | Fuente |
|---|---|---|
| Mundo → Desolación | El mundo se ha marchitado; los humanos ya no están | [SRC060] |
| Ditto → Humano | Ditto despertó transformado en humano | [SRC001] |
| Profesor Tangrowth → Mundo | Único residente antes de Ditto; mentor | [SRC003, SRC060] |
| Áreas → Ciudades de Kanto | Wasteland≈Fuchsia, Beach≈Vermilion, Ridges≈Pewter, Skylands≈Celadon/Saffron, Palette≈Pallet | [SRC044, SRC061] |
| NPCs → Área | Peakychu en Bleak Beach; Chef Dente en Rocky Ridges; DJ Rotom en Skylands; Tinkmaster/PM en Rocky Ridges | [SRC036, SRC044] |
| Requests importantes → Áreas | "Yawn Up a Storm" (Wasteland), "Brighten Things Up" (Beach), "Time to Party" (Ridges), "Rebuild the Huge Building" (Skylands) | [SRC034, SRC044] |

## 4. Relaciones de gameplay clave para razonamiento

**Cadenas causales (buenas candidatas para multi-hop):**

1. `Semillas (Env Level 3) → Cultivar → Ingrediente → Receta → Comida (flavor) → Comfort de Pokémon → Environment Level del área`
2. `Hábitat → Requisito de luz/clima → Pokémon aparece → Request → Trainer Rank → Puerta de área`
3. `Material (región) → Especialidad → Procesado → Componente → Edificio/hábitat`
4. `Generador (fuente) → Límites (VERSIONADOS: 64 gen/512 items en 1.0.x; 64 gen/1024 items en 1.1.0–1.1.1; 128 gen excl. furnaces/1024 items en 2.0.0+; ver C05) → Máquina/hábitat eléctrico`
5. `Muñeco (doll) → Dream Island concreta → Recurso raro / legendario`

**Relaciones condicionales / con matiz:**
- `Sombra ↔ Pokémon nocturnos`: la luz/oscuridad **invierte** las horas de aparición de los Pokémon [SRC017].
- `Rototiller ↔ tierra seca`: no funciona si el suelo está seco; requiere regar primero [SRC032].
- `Comida ↔ PP`: la comida restaura PP **y** potencia movimientos durante un tiempo [SRC016, SRC033].
- `Legendarios ↔ mejoras`: subir su Comfort aporta **más** Environment Level que un Pokémon normal [SRC023].

## 5. Relaciones inciertas / en conflicto (resumen)

| Relación en disputa | Postura A | Postura B | Referencia cruzada |
|---|---|---|---|
| Nº de áreas principales | 4 (+ Palette) | 6 regiones | C01 |
| Desbloqueo de áreas | Por Trainer Rank + requests | Por % de restauración (40%) | C02 |
| Nombres de Trainer Rank | Great / Ultra / Master | Super / Hyper | C03 |
| Conversión Ingot→Tinkagear | 2:1 | 1:3 | C04 |
| Límites eléctricos | 64 gen / 1024 items | otras cifras | C05 — PARTIALLY CONFIRMED (Fase 1.5): versionado 64→128 gen; 512→1024 items |
| Etapas del Team Initiation Challenge | 8 | 9 | C06 |
| Nº de legendarios/míticos | 12 | 14 | C07 |

Detalle en `contradictions/contradictions.json`.

## 6. Cómo se modelarán las relaciones (de cara a Fase 2)

- Tipos de relación candidatos: `aprende_de`, `requiere`, `construido_con`, `aparece_en`, `potencia`, `restaura`, `atrae`, `influye_en`, `desbloquea`, `procesa`, `ubicado_en`, `ofrece`, `comercia`.
- Representación futura (a decidir en Fase 2): triplas `(sujeto, predicado, objeto)` + atributos (fuente, confianza, estado FACT/INFERENCE).
- La resolución de contradicciones (C01–C07) será un input directo para el Gold Dataset.
