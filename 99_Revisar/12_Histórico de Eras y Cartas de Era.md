---
type: review
status: archived
tags: [revisar, historico, eras]
updated: 2026-04-24
---

# Histórico de Eras y Cartas de Era

> Extraído desde [[14_Vocabulario y Nomenclatura]] para limpiar el vault.
> Este contenido se conserva como historial de proceso, no como diseño vigente.

## 4. Sistema de eras — viajes en el tiempo

### 4.1 Concepto general

Cada piso de la Torre pertenece a una **línea temporal / era histórica distinta**. El Guerrero es arrastrado cronológicamente hacia adelante a través de eras, rememorando vidas pasadas de su alma. La aleatoriedad de eras es el motor narrativo y de rejugabilidad.

### 4.2 Estructura del juego — dos ciclos

> **Actualizado 2026-04-19 (segunda parte de sesión):** la estructura del juego se organiza en dos **ciclos narrativos** encadenados, no en runs independientes desde el principio. Ver §4.13 para detalle completo.

**Ciclo 1 — Tutorial narrativo (una sola vez por jugador):**
- Run lineal **fija** — todo determinado: eras, enemigos, recompensas básicas, boss final.
- Se juega **una vez** al empezar el juego. Es el tutorial + exposición del argumento.
- Termina con el **boss-agente-temporal** que rompe el tiempo y lanza al Guerrero al Ciclo 2.
- **Orden de eras:** cronológico fijo, prehistoria → eras intermedias → eras modernas.

**Ciclo 2 — Caos roguelike (repetible):**
- Runs normales del juego. El formato largo del título.
- Eras mantienen el **mismo orden cronológico** que el Ciclo 1 (prehistoria → intermedia → moderna), con posible aleatoriedad dentro de cada rango (a decidir — ver §4.5).
- Enemigos **se mezclan entre eras** con flavour adaptado a la era donde aparecen (ver §4.10).
- Pool del Guerrero **unificado**: todas las keywords de las 3 eras están disponibles desde el Acto 1 del Ciclo 2 (ya las ha "aprendido" en el Ciclo 1).
- **Cartas de era sí permanecen ligadas a la era de su acto** — no se mezclan (justificación diegética: son alter egos del protagonista en líneas temporales previas, ver §4.11).
- La **victoria final real** se fijará en alguna ascensión (a decidir — ver §10 tensiones).

**Actos por ciclo:**

Base provisional **3-4 actos por ciclo** (para testear; ajustable tras prototipo).

| Acto | Rango de era |
|------|--------------|
| **Acto 1** | **Prehistoria** (punto de partida fijo del ciclo) |
| **Acto 2** | Era intermedia (clásica / medieval / feudal / etc.) |
| **Acto 3** | Era moderna (industrial / cyberpunk / distopía / etc.) |
| **Acto 4 (opcional)** | Era futura / final — por definir si se implementa como acto separado o se funde en Acto 3 |

El número exacto de actos y qué eras concretas ocupan cada slot en el Ciclo 1 (y si hay variación en Ciclo 2) queda **pendiente de fijar** en sesiones posteriores.

### 4.3 Flecha del tiempo

- **Siempre cronológicamente hacia adelante** (de más antiguo a más futuro)
- Lore: el alma **regresa** al pasado remoto (acto 1 = prehistoria), y luego **"escapa hacia adelante"** rememorando vidas pasadas una tras otra
- Narrativamente: **inercia** — todo empuja al Guerrero hacia adelante, no puede detenerse. La Torre no permite quedarse

### 4.4 Portales de transición

- Al vencer al boss de un acto, se abre un **portal interdimensional**
- El portal arrastra al Guerrero a la siguiente era — la era de destino la decide **aleatoriamente el juego**
- Visualmente: anomalía temporal, grieta en la realidad
- Lore: la Torre expulsa al Guerrero hacia adelante, no le permite quedarse en ninguna era

### 4.5 Elección de era — por ciclo

> **Actualizado 2026-04-19:** la decisión anterior ("era 100% aleatoria al lanzamiento") queda superada por la estructura de dos ciclos.

