# Pokopia — Candidate Questions (preguntas candidatas)

> Preguntas potenciales para un futuro **Gold Dataset** de evaluación de razonamiento sobre el dominio.
> Cada pregunta incluye los metadatos definidos en `instrucciones_research.txt` §20.

**Esquema de metadatos por pregunta:** `question`, `category`, `concepts_required`, `entities_required`, `relationships_required`, `sources_required`, `requires_multi_hop`, `requires_structured_data`, `requires_case_memory`, `expected_difficulty`, `why_this_question_is_interesting`.

---

## A. Direct Lookup (consulta directa)

### Q01
- **question:** ¿Qué movimiento aprende Ditto al conocer a Squirtle, y en qué área?
- **category:** direct_lookup
- **concepts_required:** movimientos, áreas
- **entities_required:** Squirtle, Ditto, Water Gun, Withered Wasteland
- **relationships_required:** R002 (Ditto aprende_de Squirtle)
- **sources_required:** SRC016
- **requires_multi_hop:** false
- **requires_structured_data:** false
- **requires_case_memory:** false
- **expected_difficulty:** easy
- **why_this_question_is_interesting:** Verifica el conocimiento de relaciones entidad→movimiento→área de forma simple.

### Q02
- **question:** ¿Cuántos Pokémon componen la Pokédex principal del juego?
- **category:** direct_lookup
- **concepts_required:** Pokédex
- **entities_required:** (ninguna específica)
- **relationships_required:** —
- **sources_required:** SRC030, SRC043
- **requires_multi_hop:** false
- **requires_structured_data:** false
- **requires_case_memory:** false
- **expected_difficulty:** easy
- **why_this_question_is_interesting:** Número canónico; detecta la contradicción C09 (300 vs 423).

### Q03
- **question:** ¿Quién es el Pokémon con la especialidad exclusiva 'Dream Island'?
- **category:** direct_lookup
- **concepts_required:** especialidades
- **entities_required:** Drifloon
- **relationships_required:** R016 (exclusiva_de)
- **sources_required:** SRC042, SRC047
- **requires_multi_hop:** false
- **requires_structured_data:** false
- **requires_case_memory:** false
- **expected_difficulty:** easy
- **why_this_question_is_interesting:** Prueba el conocimiento de especialidades exclusivas de NPCs.

### Q04
- **question:** ¿Cuál es el sabor (flavor) de comida que debes ofrecer a un Pokémon para subir su Comfort?
- **category:** direct_lookup
- **concepts_required:** flavors, comfort
- **entities_required:** (genérico: Pokémon)
- **relationships_required:** R009 (comida→Comfort)
- **sources_required:** SRC033
- **requires_multi_hop:** false
- **requires_structured_data:** false
- **requires_case_memory:** false
- **expected_difficulty:** easy
- **why_this_question_is_interesting:** Conocimiento básico de personalización por sabor.

### Q05
- **question:** ¿En qué área se desbloquea la cocina y quién la desbloquea?
- **category:** direct_lookup
- **concepts_required:** cocina, áreas
- **entities_required:** Chef Dente, Rocky Ridges
- **relationships_required:** R024 (cocina desbloquea Chef Dente)
- **sources_required:** SRC033, SRC049
- **requires_multi_hop:** false
- **requires_structured_data:** false
- **requires_case_memory:** false
- **expected_difficulty:** easy
- **why_this_question_is_interesting:** Relación NPC→sistema→área.

---

## B. Multi-hop (razonamiento encadenado)

### Q06
- **question:** Para cocinar pan en Pokopia necesitas un Pokémon con especialidad Burn y trigo. Si quieres aumentar el Comfort de un Pokémon dándole pan dulce, ¿qué condiciones del sistema de cocina deben cumplirse (en términos de estación, especialidad e ingrediente)?
- **category:** multi_hop
- **concepts_required:** cocina, estaciones, especialidades, agricultura, flavors
- **entities_required:** Bread Oven, Burn, Wheat, Chef Dente
- **relationships_required:** R014, R024, R025, R008
- **sources_required:** SRC049, SRC033, SRC032
- **requires_multi_hop:** true
- **requires_structured_data:** false
- **requires_case_memory:** false
- **expected_difficulty:** medium
- **why_this_question_is_interesting:** Encadena agricultura→cocina→especialidad→comfort en una sola pregunta realista.

