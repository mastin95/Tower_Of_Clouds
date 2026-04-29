---
type: product
status: provisional
tags: ["producto","vision"]
updated: 2026-04-24
---

# Game Concept: [Título por definir]

*Created: 2026-03-23*
*Status: Draft — En desarrollo activo*

---

## Elevator Pitch

> Un roguelike deckbuilder donde escalas una Torre viva — un mundo vertical con
> ciudades, facciones y criaturas — eligiendo un campeón cuyas cartas reflejan
> quién es y cómo entiende el mundo. Los builds emergen de las cartas que eliges,
> no de menús. Fácil de aprender, difícil de dominar.

---

## Core Identity

| Aspecto | Detalle |
| ---- | ---- |
| **Género** | Roguelike deckbuilder single-player |
| **Plataforma** | PC (principal), otras por definir |
| **Jugadores** | Single-player |
| **Sesión típica** | 30-60 minutos por run |
| **Monetización** | Por definir |
| **Scope estimado** | Large — Early Access primero |
| **Títulos comparables** | Slay the Spire, Monster Train, Across the Obelisk |

---

## Core Fantasy

Eres alguien que se atreve a escalar la Torre — un lugar que promete poder, riqueza
y estatus a quienes ascienden, pero que está lleno de peligros y facciones en
conflicto. Cada campeón tiene su propia razón para estar ahí y su propia forma de
luchar, expresada a través de sus cartas. La Torre no es un dungeon vacío — es un
mundo vivo donde la narrativa se juega, no se lee.

---

## Unique Hook

Es como Slay the Spire, Y TAMBIÉN la Torre es un mundo vivo con habitantes,
facciones y zonas que tienen identidad propia — y cada campeón representa una
relación distinta con ese mundo, con cartas que son extensiones de su personalidad
y habilidades.

---

## Player Experience Analysis (MDA Framework)

### Target Aesthetics

| Aesthetic | Prioridad | Cómo lo entregamos |
| ---- | ---- | ---- |
| **Challenge** (maestría, obstáculos) | 1 | Fácil de aprender, difícil de dominar. Dificultad ascendente. |
| **Discovery** (exploración, secretos) | 2 | Descubrir sinergias entre cartas, builds emergentes, secretos de la Torre |
| **Fantasy** (rol, identidad) | 3 | Cada campeón con personalidad, cartas como extensión de quién es |
| **Expression** (autoexpresión) | 4 | Múltiples builds viables por campeón, libertad de elección |
| **Narrative** (drama, arco) | 5 | Historia del campeón contada a través del gameplay y el mundo |
| **Sensation** (placer sensorial) | 6 | Juice visual y sonoro en combos y efectos |
| **Fellowship** (conexión social) | N/A | Single-player |
| **Submission** (relajación) | N/A | No es el objetivo — el juego reta |

### Key Dynamics

- Los jugadores experimentarán con combinaciones de cartas para descubrir sinergias
- Los jugadores aprenderán patrones de bosses a través de runs repetidos
- Los jugadores desarrollarán preferencia por familias de cartas que forman builds coherentes
- Los jugadores sentirán que cada campeón juega radicalmente distinto

### Core Mechanics

1. **Deckbuilding por run** — elegir cartas de un pool amplio que definen tu build emergente
2. **Combate por turnos con cartas** — mano, maná, jugar cartas, resolver efectos
3. **Keywords por familia** — cada familia de cartas tiene mecánica única que define su identidad
4. **Mapa procedural de la Torre** — caminos ramificados con combates, eventos, asentamientos
5. **Meta-progresión** — desbloqueos entre runs que expanden el pool disponible

---

## Player Motivation Profile

### Primary Psychological Needs

| Necesidad | Cómo la satisface | Fuerza |
| ---- | ---- | ---- |
| **Autonomía** | Libertad total de build — sin subclases forzadas, el jugador elige su camino | Core |
| **Competencia** | Maestría a largo plazo — conocer las cartas, los enemigos, las sinergias | Core |
| **Relación** | Conexión con el campeón y el mundo de la Torre | Supporting |