**Ciclo 1 (tutorial):** eras **completamente fijas**. No hay elección ni aleatoriedad. El jugador vive la presentación narrativa en orden cronológico, con las eras concretas que el diseño escoja (a fijar más adelante).

**Ciclo 2 (caos):**
- Orden cronológico de rangos de era **siempre igual** (prehistoria → intermedia → moderna).
- **Aleatoriedad dentro de cada rango** — a decidir. Opciones abiertas:
  - **Opción A (repetición estricta):** la era concreta es la misma que el Ciclo 1 (ej. si Ciclo 1 acto 2 era Medieval, en Ciclo 2 acto 2 siempre es Medieval). El cambio viene por los enemigos mezclados y el pool unificado, no por las eras.
  - **Opción B (aleatoriedad dentro del rango):** la era concreta se elige aleatoriamente entre las opciones disponibles del rango (ej. acto 2 puede ser Medieval, Feudal Japonesa, Clásica, etc.). Añade rejugabilidad.
  - **Opción C (A/B test post-launch):** portal con 2 opciones visibles para mitigar frustración — reservado, no implementar inicialmente.
- **Decisión pendiente** — se pospone hasta fijar qué eras concretas existen en el juego y cuántas hay por rango.

**Razón filosófica de la aleatoriedad (si se elige B):** anticipación y sorpresa, filosofía Slay the Spire (no eliges zona del acto). Pero la decisión definitiva depende de contenido y testeo.

### 4.6 Boss de acto

- Cada acto tiene un boss que **ES MANIFESTACIÓN DE LA ERA** (ej: boss medieval = caballero corrupto; boss cyberpunk = hacker inmortal; boss robot = IA suprema)
- Puede ser también **reinterpretación de un boss general recurrente** — una entidad que se manifiesta distinto en cada era
- Idea abierta (no decidida): boss final del juego = **entidad recurrente REVELADA** (ha estado disfrazada en cada acto). Conecta con lore del velo negro — los poderosos de la Torre que controlan el sistema

#### 4.6.1 El boss-agente-temporal — final del Ciclo 1 (2026-04-19)

**Papel en la estructura:** cierra el Ciclo 1 y gatilla el paso al Ciclo 2 (caos). No es un boss derrotable en sentido estricto en la primera derrota — **gana la batalla narrativa** independientemente de que el jugador luche bien.

**Qué hace diegéticamente:**
- Es **el agente que rompe el tiempo**. Tras la victoria aparente del Guerrero al final del Ciclo 1, el boss-agente revela que la estructura lineal que acabamos de atravesar era tutelada por él (o por el sistema de la Torre). Rompe esa tutela: mezcla las eras, destruye el orden establecido, y **devuelve al Guerrero al inicio de la Torre** — pero ahora con las eras imbricadas, los enemigos desplazados temporalmente, y el alma del Guerrero más despierta (pool unificado).
- Advierte al Guerrero: *"el orden que viste no era real. Lo voy a mezclar. No podrás superarlo."*
- Narrativamente es un **punto de no retorno**. No se vuelve a vivir el Ciclo 1 — esta es la despedida de ese modo del juego.

**Identidad narrativa (por definir):**
- Posibles conexiones con la **entidad recurrente** ya mencionada en §4.6 — podría ser la misma entidad o una superior.
- Posibles conexiones con el **velo negro** y los poderosos de la Torre ([[21_Biblia del Mundo]]).
- Nombre, aspecto visual, voz: pendiente.

**Mecánicamente en el combate:**
- Combate completo con sus propias mecánicas únicas.
- Desenlace: independientemente de si el jugador lo "vence" o es "vencido", la escena post-combate siempre transiciona al Ciclo 2. El diseño definirá si mostrar una victoria simbólica del Guerrero que luego el boss neutraliza narrativamente, o una derrota dura con revelación.
- **Pendiente:** diseño mecánico específico del combate.

**Por qué es importante para el diseño:**
- Es el **cierre narrativo del tutorial** — el jugador entiende que "lo que aprendí era solo el principio, ahora viene el caos".
- Es el **rito de paso** ludonarrativo al modo de juego principal (runs repetibles).
- Conecta toda la filosofía de paradoja, alter egos temporales, viajes en el tiempo: el boss-agente es **literalmente la causa** del caos temporal que el jugador va a vivir de aquí en adelante.