### Q07
- **question:** Un jugador quiere desbloquear Sparkling Skylands. ¿Qué peticiones (requests) y qué rango debe completar primero, y qué movimiento aprende Ditto ahí que no se puede aprender antes?
- **category:** multi_hop
- **concepts_required:** progresión, requests, movimientos, áreas
- **entities_required:** Sparkling Skylands, Bleak Beach, Rocky Ridges, Dragonite
- **relationships_required:** R012, R013, R001
- **sources_required:** SRC034, SRC044, SRC016
- **requires_multi_hop:** true
- **requires_structured_data:** false
- **requires_case_memory:** false
- **expected_difficulty:** medium
- **why_this_question_is_interesting:** Enlaza desbloqueo de áreas, hitos de rango y movimientos por área.

### Q08
- **question:** ¿Cómo se puede hacer que un Pokémon nocturno aparezca durante el día, y qué implica esto para el diseño de su hábitat?
- **category:** multi_hop
- **concepts_required:** aparición, hábitats, luz/oscuridad
- **entities_required:** (genérico)
- **relationships_required:** R007
- **sources_required:** SRC017
- **requires_multi_hop:** true
- **requires_structured_data:** false
- **requires_case_memory:** false
- **expected_difficulty:** medium
- **why_this_question_is_interesting:** Aplica la regla de inversión luz/oscuridad a un caso concreto de diseño.

### Q09
- **question:** Un jugador está en un área con Environment Level 2 y quiere cultivar tomates. ¿Qué debe hacer primero y por qué?
- **category:** multi_hop
- **concepts_required:** Environment Level, agricultura, semillas
- **entities_required:** Tomates (cultivo), Rototiller, Water Gun
- **relationships_required:** R011, R017, R010
- **sources_required:** SRC032
- **requires_multi_hop:** true
- **requires_structured_data:** false
- **requires_case_memory:** false
- **expected_difficulty:** medium
- **why_this_question_is_interesting:** Obliga a razonar que las semillas requieren Env Level 3 y que Rototiller necesita suelo regado.

### Q10
- **question:** ¿Qué recursos únicos puedes obtener visitando Dream Islands y con qué muñeco (doll) llegarías a una isla volcánica?
- **category:** multi_hop
- **concepts_required:** Dream Islands, recursos, muñecos
- **entities_required:** Arcanine (doll), Stardust, Pokemetal
- **relationships_required:** R020, R021, R022
- **sources_required:** SRC047, SRC022, SRC048
- **requires_multi_hop:** true
- **requires_structured_data:** false
- **requires_case_memory:** false
- **expected_difficulty:** medium
- **why_this_question_is_interesting:** Conecta visitas diarias, muñecos, islas y recursos raros.

### Q11
- **question:** ¿Por qué un jugador tendría que subir el Comfort de un Pokémon legendario antes que el de uno normal para completar el juego más rápido?
- **category:** multi_hop
- **concepts_required:** Comfort, Environment Level, legendarios
- **entities_required:** (legendarios en general)
- **relationships_required:** R010, R023
- **sources_required:** SRC023, SRC045
- **requires_multi_hop:** true
- **requires_structured_data:** false
- **requires_case_memory:** false
- **expected_difficulty:** medium
- **why_this_question_is_interesting:** Aplica la regla de que los legendarios aportan más puntos de Environment.

---

## C. Constraint (restricciones y límites)

### Q12
- **question:** Un jugador quiere automatizar el riego de un huerto grande con Sprinklers. Si tiene 60 Life Coins, ¿cuántos Sprinklers puede comprar?
- **category:** constraint
- **concepts_required:** economía, riego, costes
- **entities_required:** Sprinkler (50 LC), Life Coins
- **relationships_required:** R011 (PC Shop), RULE016
- **sources_required:** SRC032, SRC035
- **requires_multi_hop:** false
- **requires_structured_data:** false
- **requires_case_memory:** false
- **expected_difficulty:** easy
- **why_this_question_is_interesting:** Aritmética simple sobre costes documentados (50 Life Coins).