### Player Type Appeal (Bartle)

- [x] **Achievers** — Desbloqueos, ascensiones, completar con todos los campeones
- [x] **Explorers** — Descubrir builds, sinergias, secretos del mundo
- [ ] **Socializers** — No aplica (single-player)
- [ ] **Killers/Competitors** — No es el foco principal

### Flow State Design

- **Onboarding**: El Guerrero como primer personaje — intuitivo, builds claros
- **Escalado de dificultad**: Pisos de la Torre + sistema de ascensión post-victoria
- **Feedback de mejora**: Builds que se sienten más potentes a medida que subes
- **Recuperación del fallo**: Runs cortos (30-60 min). El fallo enseña — conoces mejor los enemigos y las sinergias

---

## Core Loop

### Momento a momento (30 segundos)
Mirar tu mano, evaluar el tablero, jugar cartas. Decidir qué jugar, en qué orden,
contra qué objetivo. El placer viene de ejecutar combos y ver sinergias activarse.

### Corto plazo (5-15 minutos)
Un combate completo. Varios turnos donde tu build se pone a prueba. Tras ganar:
recompensa de cartas/reliquias → decisión de qué tomar → siguiente nodo del mapa.

### Sesión (30-60 minutos)
Un run completo — ascender la Torre desde el primer piso hasta el boss final
(o morir intentándolo). Cada run es una historia de cómo construiste tu build
y hasta dónde llegaste.

### Progresión a largo plazo
- Desbloquear nuevas cartas al pool
- Desbloquear nuevos campeones
- Niveles de dificultad ascendentes (Ascensión)
- Desbloquear reliquias/items al pool

### Retention Hooks
- **Curiosidad**: "¿Qué pasa si combino estas dos keywords?" "¿Qué hay en pisos superiores?"
- **Inversión**: Desbloqueos acumulados, progreso de ascensión
- **Maestría**: "Esta vez sé cómo jugar contra ese boss" "Conozco un build mejor"

---

## El Mundo: La Torre

### Concepto

La Torre es el mundo entero del juego — un mundo vertical, un microcosmos vivo.
No es un dungeon vacío que escalas, sino un lugar con civilización, conflicto y vida.
La Torre tiene 100 pisos conceptuales (la implementación exacta por definir).

### Por qué la gente sube

- **Recursos** — materiales y objetos valiosos en pisos superiores
- **Dinero** — riqueza y oportunidades de comercio
- **Poder físico** — hacerte más fuerte, nuevas habilidades
- **Poder social / estatus** — subir pisos = reconocimiento e influencia

### Estratificación social

La Torre es una estructura social vertical. Cuanto más arriba, más exclusivo:

| Pisos | Estrato | Descripción |
| ---- | ---- | ---- |
| **90-100** | Tabú | Nadie habla de esto. Mitos, religiones, miedo. Prohibido |
| **70-90** | Élite / Riqueza | Realeza, nobles, clases poderosas. Acceso restringido |
| **60-70** | Clase media-alta | Mercaderes exitosos, guerreros reconocidos, magos establecidos |
| **30-60** | Popurrí | Mezcla de todo — aventureros, facciones, ciudades modestas |
| **1-30** | Clase baja / Entrada | Abierto a todos. Fauna básica, primeros peligros |

### La llamada de la Torre

Todos los protagonistas comparten algo: desde pequeños han crecido con la idea de
que arriba de la Torre hay algo maravilloso. Cada uno lo absorbió de forma diferente
— un cuento, una religión, un rumor, un sueño. Pero todos sienten la llamada.
Religiones y creencias rodean la cima, la mayoría tabú.

### El velo negro

El velo negro no es magia ni un muro físico — es una **barrera psicológica
creada por los poderosos** de la Torre. Los de arriba mantienen el control
impidiendo que la gente de abajo aspire a subir. No con muros — con miedo,
religión, tabú, desinformación. Es tan efectivo que los de abajo ni siquiera
saben que existe. Solo cuando intentas escalar más allá de "tu lugar" empiezas
a sentirlo.