### 4.7 Cartas por era

- Cada era tiene su propio pool de cartas (~20 cartas por era según estimación inicial)
- **Arte único por carta** (estilo Slay the Spire — no arte modular ni silueta + overlay)
- El Guerrero aparece vestido/equipado de la era correspondiente (troglodita en prehistoria, samurai en feudal, cyberpunk en cyber, etc.)
- Total estimado en el juego base: **100-120 cartas con arte único**
- **Coste de arte asumido** como inversión necesaria del proyecto. Martin consciente del presupuesto

### 4.8 Identidad visual de cartas por era

- **MISMO COLOR BASE** que las cartas normales del personaje (para no romper la coherencia del pool)
- Diseño claramente de la era (sin desentonar exageradamente)
- El jugador reconoce la era por el arte y elementos decorativos
- **Opcional (pendiente decisión):** tag/ícono de era en la esquina de la carta para identificación inequívoca cuando los efectos referencien subclase

### 4.9 Subclase temporal interna

- Cada carta tiene **metadata invisible** indicando a qué era pertenece
- El jugador **NO ve "Subclase: medieval"** escrito en la carta
- Pero sí ve el arte que lo comunica (Guerrero troglodita = prehistoria, etc.)
- Algunos efectos raros pueden referenciar la subclase mecánicamente (ej: "por cada era distinta en tu descarte...")

### 4.10 Enemigos por era

- Cada era tiene sus propios enemigos con arte único
- **Keywords únicas por enemigo de cada era** (ej: "Formación" para guardias medievales que se fortalecen en pares, "Hackeo" para enemigos cyberpunk que se auto-buffean, "Manada" para prehistóricos que se fortalecen con otros del mismo tipo)
- Las keywords de enemigos **NO afectan al deckbuilding del jugador** — no son coleccionables, son flavour de combate
- Los enemigos balancean la era por lo que hacen, no por lo que pide al jugador

#### 4.10.1 Ciclo 1 — enemigos puros de era

En el Ciclo 1 (tutorial), los enemigos de cada acto son **estrictamente de la era del acto**. Un enemigo prehistórico en el Acto 1, un enemigo medieval en el Acto 2, etc. Sin mezclas. El jugador aprende la identidad de cada era en estado puro.

#### 4.10.2 Ciclo 2 (caos) — enemigos mezclados con flavour adaptado

**Regla clave del caos:** en el Ciclo 2, los enemigos **se desprenden de su era de origen** y pueden aparecer en cualquier acto, **pero siempre adaptados al flavour de la era donde aparecen**.

Ejemplos concretos:
- **Mechahitler de piedra en Edad de Piedra:** mantiene su identidad mecánica (enemigo cyberpunk/robot en origen) pero adaptado al flavour prehistórico — está hecho de piedra, no tira balas sino que **tira rocas**. Conserva su **patrón de comportamiento** (mecha-dictador agresivo) pero su **aspecto y recursos** son prehistóricos.
- **Samurai mecanizado en era cyberpunk:** su raíz feudal (samurai) se manifiesta con equipamiento cyberpunk — katana láser, armadura de neón, código de honor interpretado como contrato corporativo.
- **Hacker druida en era medieval:** un enemigo originalmente cyberpunk (hacker) reinterpretado como druida que "hackea la naturaleza" con rituales.

**Por qué funciona diegéticamente:**
El boss-agente-temporal ha **mezclado las eras**. Los enemigos están desplazados de sus líneas temporales. Al caer en una era distinta, la era los **asimila estéticamente** — la era los cubre con su flavour. La identidad mecánica profunda (el patrón de comportamiento) se mantiene, lo superficial (aspecto, recursos) se adapta.

**Implicación de diseño:**
- Cada enemigo tiene una **ficha de patrón mecánico** (core) y **varias pieles/flavours** por era donde puede aparecer.
- Coste de arte asumido (cada enemigo × N eras donde puede aparecer × ~1-2 flavours).
- Es una **mecánica de rejugabilidad** sin explotar fórmulas complejas: el mismo comportamiento en contextos visuales distintos crea variedad percibida.

