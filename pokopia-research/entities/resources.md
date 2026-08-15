# Pokopia — Entities: Recursos, materiales y crafting

> Catálogo de recursos del mundo, cadenas de procesado y fabricación.

---

## 1. Materiales base (recolección)

| Material | Origen / notas | Fuente |
|---|---|---|
| Honey | Especialidad Gather Honey (Vespiquen); árboles | [SRC042] |
| Sturdy Stick | árboles / suelo | [SRC048, SRC068] |
| Stones | suelo / rocas | [SRC048, SRC068] |
| Leaf | árboles / suelo | [SRC048, SRC068] |
| Small Log | árboles (movimiento Cut) | [SRC048, SRC037, SRC068] |
| Fresh Carrot | suelo (Withered Wastelands) | [SRC068] |
| Vine Rope | — | [SRC048, SRC068] |
| Glowing Mushroom | zonas oscuras (cuevas; Wastelands) | [SRC048, SRC068] |
| Twine | — | [SRC048] |
| Sea Glass Fragments | Bleak Beach | [SRC048] |
| Seashell | Bleak Beach | [SRC048] |
| Nonburnable Garbage | suelo / recolección | [SRC048] |
| Squishy Clay | suelo (Wastelands) | [SRC048, SRC068] |
| Fluff | — | [SRC048] |
| Wastepaper | suelo / recolección | [SRC048] |
| Copper Ore / Iron Ore / Gold Ore | minas y yacimientos; Gold en Rocky Ridges Y Withered Wastelands | [SRC048, SRC037, SRC068] |
| Pokemetal Fragment | Dream Islands / minas (también yacimiento en Wastelands) | [SRC048, SRC068] |
| Rare Pokemetal Fragment | Dream Islands / minas | [SRC048] |
| Crystal Fragment | Dream Islands | [SRC048] |
| Star Piece / Stardust | Dream Islands (con muñeco) | [SRC048, SRC022] |
| Lumber / Brick / Glass / Concrete / Paper | producidos (ver §2) | [SRC048] |
| Copper/Iron/Gold Ingot | producidos (Smelting Furnace) | [SRC048] |
| Pokemetal / Rare Pokemetal | producidos (Rarify) | [SRC048] |
| Tinkagear | producido por Tinkmaster | [SRC048, SRC037] |
| Paint | producido / PC Shop | [SRC048] |
| Armor Fragments / Strange String | — | [SRC048, SRC068] |

## 1b. Berries, plantas y bloques (Withered Wastelands, Serebii SRC068)

- **Berries naturales:** Leppa, Chesto, Rawst, Lum, Pecha, Aspear (árboles en la zona).
- **Plantas/bloques:** Tall grass, Moss, Wildflowers (+ variantes de color), Beautiful flower, Adorable hedge, Green shoots, Field grass, Ordinary soil, Sand, Ocean rock, Cave rock, Sandstone, Gravel, Mossy Soil, Hay pile, etc.
- **Yacimientos en Wastelands:** Copper deposit, **Gold deposit**, Pokémetal deposit, Broken timber.

## 1c. Tesoros y fósiles (Withered Wastelands, SRC068)

- **Lost Relics:** Large lost relic, Small lost relic.
- **Muñecos:** Pikachu doll, Eevee Doll, Ditto doll, Substitute doll.
- **Fósiles (partes):** Shield Fossil (Head/Body/Tail), Armor Fossil, Wing Fossil (Head/Right wing/Left wing/Body/Tail).
- **Otros:** Strange strings, Armor fragment.
- Se obtienen además en Poké Balls de la zona (p. ej. Torch, Security camera, Rowlet clock, kits varios) y en Sparkling Ripples (semillas, kits Leaf/Pink hut, Waterwheel/Windmill kit).

## 2. Cadenas de procesado (INPUT → OUTPUT)

| INPUT | Proceso (especialidad / equipo) | OUTPUT | Fuente |
|---|---|---|---|
| Small Logs | Chop | Lumber | [SRC037] |
| Ore | Smelting Furnace + Burn | Ingot (Cu/Fe/Au) | [SRC037] |
| Squishy Clay | Burn | Bricks | [SRC037] |
| Limestone | Concrete Mixer + Crush | Concrete | [SRC037] |
| Nonburnable Garbage | Recycle | Iron Ore | [SRC037] |
| Wastepaper | Recycle | Paper | [SRC037] |
| Iron Ingots | Tinkmaster (Engineer) | Tinkagears ⚠️ tasa 2:1 vs 1:3 (C04) | [SRC037, SRC048] |
| Star Piece | Rarify | Rare Pokemetal | [SRC037] |

## 3. Regionalidad de recursos

- **Gold Ore:** en Rocky Ridges [SRC037] y en Withered Wastelands (yacimiento + recolección) [SRC068].
- **Fresh Carrot:** Withered Wastelands (recolección natural) [SRC068].
- **Sea Glass / Seashell:** Bleak Beach [SRC048].
- **Glowing Mushroom:** zonas oscuras/cuevas (Wastelands) [SRC048, SRC068].
- **Stardust / Pokemetal / Star Piece:** principalmente Dream Islands [SRC022, SRC048].
- **Sandía (Watermelon):** DLC Bubbly Basin (solo si tienes el DLC) [SRC014, SRC013].
- **Berries (Leppa, Chesto, Rawst, Lum, Pecha, Aspear):** árboles de Withered Wastelands; Leppa se cultiva y aparece en varias requests [SRC068, SRC034].

## 4. Agricultura (cultivos)

- **Cultivos:** Beans, Wheat, Tomatoes, Potatoes, Leafy Greens [SRC032, SRC045].
- **Semillas:** se desbloquean al alcanzar **Environment Level 3** de la zona [SRC032, SRC045].
- **Etapas de crecimiento:** Planted → Sapling → Grown → Harvestable (días en tiempo real) [SRC045].
- **Riego:** Water Gun manual, Water Basin + Water specialty, Sprinklers (50 Life Coins), lluvia [SRC032].
- **Acelerador:** especialidad **Grow** [SRC032].
- **Regla de suelo:** Rototiller NO funciona en tierra seca; hay que regar primero [SRC032].
- **Cosecha:** a mano, o con Cut sobre la parcela (truco confirmado por prensa) [SRC052, SRC055].

## 5. Construcción

- **Building Kits** para casas y edificios; consumen materiales de las cadenas de §2 [SRC001, SRC037].
- Todo lo fabricado (estructuras, muebles, hábitats, infraestructura eléctrica) parte de materiales crudos [SRC037].
- Construcción sobre cuadrícula; Ditto puede fijarse a la cuadrícula [SRC055].

## Notas metodológicas

- La **lista completa de Building Kits y sus costes** está parcialmente consolidada (GAP-04): las tablas de desbloqueo por área/nivel de Environment están extraídas (SRC023), pero faltan los costes exactos de materiales.
- La tasa real de conversión de Tinkagear necesita verificación (C04).