Funciona a tres niveles:

- **Narrativo**: Una barrera social. Los poderosos la crearon para que la gente
  no escale. Cada velo roto es una mentira desmontada.
- **Para el personaje**: Solo lo ven quienes se atreven a subir. El Guerrero lo
  ve porque su egoísmo lo hace inmune — no le importa lo que le digan que no
  puede hacer. Cada campeón lo percibe por sus propias razones.
- **Para el jugador**: El contenido bloqueado no se siente como "aún no has
  desbloqueado esto" sino como "aún no has llegado tan lejos". No es un candado
  de progresión — es misterio. Al disipar un velo, la satisfacción es doble:
  mecánica (nuevo contenido) + narrativa (revelación del mundo).

La Torre siempre estuvo ahí entera. El velo es lo que te impedía verla.

### Estructura de una run

Cada run es un intento de escalar la Torre. Estructura por definir en detalle,
pero los principios son:

- **Al morir, la Torre te expulsa** — vuelves abajo
- **El deck y el poder se pierden** — construyes de nuevo cada vez (roguelike)
- **El mundo persiste** — NPCs te recuerdan, misiones completadas se mantienen,
  zonas reveladas permanecen, relaciones persisten (historia)
- **La historia avanza al llegar a hitos** — no por número de runs
- **Una sola experiencia** — no hay "modo historia" y "modo run" separados

### Ciudades

Puntos de descanso dentro de la Torre con vida propia:
- Primera ciudad en torno al piso 10
- Más ciudades en puntos estratégicos a lo largo de la Torre
- Contienen: NPCs con misiones, NPCs con cartas, mercantes
- Más interacción que las tiendas de StS — son lugares con vida

### Misiones secundarias

Ofrecidas por NPCs en las ciudades. Son secundarias de verdad:
- Aparecen como exclamaciones dentro de las ciudades
- Fácilmente ignorables — nunca ensucian la run
- Dan recompensas extra y profundizan el worldbuilding

### NPCs clave

- **El Guardián de la Torre**: Primer NPC. No es un guardián fuerte ni imponente —
  es alguien endeble que se encuentra abajo del todo como observador de la Torre.
  Ayuda a los nuevos visitantes. Ofrece algo de valor entre varias opciones al
  inicio de cada run.

### Habitantes y enemigos

Los enemigos escalan en peligro e inteligencia a medida que subes:
- **Pisos bajos**: Fauna de la Torre (semejante al mundo exterior) — algunos agresivos, otros no
- **Pisos medios**: Fauna más peligrosa, criaturas del Vacío, merodeadores humanos
- **Pisos altos**: Amenazas inteligentes — asesinos, facciones hostiles organizadas

No todo en la Torre es hostil. Hay asentamientos, comerciantes, facciones con intereses propios.

### La Torre como narrativa

La Torre es un elemento de discordia y concordia entre los seres que la habitan.
Une y divide. Las facciones compiten por recursos, territorio y control de pisos.
El jugador experimenta esta tensión a través del gameplay, no a través de texto.

La historia no es compleja — existe para dar a luz a los personajes y sus
personalidades. El mundo tiene que ser lo suficientemente interesante para ser
explicado mecánicamente jugando, sin bombardear con información.

Inspirado en: Sword Art Online (torre con pisos-mundo, motivación de escalar).

### Arco argumental central

El velo negro es el elemento significativo de la historia.

Antes, gente valiente exploraba la Torre libremente — descubrimiento, aventura.
Pero todo lo que descubrieron los valientes fue tomado por los ricos y poderosos.
Los héroes ya no existen. El dinero es lo que mueve a la gente, el poder establecido.

Los poderosos:
- Usan los asentamientos para criar guerreros a su servicio que mantienen el control
- Manipulan a la sociedad usando el miedo al velo — el velo es su herramienta de control
- Han convertido la Torre en una estructura de poder donde ellos dictan quién sube y quién no

El Guerrero rompe este esquema porque no responde a las reglas del sistema. Su
egoísmo lo hace incontrolable.