**Qué NO se mezcla en caos:**
- **Las cartas de era** del pool del acto siguen siendo estrictamente de su era (ver §4.11 para justificación diegética).

### 4.11 Choque de líneas temporales en el deck

- Al final del run, el mazo del jugador es un **collage temporal** — cartas de prehistoria + era acto 2 + era acto 3
- Visualmente cada carta muestra al Guerrero/acciones en su era correspondiente → contraste visible
- El "choque de líneas temporales" es parte del **flavor único** de cada run
- El mazo es el **artefacto narrativo** del viaje: cada run cuenta una historia distinta por las cartas acumuladas
- **Mecánicamente**: el choque es principalmente **estético + flavor**, no una penalty ni un buff obligado

#### 4.11.1 Cartas de era — alter egos temporales del protagonista (2026-04-19)

**Justificación diegética:** las cartas de era **NO representan al Guerrero** actual absorbiendo técnicas de esa era. Representan a **otra instancia del protagonista** que vivió en esa línea temporal — un **alter ego temporal** o **antepasado narrativo**.

- El arte de cada carta de era muestra a "un Guerrero" de esa era (samurai en feudal japón, cyber-Guerrero en cyberpunk, troglodita en prehistoria, etc.).
- Esa figura es **una manifestación del mismo alma** del protagonista que vivió en esa era en otra línea temporal — o un ancestro directo cuyo alma comparte raíz con el Guerrero actual.
- Cuando el Guerrero juega la carta, está **canalizando el eco** de ese otro-él — una forma débil de "rememoración de vida pasada" (alineado con el lore de "el alma regresa / rememora vidas pasadas").

**Implicaciones:**
- El Guerrero **no "aprende" técnicas ajenas** al atravesar la era. Accede a recuerdos ancestrales / resonancias de otras vidas.
- Las cartas de era son **personales** a su linaje anímico — por eso no aparecen en el pool de otras clases (cada clase tiene sus propios alter egos).
- Por eso en Ciclo 2 **las cartas de era siguen ligadas a su era**: un alter ego samurai es samurai, no se reconfigura a piedra aunque la línea temporal esté rota. El alma del otro-yo tiene su forma.

**Contraste con los enemigos en caos:** los enemigos son manifestaciones de la Torre o agentes externos que sí pueden ser desplazados y reasimilados estéticamente. Las cartas de era son **ecos internos del alma del Guerrero** — tienen identidad propia que no se deja desplazar.

**Conexión con el sistema Alma:**
- Las cartas Alma (Arma / Huevo) son el alma **del Guerrero actual** manifestándose en el presente del combate.
- Las cartas de era son el alma del Guerrero **rememorando otras vidas**.
- Ambos son manifestaciones del alma, pero en distinto nivel de "profundidad temporal": Alma = ahora; Carta de Era = vida pasada / alter ego.
- Ambas familias refuerzan el tema central: **el viaje del alma a través del tiempo**.

### 4.12 Inspiraciones para eras

- **Sword Art Online** — torre con pisos-mundo, cada uno con ambientación distinta
- **Chrono Trigger** — viajes entre eras (Prehistoria, Edad Media, Futuro, Fin del mundo) como estructura narrativa central
- **Life is Strange** — diversidad temporal como vehículo emocional
- **Steins;Gate** — paradojas y líneas temporales bifurcadas
- **Dark Souls** — estética medieval decadente
- **Blade Runner / Cyberpunk 2077** — futurismo distópico

### 4.13 Ciclo Tutorial (Ciclo 1) vs Ciclo Caos (Ciclo 2)

> **Añadida 2026-04-19:** sección dedicada a la estructura de dos ciclos del juego. Es el marco narrativo y estructural fundamental. Leer íntegra antes de diseñar contenido nuevo.

#### 4.13.1 Concepto general

El juego se estructura en **dos ciclos narrativos encadenados**:

- **Ciclo 1 — Tutorial narrativo.** Lineal, fijo, se juega una sola vez. Presenta el mundo, la mecánica, las eras en orden cronológico puro, y termina con el boss-agente-temporal que rompe el tiempo.
- **Ciclo 2 — Caos roguelike.** El formato main del juego a largo plazo. Runs repetibles con eras en orden cronológico pero enemigos desplazados temporalmente y pool del Guerrero unificado.