### Q13
- **question:** El sistema eléctrico permite 64 generadores y 1024 objetos eléctricos por zona. Si ya has colocado 20 Windmills, 10 Waterwheels y 5 Mini Generators, ¿cuántos generadores puedes añadir como máximo? (Y ¿qué implicación tiene que exista este límite para el diseño de granjas automáticas?)
- **category:** constraint
- **concepts_required:** electricidad, límites
- **entities_required:** Windmill, Waterwheel, Mini Generator
- **relationships_required:** R018, R019
- **sources_required:** SRC028, SRC070, SRC071
- **requires_multi_hop:** false
- **requires_structured_data:** true
- **requires_case_memory:** false
- **expected_difficulty:** medium
- **why_this_question_is_interesting:** Combina aritmética y razonamiento sobre restricciones de diseño. Depende de C05 (resolver antes).
- **version_note:** Premisa VERSIONADA (C05 PARTIALLY CONFIRMED, Fase 1.5): la premisa "64 gen/1024 items" es válida solo en 1.1.0–1.1.1; en 1.0.x era 64/512 y desde 2.0.0+ es 128 gen excl. furnaces/1.024 items. Para el Gold Dataset debe fijarse la versión del juego en el enunciado o parametrizarse la aritmética.

### Q14
- **question:** ¿Qué condiciones debe cumplir un jugador para acceder a Bubbly Basin? Enumera todas las condiciones de juego, no solo la compra del DLC.
- **category:** constraint
- **concepts_required:** DLC, requests, movimientos, progresión
- **entities_required:** Bubbly Basin, Dive, Manaphy, Bleak Beach
- **relationships_required:** R026
- **sources_required:** SRC008, SRC013
- **requires_multi_hop:** true
- **requires_structured_data:** false
- **requires_case_memory:** false
- **expected_difficulty:** medium
- **why_this_question_is_interesting:** Exige listar todos los requisitos (update, request, movimiento) y no olvidar ninguno.

### Q15
- **question:** Un jugador quiere reclutar a Ho-Oh. ¿Qué requisitos de contenido previo se mencionan y qué objetos necesita (campanas)?
- **category:** constraint
- **concepts_required:** legendarios, objetos
- **entities_required:** Ho-Oh, Clear Bell, Lugia, Tidal Bell
- **relationships_required:** R022 (ofrece)
- **sources_required:** SRC021
- **requires_multi_hop:** true
- **requires_structured_data:** false
- **requires_case_memory:** false
- **expected_difficulty:** hard
- **why_this_question_is_interesting:** Exige sintetizar requisitos de reclutamiento de legendarios a partir de fuentes parciales.

---

## D. Comparison (comparaciones)

### Q16
- **question:** ¿Qué diferencia existe entre subir el Comfort Level de un Pokémon y subir la Friendship? ¿Se necesitan las mismas acciones?
- **category:** comparison
- **concepts_required:** Comfort, Friendship, progresión
- **entities_required:** (genérico)
- **relationships_required:** R010, (Friendship separada)
- **sources_required:** SRC023, SRC024, SRC040
- **requires_multi_hop:** true
- **requires_structured_data:** false
- **requires_case_memory:** false
- **expected_difficulty:** medium
- **why_this_question_is_interesting:** Distingue dos sistemas de vínculo que suelen confundirse.

### Q17
- **question:** Compara Utility Poles vs Wireless Power Transmitters: ¿en qué casos usarías uno u otro?
- **category:** comparison
- **concepts_required:** electricidad, distribución
- **entities_required:** Utility Pole, Wireless Power Transmitter, Porygon
- **relationships_required:** R019
- **sources_required:** SRC028, SRC051
- **requires_multi_hop:** false
- **requires_structured_data:** false
- **requires_case_memory:** false
- **expected_difficulty:** easy
- **why_this_question_is_interesting:** Comparación directa de dos infraestructuras del mismo sistema.