> **Para más adelante**: Los magos (normales y del vacío) tienen relación con todo
> esto desde las sombras. Se definirá después de asentar las bases del Guerrero
> y la estructura de juego.

---

## Campeones

### Filosofía de diseño

- **Un campeón por run** (estructura Slay the Spire)
- Cada campeón tiene un pool de cartas amplio con varias **familias temáticas**
- Los builds **emergen orgánicamente** de las cartas elegidas durante el run
- Cada familia de cartas tiene su propia **keyword/mecánica única**
- Las cartas son extensión de la personalidad del campeón — el arte muestra al
  campeón ejecutando la habilidad (pinceladas, no cinemáticas)
- Cada campeón tiene su propia relación con la Torre y motivo para escalarla

### Campeón 1: El Guerrero

- **Origen**: Viene de fuera de la Torre
- **Historia**: Se percibe como alguien débil, del montón. Pero algo en la Torre lo
  llama (mostrado sutilmente al jugador). Es una historia de superación — alguien
  que empieza sin nada y se construye a sí mismo. Sube por **egoísmo propio** —
  no es un héroe noble, no busca salvar a nadie. Quiere subir porque quiere.
  Esa honestidad egoísta es lo que lo hace inmune al velo negro. Durante el
  ascenso encontrará un propósito, o desarrollará el que ya tenía.
- **Estilo**: Absorbe y adapta. Pool amplio de cartas — no se limita a una disciplina.
- **Familias de cartas**: Artes marciales, armas, y más por definir
- **Keywords**: Por diseñar (cada familia tendrá la suya)
- **Habilidad base** (tipo reliquia inicial de StS): "Inicio Rápido" (nombre provisional)
  — la primera carta de golpe en cada combate otorga +1 de fuerza
- **Deck inicial**: Básico como StS (golpes y defensas genéricos) + 2 cartas propias:
  - **Golpe Fuerte** (puños) — aplica la keyword **Contusión**
  - **Defensa Fuerte** — reduce el daño recibido un 25% durante 1 turno
- **Nota**: El deck inicial (excepto las 2 cartas propias) será igual para todos
  los campeones a priori

### Campeón 2: El Mago

- **Origen**: Ciudad 1 (~piso 10) — una escuela de magos humilde y simple
- **Historia**: Repudiado por su propia escuela. Rechazado por los suyos.
  Razón para subir por definir.
- **Familias de cartas**: Magia elemental, vacío, invocación, y más por definir
- **Keywords**: Por diseñar
- **Se desbloquea**: Al llegar a la Ciudad 1 en el modo historia

### Campeón 3: El Recolector

- **Origen**: Ciudad 2 (piso por definir) — clase trabajadora de la Torre
- **Historia**: Alguien práctico, con pico y herramientas de artificiero/excavador.
  No es un luchador de formación, pero pelear constantemente contra monstruos lo
  ha hecho sorprendentemente bueno en combate. Razón para subir por definir.
- **Familias de cartas**: Por definir (herramientas, explosivos, minería, supervivencia...)
- **Keywords**: Por diseñar
- **Se desbloquea**: Al llegar a la Ciudad 2

### Campeón 4: El Espía/Asesino

- **Origen**: Ciudad 3 (piso por definir) — las sombras de la Torre
- **Historia**: Opera desde las sombras. Su naturaleza habla por sí misma.
  Razón para subir por definir.
- **Familias de cartas**: Por definir (sigilo, venenos, precisión...)
- **Keywords**: Por diseñar
- **Se desbloquea**: Al llegar a la Ciudad 3

### Notas sobre campeones

- Son 4 campeones en total (Guerrero + 3 de las ciudades)
- Cada uno viene de un contexto social diferente de la Torre
- Cada uno tendrá su propia razón egoísta para subir y relación con el velo
- Las razones concretas se definirán más adelante

---

## Narrativa

### Principios

- La narrativa se **juega**, no se lee
- Las mecánicas de los campeones explican cómo funciona el mundo
- Los enemigos tienen contexto narrativo natural dentro de la Torre
- Worldbuilding a través de: cartas (arte y nombres), enemigos, eventos, zonas
- **Nunca bombardear con información** — el jugador absorbe el mundo jugando