**Filosofía:** el tutorial no es un overlay sobre el juego — **es parte del juego**, y termina con un giro narrativo que transforma la experiencia. La mecánica de ciclo 2 es justificada diegéticamente por el acto del boss-agente.

#### 4.13.2 Ciclo 1 — detalle

**Contenido:**
- **Todo fijo**: eras, secuencia de encuentros, recompensas básicas del viaje, boss final.
- **3-4 actos** (provisional para testeo — ajustable).
- Orden cronológico estricto: prehistoria → eras intermedias → eras modernas.
- Enemigos **puros de la era del acto** (sin mezclas).
- Cartas de era **de la era correspondiente al acto**.

**Objetivo de experiencia del jugador:**
- Aprender las mecánicas del juego (deckbuilding, combate, invocaciones, paradoja, etc.) de forma progresiva.
- Aprender las keywords de cada era **una por acto**, sin saturación.
- Absorber el argumento narrativo: quién es el Guerrero, qué es la Torre, cuál es la prueba tribal, qué es el alma.
- Llegar al clímax narrativo: el boss-agente-temporal que rompe el tiempo.

**Duración estimada:** 1-2 horas (dependiendo del pacing — a ajustar con playtest).

**Rejugabilidad:** **ninguna**. Una vez completado, no se vuelve a jugar. *"¿Quién en su sano juicio repite un tutorial?"* (Martin).

**Final narrativo:**
- El Guerrero vence (aparentemente) al boss.
- El boss revela su papel verdadero: es el **agente temporal** que ha permitido este viaje lineal. Lo va a romper. Advierte que el caos viene y que el Guerrero no podrá superarlo.
- El Guerrero es enviado de vuelta al inicio de la Torre — pero el tiempo ya no está ordenado.

#### 4.13.3 Ciclo 2 — detalle

**Contenido:**
- **Runs repetibles** — este es el juego roguelike.
- Eras mantienen el orden cronológico del Ciclo 1 (prehistoria → intermedia → moderna).
- **Posible aleatoriedad interna** dentro de cada rango de era (opción B de §4.5) — decisión pendiente.
- Enemigos **mezclados** entre eras con flavour adaptado a la era donde aparecen (ver §4.10.2).
- Cartas de era **siguen ligadas a su era** (no se mezclan — justificación en §4.11.1).
- **Pool del Guerrero unificado**: todas las keywords de las 3 eras disponibles desde el Acto 1 del Ciclo 2 (ver §4.13.5).
- Dificultad escalable mediante sistema de **ascensiones** (a desarrollar, ver §10.7).

**Objetivo de experiencia del jugador:**
- Hacer runs variados reutilizando conocimiento adquirido.
- Descubrir combinaciones de builds y sinergias aprovechando el pool unificado.
- Progresar en ascensiones hasta alcanzar la **victoria final real** (en alguna ascensión específica, a definir).

**Duración estimada por run:** 60-90 minutos (objetivo deckbuilder estándar).

**Rejugabilidad:** alta — es el modo principal del juego.

#### 4.13.4 Transición Ciclo 1 → Ciclo 2

**Mecánicamente:**
- Tras el boss-agente, pantalla de transición + bloqueo del Ciclo 1 para futuras partidas.
- El Ciclo 2 se desbloquea como el modo de juego principal.
- Todas las cartas desbloqueadas meta-progresión pre-Ciclo 2 están disponibles.

**Narrativamente:**
- El Guerrero "despierta" en el Acto 1 del Ciclo 2 con la sensación de haber vivido ya este camino.
- La Torre **se ve igual, pero las cosas están "mal"** — enemigos desplazados, tiempos rotos.
- El pool unificado se justifica: el alma del Guerrero ya **recordó** todas las keywords — en Ciclo 1 las aprendió una a una; en Ciclo 2 todas conviven.

#### 4.13.5 Pool del Guerrero tras la transición

**Pool Ciclo 1:** dividido por acto — en cada acto solo las keywords propias de esa era están activas en las cartas del pool de clase.

