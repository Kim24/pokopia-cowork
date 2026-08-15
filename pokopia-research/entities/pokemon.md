# Pokopia — Entities: Pokémon

> Catálogo de conocimientos sobre los Pokémon como entidades del dominio.
> Foco en lo estructural: cómo se describen, reclutan y usan. La lista íntegra de las 308 entradas está en `pokemon-catalog.md` (Fase 1).

---

## 1. Identidad y clasificación

- **Identificadores:** número de Pokédex (1–300 principal), nombre, especie.
- **Atributos por entrada de Pokédex** [SRC043, SRC036, SRC044]:
  - Tipos (hasta 2)
  - Especialidad(es)
  - Hábitat(s) donde aparece
  - Franjas horarias de aparición (día/noche/crepúsculo)
  - Condiciones climáticas
  - Flavor de comida favorito
  - Preferencias de comfort (items/muebles)
  - Localización del "Home" (su hábitat/casa)
  - Favorito item / Regalo que le gusta
- No existe captura con Poké Balls; los Pokémon se **reclutan construyendo su hábitat** y luego "familiarizándose" [SRC017, SRC032].

## 2. Especialidades (Specialties) — lista consolidada

> Consolidación de Serebii (SRC065, roster completo de Fase 1) + guías [SRC042, SRC048]. **31 especialidades confirmadas (C08 RESUELTO).** 'Scrub' no aparece en el roster y se elimina.

| Especialidad | Efecto resumido | Notas |
|---|---|---|
| Appraise | Identifica objetos / Lost Relics | Profesor Tangrowth |
| Build | Construye/instala estructuras | |
| Bulldoze | Aplana terreno | |
| Burn | Procesa con fuego (hornos, ingots, pan) | |
| Chop | Corta madera (Small Log → Lumber) | |
| Collect | Recoge materiales del suelo | |
| Crush | Machaca piedras/limestone | |
| Dream Island | Lleva a Dream Islands | Drifloon (exclusivo) |
| DJ | Reproduce música (CDs) | DJ Rotom (exclusivo) |
| Eat | Se come los ingredientes sobrantes / buffs | Mosslax (exclusivo) |
| Engineer | Procesa Tinkagears / maquinaria | Tinkmaster (exclusivo) |
| Explode | Rompe bloques grandes | |
| Fly | Transporta al jugador / amplía mapa | |
| Gather | Recolecta recursos | |
| Gather Honey | Obtiene Honey | Vespiquen (exclusivo) |
| Generate | Genera energía temporalmente | |
| Grow | Acelera cultivos / crea vegetación | |
| Hype | Anima a otros Pokémon (sube comfort) | |
| Illuminate | Enciende objetos (Peakychu) | Peakychu (exclusivo) |
| Litter | Produce semillas/excrementos → fertilizante | |
| Paint | Pinta / re-pinta muebles | Smearguru (exclusivo) |
| Party | Cocina para el grupo | Chef Dente (exclusivo) |
| Rarify | Transforma Star Piece → Rare Pokemetal | |
| Recycle | Convierte basura/madera vieja → materiales | |
| Search | Busca tesoros/objetos ocultos | |
| Storage | Guarda objetos (bolsa expandida) | |
| Teleport | Teletransporte rápido entre áreas | |
| Trade | Vende objetos por trueque | |
| Transform | Usa el poder de transformación de Ditto | Ditto (exclusivo) |
| Water | Riega cultivos / llena Water Basins | |
| Yawn | Restaura PP de Ditto con sueño | |