### Q18
- **question:** ¿Qué sistema económico (Life Coins vs trueque/Trade) usarías para conseguir un objeto raro que no se vende en el PC Shop?
- **category:** comparison
- **concepts_required:** economía, trueque
- **entities_required:** Life Coins, PC Shop, Trade
- **relationships_required:** RULE017
- **sources_required:** SRC035, SRC056
- **requires_multi_hop:** true
- **requires_structured_data:** false
- **requires_case_memory:** false
- **expected_difficulty:** medium
- **why_this_question_is_interesting:** Obliga a razonar sobre dos sistemas económicos independientes.

---

## E. Contradiction (resolución de contradicciones)

### Q19
- **question:** Algunas fuentes dicen que el juego tiene 300 Pokémon y otras que 423. ¿Cuál es el dato correcto y por qué aparece la discrepancia?
- **category:** contradiction
- **concepts_required:** Pokédex, crítica de fuentes
- **entities_required:** (Pokédex principal)
- **relationships_required:** —
- **sources_required:** SRC030, SRC043, SRC063
- **requires_multi_hop:** false
- **requires_structured_data:** false
- **requires_case_memory:** false
- **expected_difficulty:** medium
- **why_this_question_is_interesting:** Entrena al agente para distinguir fuentes fiables de marketing (C09).

### Q20
- **question:** ¿Cuántas áreas principales tiene el juego: 4 o 6? Explica la discrepancia entre fuentes.
- **category:** contradiction
- **concepts_required:** áreas, crítica de fuentes
- **entities_required:** (áreas)
- **relationships_required:** R033
- **sources_required:** SRC044, SRC061
- **requires_multi_hop:** false
- **requires_structured_data:** false
- **requires_case_memory:** false
- **expected_difficulty:** medium
- **why_this_question_is_interesting:** Resolver C01 requiere definir qué se cuenta como 'área'.

### Q21
- **question:** El Team Initiation Challenge tiene 8 o 9 etapas? ¿Cómo se explica la diferencia?
- **category:** contradiction
- **concepts_required:** progresión, final del juego
- **entities_required:** Leppa Berry
- **relationships_required:** —
- **sources_required:** SRC038, SRC042
- **requires_multi_hop:** false
- **requires_structured_data:** false
- **requires_case_memory:** false
- **expected_difficulty:** medium
- **why_this_question_is_interesting:** Resolver C06 requiere identificar el criterio de conteo.

### Q22
- **question:** ¿Cuántos legendarios hay en Pokopia: 12 o 14? ¿De qué depende la respuesta?
- **category:** contradiction
- **concepts_required:** legendarios, DLC
- **entities_required:** (legendarios), Phione
- **relationships_required:** —
- **sources_required:** SRC039, SRC045, SRC046
- **requires_multi_hop:** false
- **requires_structured_data:** false
- **requires_case_memory:** false
- **expected_difficulty:** medium
- **why_this_question_is_interesting:** La respuesta depende de si se incluye el DLC (C07).

---

## F. Novel / Creative (razonamiento novedoso sobre el dominio)

### Q23
- **question:** Diseña una cadena de automatización en Pokopia que use sensores láser, fluidos y electricidad para regar un huerto sin intervención del jugador, indicando qué componentes y especialidades necesitas y los límites del sistema que debes respetar.
- **category:** novel_creative
- **concepts_required:** sensores, electricidad, riego, automatización
- **entities_required:** Laser Sensor, Sprinkler/Water Gun, Switch, Waterwheel, Porygon
- **relationships_required:** R018, R019, RULE020, RULE019
- **sources_required:** SRC052, SRC054, SRC028
- **requires_multi_hop:** true
- **requires_structured_data:** true
- **requires_case_memory:** true
- **expected_difficulty:** hard
- **why_this_question_is_interesting:** Obliga a componer mecánicas reales en una solución creativa y a respetar los límites del sistema.