**Pool Ciclo 2:** **unificado** — todas las keywords de las 3 eras disponibles desde el Acto 1.

**Implicación de diseño:**
- Las cartas del pool de clase del Guerrero están etiquetadas internamente con su era de origen (subclase temporal — ver §4.9).
- En Ciclo 1 se filtran por acto.
- En Ciclo 2 se muestra todo el pool sin filtrado.

**Por qué es divertido:** el jugador en Ciclo 2 puede encontrarse desde el Acto 1 con una carta que en Ciclo 1 solo vio en Acto 3. Reconoce la keyword, sabe cómo usarla, y ahora puede construir builds que mezclan keywords de eras distintas — **imposibles en Ciclo 1**.

#### 4.13.6 Qué pasa si el jugador muere en Ciclo 1

**Decisión pendiente.** Opciones:

- **(A) Reinicio completo del Ciclo 1.** Purista pero frustrante si la run es larga.
- **(B) Checkpoint por acto.** Al morir, reinicias el acto actual (cartas y HP como al entrar al acto).
- **(C) Inmortalidad narrativa.** El Ciclo 1 es narrativo — si el jugador muere, una escena lo revive con una pérdida narrativa simbólica, pero continúa.
- **(D) Dificultad baja garantizada.** El Ciclo 1 es deliberadamente fácil para que la muerte sea raro (similar a pisos 1-10 tutorial de Ciudad 1 en [[21_Biblia del Mundo]]).

Sugerencia inicial: **combinación C + D** — dificultad baja para que rara vez se muera, y si ocurre, hay mecanismo narrativo de continuidad. Decidir en playtest.

#### 4.13.7 Inspiraciones de la estructura

- **Hades (Supergiant)** — "victoria" inicial que desbloquea el endgame real (ascenso fuera del infierno → re-estructuración de runs).
- **Hollow Knight / Dark Souls** — lineal con giros narrativos que transforman la experiencia.
- **NieR: Automata** — el juego tiene múltiples "ciclos" (rutas A/B/C/D/E) que reinterpretan los eventos.
- **Undertale** — la primera run y las posteriores tienen tono muy distinto; la memoria del juego persiste.
- **Slay the Spire** — post-unlock de Ascension modes como capa de rejugabilidad.
- **Chrono Trigger** — "new game+" como extensión narrativa, no solo dificultad.

---


## 7. Diversidad de eras — decisión pendiente

Martin quiere que la diversidad temporal del mazo **tenga peso mecánico**, no solo estético. Sin embargo, descartamos "Convergencias" (familia de cartas raras que recompensaban diversidad) para no saturar de sistemas.

### 7.1 Opciones en discusión

| Opción | Descripción |
|--------|-------------|
| **A) Reliquias de diversidad temporal** | Reliquias específicas que recompensan eras distintas en el mazo (ej: +1 Anima por cada era en deck). Vive FUERA del mazo pero recompensa composición. |
| **B) Paradojas que escalan con diversidad** | Algunas cartas activas de paradoja tienen efectos que escalan con eras distintas (ej: "paradoja X cartas, donde X = eras distintas en descarte"). Integra con Paradoja. |
| **C) Cartas del pool con escalado sutil** | Algunas cartas normales tienen modificador suave por diversidad (ej: "6 daño. Si hay cartas de 2+ eras en descarte, 8 daño"). ⚠ Conditional risk ya flaggeado. |
| **D) Evolución del stand condicionada por diversidad** | La diversidad de eras en el mazo afecta la evolución del stand (forma especial si mazo es multi-era). Conecta 2 sistemas. |
| **E) Boss reacciona al mazo** | Boss de acto da recompensa extra al vencerlo si el jugador tiene diversidad de eras en el mazo. |

### 7.2 Preferencia inicial

- Mi recomendación (Claude): **A + D** juntos cubren bien sin forzar condicionalidad en cartas tempranas
  - A recompensa externamente vía reliquias
  - D hace que diversidad MOLDEE al stand (mecánica firma — peso narrativo y mecánico)
- Martin: **sin decidir**. Quiere pensarlo. Próxima sesión decidir.

### 7.3 Consideraciones