- Varios Pokémon tienen **doble especialidad** [SRC042, SRC065]: Machop (Build+Gather), Pidgey (Fly+Search), Bellsprout (Grow+Litter), Slowpoke (Water+Yawn), etc.
- Las especialidades de NPCs son **únicas/exclusivas** de ese NPC [SRC042, SRC036].
- Pokémon con especialidad **"???"** en Serebii (sin rol documentado): **Magikarp (#045), Kyogre (#289), Lugia (#297), Ho-Oh (#298)** [SRC065].
- Los números de la página de Serebii son orden de página, no Pokédex nacional; el roster tiene 308 entradas con 7 grupos de números duplicados por variantes de forma (p. ej. Tatsugiri ×3, Toxtricity ×2, Shellos/Gastrodon East Sea) [SRC065].

## 3. Movimientos que Ditto aprende (relación Pokémon → Movimiento)

| Movimiento | Se aprende al conocer… | Área de encuentro | Fuente |
|---|---|---|---|
| Camouflage | Zorua | Bleak Beach | [SRC016] |
| Cut | Scyther | — | [SRC016] |
| Leafage | Bulbasaur | Withered Wasteland | [SRC016] |
| Glide | Dragonite | Sparkling Skylands | [SRC016] |
| Magnet Rise | Magnemite | — | [SRC016] |
| Rock Smash | Hitmonchan | — | [SRC016] |
| Rollout | Graveler | Rocky Ridges | [SRC016] |
| Rototiller | Drilbur | — | [SRC016] |
| Surf | Lapras | Bleak Beach | [SRC016] |
| Water Gun | Squirtle | Withered Wasteland | [SRC016] |
| Splash | Magikarp | Withered Wasteland | [SRC016] |
| Strength | Machoke | Rocky Ridges | [SRC016] |
| Stockpile Water | Piplup (+ Paldean Wooper) | request | [SRC016] |
| Waterfall | Gyarados | Sparkling Skylands | [SRC016] |
| Dive | Manaphy | Bubbly Basin (2.0.0) | [SRC013] |

## 4. Comportamiento / estado

- **Home:** cada Pokémon tiene un "Home" (su hábitat/casa) indicado en la Pokédex [SRC043].
- **Comfort Level** (5 niveles + Comfy 0 sin hogar: Iffy→Average→Nice→Great→Awesome) y **Friendship** (vínculo) → ver `entities/progression.md`.
- Los Pokémon realizan **Requests** y piden **gifts**; regalar lo que quieren sube Comfort/Friendship [SRC036, SRC024].
- **Favorites:** a cada Pokémon le gustan ciertos muebles/items; colocarlos sube su comfort [SRC040].
- Los Pokémon **se mueven por su zona** (barren, trabajan con su especialidad, se sientan, duermen) [SRC042, SRC036].
- **Lluvia/recursos:** algunos buscan recursos en zonas específicas (p. ej. Grookey se lleva recursos no usados) [SRC042].

## 5. Legendarios y míticos

| Especie | Método principal | Fuente |
|---|---|---|
| Kyogre | Historia en Withered Wasteland (Important Request 'Yawn Up a Storm!') | [SRC021, SRC046, SRC034] |
| Raikou | Historia en Bleak Beach ('Brighten Things Up!') | [SRC021, SRC046, SRC034] |
| Volcanion | Historia en Rocky Ridges ('Time to Party!') | [SRC021, SRC046, SRC034] |
| Mewtwo | Historia en Sparkling Skylands ('Rebuild the Huge Building'; Master Ball) | [SRC021, SRC046, SRC034] |
| Articuno | Freezing Chamber (Building Kit) | [SRC021] |
| Zapdos | Abandoned Power Plant | [SRC021] |
| Moltres | Altar of Flame | [SRC021] |
| Entei / Suicune / Mewtwo | Dream Islands (según muñeco) | [SRC021, SRC047] |
| Ho-Oh / Lugia | Clear Bell / Tidal Bell tras reclutar los sets | [SRC021] |
| Mew | 27 Mysterious Slates (mural) | [SRC021] |
| Manaphy | DLC Bubbly Basin (Ocean Temple, update 2.0.0) | [SRC013, SRC014, SRC034] |
| Phione | DLC Bubbly Basin (update 2.0.0) | [SRC013, SRC014] |

- Los legendarios aumentan el Environment Level **más rápido** al subir su Comfort [SRC023, SRC045].
- Conteo (C07 RESUELTO con criterio): **12 en el juego base**; **14 contando el DLC** (Manaphy, Phione) [SRC021, SRC039, SRC046].
- Kyogre, Lugia y Ho-Oh figuran en Serebii con especialidad "???"; The Games Wiki añade que Lugia/Ho-Oh no son amistosos [SRC065, SRC069].

## 6. Pokémon de evento (limitados)

- Hoppip/Skiploom/Jumpluff (More Spores for Hoppip, ~9–25 mar 2026 según fuente; C10) [SRC004, SRC029]
- Sableye (evento, listado por The Games Wiki) [SRC069]
- Otros: ver eventos en `domains.md` §18 y `sources/sources.json`.

## 7. Notas metodológicas

- Catálogo íntegro consolidado en **Fase 1** → `entities/pokemon-catalog.md` (308 entradas Serebii, validado contra The Games Wiki: 300 numerados + 7 sin número + 4 de evento). Las especialidades por especie y las variantes de forma (duplicados de número) están ahí.
- Discrepancias de especialidades entre Serebii y The Games Wiki detectadas en la validación (p. ej. Victreebel: Grow+Chop vs Chop+Litter; Pidgeot: Fly+Chop vs Fly+Search; Porygon-Z: Rarify vs Recycle) → Serebii se considera fuente canónica para el roster [SRC065, SRC069].
