# Pokémon Pokopia — Domain Overview

> **Domain Research — Fase 1 (Pokopia Intelligence Lab)**
> Estado: investigación inicial basada en fuentes públicas (oficiales + wikis + guías + comunidad).
> Fecha de recuperación de fuentes: 2026-08-15. Regla de oro: **no inventar**. Todo lo que no está confirmado está marcado.

---

## 1. Qué es el juego

Pokémon Pokopia es un **juego de simulación de vida (life simulation)** para **Nintendo Switch 2**, publicado por The Pokémon Company y Nintendo, y desarrollado por **The Pokémon Company, GAME FREAK inc. y KOEI TECMO GAMES** [SRC001, SRC002].

- **Género:** life simulation / town-building / sandbox (el primer juego de simulación de vida de la franquicia) [SRC001, SRC015].
- **Fecha de lanzamiento global:** 5 de marzo de 2026 [SRC004, SRC015, SRC003].
- **Jugadores:** 1–4 [SRC001, SRC015].
- **Tamaño de descarga en eShop:** ~10 GB [SRC015].
- **Precio/bonus:** la alfombra Ditto (Ditto Rug) como bonus de compra anticipada vía Mystery Gifts [SRC004, SRC005, SRC006].

### 1.1 Premisa / lore oficial

> "Pokémon y las personas alguna vez vivieron felices juntos, pero el mundo se ha marchitado y los humanos ya no están. El único residente que queda es el Profesor Tangrowth, que vive solo en el yermo." [SRC060]

El jugador interpreta a un **Ditto** que ha despertado de un largo sueño y **se ha transformado en humano**. Ditto conoce al **Profesor Tangrowth** (un Tangrowth peculiar que vive solo en un lugar donde humanos y Pokémon convivían), y decide reconstruir la zona desde cero para crear una utopía para todos [SRC003, SRC001].

### 1.2 Bucle de juego central

1. Ditto aprende **movimientos** de los Pokémon que conoce (p. ej. Leafage de Bulbasaur para crear vegetación, Water Gun de Squirtle para revivir plantas secas, Rock Smash, Glide, Surf…) [SRC001, SRC003].
2. El jugador recolecta materiales, fabrica objetos, cultiva vegetales y **construye hábitats y casas** para atraer Pokémon. [SRC001, SRC015].
3. Los Pokémon llegan con **requests (peticiones)**, algunas importantes ligadas a problemas grandes. Cumplirlas desarrolla el área. [SRC003].
4. La construcción de hábitats atrae Pokémon; el estado del área se mide con **Environment Level**; el jugador progresa por **Trainer Ranks** y desbloquea más áreas. [SRC034, SRC019].
5. Hay ciclo día/noche ligado al **tiempo real**, clima cambiante y ubicaciones con características propias. [SRC001].

### 1.3 Naturaleza del conocimiento del dominio

Pokopia es un dominio **rico en entidades interconectadas**: no existe combate; la progresión depende de acciones de mundo (construcción, agricultura, cocina, hábitats, peticiones, energía, agua). Esto lo convierte en un buen caso de estudio para razonamiento multi-hop (véase `domain-map/domains.md` y `candidate-questions/questions.md`).

---

## 2. Sistema de juego en una mirada