- Las Convergencias (propuestas en sesión anterior) fueron **descartadas**: añadían una 3ª capa de "cartas raras especiales" sobre Paradoja. Redundantes.
- Cualquier solución elegida debe:
  1. No condicionar decisiones tempranas (no hipotecar acto 1 a lo que pase en acto 2+)
  2. No añadir complejidad mecánica masiva (preferir integrarse con sistemas existentes)
  3. Recompensar sin castigar (el que NO tiene diversidad no debe ser strictly peor)

---


### 2026-04-19 (segunda parte) — Sesión de rediseño: Estructura de dos ciclos y cartas de era

**Contexto:** tras cerrar el rediseño del Sistema Alma, se abrió la discusión de cómo funcionan las **cartas de era** y el **pool general del Guerrero**. Durante la discusión, Martin propuso una idea narrativa grande que reestructura el juego: un Ciclo 1 tutorial fijo + Ciclo 2 caos roguelike, conectados por un boss-agente-temporal. Se cerró como dirección principal del juego.

**Decisiones cerradas — Estructura del pool del Guerrero:**

1. El pool del Guerrero en cualquier acto se compone de tres capas:
   - **Cartas de clase del Guerrero (base)** — siempre disponibles, keywords de las 3 eras.
   - **Cartas neutrales** — compartidas con otras clases (estilo *Colorless* de StS), siempre disponibles.
   - **Cartas de clase del Guerrero de la era actual** — las "cartas de era", disponibles solo en el acto de esa era.
2. **Cartas Alma** (Arma de Alma, Huevo de Alma) son **transversales** al sistema de eras — no cambian por acto. Son subfamilia del pool del Guerrero.
3. **Las cartas de era son específicas de cada clase** — cuando se implemente el Mago, Recolector, Espía, cada uno tendrá sus propias cartas de era con arte e identidad propia. Cada **clase × era** es un set.
4. **NO existen "cartas genéricas de era"** compartidas entre clases. Solo hay cartas neutrales (no-era) compartidas.

**Decisiones cerradas — Naturaleza de las cartas de era:**

5. Las cartas de era son **el culmen mecánico** — más potentes y únicas, con arte propio y flavour diferenciado.
6. **Obtención garantizada:** premio asegurado por vencer **élite** + premio asegurado por vencer **boss de acto**.
7. Dado que son garantizadas, **algunas NO pueden ser tan buenas** (balance: no todas deben ser top-tier).
8. Tienen una **"interacción simple pero efectiva/divertida"** por definir en el futuro (propuestas: keyword única + estado temático / keyword ligera intra-era / trigger contextual / huella temporal). Martin pide que **no sean muy fuertes**.
9. **Justificación diegética clave:** las cartas de era **NO** son técnicas que el Guerrero actual absorbe. Son manifestaciones del protagonista en **líneas temporales previas** — alter egos / antepasados / "otros-yo" que vivieron en esa era. Cuando el Guerrero juega la carta, canaliza el eco de ese otro-él. Conecta con el lore de "el alma rememora vidas pasadas".

**Decisiones cerradas — Estructura de dos ciclos (Estructura 3 confirmada):**

10. **Ciclo 1 — Tutorial narrativo:** run lineal fija, todo determinado (eras, enemigos, recompensas básicas, boss final). Se juega **una sola vez** por jugador. Termina con el boss-agente-temporal. Orden cronológico de eras fijo.
11. **Ciclo 2 — Caos roguelike:** runs repetibles. Eras en mismo orden cronológico que Ciclo 1. Enemigos mezclados entre eras con flavour adaptado. Pool del Guerrero unificado (todas las keywords disponibles desde Acto 1).
12. **Ciclo 1 se juega una sola vez.** No se repite. *"¿Quién en su sano juicio repite un tutorial?"* (Martin). El tutorial no es un overlay separado del juego — es parte narrativa del juego que solo se experimenta una vez.
13. **3-4 actos por ciclo** (provisional para testeo). Ajustable tras playtest.
14. **Victoria final real** del juego se sitúa en alguna **ascensión** del Ciclo 2 (a decidir). Sistema de ascensiones por desarrollar.