### Momentos narrativos (estilo novela visual)

En momentos muy puntuales, el personaje habla o piensa — estilo novela visual.
El jugador ve el mapa desde fuera y lee al personaje. Esto ocurre SOLO en:

- Hitos narrativos relevantes de la historia
- Primeros encuentros con NPCs importantes (Guardián, mercante, etc.)
- Revelaciones del mundo (como ver el velo negro por primera vez)

No en cada combate, no en cada evento. Solo cuando merece la pena. Son meras
conversaciones y pensamientos, pocos y puntuales.

### Tutorial: Los primeros pisos

Los primeros pisos (~10, adaptable) sirven como tutorial y primera revelación
narrativa a la vez. Cada piso enseña una mecánica de juego:

- Ataque básico → Defensa básica → Cartas especiales del campeón → Habilidad
  pasiva → Eventos → Mecánicas de run (tienda, recompensas)

Al final del tutorial, el jugador llega a la primera ciudad y ve por primera
vez el **velo negro** justo encima. El Guerrero se pregunta qué es esa oscuridad
(momento novela visual). Primer gancho narrativo: el jugador sabe jugar Y tiene
una pregunta — ¿qué hay más allá del velo?

El número exacto de pisos del tutorial se adaptará a las mecánicas que necesitemos
enseñar.

### Profundidad

Más que Slay the Spire (casi sin narrativa), cercano a Monster Train (premisa clara,
mundo que justifica las mecánicas), con mayor riqueza en el worldbuilding. El reto:
crear un mundo lo suficientemente interesante que pueda ser explicado mecánicamente
sin texto excesivo.

---

## Game Pillars

> Por definir en detalle. Candidatos basados en la visión actual:

### Pilar 1: Maestría a través de conocimiento
Cada run enseña algo. El jugador mejora porque *sabe más*, no porque desbloquea
más poder.

### Pilar 2: Builds emergentes, no prescriptivos
El jugador descubre su build, no lo selecciona de un menú. Las cartas que eliges
cuentan quién eres.

### Pilar 3: El mundo se juega, no se lee
La narrativa existe a través de las mecánicas, el arte y los encuentros. Nunca
a través de walls of text.

### Anti-Pillars

- **NO es un RPG narrativo** — la historia está presente pero no es el centro
- **NO es un juego de colección** — no acumulas cientos de cartas entre runs
- **NOT pay-to-win** — si hay monetización, es cosmética o expansiones de contenido

---

## Inspiration and References

| Referencia | Qué tomamos | Qué hacemos diferente | Por qué importa |
| ---- | ---- | ---- | ---- |
| Slay the Spire | Estructura de run, 1 campeón, builds emergentes | La Torre como mundo vivo, mayor worldbuilding | Valida la estructura core |
| Monster Train | Mundo con premisa que justifica mecánicas | No multi-lane, pero sí mundo con identidad | Valida narrativa funcional |
| Across the Obelisk | RPG depth en deckbuilder, personajes con identidad | Single-player, builds por elección no por party | Valida profundidad de personajes |
| Balatro | Combos adictivos, descubrir sinergias | Contexto narrativo, mundo, personajes | Valida el dopamine loop de sinergias |

**Inspiraciones no-gaming**: Sword Art Online (torre con pisos-mundo, motivación de escalar)

---

## Target Player Profile

| Atributo | Detalle |
| ---- | ---- |
| **Rango de edad** | 16-35 |
| **Experiencia gaming** | Mid-core a Hardcore |
| **Tiempo disponible** | Sesiones de 30-60 minutos |
| **Plataforma** | PC principal |
| **Juegos que juegan** | Slay the Spire, Monster Train, Balatro, Hades |
| **Lo que buscan** | Un deckbuilder con más profundidad de mundo y personajes con identidad |
| **Qué los alejaría** | Gameplay repetitivo, falta de variedad de builds, walls of text |

---

## Technical Considerations

