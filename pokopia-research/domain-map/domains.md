# Pokopia — Domain Map: Sistemas del dominio

> Este documento enumera y describe los **sistemas** del juego tal como los descubrimos en esta fase.
> No es una lista cerrada: se ampliará a medida que aparezca nueva evidencia.
> Clasificación de afirmaciones: `FACT` (afirmado), `INFERENCE` (deducido), `UNKNOWN`.

---

## Índice de sistemas

1. [Pokémon y Pokédex](#1-pokémon-y-pokédex)
2. [Movimientos / Transformaciones de Ditto](#2-movimientos--transformaciones-de-ditto)
3. [Especialidades (Specialties)](#3-especialidades-specialties)
4. [Hábitats y aparecimiento](#4-hábitats-y-aparecimiento)
5. [Food & Cooking (Alimentos y cocina)](#5-food--cooking-alimentos-y-cocina)
6. [Farming & Gardening (Agricultura)](#6-farming--gardening-agricultura)
7. [Recursos, materiales y crafting](#7-recursos-materiales-y-crafting)
8. [Construcción y terraforming](#8-construcción-y-terraforming)
9. [Economía: Life Coins, PC Shop y trueque](#9-economía-life-coins-pc-shop-y-trueque)
10. [Electricidad y agua](#10-electricidad-y-agua)
11. [Áreas / regiones y puertas](#11-áreas--regiones-y-puertas)
12. [Quests / Requests](#12-quests--requests)
13. [Progresión: Trainer Rank, Environment Level, Comfort, Friendship](#13-progresión)
14. [NPCs y Pokémon especiales](#14-npcs-y-pokémon-especiales)
15. [Legendarios y míticos](#15-legendarios-y-míticos)
16. [Dream Islands y Cloud Islands](#16-dream-islands-y-cloud-islands)
17. [Multiplayer](#17-multiplayer)
18. [Eventos y Mystery Gifts](#18-eventos-y-mystery-gifts)
19. [DLC / Expansiones](#19-dlc--expansiones)
20. [Customización y decoración](#20-customización-y-decoración)
21. [Mini-juegos y actividades](#21-mini-juegos-y-actividades)
22. [Sensores, automatización y física de bloques](#22-sensores-automatización-y-física-de-bloques)

---

## 1. Pokémon y Pokédex

- **Pokédex principal: 300 Pokémon** numerados, todos obtenibles en el juego y requeridos para completar la Pokédex [SRC030, SRC043]. Incluye a Ditto (el propio jugador) [SRC043].
- Existen **Pokédex independientes** para Pokémon de eventos y para Bubbly Basin (DLC) [SRC030, SRC015]. La **Cloud Island Pokédex** es idéntica a la principal [SRC030].
- Cada entrada tiene: número, especie, **tipos**, **especialidad(es)**, **hábitat(s)**, **franjas de día/noche**, **condiciones de clima**, **flavor favorito** y preferencias de comfort [SRC043, SRC044, SRC036].
- Los Pokémon se **reclutan** atrayéndolos con hábitats (no se capturan con Poké Balls) [SRC017, SRC032].
- Los legendarios tienen hábitats marcados como "???" y requisitos especiales [SRC043].
- Los Pokémon de eventos (p. ej. Hoppip/Skiploom/Jumpluff) no se pueden encontrar fuera del periodo de evento [SRC004, SRC005].

## 2. Movimientos / Transformaciones de Ditto

Ditto aprende **movimientos** al conocer a ciertos Pokémon; cada movimiento usa **PP** y no puede usarse de forma continua sin descanso [SRC016].

**Movimientos primarios** (lista de Serebii) [SRC016]:

| Movimiento | Efecto | Cómo se aprende |
|---|---|---|
| Camouflage | Te transformas en el objeto que tienes delante | Conocer a Zorua en Bleak Beach |
| Cut | Corta hierba y árboles | Conocer a Scyther |
| Leafage | Crea hierba en el suelo | Conocer a Bulbasaur |
| Glide | Planea por el aire | Conocer a Dragonite en Sparkling Skylands |
| Magnet Rise | Vuela por el cielo; rompe objetos (post-game) | Conocer a Magnemite |
| Rock Smash | Rompe rocas | Conocer a Hitmonchan |
| Rollout | Rueda hacia delante; usa el medidor de Rock Smash al romper rocas | Conocer a Graveler en Rocky Ridges |
| Rototiller | Remueve el suelo para plantar semillas | Conocer a Drilbur |
| Surf | Navega por el agua | Conocer a Lapras en Bleak Beach |
| Water Gun | Hidrata en forma de + | Conocer a Squirtle en Withered Wasteland |

**Movimientos secundarios** [SRC016]:

| Movimiento | Efecto | Cómo se aprende |
|---|---|---|
| Splash | Salto | Conocer a Magikarp en Withered Wasteland |
| Strength | Empuja objetos | Conocer a Machoke en Rocky Ridges |
| Stockpile Water | Mueve agua para crear charcas y cascadas | Completar request de Piplup y conocer a Paldean Wooper |
| Waterfall | Escala cascadas | Conocer a Gyarados en Sparkling Skylands |
| Dive (v2.0.0) | Nadar y construir bajo el agua | Ayudar a Manaphy (update 2.0.0) [SRC013] |

**Power-ups de movimientos**: la comida cocinada potencia Cut, Rock Smash, Leafage y Water Gun (y Surf con smoothies en el DLC) durante un periodo; tienen un medidor de PP propio que se agota por separado [SRC016, SRC026, SRC033].

## 3. Especialidades (Specialties)

- Las **especialidades** son "roles de trabajo" que cada Pokémon realiza tras ser reclutado. **No son habilidades (abilities)** y no se pueden aprender [SRC032, SRC042].
- No hay combate: cada Pokémon contribuye con trabajo práctico [SRC042].
- Serebii documenta al menos: **Burn, Chop, Crush, Grow** [SRC018]. La lista agregada de guías incluye ~31: Appraise, Build, Bulldoze, Burn, Chop, Collect, Crush, Dream Island, DJ, Eat, Engineer, Explode, Fly, Gather, Gather Honey, Generate, Grow, Hype, Illuminate, Litter, Paint, Party, Rarify, Recycle, Search, Storage, Teleport, Trade, Transform, Water, Yawn [SRC042, SRC048]. ('Scrub' NO es una especialidad; ver C08.)
- Algunos Pokémon tienen **doble especialidad** (p. ej. Machop: Build + Gather; Pidgey: Fly + Search; Bellsprout: Grow + Litter; Slowpoke: Water + Yawn) [SRC042].
- Varias especialidades son **exclusivas de NPCs** (DJ → Stereo Rotom; Illuminate → Peakychu; Eat → Mosslax; Appraise → Profesor Tangrowth; Engineer → Tinkmaster; Party → Chef Dente; Transform → Ditto; Dream Island → Drifloon; Gather Honey → Vespiquen) [SRC042, SRC036].

## 4. Hábitats y aparecimiento

- Para que un Pokémon aparezca hay que **construir su hábitat** combinando varios objetos; tras un tiempo puede aparecer un Pokémon salvaje [SRC017].
- El aparecimiento varía según **ubicación, hora del día y clima** [SRC017].
- **Regla de luz/darkness:** los Pokémon nocturnos pueden aparecer de día si el hábitat está en un lugar oscuro (cueva/subterráneo); los diurnos pueden aparecer de noche si el hábitat está rodeado de luz brillante [SRC017].
- Hay **209 hábitats** en el juego base [SRC043]. Cada hábitat está descrito en un Habitat Dex [SRC017].
- Los hábitats se pueden mejorar (camas, decoración…) [SRC017].
- Algunos hábitats requieren **electricidad** (se marcan con un icono de rayo) [SRC043].

## 5. Food & Cooking (Alimentos y cocina)

- La cocina se desbloquea en **Rocky Ridges** al rescatar al **Chef Dente** (un Greedent atrapado en un barril) [SRC033, SRC045, SRC049].
- Hay **4 tipos de comida** (Salad, Soup, Bread, Hamburger Steak), cada uno con **6 variantes** → **24 recetas** [SRC033, SRC045]. En el DLC se añaden **smoothies** [SRC013].
- Cada tipo potencia un movimiento: Salad→Leafage; Soup→Water Gun; Bread→Cut; Hamburger Steak→Rock Smash [SRC016, SRC033].
- Las comidas **restauran PP por completo** y pueden regalarse a los Pokémon [SRC033, SRC045].
- Estaciones: Chopping Board (ensaladas), Cooking Pot (sopas), Frying Pan (hamburguesas), Bread Oven (pan). Las 3 últimas requieren fuego/estufa; el Bread Oven requiere un Pokémon con especialidad **Burn** [SRC033, SRC049].
- Especialidades de **helper** pueden modificar recetas (Chop→Shredded Salad; Crush→Crushed Berry Salad; Burn→Bread Bowl) [SRC049, SRC033].
- **Flavors:** 5 sabores (Sweet, Spicy, Dry, Bitter, Sour) + neutro [SRC033, SRC045]. Cada Pokémon tiene un flavor favorito en su Pokédex [SRC033].
- **Mosslax** (Snorlax con musgo) otorga un buff diario según el flavor de la comida ofrecida en el Gourmet's Altar [SRC033].

## 6. Farming & Gardening (Agricultura)

- La agricultura usa el movimiento **Rototiller** (de Drilbur) para preparar el suelo, **Water Gun** para regar y la especialidad **Grow** para acelerar el crecimiento [SRC032].
- **Limitación clave:** Rototiller no funciona en tierra seca; hay que regar antes [SRC032].
- Cultivos conocidos: Beans, Wheat, Tomatoes, Potatoes, Leafy Greens; las semillas se desbloquean al alcanzar **Environment Level 3** en su zona [SRC032, SRC045].
- Métodos de riego: manual (Water Gun), Water Basin + especialidad Water, Sprinklers (50 Life Coins), lluvia [SRC032].
- Los cultivos tienen 4 etapas: Planted, Sapling, Grown, Harvestable; tardan días (reloj real) [SRC045].
- Truco comunitario confirmado por prensa: usar **Cut** para cosechar parcelas enteras sin dañar la planta [SRC055, SRC052].

## 7. Recursos, materiales y crafting

- Todo lo fabricado (estructuras, muebles, hábitats, infraestructura) parte de **materiales crudos** recolectados del entorno [SRC037].
- **Materiales base:** Honey, Sturdy Stick, Stones, Leaf, Small Log, Vine Rope, Glowing Mushroom, Twine, Sea Glass Fragments, Seashell, Nonburnable Garbage, Squishy Clay, Fluff, Wastepaper, Copper/Iron/Gold Ore, Pokemetal Fragment, Rare Pokemetal Fragment, Crystal Fragment, Lumber, Brick, Copper/Iron/Gold Ingot, Pokemetal, Rare Pokemetal, Glass, Concrete, Paper, Tinkagear, Strange String, Armor Fragments, Stardust, Paint [SRC048].
- **Cadenas de procesado clave** (INPUT → OUTPUT, con especialidad/equipo) [SRC037]:
  - Small Logs → Lumber (especialidad Chop)
  - Ore → Ingot (Smelting Furnace + Burn)
  - Squishy Clay → Bricks (especialidad Burn, directo)
  - Limestone → Concrete (Concrete Mixer + Crush)
  - Nonburnable Garbage → Iron Ore (especialidad Recycle)
  - Wastepaper → Paper (especialidad Recycle)
  - Iron Ingots → Tinkagears (Tinkmaster / Engineer) ⚠️ tasa en disputa (ver C04)
  - Star Piece → Rare Pokemetal (especialidad Rarify)
- **Localización por región** [SRC037]: cada región tiene materiales exclusivos (p. ej. Gold Ore solo en Rocky Ridges; Stardust solo en Dream Islands).

## 8. Construcción y terraforming

- El mundo se construye con **bloques sobre una cuadrícula**; Ditto se puede fijar a la cuadrícula (ZL) [SRC055].
- Movimientos que terraforman: Water Gun (revitalizar tierra), Leafage (crear hierba), Rock Smash (romper rocas), Rototiller (enriquecer suelo) [SRC040].
- **Building Kits** crean casas y edificios; las construcciones requieren materiales y a veces Pokémon asignados [SRC001, SRC037, SRC032].
- **Terraforming post-game:** con Magnet Rise (Magnemite) se pueden mover árboles y rocas enteros [SRC055].
- Los edificios (incluido el Pokémon Center) se reconstruyen por regiones [SRC035].

## 9. Economía: Life Coins, PC Shop y trueque

- **Life Coins** = moneda principal, se gana con **Challenges** (PC del Pokémon Center), **Stamp Rally** (semanal) y vendiendo materiales [SRC035].
- Se gastan en el **PC Shop**: recipes, semillas, building kits, Packing Tips (inventario), PP Up, muebles [SRC035].
- **Trueque (Trade):** los Pokémon con especialidad Trade venden objetos a cambio de **objetos de valor equivalente** (no monedas); cada objeto tiene un valor en puntos [SRC035, SRC056].
- Life Coins y trueque son **sistemas independientes** [SRC035].
- Stamp Rally: semanal, ~1.500–2.000+ Life Coins; los sellos se canjean los viernes (tiempo real) [SRC035].

## 10. Electricidad y agua

- La electricidad se genera con: **Mini Generator** (5 unidades), **Windmill** (10/20 según altitud), **Waterwheel** (20), **Furnace** (30, requiere combustible) [SRC028, SRC057].
- Los Pokémon con especialidad **Generate** pueden energizar temporalmente objetos [SRC057].
- Distribución con **Utility Poles** (rango ~10 bloques, ±5 verticales, hasta 20 conexiones) y **Wireless Power Transmitters** (mayor alcance, atraviesa objetos; requiere Porygon) [SRC028, SRC051].
- **Límites (VERSIONADOS, C05 PARTIALLY CONFIRMED en Fase 1.5):** generadores: 64 por zona (1.0.x–1.1.1) → **128 excluyendo furnaces** (2.0.0+, nota oficial); objetos eléctricos: 512 (1.0.x) → **1.024** (1.1.0+; sin cambio en 2.0.0) [SRC028, SRC070, SRC071]. La semántica de "excl. furnaces" y el tope de 256 transmisores por zona siguen **UNKNOWN** (ver C05).
- El agua fluye por gravedad; las **waterwheels** necesitan agua fluyendo; hay tuberías de hierro para encauzar líquidos verticalmente [SRC041].
- **Charging Station** acumula electricidad para que Peakychu use Illuminate [SRC057].

## 11. Áreas / regiones y puertas

- 4 áreas principales + Palette Town (sandbox) + Bubbly Basin (DLC) [SRC044].
- El acceso entre áreas usa **puertas verdes** que requieren Trainer Rank + completar requests [SRC034, SRC048].
- Resumen de requisitos documentados [SRC034, SRC044]:
  - Withered Wasteland: inicio.
  - Bleak Beach y Rocky Ridges: ambas se desbloquean tras "Yawn Up a Storm" (Great Rank) — se pueden hacer en cualquier orden [SRC034, SRC044].
  - Sparkling Skylands: tras "Brighten Things Up" (Bleak Beach) y "Time to Party" (Rocky Ridges) (Ultra Rank) [SRC034, SRC044].
  - Palette Town: disponible desde el inicio (vía camino al oeste de Withered Wasteland) [SRC044].
- ⚠️ Existen descripciones alternativas del desbloqueo (40% de restauración; Hyper Trainer Rank) — ver contradicciones C01/C02.

## 12. Quests / Requests

- **Requests** = sistema de misiones. Los Pokémon con burbuja de diálogo dan peticiones; se rastrean en el menú Requests del Pokédex [SRC034].
- **Important Requests** = hitos narrativos que suben el Trainer Rank [SRC019, SRC034]:
  - "Yawn Up a Storm!" (Withered Wasteland)
  - "Brighten Things Up!" (Bleak Beach)
  - "Time to Party!" (Rocky Ridges)
  - "Rebuild the Huge Building!" (Sparkling Skylands)
  - "Do the Team Initiation Challenge!" (global, final)
- Completar requests sube el Comfort Level del Pokémon solicitante y da recompensas (recetas, muebles, movimientos) [SRC034, SRC036].

## 13. Progresión

- **Trainer Rank:** No rank → Great → Ultra → Master. Sube solo con Important Requests. Great abre Bleak Beach y Rocky Ridges; Ultra abre Sparkling Skylands; Master = hito final (sin área nueva) [SRC034]. ⚠️ Los nombres de los rangos difieren entre fuentes (ver C03).
- **Environment Level (por área):** 1→10. Sube con la suma de Comfort de los Pokémon del área. Nivel 5 requerido en cada área para el final; nivel 10 = máx [SRC023, SRC040]. Puede **bajar** [SRC023].
- **Comfort Level (por Pokémon):** 5 niveles + Comfy 0 (sin hogar): Iffy, Average, Nice, Great, Awesome (el "No Home" no es un nivel, es ausencia de hogar) [SRC023, SRC040, SRC045]. Se sube con hábitats/casas adecuados, muebles que le gustan, comida del flavor preferido, gifts, requests, mini-juegos.
- **Friendship (vínculo con Ditto):** separada del Comfort; sube con requests y gifts; al máximo el Pokémon te llama por tu nombre y te considera "best friend" (marca en la Pokédex) [SRC024].
- **PP (energía de movimientos):** medidor de PP; se restaura en el Pokémon Center, con comida o ingredientes; PP Up aumenta el máximo [SRC035, SRC016].
- **Team Initiation Challenge:** cadena final de entregas (8 o 9 etapas según la fuente — ver C06) con badges que parodian los Gym Badges de Kanto; completarla dispara los créditos [SRC038, SRC042].

## 14. NPCs y Pokémon especiales

7 NPCs con nombre, cada uno con especialidad única [SRC036, SRC007, SRC048]:

| NPC | Especie | Especialidad | Rol |
|---|---|---|---|
| Profesor Tangrowth | Tangrowth | Appraise | Mentor, da la Pokédex, identifica Lost Relics |
| Chef Dente | Greedent | Party | Desbloquea cocina; cocina en grupo |
| Peakychu | Pikachu (variante pálida) | Illuminate | Restaura la luz en Bleak Beach |
| Mosslax | Snorlax (con musgo) | Eat | Buffs diarios por flavor |
| Smearguru | Smeargle (variante pintora) | Paint | Customización/re-pintado de muebles |
| DJ Rotom | Rotom (Stereo Rotom) | DJ | Música (CDs) |
| Tinkmaster | Tinkaton | Engineer | Construcción tardía; crea Tinkagears |

Ver `entities/npcs.md` para detalle.

## 15. Legendarios y míticos

Lista documentada: **Kyogre, Raikou, Entei, Suicune, Volcanion, Articuno, Zapdos, Moltres, Lugia, Ho-Oh, Mewtwo, Mew** (12, según The Games Wiki y Eurogamer) [SRC039, SRC045]. Polygon menciona **14** incluyendo probablemente a Phione (DLC) — ver C07 [SRC046].

- Encuentros de historia: Kyogre (Withered Wasteland), Raikou (Bleak Beach), Volcanion (Rocky Ridges), Mewtwo (Sparkling Skylands) [SRC021, SRC046].
- Aves legendarias: Building Kits (Freezing Chambers → Articuno; Abandoned Power Plant → Zapdos; Altar of Flame → Moltres) [SRC021].
- Legendary Beasts y Mewtwo: en Dream Islands según el muñeco usado [SRC021, SRC047].
- Ho-Oh y Lugia: Campanas (Clear Bell / Tidal Bell) tras reclutar los sets; sueltan plumas [SRC021].
- Mew: 27 Mysterious Slates en un mural [SRC021].
- Los legendarios aumentan el Environment Level más rápido si subes su Comfort [SRC023, SRC045].

## 16. Dream Islands y Cloud Islands

- **Dream Islands:** islas de recursos visitables **una vez por día** con Drifloon usando muñecos (dolls); isla según el muñeco; recursos únicos (Stardust, Pokemetal…); chance de encontrar legendarios [SRC022, SRC047, SRC011].
- Muñecos → isla: Pikachu→Ocean; Eevee→Wasteland; Dragonite→Sky; Clefairy→Rock Peak; Arcanine→Volcanic; Starmie (DLC)→Basin; Ditto/Substitute→aleatoria [SRC047].
- **Cloud Islands:** islas persistentes online (4 jugadores); Pokédex y rewards compartidos; bolsa separada; Virtual Mode con Mysterious Goggles [SRC010, SRC012].

## 17. Multiplayer

- **Link Play** en el PC del Pokémon Center: Invite Others / Visit a Friend / Play on a Cloud Island / GameShare [SRC009, SRC012].
- Requiere **Environment Level 2** (~30 min de juego) [SRC009].
- 2–4 jugadores; online requiere Nintendo Switch Online [SRC009, SRC012].
- **Spectator Mode** en áreas de historia; **Palette Town** permite colaboración total (construir, cosechar, vender…) [SRC009, SRC012].
- **GameShare**: hasta 2 jugadores, solo Palette Town, solo el host necesita el juego [SRC012].
- Los progresos y recompensas de challenges van solo al host [SRC009].

## 18. Eventos y Mystery Gifts

- **Eventos limitados** con Pokémon exclusivos, hábitats e items; usan moneda de evento obtenida en Dream Islands; el Pokémon reclutado se queda permanentemente [SRC029, SRC004].
- Eventos documentados (2026) [SRC029]:
  - More Spores for Hoppip (10–25 marzo): Hoppip/Skiploom/Jumpluff [SRC004, SRC029]
  - Copycat Challenge (1 abril)
  - Bulbasaur's Jump Rope Contest (19–26 abril)
  - Sableye's Gem Hunt (29 abril–14 mayo)
  - Wish Upon a Jirachi (23 junio–8 julio)
  - Zorua's Hide-and-Sneak Contest (19–27 julio)
  - Fetching Scales for Feebas (13–28 agosto)
- **Mystery Gifts:** Internet (automáticos, p. ej. Ditto Rug), serial codes (un solo uso), passwords (multiuso). Chansey Plan para Pokopia Gardens (Londres/Berlín/París) [SRC029, SRC031].
- Los eventos limitados no requieren NSO; están ligados al reloj del sistema [SRC029].

## 19. DLC / Expansiones

- **Expansion Pass** de 3 partes; una sola compra da acceso a las tres [SRC013, SRC014].
- **Parte 1: Bubbly Basin** (5 ago 2026): pueblo submarino; bloques boyantes; sandías (Water specialty); smoothies; potencia Surf; Sharpedo submarine; nuevo Dream Island con muñeco Starmie [SRC013, SRC014].
- Requisitos de acceso: update 2.0.0 + request "Raise the environment level!" en Bleak Beach + aprender Dive [SRC013, SRC008].
- **Update 2.0.0 (gratis):** movimiento **Dive** aprendido de **Manaphy** [SRC013, SRC014].
- **Parte 2:** finales de 2026 (accessories para vestir junto a los Pokémon). **Parte 3:** 2027 [SRC013, SRC060].

## 20. Customización y decoración

- Ditto se personaliza (peinados, outfits) [SRC003].
- Muebles y decoración: se fabrican y colocan; algunos son "Sparkling Water Ripples" (animados) [SRC027].
- **Painting** (Smearguru) y CDs de música (DJ Rotom) [SRC036].
- Favorite items: cada Pokémon tiene gustos; los muebles adecuados suben su Comfort [SRC036, SRC040].

## 21. Mini-juegos y actividades

- Jump Rope (con Bulbasaur), Hide-and-Sneak (Zorua), quizzes que los Pokémon te hacen [SRC036, SRC029].
- Suben el Comfort/Friendship aunque no salga bien [SRC036, SRC040].
- Photo Mode / Highlight Reel [SRC038].

## 22. Sensores, automatización y física de bloques

- **Laser sensors** activados por movimiento; combinables con ventanas/puertas/hatches, fluidos y switches eléctricos para crear cadenas automáticas [SRC052, SRC053, SRC054].
- Pokémon también pueden activar sensores; los fluidos activan sensores (no floor switches) [SRC054].
- La comunidad ha creado granjas automáticas, cascadas de lava automáticas y ciudades autosostenibles [SRC052, SRC053].
- Clasificación: la mayor parte es **STRATEGY/community** — no es mecánica oficialmente documentada [SRC054].

---

## Mapa de conexiones entre sistemas (visión general)

```
Pokémon ──(aprende movimiento)──▶ Ditto (movimientos/transformaciones)
Pokémon ──(tiene)──▶ Especialidad ──(procesa)──▶ Materiales ──▶ Crafting ──▶ Objetos/Edificios/Hábitats
Pokémon ──(atraído por)──▶ Hábitat ──(requiere)──▶ Materiales + A veces Electricidad
Cultivos ──▶ Ingredientes ──▶ Recetas ──▶ Comida ──▶ Power-up de movimientos / Comfort de Pokémon
Comida ──(flavor favorito)──▶ Comfort Level ──▶ Environment Level ──▶ Desbloqueos PC Shop / final
Requests ──▶ Trainer Rank ──▶ Puertas/Áreas
Legendarios ──▶ Building Kits / Dream Islands / Campanas
```

Detalle entidad por entidad en `entities/`; relaciones formales en `relationships/relationships.json`.