**Decisiones cerradas — El boss-agente-temporal:**

15. El boss final del Ciclo 1 es el **agente que rompe el tiempo**. Su papel es **gatillar el paso al Ciclo 2**, no ser derrotado definitivamente.
16. Narrativamente: tras la "victoria aparente" del Guerrero, el boss revela que todo el viaje lineal ha sido tutelado (por él o por el sistema de la Torre). Rompe ese orden, mezcla las eras, y envía al Guerrero de vuelta al inicio — pero con el tiempo ya desordenado.
17. Advertencia narrativa: *"el orden que viste no era real. Lo voy a mezclar. No podrás superarlo."*
18. Punto de no retorno: el Guerrero nunca vuelve al Ciclo 1 tras este evento.
19. Posibles conexiones con la entidad recurrente (§4.6) y el velo negro ([[21_Biblia del Mundo]]) — a definir.

**Decisiones cerradas — Enemigos en Ciclo 2 (Caos):**

20. Los enemigos **se mezclan entre eras**. Un enemigo originalmente de cualquier era puede aparecer en cualquier acto.
21. Al aparecer en un acto, **se adaptan al flavour de la era donde aparecen** — mantienen su patrón mecánico pero cambian aspecto y recursos.
22. Ejemplo canónico dado por Martin: *"un mechahitler hecho de piedra para la edad de piedra, que no tira balas sino rocas"*.
23. Coste de arte asumido: cada enemigo × N eras donde puede aparecer × ~1-2 flavours.
24. **Rejugabilidad sin fórmulas complejas:** el mismo enemigo con distinto flavour crea variedad percibida.

**Decisiones cerradas — Pool del Guerrero en Ciclo 2:**

25. Pool **unificado** desde el Acto 1 del Ciclo 2. Todas las keywords de las 3 eras disponibles.
26. Justificación diegética: el Guerrero ya aprendió todas las keywords en Ciclo 1. En Ciclo 2 su alma las tiene todas despiertas simultáneamente.
27. Las **cartas de era SÍ siguen ligadas a su era** (no se mezclan como los enemigos). Justificación: son alter egos temporales con identidad propia que no se deja desplazar.

**Cabos sueltos / decisiones abiertas tras la sesión:**

- Identidad narrativa del boss-agente-temporal (nombre, aspecto, voz, conexión con velo negro).
- Naturaleza de los alter egos (¿misma alma en distintas vidas? ¿ancestros? ¿ambos?).
- Eras concretas del Ciclo 1 (qué era intermedia, qué era moderna).
- Aleatoriedad de eras en Ciclo 2 (A repetición / B aleatoriedad dentro del rango / C portal).
- Sistema completo de ascensiones.
- Qué pasa si el jugador muere en Ciclo 1 (A/B/C/D opciones planteadas).
- UX de transición Ciclo 1 → Ciclo 2.
- Número exacto de actos (3 vs 3-4 vs más).
- "Interacción simple pero efectiva" de las cartas de era (por decidir, propuestas anotadas).
- Si el boss final real (en ascensión) es la misma entidad que el boss-agente o distinta.

**Descartado explícitamente:**

- "Cartas de la era de la clase del Guerrero" como capa aparte (descartada como redundante con el pool base del Guerrero).
- Cartas de era que se mezclen con enemigos en Ciclo 2 (siguen ligadas a su era de origen).
- Tutorial que se repite (UX: tutoriales no se repiten).

**Principios establecidos/reforzados:**

28. **Ludonarrativa reforzada:** la estructura mecánica ES la narrativa. Ciclo 1 lineal = viaje ordenado; Ciclo 2 caos = tiempo roto por el antagonista. La jugabilidad cuenta la historia.
29. **Flavour adaptativo sin complejidad sistémica:** los enemigos en Ciclo 2 reutilizan patrones con skins distintos. Variedad barata, identidad preservada.
30. **Tutorial como parte del juego**, no como overlay desechable. Cierra con impacto narrativo.

**Filosofía establecida:**

> *"El primer ciclo es todo fijo. Realmente es solo para presentar la historia, es literalmente el tutorial. ¿Quién en su sano juicio repite un tutorial?"* — Martin, 2026-04-19

---