| Consideración | Evaluación |
| ---- | ---- |
| **Engine** | Unity 6.3 LTS (6000.3) — ya configurado, asset base (RogueEngine) en Unity |
| **Desafíos técnicos clave** | Keywords únicas por familia, sistema de combos/sinergias, AI de enemigos con patrones |
| **Estilo artístico** | 2D con estilo propio — por definir en detalle |
| **Complejidad del art pipeline** | Media (asset base + modificaciones + arte nuevo) |
| **Audio** | Moderado — SFX de combate, música ambiental por zona |
| **Networking** | Ninguno (single-player) |
| **Volumen de contenido** | EA: 1 campeón, 2-3 zonas, ~100 cartas. Full: 2+ campeones, 3+ zonas, 200+ cartas |
| **Sistemas procedurales** | Mapa de la Torre (ya implementado en RogueEngine) |

---

## Risks and Open Questions

### Design Risks
- Las keywords por familia pueden ser difíciles de balancear entre sí
- El worldbuilding mecánico es un reto de diseño complejo — fácil caer en texto excesivo
- Builds emergentes requieren un pool de cartas muy bien diseñado

### Technical Risks
- Implementar keywords únicas puede requerir modificaciones profundas de RogueEngine
- La AI de bosses con patrones aprendibles requiere diseño y testing extensivo

### Market Risks
- Género saturado — StS, Monster Train, y muchos más. Necesita diferenciación clara
- Desarrollador solo aprendiendo — velocidad de desarrollo incierta

### Scope Risks
- "Mundo vivo" puede crecer indefinidamente si no se acota
- Cada campeón nuevo multiplica contenido necesario (cartas, keywords, balanceo)

### Open Questions
- ¿Cuáles son las keywords concretas de cada familia de cartas?
- ¿Cuántas zonas tiene la Torre? ¿Cuál es la estructura exacta?
- ¿Hay facciones definidas? ¿Cuántas? ¿Qué quieren?
- ¿Cómo es la meta-progresión exacta? ¿Qué se desbloquea y cómo?
- ¿Cómo se monetiza? ¿Premium? ¿EA con precio?
- ¿Cuál es el estilo artístico concreto?
- ¿El Mago quién es y qué lo motiva?

---

## MVP Definition

**Hipótesis core**: Los jugadores encuentran satisfactorio el loop de combate con
cartas + keywords + builds emergentes durante runs de 30+ minutos.

**Requerido para MVP**:
1. El Guerrero jugable con al menos 2 familias de cartas con keywords funcionales
2. 2 zonas de la Torre con combates, eventos básicos y boss por zona
3. Pool de ~80-100 cartas con sinergias funcionales entre familias
4. Meta-progresión básica (desbloqueo de cartas)

**Explícitamente NO en MVP**:
- Segundo campeón (Mago)
- Narrativa elaborada / lore profundo
- Sistema de ascensión completo
- Arte final (placeholder aceptable)
- Audio pulido

### Scope Tiers

| Tier | Contenido | Features | Objetivo |
| ---- | ---- | ---- | ---- |
| **MVP** | 1 campeón, 2 zonas, ~80 cartas | Core loop + keywords | Validar que el loop es divertido |
| **Early Access** | 1 campeón completo, 3 zonas, ~120 cartas | Loop + meta-progresión + ascensión | Lanzar al público, recoger feedback |
| **EA Update 1** | +Mago, cartas nuevas | 2 campeones, más contenido | Expandir variedad |
| **1.0** | 2+ campeones, 3+ zonas, 200+ cartas, lore completo | Todo pulido | Lanzamiento completo |

---

## Next Steps

- [ ] Definir keywords concretas por familia de cartas
- [ ] Diseñar la estructura de zonas de la Torre
- [ ] Definir las facciones del mundo
- [ ] Diseñar el Guerrero en detalle (familias, cartas iniciales)
- [ ] Diseñar patrones de bosses
- [ ] Crear primer prototipo con una keyword funcional
- [ ] Decompose into systems (`/map-systems`)
- [ ] Author per-system GDDs (`/design-system`)