### Q24
- **question:** Si quisieras subir el Environment Level de Sparkling Skylands lo más rápido posible, ¿qué estrategia seguirías combinando legendarios, comida y requests?
- **category:** novel_creative
- **concepts_required:** Environment Level, legendarios, comida, requests
- **entities_required:** Mewtwo, Mosslax
- **relationships_required:** R010, R023, R009
- **sources_required:** SRC023, SRC033, SRC045
- **requires_multi_hop:** true
- **requires_structured_data:** false
- **requires_case_memory:** false
- **expected_difficulty:** hard
- **why_this_question_is_interesting:** Requiere sintetizar varias mecánicas en una estrategia óptima razonada.

### Q25
- **question:** ¿Qué mecánicas del juego no requieren combate y cómo contribuyen todas juntas a la 'utopía' narrativa que busca reconstruir Ditto?
- **category:** novel_creative
- **concepts_required:** (meta) diseño de juego, narrativa
- **entities_required:** Profesor Tangrowth, Ditto
- **relationships_required:** —
- **sources_required:** SRC001, SRC060
- **requires_multi_hop:** true
- **requires_structured_data:** false
- **requires_case_memory:** false
- **expected_difficulty:** hard
- **why_this_question_is_interesting:** Pregunta de síntesis que conecta mecánicas y lore.

### Q26
- **question:** Propon tres formas distintas de obtener materiales raros (p. ej. Pokemetal) y compáralas en términos de esfuerzo y disponibilidad diaria.
- **category:** novel_creative
- **concepts_required:** recursos, Dream Islands, crafting
- **entities_required:** Drifloon, Pokemetal, Doll
- **relationships_required:** R020, R022, R014
- **sources_required:** SRC022, SRC047, SRC048
- **requires_multi_hop:** true
- **requires_structured_data:** false
- **requires_case_memory:** false
- **expected_difficulty:** medium
- **why_this_question_is_interesting:** Compara rutas de obtención con restricciones (1 visita/día).

---

## G. Meta-preguntas (sobre el propio corpus)

### Q27
- **question:** ¿Qué fuente(s) utilizarías como canónicas para responder sobre el desbloqueo de áreas, y por qué descartarías las demás?
- **category:** meta
- **concepts_required:** criticidad de fuentes
- **entities_required:** —
- **relationships_required:** —
- **sources_required:** SRC034, SRC044, SRC046
- **requires_multi_hop:** false
- **requires_structured_data:** false
- **requires_case_memory:** false
- **expected_difficulty:** hard
- **why_this_question_is_interesting:** Evalúa la capacidad del agente para justificar la jerarquía de evidencia (C02).

### Q28
- **question:** Dada la contradicción sobre la tasa de Tinkagear (2:1 vs 1:3), ¿qué dato adicional necesitarías y de qué fuente para resolverla con confianza?
- **category:** meta
- **concepts_required:** criticidad de fuentes, resolución de contradicciones
- **entities_required:** Tinkagear, Iron Ingot, Tinkmaster
- **relationships_required:** R014
- **sources_required:** SRC037, SRC048
- **requires_multi_hop:** true
- **requires_structured_data:** false
- **requires_case_memory:** false
- **expected_difficulty:** hard
- **why_this_question_is_interesting:** Evalúa la planificación de verificación empírica (C04).

---

## Notas para Fase 2

- Las preguntas **Q13, Q19, Q20, Q21, Q22, Q27, Q28** dependen de la **resolución de contradicciones** (C01–C09) o de datos estructurados todavía no consolidados (GAP-03, GAP-05, GAP-07).
- **Q13 (C05, Fase 1.5):** la premisa es versionada (64 gen/1024 items solo en 1.1.0–1.1.1; ver `version_note` de Q13). Las respuestas cuantitativas sobre límites deben anclar la versión del juego (1.0.x / 1.1.0–1.1.1 / 2.0.0+).
- **Q23:** al citar RULE019 debe usarse la versión vigente (128 gen excl. furnaces / 1.024 items en 2.0.0+); el tope de 256 transmisores no está verificado.
- Antes de convertirlas en Gold Dataset, se debe decidir el **formato de respuesta esperada** (abierta vs opción múltiple vs numérica) y el **método de scoring** (manual vs LLM-as-judge).
- Las categorías `multi_hop`, `constraint`, `comparison`, `contradiction` y `novel_creative` cubren los cinco tipos de razonamiento que se quieren evaluar.