| Aspecto | Dato | Fuente |
|---|---|---|
| Plataforma | Nintendo Switch 2 (exclusivo) | [SRC001, SRC015] |
| Género | Life simulation / town building | [SRC001, SRC015] |
| Desarrolladores | The Pokémon Company / GAME FREAK / KOEI TECMO GAMES | [SRC002] |
| Protagonista | Ditto transformado en humano | [SRC001, SRC003] |
| Mentor principal | Profesor Tangrowth | [SRC003, SRC007] |
| Nº de Pokémon (Pokédex principal) | 300 | [SRC030, SRC043] |
| Pokédex de eventos | Independiente | [SRC030, SRC029] |
| Pokédex de Cloud Islands | Idéntica al principal | [SRC030] |
| Pokédex de Bubbly Basin (DLC) | Independiente | [SRC015] |
| Nº de hábitats | 209 (base) | [SRC043] |
| Especialidades | ~31 confirmadas (ver `entities/pokemon.md`) | [SRC042, SRC048] |
| Áreas principales | Withered Wasteland, Bleak Beach, Rocky Ridges, Sparkling Skylands | [SRC044] |
| Zona sandbox | Palette Town | [SRC044] |
| DLC | Expansion Pass (3 partes); Parte 1: Bubbly Basin (5 ago 2026) | [SRC013, SRC014] |
| Movimientos de Ditto | ~10 primarios + ~5 secundarios + 1 de DLC (Dive) | [SRC016, SRC013] |
| Monedas | Life Coins (PC Shop) + sistema de trueque (Trade) | [SRC035] |
| Multiplayer | Link Play (online/local), GameShare, Cloud Islands | [SRC009, SRC012] |

---

## 3. El mundo (contexto narrativo-geográfico)

El juego transcurre en un **Kanto reimaginado y abandonado**: varias áreas están basadas en ciudades de Kanto [SRC044, SRC061]:

| Área | Inspiración | Notas |
|---|---|---|
| Withered Wasteland | Ciudad Fucsia (Fuchsia City) | Área inicial; sequía; quest "Yawn Up a Storm" [SRC044, SRC061] |
| Bleak Beach | Ciudad Carmín (Vermilion City) | Incluye el S.S. Anne; ciudad a oscuras; quest "Brighten Things Up" [SRC044, SRC061] |
| Rocky Ridges | Ciudad Plateada (Pewter City) | Bosque con vías de tren; incluye el Museo de Ciudad Plateada; quest "Time to Party" [SRC044, SRC061] |
| Sparkling Skylands | Híbrido Celadon + Saffron | Islas flotantes en el cielo [SRC044, SRC061] |
| Palette Town | Ciudad Paleta (Pallet Town) | Zona sandbox de construcción libre; Eevee como personaje especial [SRC044, SRC044] |

> ⚠️ **Desacuerdo entre fuentes sobre el número de áreas y su orden de desbloqueo** — ver `contradictions/contradictions.json` (C01, C02).

---

## 4. Fuentes consultadas (resumen)

- **Nivel 1 (oficial):** press.pokemon.com, asia-press.portal-pokemon.com, pokopia.pokemon.com, nintendo.com, Nintendo Support. [SRC001–SRC014, SRC060, SRC064]
- **Nivel 2 (wikis/bases de datos):** Serebii.net, Bulbapedia, The Games Wiki, Fextralife. [SRC015–SRC031, SRC032–SRC041]
- **Nivel 3 (guías):** Nintendo Life, VGC, Polygon, Eurogamer, Game8, Dexerto, GamesRadar, Pocket Tactics, IGN, GameRant, pokopiaguide.com, thegamer, rectifygaming, Vandal, popcultdaily, pokopia.center, pokopiamap.com. [SRC042–SRC058, SRC062, SRC063]
- **Nivel 4 (comunidad):** r/Pokopia (acceso indirecto vía prensa), Kotaku, Eurogamer, YouTube (Sieger Geek Labs, AbdallahSmash, IGN). [SRC052–SRC055, SRC059]

Inventario completo con URLs: `sources/sources.json`.

---

## 5. Lecturas recomendadas dentro del paquete

- `domain-map/domains.md` — los sistemas del juego.
- `domain-map/relationships.md` — mapa conceptual de alto nivel.
- `entities/*.md` — catálogos por entidad.
- `rules/rules.json` — reglas de juego/normas de negocio.
- `contradictions/contradictions.json` — desacuerdos entre fuentes.
- `knowledge-gaps/gaps.md` — lo que no sabemos.
- `candidate-questions/questions.md` — preguntas para futuro Gold Dataset.
