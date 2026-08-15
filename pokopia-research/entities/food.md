# Pokopia — Entities: Food & Cooking

> Sistema de cocina: recetas, sabores, estaciones y efectos.

---

## 1. Desbloqueo

- La cocina se desbloquea al rescatar al **Chef Dente** (Greedent) en **Rocky Ridges** (quest "Time to Party!") [SRC033, SRC045, SRC049].

## 2. Estaciones de cocina

| Estación | Prepara | Requisito extra |
|---|---|---|
| Chopping Board (tabla de cortar) | Ensaladas (Salads) | — |
| Cooking Pot (olla) | Sopas (Soups) | Fuego/estufa |
| Frying Pan (sartén) | Hamburger Steak | Fuego/estufa |
| Bread Oven (horno de pan) | Pan (Breads) | Pokémon con especialidad **Burn** |

Fuente: [SRC033, SRC049]

## 3. Tipos de comida y variantes

- **4 tipos × 6 variantes = 24 recetas** base [SRC033, SRC045].
- **Smoothies** (solo DLC Bubbly Basin, update 2.0.0): se hacen con sandías; potencian **Surf** [SRC013, SRC014].

| Tipo de comida | Potencia movimiento | Fuente |
|---|---|---|
| Salad (ensalada) | Leafage | [SRC016, SRC033] |
| Soup (sopa) | Water Gun | [SRC016, SRC033] |
| Bread (pan) | Cut | [SRC016, SRC033] |
| Hamburger Steak | Rock Smash | [SRC016, SRC033] |
| Smoothie (DLC) | Surf | [SRC013] |

## 4. Sabores (Flavors)

- 5 sabores + neutro: **Sweet (dulce), Spicy (picante), Dry (seco), Bitter (amargo), Sour (ácido)** y Neutral [SRC033, SRC045].
- Cada Pokémon tiene un **flavor favorito** registrado en su entrada de Pokédex [SRC033].
- La comida del flavor favorito sube **Comfort**; la del flavor no favorito puede bajarlo [SRC033, SRC023].
- **Mosslax** otorga un buff diario según el sabor de la comida ofrecida en el Gourmet's Altar; el buff dura hasta las 5:00 AM [SRC033].

## 5. Efectos

- La comida **restaura PP por completo** y **potencia un movimiento** durante un tiempo (con su propio medidor de PP de potencia) [SRC016, SRC033].
- Puede **regalarse a los Pokémon** (sube Comfort/Friendship si es su sabor favorito) [SRC033, SRC045].
- Ingredientes vienen de la agricultura (`entities/resources.md`) [SRC032, SRC045].

## 6. Modificaciones de receta por especialidades helper

| Especialidad | Efecto en receta | Fuente |
|---|---|---|
| Chop | Shredded Salad | [SRC049] |
| Crush | Crushed Berry Salad | [SRC049, SRC033] |
| Burn | Bread Bowl | [SRC049, SRC033] |

## 7. Ingredientes conocidos

- Berries (para salad bowls y smoothies), Wheat, Potatoes, Tomatoes, Leafy Greens, Beans (todos cultivables) [SRC032, SRC045].
- Honey (especialidad Gather Honey de Vespiquen) [SRC042].

## Notas metodológicas

- La **lista completa de 24 recetas** con sus nombres e ingredientes no se ha consolidado aún (GAP-05): las fuentes describen el sistema, no la tabla íntegra. Las recetas se desbloquean por Environment Level del área [SRC033].
