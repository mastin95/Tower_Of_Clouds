---
type: glossary
status: active
tags: ["producto","vocabulario","decisiones"]
updated: 2026-04-29
---

# Vocabulario y Nomenclatura del Juego

*Documento vivo de nomenclatura, traducciones y registro de decisiones.*
*Ya no es fuente de verdad mecánica. Los sistemas del juego viven en [[12_Mecánicas Centrales]].*

*Created: 2026-04-17*
*Last updated: 2026-04-29*
*Status: Documento vivo — actualizar con cada decisión de nombrado, traducción o registro*

---

## Nota de autoridad

Este archivo gobierna:

- nombres oficiales
- traducciones
- principios de nomenclatura
- tensiones semánticas
- registro de decisiones

Este archivo NO gobierna:

- sistemas mecánicos
- estructura del juego
- canon estructural o metafísico

Las secciones mecánicas que permanezcan aquí deben leerse como **historial de decisiones
de nomenclatura o snapshots de trabajo**, no como fuente de verdad.

Sistemas y marcos descartados que sigan documentados aquí — por ejemplo
`eras`, `cartas de era`, `alter egos temporales` o versiones previas del Sistema
Alma — se conservan solo como **registro del proceso**, no como diseño vigente.

---

## 1. Propósito del documento

Este archivo existe para garantizar **cohesión argumental** entre los nombres del juego,
sus traducciones, y el lore. Responde a preguntas como:

- ¿Cómo se llama esto en nuestro juego?
- ¿Por qué se llama así y no de otra forma?
- ¿Qué alternativas se descartaron y por qué?
- ¿En qué obras nos inspiramos?
- ¿Qué tensiones semánticas quedan abiertas?

### Cuándo consultarlo

- Al proponer una nueva carta, habilidad, enemigo, keyword o concepto
- Al traducir un término al inglés
- Al detectar una posible inconsistencia con algo ya establecido
- Al buscar inspiración que no rompa el registro
- Al revisar nombres, traducciones o framing conceptual de un sistema ya
  documentado en [[12_Mecánicas Centrales]]

### Cuándo actualizarlo

- Cada vez que se cierra una decisión de nombrado
- Cada vez que se encuentra una tensión nueva
- Cada vez que se cataloga una nueva inspiración
- Cada vez que cambia el framing verbal de un sistema, no su autoridad mecánica

### Rol que ejecuta esta función

En la industria esta función se llama **loremaster / lore keeper** (custodia de consistencia), **world builder** (diseño estructural del mundo), o **narrative designer** (puente mecánica-narrativa). En este proyecto, los subagentes `world-builder`, `narrative-director` y `creative-director` cubren esos roles. El concepto académico que engloba esta disciplina es **ludonarrative cohesion** — que los sistemas y la narrativa digan lo mismo sin contradecirse.

---

## 2. Principios de nomenclatura

1. **Cada nombre debe cargar significado mecánico Y lore.** Si un término solo describe qué hace mecánicamente sin conectar con el mundo, está mal elegido.
2. **Preferencia español.** El juego se diseña en español primero. El inglés es traducción consciente, no al revés.
3. **Cohesión de registro.** No mezclar vocabularios sin razón: si el registro es marcial-místico, no meter términos cotidianos o corporativos.
4. **Simple pero evocador.** Martin rechaza lo rebuscado. Nombres cortos, claros, con peso.
5. **Diferenciación del género.** El juego es deckbuilder roguelike — los nombres no pueden sonar igual que Slay the Spire o Monster Train sin razón fuerte. La identidad propia exige vocabulario propio.
6. **El nombre debe sobrevivir la mayúscula.** Si no funciona escrito como *"Play a Gift"* o *"Jugar un Don"*, no es suficientemente específico.

---

## 2bis. Principios transversales de diseño

Principios establecidos a lo largo del proyecto que **aplican a todos los sistemas**, no solo a un sistema específico. Consultarlos antes de proponer mecánicas, para asegurarse de que encajan con la filosofía global.

### 2bis.1 Meta-progresión universal de cartas

**Regla (2026-04-19):** *Todo lo que sea carta tiene meta-progresión.*

Aplicado: las cartas del juego (Armas, Escudos, Dones, Artes, Almas — todos los tipos) tienen un sistema de desbloqueo entre runs. No solo son las cartas Alma. Modelo actual: C — pool base disponible desde el run 1, nuevas cartas desbloqueadas cada X runs completados (victoria o derrota).

**Por qué:** longevidad de contenido, identidad de clase expandible, progresión visible entre runs. No castiga al jugador que no completa hitos específicos (cada X runs basta).

**Implicación:** al diseñar cualquier carta nueva, considerar en qué nivel meta-progresión se desbloquea.

### 2bis.2 Flexibilidad del sistema base

**Regla (2026-04-19):** *El sistema base uniforme debe ser modificable por reliquias, efectos y cartas especiales sin que eso sea complejidad añadida — es el modo de mantener variedad.*

Aplicado: todas las reglas mecánicas (cómo se invoca un huevo, cómo funciona paradoja, cómo se alimentan ofrendas, cuándo evoluciona algo, etc.) son **norma por defecto**. Cada regla debe poder ser overrideable por contenido específico.

**Implicación programática:** las reglas se implementan como **flags/configs por carta/entidad**, no como hardcode. Ejemplos:
- `paradojable: bool` por carta (actualmente `true` para todas menos Alma; preparado para cambiar).
- `timer_initial: int` por huevo (actualmente 3 para el Básico; ajustable per-type).
- `ofrenda_opcional: bool` (actualmente `false` — quemado automático; una reliquia puede ponerlo a `true` para cierta configuración).

**Por qué:** el juego se renueva en runs avanzados y post-launch via reliquias/efectos que rompen reglas base. Si el sistema base es rígido, cada modificación es refactor; si es flexible, son configs.

### 2bis.3 Primero infraestructura, luego tuning

**Regla (2026-04-19):** *No profundizar en detalle fino antes de testear la infraestructura. Primero queremos un setup inicial para crear la infraestructura que lo haga posible y testearlo; pensar en el detalle fino sin datos es completamente ineficiente.*

Aplicado: los números concretos (costes de energía, duraciones, daños, contadores) son **provisionales** en el diseño base. Se ajustan tras playtest.

**Implicación:** al documentar un sistema, reservar un apartado de "decisiones pospuestas a testeo" y no bloquear cierre por detalles que dependen de datos. Cerrar la arquitectura, dejar los números abiertos.

**Por qué:** el tuning sin datos es especular. El playtest revela qué es demasiado fuerte, demasiado débil, qué fricciones hay. Diseñar finamente sin ese input produce trabajo que se desecha.

### 2bis.4 Opt-in sobre mecánicas obligatorias

**Regla (2026-04-19):** *Las mecánicas deckbuilder se ofrecen al jugador como opciones. El power lo tiene el jugador que decide su build.*

Aplicado: el sistema Alma no es una mecánica firma pasiva (como era el stand). Es un tipo de carta opt-in. El jugador puede ignorarlo y ganar el run si lo prefiere.

**Implicación:** al diseñar una nueva mecánica, preferir hacerla accesible vía cartas/reliquias que el jugador puede elegir o ignorar, en vez de imposiciones siempre-activas sobre el personaje.

**Por qué:** refuerza la filosofía deckbuilder (variedad de builds), da poder al jugador, evita que runs se sientan "igual" por mecánicas siempre-impuestas.

### 2bis.5 Diegesis antes que mecánica elegante

**Regla implícita reforzada:** si una mecánica es elegante pero no tiene explicación diegética coherente, buscar alternativa que sí la tenga o reformular.

Aplicado: el rediseño del Sistema Alma se gatilló porque el stand (mecánica elegante) tenía falla diegética (cómo interactúa con el enemigo). Se iteró hasta encontrar una versión (invocación opt-in) que sí cerraba diegéticamente.

**Por qué:** el juego tiene tono narrativo-místico fuerte. Si las mecánicas rompen la diegesis, el tono se diluye. Preservar la cohesión ludonarrativa es principio de proyecto.

---

## 3. Tipos de carta y rasgos visibles

> **Nota de alcance:** esta sección conserva el **naming** y la justificación
> semántica de los tipos de carta. La taxonomía jugable vigente se decide en
> [[12_Mecánicas Centrales]].

> **Actualización 2026-04-29:** la taxonomía vigente de prototipo usa tipos
> funcionales: **Ataque / Defensa / Arte / Don / Alma**.  
> **Arma deja de ser tipo de carta vigente** y pasa a ser un rasgo visible de
> algunos Ataques. La sección antigua de `Arma` como tipo se conserva como
> memoria de proceso, no como autoridad actual.

### 3.0 Taxonomía vigente de prototipo

Tipos funcionales actuales:

- **Ataque**
- **Defensa**
- **Arte**
- **Don**
- **Alma**

Rasgo visible actual:

- **Arma**: símbolo visible en algunos Ataques.

Reglas de nomenclatura:

- **Arma no es un tipo de carta.**
- Un Ataque puede tener Arma o no tenerla.
- Los Ataques básicos no tienen Arma.
- Defensa, Arte, Don y Alma no tienen Arma.
- Arma no tiene efecto inherente: solo importa cuando una carta, trofeo,
  reliquia o regla la referencia.
- Las armas pueden tener tendencias de diseño, pero esas tendencias no son
  reglas automáticas.

Tooltip recomendado:

```text
Arma: símbolo usado por algunos Ataques. Algunas cartas y trofeos reaccionan a Armas concretas o distintas.
```

Valor anómalo:

- **?** es un valor de Arma.
- **?** no es una categoría adicional.
- Todas las cartas con **?** comparten la misma Arma.
- Tooltip recomendado:

```text
Arma anómala: herramienta de origen desconocido.
```

Ejemplo:

```text
Globos de Agua
Tipo: Ataque
Arma: ?
Efecto: daño + Empapado en área
```

### 3.1 Arma (tipo retirado) / Weapon (archivado)

> **Estado 2026-04-29:** retirado como tipo de carta vigente.  
> El contenido de esta subsección se conserva como justificación histórica de
> por qué el término `Arma` tenía peso semántico, pero la lectura actual es:
> **Arma = símbolo/rasgo visible de algunos Ataques**, no tipo funcional.

**Qué representa mecánicamente:** Carta de daño físico directo. Incluye armas físicas (espada, hacha) Y ataques corporales imbuidos con el cuerpo del personaje (puño cargado, patada).

**Qué representa en el lore:** Acción física del campeón. En la filosofía del proyecto, *"las cartas son acciones del personaje — el arte muestra lo que hace"* (world-bible). Un Arma es el personaje atacando con algo tangible: el arma misma o el cuerpo convertido en arma.

**Por qué este nombre:**
- Directo, universal, sin ambigüedad
- Encaja con el Guerrero, que llega con espada y escudo (kit de prueba de su tribu)
- Permite extensión natural a otros campeones: el Mago tendrá "Armas" aunque sean bastones o focos, el Recolector tendrá pico, el Espía tendrá daga

**Alternativas consideradas:**
- *Ataque* — genérico, no diferencia físico/mágico, se solapa con Arte
- *Golpe* — muy específico, excluye armas de proyectil o larga distancia

**Inspiraciones:** Slay the Spire (*Attack* card type como base común). Dark Souls 3 (*Weapon Arts* — técnica ligada al arma; aunque aquí separamos Arma de Arte).

**Riesgos / tensiones:** Ninguna significativa.

---

### 3.2 Escudo (tipo retirado) / Shield (archivado)

> **Estado 2026-04-29:** retirado como tipo de carta vigente.  
> La función defensiva actual se denomina **Defensa**. Escudo puede seguir
> existiendo como objeto, gesto, arte de carta o fuente de bloqueo, pero no como
> tipo funcional principal.

**Qué representa mecánicamente:** Carta de defensa. Bloqueo físico, absorción de daño, reducción.

**Qué representa en el lore:** Acción defensiva física. Escudo literal o cuerpo imbuido para absorber golpe.

**Por qué este nombre:**
- Martin descartó *Defensa* (el nombre original) porque era abstracto. *Escudo* es concreto, evocador, imagen clara.
- Conexión directa con el Guerrero (espada y escudo de su tribu).
- Paralelismo estético con *Arma*: dos términos físicos y concretos, no dos términos mecánicos abstractos.

**Alternativas consideradas:**
- *Defensa* — original, descartado por abstracto
- *Guardia* — demasiado marcial-específico, no incluye bloqueo mágico
- *Muro / Barrera* — arquitectónico, excluye escudo portátil

**Inspiraciones:** Dark Souls (shield como pieza central del combate táctico). Estética de escudo imbuido (anime shōnen: el escudo como extensión del alma).

**Riesgos / tensiones:** Ninguna significativa. Posible tensión si el Mago tiene *escudos mágicos* — ¿son cartas tipo Escudo o tipo Don? Decisión futura.

---

### 3.3 Don (ES) / Gift (EN)

**Qué representa mecánicamente:** Carta que se juega y **queda activa en combate, modificando reglas**. Equivalente a "Poderes" en Slay the Spire. Efecto persistente.

**Qué representa en el lore:** **Un regalo de algo superior.** En el worldview del juego, la Torre le **cede Anima al outsider** — le otorga poder, no se lo cobra. Un Don es la manifestación jugable de esa cesión: el Guerrero activa algo que **la Torre le ha concedido**, y ese don queda con él durante el combate.

**Por qué este nombre:**
- La palabra *don* en español conserva casi exclusivamente el sentido elevado ("tiene un don", "don divino") — no significa "regalo envuelto" en uso común.
- Encaja de forma **muy fuerte** con el estatus de outsider del Guerrero: él recibe dones porque la Torre lo acepta. No los gana, no los aprende — le son concedidos.
- Distingue limpio de *Arte*: un Arte se aprende/practica; un Don se recibe. Dos relaciones distintas con el poder.

**Alternativas consideradas:**
- *Aura* — descartado: místico genérico, muy usado
- *Marca* — descartado: sugiere algo impuesto, ofensivo
- *Sello* — descartado: encierra/bloquea, connotación negativa
- *Ancla* — descartado: físico, no espiritual
- *Pacto* — descartado: implica intercambio/coste, no encaja con la Torre que cede gratis
- *Ley* — tentador (tono Jujutsu Kaisen: "en este combate, X es verdad"), pero demasiado autoritario para un outsider humilde

**Inspiraciones:**
- **Hades** — *Boons* como favores otorgados por dioses. Mismo concepto, otro nombre. La diferencia: los Boons de Hades son transaccionales (los dioses piden algo); los Dones de la Torre no (la Torre simplemente cede).
- **A Song of Ice and Fire** — *"The Gift"* como tierra cedida o don sobrenatural.
- **Tales of Arise** — *Astral Gifts*.
- **Lore propio** — alineación directa con la biblia del mundo: *"La Torre le cede Anima más fácilmente al outsider... no es consciente pero reacciona"*.

**Traducción al inglés — debate:**
- Consideramos *Boon* (muy RPG-coded, Hades), *Blessing* (teísta), *Grace* (cristiano), *Endowment* (corporativo), *Gift*.
- **Elegido: Gift.** Razones:
  - Comparte etimología con *don* (raíz IE *do-* = dar).
  - *Boon* es transaccional, no encaja con una Torre que cede sin pedir.
  - *Blessing / Grace* son teístas — la Torre no es un dios, es algo superior impersonal.
  - *Gift* capitalizado ("play a Gift", "a Gift from the Tower") lee como divino en contexto RPG.

**Riesgos / tensiones:**
- *Gift* en inglés coloquial lee como "regalo envuelto". Mitigación: mayúscula consistente + framing en tutorial ("a Gift from the Tower") + arte que enmarca el concepto (luz descendente, aura).

---

### 3.4 Arte (ES) / Arte (EN, preservando sabor)

**Qué representa mecánicamente:** Carta de utilidad instantánea. Efectos que se aplican al jugar y luego desaparecen: draw, energía, debuff, buff temporal. Equivalente a "Habilidades" en Slay the Spire.

**Qué representa en el lore:** **Una técnica que el Guerrero aprende, afina o
canaliza dentro de la Torre.** Un Arte expresa práctica, oficio y dominio: no
es un don concedido ni una persistencia pasiva, sino una ejecución técnica del
portador en ese momento.

**Por qué este nombre:**
- Martin descartó *Habilidad* porque "suena demasiado efímero" — una habilidad es algo que tienes o no; un Arte es algo que **practicas y dominas**.
- *Arte* carga connotación de **maestría, disciplina, oficio** — el Guerrero está aprendiendo. Encaja con el arco narrativo de superación.
- Tradición sólida en JRPGs (Tales of, Xenoblade, Dark Souls) — legitima el término sin que suene forzado.
- Encaja con la fantasía del Guerrero como alguien que **practica y domina**
  técnicas durante la subida, en vez de limitarse a recibir poderes pasivos.

**Alternativas consideradas:**
- *Habilidad* — descartado: efímero, soso, no aporta identidad
- *Pulso / Chispa / Onda* — descartados: demasiado ambiguos o chocan con la afinidad de fuego del Guerrero (Chispa)
- *Gesto* — bueno pero más limitado que Arte
- *Impulso* — directo pero menos elegante
- *Reflejo* — implica reacción involuntaria, no técnica practicada
- *Aliento* — hermoso (psique = aliento) pero etéreo para cartas de utilidad activa

**Inspiraciones:**
- **Tales of (serie entera)** — *Artes* como nombre del sistema de habilidades activas. Base Artes / Arcane Artes / **Mystic Artes** (ultimates). Paralelismo interesante: el tiering base → mystic podría inspirar la evolución de cartas de Alma del stand.
- **Xenoblade Chronicles (serie entera)** — *Arts* como el sistema de habilidades central. Con cooldown, asignadas a botones, definen el estilo de cada personaje.
- **Dark Souls 3** — *Weapon Arts* (técnica ligada al arma). Aquí separamos *Arma* de *Arte* para mayor limpieza.
- **Artes marciales orientales** (concepto cultural) — "arte" como disciplina practicada, no truco.

**Traducción al inglés — decisión:**
- Consideramos *Art* (limpio), *Arte* (sabor preservado, Tales-coded), *Technique* (largo, genérico), *Form* (marcial estricto), *Way* (filosófico).
- **Elegido: Arte** (preserva sabor español, alineación directa con la serie *Tales of* en inglés). Los jugadores familiarizados con JRPGs ya aceptan el término en inglés.

**Riesgos / tensiones:** Ninguna significativa. Posible confusión con "arte" visual (el arte de la carta) en comunicación interna — mitigable por contexto.

---

### 3.5 Alma (ES) / Alma (EN, preservando sabor)

> **Actualizado 2026-04-19:** el tipo Alma ha sido rediseñado profundamente. Ya no es "carta del stand con energía propia". Es ahora un **tipo de carta invocadora** que el Guerrero juega para canalizar su propia alma. Ver sección 5 completa.

**Qué representa mecánicamente:** Carta **invocadora**. Se juega desde la mano del Guerrero gastando **energía del Guerrero** (no hay energía separada para Alma — ese recurso fue descartado). Al jugarse, invoca una de dos manifestaciones del alma:
- **Arma de Alma** — un buff temporal sobre el Guerrero (próximas N cartas de ataque potenciadas).
- **Huevo de Alma** — una entidad anímica en campo que evoluciona con alimentación.

La carta Alma se exhausta al jugarse (recuperable en el siguiente combate). Tiene rareza estándar (común, rara, épica) y meta-progresión (se desbloquean entre runs). Detalle completo en sección 5.

**Qué representa en el lore:** **El Guerrero canalizando su propia alma.** El Guerrero es outsider tocado por la Torre, que le cede Anima con inusual facilidad y despierta su capacidad de proyectar fragmentos de su esencia como manifestaciones puntuales. Cada carta Alma es un ritual breve: el Guerrero invoca una forma de su alma, la usa, y al terminar el combate la libera. No es una presencia constante — es un acto deliberado.

Dos modos de canalización reflejan dos relaciones distintas del Guerrero con su alma:
- **Sublimación (Arma):** el alma se invierte *sobre* el portador, lo potencia. Íntimo, directo, sin riesgo.
- **Proyección externa (Huevo):** el alma se extiende *fuera* del Guerrero como entidad gestante. Frágil al principio, potente si se alimenta. Riesgo-recompensa.

**Por qué este nombre:**
- Conexión directa con el concepto primigenio: *Alma* es uno de los 5 poderes primigenios del worldview (Alma, Magia, Cielo/Infierno, Arma, Tiempo).
- Refleja que estas cartas son **lo más íntimo del personaje** — son literalmente su alma actuando.
- Visualmente distintas, arte propio, borde diferente — el nombre refuerza esa diferenciación.

**Alternativas consideradas:**
- *Stand* — demasiado meta-referencial (JoJo), rompe la inmersión
- *Eco* — bueno pero colisiona con "Ecos de alma" (concepto lore general)
- *Resonancia* — largo, no se siente especial
- *Vínculo* — técnico, corporativo
- *Invocación* (considerado 2026-04-19) — demasiado genérico, pierde el sabor específico del alma

**Inspiraciones:**
- **Persona (serie)** — invocación del alma como entidad auxiliar, no presencia constante
- **Shin Megami Tensei** — demonios invocados que se alimentan para crecer
- **JoJo's Bizarre Adventure — Echoes de Koichi** — formas evolutivas del stand (preservado como referencia para Forma 1/2/3 del Huevo)
- **Pokémon / Digimon** — huevos que eclosionan y evolucionan
- **Yu-Gi-Oh!** — tributos de cartas como coste de invocación (inspiración para el quemado automático de ofrendas)
- **Hollow Knight** — *Soul* como recurso del alma; canalización deliberada
- **Slay the Spire** — opt-in mechanics vía drafting; la filosofía del jugador que elige su build

**Traducción al inglés — decisión:**
- Consideramos *Soul* (limpio, directo) vs *Alma* (sabor preservado).
- **Elegido: Alma** (preserva sabor español, identidad propia). *Hollow Knight* normalizó *Soul* como término de juego — si usáramos *Soul* nos compararían con él. *Alma* es nuestro.

**Propiedad importante — no paradojables (por ahora):** Las cartas Alma son UNA EXCEPCIÓN en el sistema de Paradoja. No se pueden paradojar. Son únicas e invariables. **La estructura programática deja la puerta abierta** para activar esta propiedad en el futuro si se diseña así (variantes raras, efectos de reliquia, nuevas cartas). Ver secciones 5.12 y 6.3 para detalle.

---

## 4. Sistema de eras — viajes en el tiempo

> **Movido a histórico:** [[12_Histórico de Eras y Cartas de Era]]
>
> Este marco se conserva como registro del proceso y no debe leerse como diseño vigente.
## 5. El Sistema Alma — Invocaciones del Guerrero

> **Nota editorial (2026-04-19):** esta sección reemplaza el diseño anterior del "Stand / digihuevo" (versión del 2026-04-18). El sistema se ha reformulado de fondo para resolver problemas diegéticos y reforzar la filosofía deckbuilder. Los cambios principales están documentados en la sección 5.2. Ver también el registro de decisiones en la sección 14.
>
> **Actualización 2026-04-24:** el marco `Arma de Alma + Huevo de Alma` ha quedado bajo revisión fuerte tras la auditoría post-reorganización. La dirección provisional más reciente entiende `Alma` como la máxima expresión de clase, en una capa más minimalista y de alto potencial. Ver [[15_Sesión 2026-04-24 — Criterios de Mutación y Alma]].

### 5.1 Concepto general y filosofía

El **Sistema Alma** es la familia de cartas y mecánicas que permite al Guerrero canalizar su propia alma durante el combate. Es una mecánica **opt-in** — el jugador decide si su build la incorpora o no.

**Principios rectores:**

1. **El deck es el centro.** El sistema Alma existe para **reforzar** el deckbuilding, no para desplazarlo. Ofrece opciones atractivas sin volverse obligatorio. El power lo tiene el jugador, que decide abrazarlo o ignorarlo.
2. **Opt-in puro.** Si no te interesa, no coges cartas Alma. El Guerrero puede completar un run sin ellas. Son una de varias estrategias posibles.
3. **Dos puertas de entrada.** *Arma de Alma* = rampa baja, efecto directo, curva de aprendizaje sencilla. *Huevo de Alma* = compromiso mayor, recompensa mayor. El jugador elige su nivel de complejidad.
4. **Gestión del mazo empoderada.** Las cartas Alma son decisiones de deck, no un sistema paralelo. Encajan en el ciclo normal de recompensas, con las reglas normales del mazo (rareza, copias, mejoras).
5. **Flexibilidad del sistema base.** Todas las reglas que siguen son **norma por defecto**. Las excepciones (reliquias, efectos, cartas raras) pueden modificar cualquier regla sin que eso sea complejidad añadida — es el modo en que el juego se mantiene fresco.
6. **No profundizar en detalle fino antes de testear.** Los números y los efectos concretos son provisionales. La infraestructura es lo primero; el tuning viene con datos de playtest.

### 5.2 Evolución del diseño — qué cambió y por qué

**Diseño anterior (2026-04-18, ahora descartado):**

El "Stand / digihuevo" era una mecánica firma pasiva del Guerrero — un ser que lo acompañaba siempre en combate, tenía energía propia, HP propia, 3 cartas Alma iniciales fijas en el mazo con subtipos invisibles (Alma-Arma, Alma-Escudo, Alma-Arte), y evolucionaba forzosamente en las transiciones de acto junto con la era.

**Problemas identificados durante la iteración del 2026-04-19:**

- **Problema diegético:** si el stand era un ente aparte del Guerrero, ¿cómo interactuaba físicamente con el enemigo? Soluciones propuestas (asimetría de percepción, enemigos como ecos, stand como canal puro, arma viva, forma/aura...) resolvían uno u otro ángulo pero dejaban cabos sueltos. El jugador iba a preguntar "¿y por qué esto toca al enemigo?" — y ninguna respuesta era totalmente satisfactoria.
- **Duplicación de targets:** si el enemigo podía atacar tanto al Guerrero como al stand, el combate se complicaba sin ganar profundidad real.
- **Stand como amplificador pasivo perdía peso.** Si el stand solo empoderaba al Guerrero sin hacer acciones propias, su figura se diluía.
- **Mecánica firma obligatoria chocaba con filosofía deckbuilder.** Al ser pasiva e imposible de ignorar, el diseño ignoraba el poder del jugador para elegir su estilo.

**Diseño nuevo (2026-04-19):**

El Alma ya no es un ser permanente en campo. Es un **tipo de carta invocadora**. El jugador decide si la incorpora a su deck. Cuando la juega, **canaliza** temporalmente su alma en una de dos formas:

- **Arma de Alma** — un buff directo sobre el Guerrero durante unas jugadas.
- **Huevo de Alma** — una entidad anímica en campo que puede evolucionar con alimentación.

**Qué se conserva del diseño anterior:**
- El concepto del "huevo" como primera forma de una entidad evolutiva.
- Las formas evolutivas (Forma 1 → 2 → 3).
- La idea de "el alma del Guerrero manifestándose" como fantasía central.
- La excepcionalidad del tipo Alma respecto a Paradoja (ahora *por ahora*, no definitiva — ver 5.12).
- El tipo de carta *Alma* como categoría con borde e identidad visual propia.

**Qué se descarta:**
- Stand siempre en campo con HP/energía propias.
- 3 cartas Alma iniciales fijas en el mazo con subtipos invisibles (Alma-Arma/Escudo/Arte).
- Evolución ligada a transiciones de acto.
- Energía del stand como recurso separado (queda hueco programático por si volviera en diseños futuros de otra clase).
- Pool de Alma cerrado y pequeño (ahora las cartas Alma entran en el ciclo normal de drafting y rareza).

### 5.3 Arquitectura del sistema

A nivel programático, el sistema distingue tres categorías de objeto:

**(A) Cartas Alma** (Arma de Alma, Huevo de Alma):
- Son **cartas** en el sentido clásico deckbuilder.
- Siguen el ciclo normal del mazo: mazo ↔ mano ↔ descarte ↔ exhaust.
- Se juegan desde la mano gastando **energía del Guerrero** (no hay energía separada para Alma).
- Al jugarse, se exhaustan (salen del combate). Al terminar el combate, vuelven al mazo normal.
- Son mejorables como cualquier otra carta (upgrade común/raro/épico).
- Tienen rareza estándar (común, rara, épica).
- Tienen meta-progresión: se desbloquean progresivamente entre runs.
- **No son paradojables por ahora.** La estructura programática deja el hook abierto.

**(B) Entidades Alma — Huevos invocados:**
- Son **entidades** en campo, no cartas.
- Se crean al jugar una carta Huevo de Alma.
- Tienen estado propio: forma actual (1/2/3), contador de alimentación, timer restante (si aplica), tipo de ofrenda requerida, pasiva activa.
- **No tienen HP.** Su ciclo de vida se rige por timer y alimentación (excepción: enemigos especiales que pueden devorar — ver 5.11).
- Viven solo el combate. Al terminar el combate, desaparecen. El siguiente combate es un ritual nuevo.
- No son cartas — no van al mazo, al descarte o al exhaust. Son **más parecidas al Guerrero** en rango conceptual (entidades de combate con estado propio), pero sin serlo.

**(C) Arma de Alma — estado sobre el Guerrero:**
- No es entidad ni carta. Es un **estado / contador** aplicado al Guerrero.
- Dura un número de "usos" (jugadas de cartas compatibles), no turnos.
- Al expirar (usos consumidos), el estado desaparece.

**Por qué esta separación importa:**

Las **cartas** son los Armas/Huevos en el mazo; las **entidades** son los Huevos invocados en campo. Una carta Huevo produce una entidad Huevo al jugarse — pero son conceptos distintos con ciclos independientes. La carta se exhausta (exhaust por combate, recuperable); la entidad vive su propio ciclo (hasta morir o hasta fin de combate). Esta distinción es fundamental para que el sistema sea limpio y flexible.

### 5.4 Arma de Alma

**Qué representa diegéticamente:**

El Guerrero canaliza brevemente su alma en su arma mortal o en sus acciones físicas. Durante un número de golpes, el arma está imbuida de Anima propia del Guerrero — corta con una línea de luz, resuena, deja estela. Visualmente se ve al alma "investir" a su portador. Es canalización directa: el alma no se separa del Guerrero, lo potencia.

**Mecánica base:**

- **Coste:** energía del Guerrero (varía por Arma — la básica cuesta 1).
- **Efecto:** aplica un buff/modificador sobre las próximas **N jugadas de cartas de ataque** del Guerrero. N se define por Arma.
- **Consumo por usos, no por turnos:** el jugador controla el ritmo. Puede apurar todos los usos en un turno, o repartirlos entre varios.
- **Carta se exhausta al jugarse**, recuperable al siguiente combate.
- **El efecto es un estado sobre el Guerrero**, no una entidad separada.
- **Visual:** mientras el Arma esté activa, las cartas de ataque en mano muestran un aura u overlay distintivo. Al jugarse cada carta afectada, animación anímica sobre el golpe. Contador visible de usos restantes (tanto en HUD como en las cartas afectadas).

**Variantes temáticas (catálogo inicial a ampliar):**

| Variante | Efecto (base a tunear) | Sabor visual |
|----------|-----------------------|---------------|
| **Arma de Filo** (básica) | +X daño puro en las próximas N cartas de ataque | Filo de luz que prolonga la hoja |
| **Arma de Trueno** | El ataque salpica a un enemigo adicional | Arco eléctrico entre enemigos |
| **Arma de Sombra** | Aplica un estado (veneno, debilidad) al golpear | Estela oscura que contamina |
| **Arma del Tiempo** | El último ataque de la tanda se repite | Eco temporal del golpe |
| **Arma de Luz** | Cura al Guerrero por porcentaje del daño infligido | Energía devuelta al portador |

Las variantes se desbloquean entre runs (meta-progresión — ver 5.7 y sección 14). Cada una tiene sabor visual y narrativo propio.

**Rareza y pool:**

- La Arma de Filo básica es **común**. Forma parte del mazo inicial del Guerrero (1 copia — ver 5.6).
- Otras variantes aparecen como **común** o **rara** según potencia y coste.
- Variantes futuras ultra potentes pueden ser **épicas** (y tener límite de copias por mazo).

### 5.5 Huevo de Alma

**Qué representa diegéticamente:**

El Guerrero invoca una **forma gestante de su propia alma** — un huevo anímico. El huevo es una manifestación frágil que debe ser alimentada con las técnicas del Guerrero para madurar. Al alimentarlo, el Guerrero le "enseña" al alma cuáles son sus técnicas dominantes — y el huevo crece en esa dirección temática.

Es proyección externa (a diferencia del Arma, que es sublimación interna). El alma sale del Guerrero como entidad auxiliar, vive aparte, actúa aparte. Más arriesgado (requiere alimentación, puede morir si se desatiende) pero más potente (su pasiva opera todo el combate y puede evolucionar).

#### 5.5.1 Invocación

- **Coste:** energía del Guerrero (el Huevo Básico cuesta 2; otros huevos pueden variar).
- **Al jugar la carta:**
  - La carta Huevo de Alma se exhausta (recuperable en el siguiente combate).
  - Aparece la **entidad Huevo** en campo, junto al Guerrero.
  - Estado inicial: **Forma 1 (Huevo)**.
  - Timer inicial asignado según el tipo de huevo (el Básico: 3 turnos; otros pueden variar).
  - Pasiva Forma 1 activa desde ese mismo turno.

#### 5.5.2 Pasiva base y ofrendas

- **Pasiva base:** cada huevo tiene una pasiva activa desde Forma 1. Debe ser modesta pero útil — justifica invocar incluso si el jugador no puede alimentarlo.
- **Ofrenda requerida:** cada huevo exige un **tipo específico de carta** como ofrenda. Ejemplos:
  - Huevo Básico → cualquier ataque de 1+ energía.
  - Huevo de Veneno → cartas de veneno.
  - Huevo de Fuego → cartas de fuego.
  - Huevo de Escudo → cartas de bloqueo.
- **Sin HP.** El huevo no puede ser dañado por ataques enemigos normales. Excepción: enemigos que devoran almas (ver 5.11).

#### 5.5.3 Alimentación — reglas

- **Quemado automático y no opcional.** Cuando el Guerrero juega una carta que cumple la ofrenda de un huevo activo, esa carta se **quema** (exhaust para el combate) automáticamente. No hay opción de "no alimentar" — es consecuencia directa de tener el huevo en campo.
  - *Razón de diseño:* simplifica el turno (no requiere pausas para decidir "ofrendar sí/no") y refuerza que **la decisión importante es invocar o no** el huevo, no alimentarlo turno a turno.
- **Una carta alimenta a todos los huevos compatibles a la vez.** Si tienes 2 Huevos de Veneno, jugar 1 carta de veneno alimenta a ambos simultáneamente (1 contador a cada uno). Si tienes 1 Huevo de Veneno + 1 Huevo Básico, una carta de veneno de 1+ energía alimenta a ambos.
- **Cada alimentación:**
  - Resetea o extiende el timer del huevo (por defecto: restaura al máximo; algunos huevos pueden usar +X turnos).
  - Incrementa el contador de evolución en 1.
- **La carta ofrendada** sale del combate vía exhaust normal. Al terminar el combate, vuelve al mazo en el siguiente combate (recuperable).

#### 5.5.4 Evolución — transiciones

**Regla universal:** la evolución ocurre **al inicio del siguiente turno**, nunca instantáneamente al cumplir el contador. Da telegrafía al jugador y evita combos abusivos.

**Forma 1 → Forma 2 (Eclosionado):**
- Disparador: **3 alimentaciones acumuladas** (base, ajustable por huevo específico).
- La transición ocurre al inicio del siguiente turno.
- Al eclosionar:
  - **Efecto inmediato** (un "estallido" alineado con el tema del huevo — ejemplo: el Básico da +1 energía ese turno; el Huevo de Veneno dobla el veneno activo en todos los enemigos).
  - Pasiva Forma 2 más potente, sustituye a la de Forma 1.
  - **Inmune a expiración por timer.** El huevo Forma 2 ya no muere de hambre — ha nacido, es útil, persiste.
- El Huevo Básico topa en Forma 2 (es el tutorial — no tiene Forma 3).

**Forma 2 → Forma 3 (Maduro):**
- Disparador: **5 alimentaciones adicionales** (total 8 desde Forma 1; base ajustable por huevo).
- La transición ocurre al inicio del siguiente turno.
- Forma 3 características:
  - **Pasiva muy potente** alineada con el tema del huevo.
  - **Ultimate activable una vez por combate.** El jugador puede elegir **consumir al huevo** para disparar un efecto masivo alineado con su tema. Si no detona el ultimate, el huevo sigue dando la pasiva hasta fin de combate.
  - Decisión estratégica: ¿explota el huevo ahora para romper el combate, o lo dejo pasivo para el sostenido?

**Al final del combate:**
- **Todos los huevos desaparecen.** El efecto es solo combate.
- En el siguiente combate, si vuelves a jugar la carta Huevo, se invoca desde cero (Forma 1), a menos que una reliquia/efecto especial diga lo contrario.

#### 5.5.5 Muerte por timer

- Si el huevo (Forma 1) no recibe alimentación antes de que su timer llegue a 0, **desaparece sin ceremonia**.
- No hay feedback especial (ni efecto, ni animación dramática).
- La energía invertida al invocarlo se pierde. La carta Huevo quedó exhaustada (recuperable al siguiente combate, pero inútil en este).
- Excepción: reliquias/efectos pueden alterar esta regla (ej: "al morir por timer, aplica 5 daño al enemigo").

#### 5.5.6 Variantes temáticas — ejemplos seed

| Huevo | Coste | Ofrenda | Pasiva F1 | Transición F2 | Forma Madura |
|-------|-------|---------|-----------|---------------|--------------|
| **Básico** | 2 | Ataque 1+ energía | +1 daño en ataques 1+ energía | +1 energía al eclosionar; pasiva sube a +2 daño ataques y +1 bloqueo defensas | — (sin F3) |
| **Veneno** | 2 | Cartas de veneno | Aplica 1 veneno/turno al enemigo principal | Estallido: dobla veneno activo; pasiva sube a 2 veneno/turno en área | Pasiva: 3 veneno/turno en área. Ultimate: enemigos con 10+ veneno reciben daño letal |
| **Fuego** | 2-3 | Cartas de fuego | +1 daño a enemigos ardiendo | Por definir | Por definir |
| **Escudo** | 2-3 | Cartas de bloqueo | +1 bloqueo al jugar un Escudo | Por definir | Por definir |

Los números concretos son provisionales y se tunean con playtest. El diseño de catálogo completo de huevos queda pospuesto al testeo.

### 5.6 Mazo inicial — las cartas Alma básicas

El Guerrero arranca cada run con **1 copia de Arma de Alma Básica + 1 copia de Huevo de Alma Básico** en su mazo.

**Rareza: común** — pueden aparecer también en el pool normal post-combate como recompensa (no son "inicial exclusiva"). El jugador puede duplicarlas si quiere invocarlas con más frecuencia.

**Filosofía tutorial:** enseñar rápido al jugador. Desde el run 1 ya tiene ambas cartas y puede experimentar el sistema sin depender de la suerte del drafting.

**Arma de Alma Básica (Arma de Filo Básica):**
- Coste: **1 energía**
- Efecto: las próximas **3 cartas de ataque** ganan **+2 daño**
- Rareza: **común**
- Visual: aura simple sobre las cartas de ataque en mano mientras está activa
- Modo tutorial: rampa baja, efecto legible, sin mecánicas exóticas

**Huevo de Alma Básico:**
- Coste: **2 energía**
- Tipo de ofrenda: **ataques de 1+ energía** (excluye bloqueos, utilidades y ataques de 0 coste)
- Timer inicial (Forma 1): **3 turnos**
- Pasiva Forma 1: al jugar un ataque de 1+ energía, **+1 daño adicional**
- Alimentación: cada ataque de 1+ energía jugado se quema automáticamente como ofrenda y suma 1 al contador
- Eclosión (3 alimentaciones) → Forma 2 al inicio del siguiente turno:
  - Efecto inmediato: **+1 energía ese turno**
  - Pasiva Forma 2: ataques de 1+ energía → **+2 daño**; bloqueos → **+1 bloqueo**
  - Inmune a expiración por timer
- **Sin Forma 3.** El Huevo Básico es tutorial. Topa en Forma 2. Los huevos temáticos sí tienen las 3 formas completas.

**Razonamiento diegético del básico universal:**
El Huevo Básico representa el alma del Guerrero **en su forma menos especializada** — aún no ha elegido una faceta dominante. Cualquier técnica marcial del Guerrero que implique esfuerzo combativo (ataque con coste real ≥ 1 energía) alimenta al alma. No alimenta con bloqueos/utilidades porque el Huevo Básico "crece con intención combativa" — es un huevo marcial puro. Los huevos temáticos (veneno, fuego, escudo...) se especializan en facetas distintas del alma que el Guerrero despierta al elegirlos.

### 5.7 Obtención de cartas Alma durante el run

El sistema de obtención sigue la lógica diegética del origen de cada subfamilia:

**Armas de Alma — pool normal post-combate:**
- Aparecen como recompensa post-combate con las otras cartas, según su rareza (común/rara/épica).
- Rationale diegético: una Arma de Alma representa una técnica de canalización que el Guerrero aprende durante su viaje — encaja con el loot corriente (cartas absorbidas de la Torre).

**Huevos de Alma — eventos especiales:**
- **NO aparecen** en el pool normal post-combate.
- Aparecen en: **eventos narrativos especiales**, **altares dedicados**, **recompensas de boss**, posiblemente **tiendas con stock rotativo**.
- Rationale diegético: un Huevo es la gestación de un aspecto anímico — un momento ceremonial, no un loot casual. Aparece en lugares cargados de significado (altar, jefe, evento). Controla además cuántos huevos puede acumular el jugador (el sistema soporta múltiples, pero la escasez natural los hace valiosos).

**Copias múltiples:**
- **Sin límite de copias por carta** para comunes y raras. El jugador puede acumular 3, 4, 5 Huevos Básicos si lo quiere y rompe el combate al invocarlos (ver 5.8).
- Épicas únicas pueden tener límite de 1 copia (decisión caso por caso).

**Meta-progresión (modelo C):**
- **Pool base**: 3-4 Armas + el Huevo Básico disponibles desde el run 1.
- **Cada X runs completados** (victoria o derrota) se desbloquea una nueva carta Alma para el pool. Aplica a Armas y a Huevos por igual.
- **Regla transversal:** *todo lo que sea carta tiene meta-progresión*. No solo Alma — se aplica al resto del contenido también.

### 5.8 Coexistencia y múltiples invocaciones

**Arma + Huevo coexisten:** puedes tener un Arma de Alma activa mientras hay Huevos en campo. No se excluyen. El Arma afecta al Guerrero; el Huevo vive aparte.

**Múltiples huevos simultáneos:** **sin límite duro**. El límite natural es tu energía + tu mazo:
- Tener 3 huevos activos al mismo tiempo es caro (energía de invocación) y exige un deck muy enfocado (cada uno pide su ofrenda).
- Romper el juego en fases avanzadas es **feature**, no bug. Con mucha suerte y build optimizado, el jugador puede tener configuraciones abusivas — es parte del *fantasy deckbuilder* (subida de adrenalina en runs tardíos).

**Cartas raras que invocan 2 huevos de golpe:** existen. Son **ultra raras** (épicas). No son la norma, pero el sistema las soporta.

### 5.9 Reglas universales del sistema

Aplicables a todos los huevos y todas las transiciones salvo excepción explícita (reliquia, efecto, carta especial):

1. **Evolución al inicio del siguiente turno.** Nunca instantánea. Da telegrafía al jugador y evita combos abusivos de invocar-eclosionar-ultimate en el mismo turno.
2. **Arranque siempre en Forma 1.** Cada combate es un ritual nuevo. Excepciones posibles vía reliquias.
3. **Quemado automático de ofrendas.** Si juegas una carta compatible con un huevo activo, se quema sin elección. Fomenta que el jugador **piense antes de invocar**, no durante cada turno.
4. **Una carta alimenta a todos los huevos compatibles a la vez.** Eficiente cuando hay varios del mismo tipo; no hay que repartir.
5. **Sin límite de huevos simultáneos.** Solo límites naturales (energía, mazo).
6. **Sin límite de copias de cartas Alma** para rarezas común/rara. Épicas únicas pueden tener límite de 1 por mazo.
7. **Carta Alma exhaust al jugarse**, recuperable en el siguiente combate.
8. **El Huevo-entidad vive solo el combate.** Desaparece al terminar.
9. **No paradojable por ahora.** Estructura programática preparada para activarlo si se diseña así en el futuro.

### 5.10 Interacciones entre huevos — semillas de diseño

Pendiente de desarrollo específico. Semillas iniciales a explorar cuando se diseñen variantes concretas:

- **Veneno + Fuego:** enemigos envenenados también arden (sinergia daño sostenido).
- **Básico + cualquier otro huevo:** el Básico actúa como comodín — copia parcialmente la pasiva del otro huevo activo.
- **Sombra + Luz:** efectos duales (uno debilita, otro cura simultáneamente).
- **Dos huevos del mismo tipo:** pasiva se acumula (×2) + una sola ofrenda alimenta a ambos (riesgo de vaciar mazo rápido).

Ninguna de estas interacciones es compromiso firme — son seeds que el diseño validará cuando se concreten huevos específicos. **El sistema soporta interacciones arbitrarias entre huevos**; los diseñadores deciden cuáles se implementan.

### 5.11 Enemigos que comen huevos

**Regla especial:** ciertos enemigos pueden tener la acción de **devorar un huevo** del campo como parte de su set de habilidades. Al hacerlo, el huevo desaparece y el enemigo suele ganar un buff (cura, daño, stat).

**Por qué existen:**
- Aportan tensión en combates donde el jugador se apoya mucho en huevos.
- Crean encuentros de **contrarresto** al sistema Alma sin invalidarlo por completo.
- Encaja diegéticamente: ciertos seres de la Torre son **comedores de almas** — entidades que se alimentan de Anima anímica expuesta (ver 5.14).

**Frecuencia:** debe ser baja y reservada para enemigos especiales (boss minor, enemigo raro de cierta era, boss final). No debe ser norma — si cada combate tuviera un comedor, el sistema Alma sería frustrante.

**Mecánica exacta:** pendiente de diseño específico con enemigos concretos. Lo que queda fijado en esta sección es el **hook sistémico** — el sistema Alma contempla esta interacción desde la arquitectura.

### 5.12 Relación con Paradoja

- **Cartas Alma (Arma y Huevo) no son paradojables por ahora.**
- **Razón diegética:** el alma es la forma pura, la esencia misma del Guerrero. La Paradoja opera sobre **técnicas** (acciones con forma opuesta concebible). El alma no es una técnica — es quién eres. No tiene forma-sombra.
- **Razón estructural programática:** a nivel de sistema, la propiedad "paradojable" está implementada como **flag por carta**. Las cartas Alma tienen el flag en `false`. Cambiarlo a `true` en el futuro (para variantes raras, para un nuevo tipo de carta Alma paradojable, o como efecto de una reliquia) **no requiere refactor** del sistema.
- **Reliquias y efectos pueden sobrescribir la regla.** Por ejemplo, una reliquia puede permitir paradojar cartas Alma específicas o temporalmente — el sistema base es flexible.

### 5.13 Identidad visual

**Cartas Alma (tanto Arma como Huevo):**
- **Borde distintivo** respecto a las cartas normales del mazo.
- **Aura especial** en la ilustración (luminosidad, estela anímica, glow).
- **Arte propio por carta** — el Guerrero puede aparecer (invocando) o no (el foco está en lo invocado, especialmente en las cartas Huevo).

**Arma de Alma activa:**
- Todas las cartas de ataque en mano muestran un aura/overlay mientras el Arma está activa.
- El aura se "consume" visualmente al jugar cada carta de ataque afectada.
- Contador de usos visible (ej: "3/3" → "2/3" tras jugar la primera carta afectada).

**Huevo invocado:**
- **Presencia visible a un lado del Guerrero.** Arte estético propio por tipo de huevo.
- **Timer visible** (cuenta regresiva de turnos si está en Forma 1).
- **Contador de alimentación visible** (ej: "1/3" para la primera eclosión; "4/8" para la transición a Forma 3).
- **Animación de transición** cuando evoluciona (Forma 1 → 2 → 3). Debe sentirse significativa.
- **Animación de muerte** si expira por timer (sencilla, sin drama — coherente con "desaparece sin ceremonia").

**Principio general:** las cartas Alma y sus invocaciones deben sentirse **inmediatamente distintas** del resto del juego. Son la firma visual del Guerrero.

### 5.14 Lore diegético — el porqué narrativo del sistema

Esta sección consolida la lógica narrativa que fundamenta cada decisión mecánica del sistema.

**Qué es un alma en este mundo:**
El alma es uno de los 5 poderes primigenios (ver [[23_Sistema de Poder]]). Los humanos son mezclas de conceptos primigenios dentro de un cascarón físico. El alma es el núcleo esencial del ser — lo que el sujeto **es**, no lo que **hace**.

**Por qué el Guerrero puede canalizar su propia alma:**
El Guerrero es **outsider** — su tribu está fuera del sistema político de la Torre. La Torre, al detectarlo, le **cede Anima con inusual facilidad** (ver [[21_Biblia del Mundo]]). Esta cesión no es solo un flujo de energía exterior: despierta en el Guerrero la capacidad latente de **canalizar su propia alma**. El Guerrero aprende, dentro de la Torre, a proyectar fragmentos de su esencia como manifestaciones puntuales.

**Por qué es un ritual puntual, no una presencia constante:**
Canalizar el alma requiere energía y voluntad. No es algo que el Guerrero mantenga permanentemente — lo hace cuando lo necesita, durante el combate. Cada carta Alma es un **ritual breve**: el Guerrero invoca una forma de su alma, la manifiesta, la usa, y al terminar el combate la libera. El alma vuelve a su estado normal (unificada dentro del Guerrero).

**Por qué hay dos tipos de invocación (Arma y Huevo):**
El alma se puede manifestar de dos formas según la intención del portador:
- **Como sublimación del Guerrero (Arma de Alma):** el alma se invierte **sobre** el arma mortal o el cuerpo del Guerrero. No se separa del portador — lo potencia. Es la canalización directa, íntima. Visualmente se ve al Guerrero ardiendo con luz anímica durante sus próximos golpes.
- **Como proyección externa (Huevo de Alma):** el alma se extiende **fuera** del cuerpo del Guerrero como una entidad gestante externa. Es más arriesgado (requiere alimentación, puede morir si se desatiende) pero más potente (vive aparte, actúa aparte, puede evolucionar).

**Por qué el Huevo empieza como huevo:**
El alma proyectada hacia afuera del cuerpo está **fuera de su continente natural** y recobra una forma primigenia: un huevo, símbolo de lo aún-no-formado. Para madurar, el alma necesita **memoria** — técnicas del Guerrero que pueda absorber como identidad temporal. De ahí la mecánica de alimentación.

**Por qué la alimentación es con cartas del Guerrero (ofrendas que se queman):**
Las cartas son técnicas / recuerdos / acciones del Guerrero. Alimentar al huevo es literalmente **darle al alma una técnica como molde**. El Guerrero le dice al huevo "así soy yo, aprende esto". La técnica se consume **durante este combate** — el Guerrero la cede al huevo para que crezca. Al terminar el combate, el huevo desaparece, y la técnica vuelve al mazo en el siguiente combate: el Guerrero recupera lo que prestó.

**Por qué el huevo temático crece en esa dirección:**
Un Huevo de Veneno solo aprende de técnicas de veneno — porque ese aspecto del alma del Guerrero tiene afinidad con la toxicidad. El Guerrero "despierta" la faceta venenosa de su alma y la hace crecer. Un Huevo de Fuego despierta la faceta flamígera, etc. El Huevo Básico (acepta cualquier ataque marcial) representa el alma **aún no especializada** — puro ímpetu guerrero, antes de que un aspecto dominante emerja.

**Por qué el enemigo no ataca al huevo (ni al Arma):**
Los seres físicos de la Torre (enemigos comunes) no pueden percibir ni interactuar con lo anímico expuesto. El Arma de Alma es un estado interno del Guerrero — no existe como objetivo externo. El Huevo invocado es anímico puro — los sentidos físicos del enemigo no lo captan. El Guerrero sí puede interactuar con ambos (porque la Torre le cedió Anima y lo convirtió en sensible a lo anímico-físico).

**Excepción — enemigos que devoran almas:**
Ciertos seres de la Torre han desarrollado el hambre de Anima expuesta. Son criaturas raras, antiguas o maldecidas, capaces de **percibir y consumir** huevos anímicos. Cuando uno aparece en el campo, el jugador debe proteger sus huevos o priorizar la eliminación del devorador. Este hook sistémico encaja con los comedores de almas del lore de la Torre (ver [[23_Sistema de Poder]] y [[21_Biblia del Mundo]] para desarrollo específico).

**Por qué Forma Madura tiene un ultimate que consume al huevo:**
Cuando el huevo alcanza su forma adulta, el alma del Guerrero ha cristalizado temporalmente. El jugador puede elegir **liberar esa cristalización** de golpe — el alma regresa al Guerrero a través de un estallido que aniquila al enemigo. Es la culminación del ritual. O puede elegir mantener el huevo activo como pasiva sostenida. Doble decisión estratégica, coherente con la lógica del Guerrero que gestiona su alma consciente.

**Por qué Alma no se paradoja:**
La Paradoja es la inversión narrativa de una técnica — el camino opuesto, la forma-sombra. El alma no es una técnica, es **quien eres**. No tiene camino opuesto sin cambiar la ontología del personaje. Si en el futuro se diseñara una "paradoja del alma", sería un evento narrativo de peso (no una mecánica casual) — por eso el flag está dejado abierto a nivel programático pero apagado por defecto.

**Por qué cada combate arranca con huevos en Forma 1 (el alma "olvida"):**
Cada combate es un ritual nuevo. El huevo que el Guerrero invocó en el combate anterior ha sido liberado al terminar — el alma volvió al Guerrero. Cuando en el siguiente combate vuelve a invocar, el ritual empieza de cero. El alma no "recuerda" la forma previa: lo que recuerda el Guerrero es la *técnica de invocar*, no la forma resultante. Esto justifica diegéticamente que cada combate sea un reinicio limpio, y deja espacio para reliquias que **rompan** esta regla (ej: "tu alma recuerda — arranca en Forma 2").

### 5.15 Principios de flexibilidad del sistema

El sistema base recogido en esta sección es **el modo por defecto**. Todas las reglas son **modificables por reliquias, efectos especiales o cartas raras**. Esta flexibilidad no es complejidad añadida — es el modo en que el juego se renueva en runs avanzados y post-launch.

**Ejemplos de modificaciones posibles** (no todas diseñadas, son seeds):
- Reliquia que permite arrancar un huevo en Forma 2.
- Efecto que mantiene un huevo vivo entre combates.
- Carta rara que permite paradojar una carta Alma específica.
- Reliquia que hace que un huevo al morir por timer libere un efecto.
- Efecto que permite al Arma de Alma durar turnos en vez de usos.
- Carta épica que invoca 2 huevos de golpe con una sola carta.
- Huevo que acepta múltiples tipos de ofrenda.
- Huevo cuya ofrenda NO es automática (el jugador elige cada vez).
- Reliquia que evita el quemado de ofrendas (la carta se alimenta pero NO se quema).

**Principio programático transversal:** el sistema se diseña con **hooks claros** para que cada regla sea *overridable*. Esto requiere disciplina (cada regla debe ser un flag/config, no hardcode) pero paga dividendos en diseño de contenido.

### 5.16 Decisiones pospuestas a testeo

El equipo ha acordado (principio transversal) **no profundizar en detalle fino antes de testear la infraestructura**. Las siguientes decisiones quedan pendientes de validación por prototipo:

1. **Forma Madura (Forma 3) — detalles concretos por huevo:** números, pasivas, ultimates específicos. Marco aprobado: *ultimate activable que consume al huevo* + *pasiva potente alineada con tema*. Los detalles se cierran con ejemplos reales tras testeo.
2. **Interacciones específicas entre huevos:** cuáles se implementan, cuántas, con qué sinergias. Semillas anotadas en 5.10.
3. **Mecánica exacta de "enemigos que comen huevos":** qué enemigos, qué condiciones, qué animación, qué buff ganan. Anotado como hook sistémico en 5.11.
4. **Nombre definitivo del concepto de Huevo:** "digihuevo" sigue siendo provisional. Ver tensión 10.3.
5. **Catálogo completo de Armas y Huevos desbloqueables:** cuántas hay en total, orden de desbloqueo meta, qué hitos se usan. Anotado como decisión de producción.
6. **Balance numérico:** todos los números (coste de energía, duraciones, pasivas) son provisionales. Ajustables con playtest.

### 5.17 Inspiraciones del sistema Alma (actualizadas)

- **Persona (serie)** — invocación del alma como entidad auxiliar. El Persona no acompaña siempre al personaje: aparece para ejecutar su efecto y se retira. Mismo principio en Alma.
- **Shin Megami Tensei** — demonios que se invocan, se alimentan/entrenan, y tienen lealtad condicionada. Inspira la mecánica de alimentación.
- **Pokémon / Digimon** — huevos que eclosionan y evolucionan en formas. Inspiración estructural del huevo y sus etapas evolutivas.
- **Yu-Gi-Oh! (tributos para invocación)** — sacrificar cartas como coste de invocación. La mecánica de quemado automático es prima directa de esta idea — aunque aquí el tributo es "post-invocación" (alimentar) en vez de pre-invocación.
- **Slay the Spire** — mecánicas opt-in vía drafting. El jugador decide si su build abraza Alma o la ignora. La filosofía del "pool limpio de contenido relevante por run" se aplica.
- **JoJo's Bizarre Adventure — Echoes de Koichi** — evolución del stand en ACT 1/2/3. Se mantiene como inspiración para las formas evolutivas (aunque el stand como tal ya no existe — queda el ecosistema de formas).
- **Hollow Knight** — Soul como recurso central del alma. La canalización del alma como acción deliberada del protagonista.

---

## 6. Paradoja — mecánica de inversión temporal

### 6.1 Qué es

**Paradoja es un ESTADO permanente que puede aplicarse a cartas del mazo del jugador.** Cuando una carta queda paradojada, su efecto se reemplaza por una **forma paradoja pre-diseñada** — la inversión narrativa de su efecto original, escrita a mano por el diseñador.

**Qué NO es:**
- NO son cartas "ya paradojadas" que aparecen en el pool normal (eso diluiría la pool)
- NO es una modificación temporal por combate (las paradojas de eventos son permanentes)
- NO es inversión algorítmica (cada paradoja es diseño per-card)
- NO es dependiente de eras
- NO siempre es una acción activa del jugador (los eventos pasivos aplican sin requerir acción activa)

### 6.2 La forma paradoja — inversión narrativa

Cada carta paradojable tiene una **forma paradoja pre-diseñada** por el diseñador. La inversión es **narrativa**, no matemática — el diseñador decide qué es "lo contrario" de esa carta específica para mantener coherencia.

**Ejemplos:**

| Carta base | Forma paradoja |
|------------|----------------|
| **Colmillo Venenoso** — 3 daño + 2 veneno al enemigo | Curas 3 HP + 2 regeneración a ti |
| **Golpe Honorable** — 8 daño | Ganas 8 bloqueo |
| **Escudo Real** — +5 bloqueo | 5 daño a todos los enemigos |
| **Bendición Ancestral** — curas 6 HP | Todos los enemigos pierden 6 HP |
| **Ritual Prohibido** — pierdes 4 HP, +2 Anima este turno | Ganas 4 HP, enemigos pierden 2 Anima si tienen |

### 6.3 Alcance — qué cartas son paradojables

**Paradojables (por defecto):**
- Todas las cartas del pool normal paradojable: **Ataque, Defensa, Don, Arte**
- Cada una de estas tiene su forma paradoja diseñada a mano

**NO paradojables por ahora (excepciones):**
- **Cartas Alma** (Arma de Alma y Huevo de Alma) — son únicas, especiales, invariables. No tienen forma paradoja en el diseño base.
- **Estructura programática preparada** para activarlo en el futuro: el flag "paradojable" existe por carta en el sistema. Cambiarlo a `true` para variantes específicas (ej: una carta Alma rara con propiedad única, un efecto de reliquia que habilite paradoja de Alma temporalmente) **no requiere refactor**. El diseño actual simplemente tiene todas las cartas Alma con el flag en `false`.
- Razón diegética: el alma es la forma pura, no una técnica con camino opuesto (ver 5.12 y 5.14).

**Implicación de diseño:**
- Con ~100-120 cartas base paradojables × 2 efectos cada una (normal + paradoja) = **200-240 efectos totales a diseñar**
- **Coste de diseño ASUMIDO** por Martin como inversión necesaria del proyecto
- Si en el futuro se abre paradoja de Alma, sumaría efectos proporcionales al subset habilitado

### 6.4 Cómo se adquiere — dos canales

**CANAL 1 — Eventos pasivos (frecuencia: COMÚN)**

- Aparecen regularmente en el mapa del juego
- El evento presenta al jugador **3 cartas aleatorias de su mazo** (idealmente una de cada rareza — común, poco común, rara)
- El jugador **elige 1 de las 3** para paradojar
- La carta elegida queda **paradojada PERMANENTEMENTE para el resto del run**
- La transformación no se revierte salvo que el run termine

**Ejemplo de evento:**
> *"El Espejo del Tiempo"* — Te miras en un espejo y ves tu reflejo invertido. Elige 1 de estas 3 cartas aleatorias de tu mazo para paradojar permanentemente: [común] [poco común] [rara]

---

**CANAL 2 — Eventos raros con cartas activas (frecuencia: RARO — pocas veces por run)**

- Aparecen pocas veces por run (eventos raros del mapa)
- El jugador puede elegir **1 de 3 cartas** que **USAN la mecánica de Paradoja activamente**
- Estas cartas se añaden al mazo y llevan el mecanismo de Paradoja dentro de su efecto

**Dos familias de cartas activas de Paradoja:**

**Familia APLICADORAS — paradojan en tiempo real durante combate:**

> Ejemplo: **Visión Recurrente** (Don raro) — *Al robar mano cada turno, paradoja 1 carta aleatoria de la mano hasta el final del turno.*

**IMPORTANTE:** las paradojas aplicadas por cartas activas (poderes en combate) son **TEMPORALES — solo duran el combate**. Se resetean al terminar la pelea.

**Familia AMPLIFICADORAS — interactúan con cartas ya paradojadas:**

> Ejemplo: **Convergencia Momentánea** (Don raro) — *1 vez por turno, la primera carta paradojada que juegues aplica AMBOS efectos — normal Y paradoja.*

---

### 6.5 Permanencia — resumen crítico

| Tipo de paradoja | Duración |
|------------------|----------|
| **Eventos pasivos** (aplicar a cartas del deck) | **PERMANENTE** (todo el run) |
| **Cartas activas poderes/Aplicadoras** | **TEMPORAL** (solo el combate) |

Esta distinción es importante para balance:
- Eventos = peso narrativo, decisión con consecuencia de run
- Cartas activas = herramienta táctica, se resetea cada combate para evitar snowball

### 6.6 Visual — cómo reconocer cartas paradojadas

Las cartas paradojadas deben llevar un **marcador claro e inmediato**:

- **Borde especial** (diseño pendiente — propuesta: efecto "espejo", colores invertidos, shimmer temporal)
- **Icono de Paradoja** en la esquina (propuesta: símbolo ∞ roto, espiral invertida, reloj inverso)
- **Texto directo** — la carta muestra la forma paradoja como efecto (no el original tachado)
- Cuando el jugador ve la carta en mano, **no hay ambigüedad** sobre qué efecto va a ejecutar al jugarla

### 6.7 Lore

El alma del Guerrero, al rememorar vidas pasadas, descubre que cada técnica tiene una **forma en sombra** — su opuesto causal. Cuando una carta queda paradojada, es esa forma en sombra la que se manifiesta ahora en vez de la original. No es una inversión matemática — es el Guerrero accediendo a una **vida alternativa** donde esa técnica tomó su forma opuesta.

Cada paradoja aplicada es un momento donde **el alma ha decidido mostrarse como lo que NO fue** — el camino no tomado, la decisión opuesta, el yo alternativo.

### 6.8 Riesgos y consideraciones de diseño

- **Doble coste de diseño por carta.** Mitigación: asumido.
- **Carga visual.** Las cartas paradojadas tienen que distinguirse SIN saturar la UI. La iconografía debe ser sencilla.
- **Balance por pares.** Si la paradoja es mucho más fuerte que la original, todo el mundo paradoja; si es mucho más débil, nadie. Cada par debe ser una elección interesante, no obvia.
- **Frecuencia de eventos pasivos.** Si aparecen demasiado, el mazo se vuelve 50% paradoja — pierde gracia. Si aparecen muy poco, el sistema no impacta. Calibrar con playtesting.
- **Interacción con cartas Alma.** Las cartas Alma NO son paradojables. Si una carta activa (Canal 2) dice "paradoja 1 carta aleatoria", las cartas Alma se excluyen del pool de candidatas.

---

## 7. Diversidad de eras — decisión pendiente

> **Movido a histórico:** [[12_Histórico de Eras y Cartas de Era]]
>
> Esta decisión dependía del marco de eras/cartas de era ya archivado.
## 8. Trofeos y reliquias

### 8.1 Decisión — separación limpia

Las **cartas no son trofeos** narrativamente (eran forzadas; "One Piece son los amigos que hicimos" effect). Las cartas son habilidades/técnicas absorbidas. Para el tema "trofeo" que la tribu del Guerrero pide:

- **Trofeos = reliquias específicas** (objetos físicos que caen de bosses o eventos especiales)
- Sistema de reliquias estilo Slay the Spire: objetos coleccionables con efectos pasivos
- El Guerrero vuelve a la tribu con **un trofeo físico** (reliquia final o específica) que satisface la prueba tribal

### 8.2 Estado

- Decisión provisional confirmada por Martin ("por ahora"). Revisable si surge mejor framing narrativo
- No bloqueante para el diseño de otros sistemas

---

## 9. Conceptos transversales del lore

### 9.1 Anima

**Qué es:** Energía de alma ambiental que satura la Torre. Recurso de combate (3 base para el Guerrero). Definido en [[23_Sistema de Poder]] y [[21_Biblia del Mundo]].

**Cómo se usa en gameplay:** Coste de jugar cartas. El Guerrero canaliza Anima de la Torre a través de sus cartas.

**Nombre en inglés:** **Anima** (preservado — término latino/místico universal).

### 9.2 Alma (concepto primigenio)

**Qué es:** Uno de los 5 poderes primigenios del worldview. En la cosmología del juego, *"los humanos son mezclas de conceptos primigenios dentro de un cascarón (cuerpo)"*. Alma es el concepto central.

**Relación con el tipo de carta *Alma*:** Las cartas del stand se llaman *Alma* porque son la manifestación del alma del personaje. Pero *alma* como concepto primigenio es más amplio.

### 9.3 Eco

**Qué es:** concepto narrativo que describe **qué es una carta en el juego**.

Definición vigente:

> Un Eco es una memoria de alma conservada en el Anima.

Uso:

- **Eco** es el término común y visible.
- **Eco de alma** puede usarse cuando haga falta enfatizar emoción, memoria o
  legado.
- **Eco conservado en el Anima** es la formulación técnica más precisa.
- Evitar que `Eco` compita con el tipo de carta **Alma**: una carta Alma también
  puede representarse como carta, pero su origen es la propia alma del personaje,
  no un Eco externo corriente.

Frase rectora:

> Una carta no es un objeto. Es la forma jugable de un Eco: una memoria de alma que el personaje aprende a interpretar.

### 9.4 Gramática de resonancia

Esta gramática explica cómo una memoria de alma se convierte en una carta de
deckbuilder sin sentirse como loot físico.

| Término | Definición | Lectura jugable |
|---------|------------|-----------------|
| **Resonancia** | Momento en que el alma detecta un Eco compatible | Aparición de opciones de recompensa |
| **Inscripción** | Fijación temporal de un Eco al alma activa durante la run | Añadir una carta al mazo de la run |
| **Canalización** | Uso de un Eco inscrito durante el combate | Jugar una carta |
| **Impronta** | Huella persistente que queda al descubrir/despertar un Eco | Desbloqueo/meta-progresión; el Eco puede volver a aparecer |

Secuencia rectora:

```text
El Eco resuena.
El personaje lo inscribe.
La carta lo representa.
El combate lo canaliza.
La muerte borra la inscripción, pero no la impronta.
```

Implicación de diseño:

- El combate no "suelta cartas" como objetos físicos.
- Al terminar un combate, el Anima residual resuena con el alma del personaje.
- Aparecen varios Ecos posibles.
- Al elegir uno, el jugador lo inscribe temporalmente en la run.
- Al morir o ser expulsado, las inscripciones activas se pierden.
- Las improntas ya despertadas no se borran del todo; por eso la pool
  desbloqueada puede crecer entre runs.

### 9.5 Fantasía diegética del sistema

Nombre operativo para el objetivo de dirección:

> La fantasía diegética del sistema es la forma en que una mecánica abstracta se convierte en una experiencia que parece pertenecer al mundo, al personaje y al tono emocional del juego.

En este juego:

- Mecánica abstracta: elegir cartas, jugar cartas, ganar recompensas.
- Fantasía diegética: resonar con Ecos, inscribir memorias de alma, canalizar
  legado.

Componentes:

- **Cohesión ludonarrativa**: la mecánica y el lore dicen lo mismo.
- **UX diegética**: la interfaz parece una expresión del mundo, no solo un menú.
- **Game feel emocional**: sonido, timing, animación y feedback dan peso al acto.
- **Identidad audiovisual del sistema**: cada sistema tiene un lenguaje visual y
  sonoro reconocible.

Frase rectora:

> El jugador no recibe cartas: inscribe Ecos.

### 9.6 Stand / Criatura

Ver sección 5 completa. Nombre definitivo pendiente.

---

## 10. Tensiones abiertas

### 10.1 Colisión "ecos de alma" vs tipo "Alma" — resuelta parcialmente

**Problema:** El world-bible dice *"las cartas son ecos de alma canalizados por el jugador"* — concepto general que aplica a **todas las cartas**. Pero el tipo **Alma** es solo un tipo específico (las del stand). Un jugador podría preguntar: *"¿y las Artes no son también del alma?"*.

**Resolución vigente 2026-04-29:**

- El término común será **Eco**.
- La definición técnica será: **memoria de alma conservada en el Anima**.
- `Eco de alma` queda permitido como formulación emocional/lore.
- `Eco de Anima` queda como formulación técnica posible, pero no como término
  visible principal.
- El tipo **Alma** se conserva para cartas íntimas del personaje, diferenciadas
  por origen y tratamiento visual.

**Pendiente:** actualizar [[21_Biblia del Mundo]] para alinear esta definición y evitar que parezca que todas las cartas son del tipo Alma.

### 10.2 Escudos mágicos del Mago — ¿tipo Escudo o tipo Don?

**Problema:** Cuando llegue el diseño del Mago (campeón 2), algunas cartas podrían ser "escudos mágicos" (barrera arcana, ward). ¿Se clasifican como *Escudo* (defensa) o como *Don* (efecto persistente otorgado)?

**Estado:** No urgente. Resolver al diseñar el Mago.

### 10.3 Nombre del stand / criatura

**Problema:** Actualmente llamado "stand", "criatura", o "digihuevo" internamente. Ninguno es nombre final válido.

**Requisitos del nombre:**
- No meta-referencial (no "stand" directo)
- No IP conflict (no "digihuevo")
- Evoque: criatura mística, compañero, extensión del alma
- Funcione en español e inglés
- Que respete el tono místico + marcial del juego

**Candidatos explorados (sin decisión):** Daemon, Animus, Crisálida (solo forma huevo), Eco...

**Estado:** Pendiente próxima sesión.

### 10.4 Marco temporal archivado

> Movido a [[13_Histórico Archivado de Vocabulario]].

---

### 10.6 Nombre del keyword activo de Paradoja

El sistema de Paradoja usa el nombre **"Paradoja"** (confirmado), pero las cartas que USAN la mecánica activamente no tienen nombre específico. Quizás no lo necesitan — son simplemente cartas que mencionan "Paradoja" en su texto.

**Estado:** Posiblemente no requiere nombre adicional. Pendiente confirmación.

### 10.7 Ascensiones — sistema de dificultad post-victoria (2026-04-19)

**Contexto:** Martin estableció que la **victoria final real** del juego se sitúa en alguna ascensión específica del Ciclo 2 (caos), no en el primer run completado. Modelo inspirado en Slay the Spire (ascensiones 1-20, cada una añadiendo modificadores de dificultad).

**Decisiones abiertas:**
- ¿Cuántas ascensiones hay (1-20 StS-style, menos, más)?
- ¿Qué modificadores introduce cada ascensión (enemigos más fuertes, menos curación, cartas malditas forzadas, etc.)?
- ¿En qué ascensión específica se sitúa la "verdadera victoria" narrativa?
- ¿Hay narrativa asociada a ciertas ascensiones o son solo modificadores de dificultad?

**Referencia previa:** en [[21_Biblia del Mundo]] (sección "Decisiones de diseño tomadas") ya se había fijado: *"Ascensión separada de narrativa — capa de dificultad para rejugabilidad, sin peso narrativo (por ahora)"*. Esa decisión del 2026-03-25 **puede revisarse** a la luz de la decisión del 2026-04-19 que sitúa la "victoria real" en alguna ascensión — lo cual le da peso narrativo implícito.

**Estado:** Pendiente diseño completo. Referenciar aquí cuando se cierre.

### 10.8 Marco temporal archivado

> Movido a [[13_Histórico Archivado de Vocabulario]].

---
## 11. Preguntas pendientes (por orden de prioridad)

> **Actualizado 2026-04-19:** tras el rediseño del sistema Alma, las preguntas obsoletas del antiguo "stand siempre en campo" han sido retiradas. Las nuevas preguntas abiertas se listan a continuación.

### 11.1 Pendientes de sesión de diseño (no requieren playtest)

> Esta tabla conserva solo preguntas activas para la nota viva. Las preguntas ligadas al marco temporal archivado viven en [[13_Histórico Archivado de Vocabulario]].

| # | Pregunta | Contexto | Dependencias |
|---|----------|----------|--------------|
| 1 | **Nombre definitivo del concepto Huevo / Alma invocada** | §10.3 | "Digihuevo" sigue siendo provisional |
| 2 | **Boss final "real" (en ascensión)** — ¿es la misma entidad recurrente que el boss final del juego, o otra? | §10.7 | Afecta a estructura narrativa de endgame |
| 3 | **Ascensiones — sistema completo** (cuántas, qué modifican, en cuál la victoria real) | §10.7 | Define el endgame |
| 4 | **Actualizar definición de Eco en Biblia del Mundo** | §9.3 / §10.1 | Alinear "Eco = memoria de alma conservada en el Anima" |
| 5 | **Marcador visual específico de cartas paradojadas** | §10.6 | Decisión de arte/UI |
| 6 | **Nombre de la clase Guerrero** (favorito: "Forjado") | — | Menor urgencia |
| 7 | **Keywords compartidas universales del juego** (Furia, Precisión, Protección, etc.) | Cartas del jugador | Menor urgencia hasta diseñar pool |

### 11.2 Pospuestas a playtest (principio transversal: no profundizar sin datos)

| # | Pregunta | Contexto |
|---|----------|----------|
| P1 | **Forma Madura (F3) — detalles concretos por tipo de huevo** (pasiva, ultimate, números) | Sección 5.5.4 / 5.16 |
| P2 | **Interacciones específicas entre huevos** — cuáles se implementan | Sección 5.10 |
| P3 | **Mecánica exacta de enemigos que comen huevos** — qué enemigos, condiciones, buff | Sección 5.11 |
| P4 | **Catálogo completo de Armas y Huevos desbloqueables** — cuántos, orden meta, hitos | Sección 5.4 / 5.5 |
| P5 | **Balance numérico del sistema Alma** — costes de energía, duraciones, pasivas | Sección 5 entera |
| P6 | **Composición del mazo inicial del Guerrero** más allá de las 2 cartas Alma básicas | Sección 5.6 |

### 11.3 Decisiones obsoletas (retiradas 2026-04-19)

- ~~Qué hace el stand en combate entre cartas Alma (pasivo mínimo por forma)~~ → el concepto de "stand siempre en campo" ya no existe.
- ~~Modelos de afinidad del stand D/E/F~~ → obsoletos, el sistema de evolución ya no depende de afinidad automática sino de alimentación explícita.

---

## 12. Tabla completa de traducciones

| Concepto | Español | Inglés | Notas |
|----------|---------|--------|-------|
| Tipo carta 1 | Ataque | Attack | Funcional; sustituye a Arma como tipo vigente |
| Tipo carta 2 | Defensa | Defense | Funcional; sustituye a Escudo como tipo vigente |
| Tipo carta 3 | Don | Gift | Mayúscula + contexto para sentido divino |
| Tipo carta 4 | Arte | Arte | Preservado — tradición *Tales of* |
| Tipo carta 5 | Alma | Alma | Preservado — identidad propia |
| Rasgo visible de Ataque | Arma | Weapon | Símbolo, no tipo de carta |
| Arma anómala | ? | ? | Herramienta de origen desconocido |
| Recurso de combate | Anima | Anima | Preservado — latino/místico |
| Concepto general de carta | Eco | Echo | Memoria de alma conservada en el Anima |
| Detección de Eco compatible | Resonancia | Resonance | Aparición de opciones de recompensa |
| Fijación temporal de Eco | Inscripción | Inscription | Añadir carta al mazo de la run |
| Uso del Eco en combate | Canalización | Channeling | Jugar carta |
| Huella persistente de Eco | Impronta | Imprint | Desbloqueo/meta-progresión |
| Subfamilia Alma (buff) | Arma de Alma | Soul Weapon | Directo |
| Subfamilia Alma (entidad) | Huevo de Alma | Soul Egg | Directo; "digihuevo" era provisional interno |
| Entidad invocada en campo | Huevo | Egg | Directo |
| Formas evolutivas del huevo | Forma 1 (Huevo) / Forma 2 (Eclosionado) / Forma 3 (Maduro) | Form 1 (Egg) / Form 2 (Hatched) / Form 3 (Mature) | Directo |
| Recurso consumido para alimentar | Ofrenda | Offering | Directo; también "tributo" en contextos Yu-Gi-Oh-esque |
| Acción de alimentar | Alimentar / Alimentación | Feed / Feeding | Directo |
| Transición F1 → F2 | Eclosión / Eclosionar | Hatching / Hatch | Directo |
| Efecto activable final del huevo | Ultimate del huevo (sin término fijado) | *por definir* | **Pendiente** |
| Estado de inversión | Paradoja | Paradox | Directo, ambas ortografías reconocibles |
| Era (período histórico) | Era | Era / Epoch | Era funciona en ambos idiomas |
| Objetos coleccionables | Reliquia | Relic | Directo (Slay-standard) |

### Términos retirados (obsoletos desde 2026-04-19)

Los siguientes términos pertenecían al diseño anterior del stand y **ya no aplican**:

| Término retirado | Razón |
|------------------|-------|
| Stand / Criatura (como mecánica siempre activa) | Sustituido por "Sistema Alma — Invocaciones" |
| Arma como tipo de carta | Sustituido por Ataque como tipo funcional; Arma pasa a ser rasgo visible de algunos Ataques |
| Escudo como tipo de carta | Sustituido por Defensa como tipo funcional; escudo/armadura quedan bajo función defensiva |
| Alma-Arma / Alma-Escudo / Alma-Arte (subtipos internos) | Subtipos invisibles descartados; ahora hay subfamilias explícitas (Arma de Alma, Huevo de Alma) |
| Energía del stand | Descartada — solo hay energía del Guerrero. Hueco programático preservado por si vuelve. |
| 3 cartas Alma iniciales del mazo | Descartadas — ahora el mazo inicial tiene solo 1 Arma Básica + 1 Huevo Básico, y ambas son comunes del pool |

---

## 13. Biblioteca de inspiraciones

Obras citadas a lo largo de la discusión. Sirve como referencia para buscar inspiración sin perder el registro.

### 13.1 JRPGs
- **Tales of (serie)** — *Artes* (Base, Arcane, Mystic). Tiering base → ultimate. **Tomamos:** el sistema de tiering para evolución de cartas de Alma. **Evitamos:** la complejidad de combos en tiempo real.
- **Xenoblade Chronicles (serie)** — *Arts* con cooldown, asignadas a personaje. **Tomamos:** legitima el término *Art/Arte*. **Evitamos:** combate MMO-style.
- **Persona (serie)** — manifestación del alma como ente combatiente. **Tomamos:** el vínculo íntimo personaje-criatura. **Evitamos:** su estructura narrativa (calendario, social links).
- **Chrono Trigger** — viajes entre eras (Prehistoria, Edad Media, Futuro, Fin del mundo). **Tomamos:** la estructura de eras como motor narrativo. **Evitamos:** party-based combat.
- **Final Fantasy XIV** — *Gifts* desde dioses. **Tomamos:** el framing de "poder otorgado".

### 13.2 Deckbuilders roguelike
- **Slay the Spire** — *Attack / Skill / Power* como tipos base. **Tomamos:** la estructura de tipos + reliquias + mapa + arte único por carta. **Evitamos:** sus nombres genéricos (Attack/Skill/Power) — los nuestros cargan lore.
- **Monster Train** — mundo con premisa que justifica mecánicas. **Tomamos:** el principio de "lore que explica mecánicas". **Evitamos:** multi-lane.
- **Balatro** — combos adictivos. **Tomamos:** el dopamine loop. **Evitamos:** ausencia de narrativa.
- **Hades** — *Boons* otorgados por dioses. **Tomamos:** el concepto de poder otorgado. **Evitamos:** la transaccionalidad (la Torre no pide nada a cambio).

### 13.3 Souls-like / Fantasía occidental
- **Dark Souls 3** — *Weapon Arts* como técnica ligada al arma. **Tomamos:** legitima *Arte* en registro marcial-místico. **Evitamos:** su tono cripto-religioso.
- **Hollow Knight** — *Soul* como recurso y combate espiritual. **Tomamos:** la fuerza del concepto alma-energía. **Evitamos:** usar *Soul* literal (ya es suyo).

### 13.4 Shōnen / Anime
- **JoJo's Bizarre Adventure (Echoes de Koichi)** — stand con formas evolutivas. **Tomamos:** la estructura de 3 formas. **Evitamos:** la meta-referencia directa a "stand".
- **Digimon** — concepto de evolución por etapas (huevo → formas). **Tomamos:** la estructura conceptual. **Evitamos:** el nombre "digi-" y la estética específica.
- **Pokémon** — iniciales con 3 formas evolutivas. **Tomamos:** la estructura. **Evitamos:** control directo.
- **Jujutsu Kaisen** — técnica heredada, energía maldita. **Tomamos:** el registro marcial-místico, la idea de "técnica que es tuya". **Evitamos:** la complejidad del power-scaling shōnen.
- **Hunter x Hunter (Nen)** — sistema de poderes categorizados, basado en personalidad. **Tomamos:** la idea de que el poder refleja quién eres. **Evitamos:** el gating narrativo de habilidades.
- **Tower of God** — outsiders irregulares que desestabilizan el orden. **Tomamos:** el concepto de outsider (ya en world-bible). **Evitamos:** la estructura política bizantina.
- **Sword Art Online** — torre con pisos-mundo, motivación de escalar. **Tomamos:** estructura de torre vertical y pisos temáticos. **Evitamos:** death-game fanservice.
- **Steins;Gate** — paradojas temporales, líneas bifurcadas. **Tomamos:** la fuerza del concepto *paradoja*. **Evitamos:** la complejidad de visual novel.

### 13.5 Literatura fantástica
- **A Song of Ice and Fire** — *"The Gift"*. **Tomamos:** legitima *Gift* con sentido elevado.
- **Tolkien** — *The Gift of Men*. **Tomamos:** ancestry del término *gift* en fantasía alta.

### 13.6 Kingdom Hearts / Disney
- **Kingdom Hearts** — *Keyblade* como extensión del corazón. **Tomamos:** la idea de arma-extensión-del-alma para Ataques del Guerrero con Arma.

### 13.7 Cine / Series
- **Blade Runner / Cyberpunk 2077** — futurismo distópico, estética para era del acto 3. **Tomamos:** paleta y tono.
- **Arcane** — Zaun como ciudad vertical con estratos, paralelismo con la Torre. **Tomamos:** el tratamiento visual de "estratos sociales verticales".
- **Hunger Games** — Distrito 12 como "demasiado pobre para importar" (paralelismo con pisos bajos de la Torre). **Tomamos:** dinámica de poder vertical.

---

## 14. Registro de decisiones (fechado)

### 2026-04-17 — Sesión de brainstorm: nombres de tipos de carta

**Contexto:** Pivot previo eliminó los 5 tipos de alma como subtipos visibles. Quedó pendiente nombrar los 4 tipos normales + el tipo Alma.

**Decisiones cerradas:**
1. **Arma** confirmado como tipo en ese momento; **superado el 2026-04-29**,
   ahora Arma es rasgo visible de Ataques.
2. **Defensa → Escudo** en ese momento; **superado el 2026-04-29**, ahora
   Defensa es tipo funcional vigente.
3. **Poder persistente → Don** (sentido elevado, encaje con outsider)
4. **Utilidad instantánea → Arte** (rechazó *Habilidad* por efímero, prefirió peso de *Arte*)
5. **Cartas del stand → Alma** (confirmado)
6. **Traducciones:** Weapon / Shield / **Gift** (con framing) / **Arte** (preservado) / **Alma** (preservado)

---

### 2026-04-18 — Sesión de brainstorm: stand, eras y Paradoja

> Movido a [[13_Histórico Archivado de Vocabulario]].
### 2026-04-19 — Sesión de rediseño: Sistema Alma reformulado

**Contexto:** Martin detectó fallas estructurales en el diseño anterior del stand (problema diegético de interacción con el enemigo, duplicación de targets, pérdida de peso como amplificador pasivo, conflicto con la filosofía deckbuilder opt-in). Iteramos hasta reformular el sistema de fondo.

**Decisiones cerradas — Arquitectura del nuevo Sistema Alma:**

1. Las cartas **Alma** pasan de ser "cartas del stand siempre en mazo" a ser **tipo de carta invocadora opt-in**. El jugador decide si las incorpora a su build. Filosofía deckbuilder preservada.
2. Dos subfamilias explícitas: **Arma de Alma** (buff sobre el Guerrero) y **Huevo de Alma** (entidad en campo).
3. **Solo energía del Guerrero** — la energía del stand se descarta. La estructura programática preserva el hueco por si vuelve en otras clases.
4. Cartas Alma **exhaust al jugarse** (recuperables en siguiente combate). Siguen el ciclo normal del mazo.
5. El **Huevo-entidad** NO es una carta — es una entidad en campo, con estado propio (forma, timer, contador, pasiva), sin HP. Es un concepto arquitectural distinto (más cercano al Guerrero que a una carta).
6. **Regla transversal:** todo lo que sea carta tiene **meta-progresión**. Modelo C (pool base + desbloqueo cada X runs).

**Decisiones cerradas — Arma de Alma:**

7. Coste base: 1 energía para la Arma de Alma Básica (Filo Básica).
8. Efecto base: próximas **3 cartas de ataque +2 daño**.
9. Duración por **usos de cartas**, no turnos. El jugador controla el ritmo.
10. Variantes temáticas: Filo, Trueno, Sombra, Tiempo, Luz (catálogo a ampliar).
11. **Visualmente especial**: aura sobre las cartas de ataque en mano mientras está activa. Se "consume" visualmente al usarse.

**Decisiones cerradas — Huevo de Alma:**

12. Coste de invocación: solo energía (Huevo Básico = 2 energía). **No requiere ofrenda de entrada**.
13. **Pasiva base** desde Forma 1 (modesta pero útil).
14. **Timer de vida** inicial: 3 turnos (Huevo Básico). Ajustable por tipo.
15. **Ofrenda específica por huevo** (el Básico: ataques de 1+ energía; otros: veneno/fuego/bloqueo/etc.).
16. **Quemado automático sin elección:** si la carta jugada cumple la ofrenda, se quema como exhaust del combate. Simplifica el turno y obliga a comprometerse al invocar.
17. **Una carta alimenta a todos los huevos compatibles** simultáneamente.
18. **Evolución F1 → F2** tras 3 alimentaciones. Transición al inicio del siguiente turno.
19. **Forma 2** inmune a expiración por timer. Efecto inmediato al eclosionar.
20. **Evolución F2 → F3** tras 5 alimentaciones adicionales (8 totales).
21. **Forma 3 (Maduro)** tendrá una **ultimate activable** que consume al huevo + pasiva potente. Detalles específicos pospuestos a playtest.
22. **Muerte por timer:** desaparece sin ceremonia. No feedback especial.
23. **Sin HP.** No atacable por enemigos normales. **Excepción: enemigos que devoran almas** — hook sistémico aceptado, diseño específico pospuesto.
24. Huevo-entidad vive solo el combate. Cada combate es un ritual nuevo — siempre arranca en Forma 1 (salvo reliquias).

**Decisiones cerradas — Reglas universales del sistema:**

25. **Evolución siempre al inicio del siguiente turno**, universal con excepciones.
26. **Siempre arranca en Forma 1**, excepto excepciones (reliquias, efectos).
27. **Sin límite de huevos simultáneos.** Romper el juego en fases avanzadas es feature.
28. **Arma + Huevo coexisten.**
29. **Sin límite de copias por carta** (comunes/raras). Épicas únicas pueden tener límite.
30. **Cartas que invocan 2 huevos de golpe** existen como ultra raras.
31. **No paradojables por ahora.** Estructura programática preparada para activar en el futuro.

**Decisiones cerradas — Mazo inicial y obtención:**

32. Mazo inicial del Guerrero incluye **1 Arma Básica + 1 Huevo Básico**.
33. Rareza de ambas: **común** (no "inicial exclusiva") — pueden aparecer como recompensa del pool normal.
34. **Armas** se obtienen en el **pool normal post-combate**.
35. **Huevos** se obtienen en **eventos especiales, altares, recompensas de boss** (no en pool normal).

**Principios transversales establecidos en esta sesión:**

36. **Todo lo que sea carta tiene meta-progresión.** Regla general del juego, no solo del sistema Alma.
37. **Sistema base flexible a modificación.** Reliquias, efectos y cartas raras pueden sobrescribir cualquier regla base. Esto no es complejidad — es el modo de mantener variedad.
38. **No profundizar en detalle fino antes de testear.** Primero infraestructura funcional, luego tuning con datos de playtest.

**Descartado explícitamente (razonado durante la sesión):**

39. Stand siempre en campo con HP y energía propias.
40. Enemigos con 2 targets (Guerrero + stand).
41. Stand como solo amplificador pasivo (pierde peso).
42. 3 cartas Alma iniciales fijas con subtipos invisibles.
43. Evolución del stand ligada a transiciones de acto.
44. Opciones diegéticas parches descartadas: "las almas se pueden pegar entre sí" (regla metafísica arbitraria), "todo tiene alma y el stand ataca almas" (cambia naturaleza del combate).
45. Opciones diegéticas consideradas y descartadas como marco único: "Torre es umbral" (válida pero requeriría 2 targets), "enemigos son ecos" (desplaza el problema), "stand canaliza sin tocar" (pierde peso), "arma viva" / "forma/aura" (reconceptualizaciones grandes). Al final, el problema se disolvió al convertir Alma en mecánica invocadora.

**Próximas decisiones pendientes (para sesiones posteriores o playtest):**

- Nombre definitivo del concepto ("digihuevo" sigue provisional)
- Forma Madura: detalles numéricos y ultimates específicos (tras playtest)
- Catálogo concreto de Armas y Huevos desbloqueables (tras playtest)
- Interacciones específicas entre huevos (tras playtest)
- Mecánica exacta de enemigos que devoran almas (tras diseño de enemigos)
- Balance numérico general del sistema Alma (tras playtest)
- Composición del resto del mazo inicial del Guerrero (tras diseño de pool básico)
- Las preguntas pre-existentes no resueltas (diversidad de eras, boss final recurrente, alineación de la definición de Eco en Biblia del Mundo, era final cronológica, etc. — ver sección 11)

**Filosofía establecida:**

> *"El deck es lo más importante. Las cartas Alma son opciones ofrecidas al jugador — si le interesa la mecánica la coge, si no, no. El power lo tiene el jugador. Queremos ofrecer cosas interesantes para ser elegidas, ahora o en el futuro cuando se sienta más cómodo. Ese es el poder del deckbuilding."* — Martin, 2026-04-19

---

### 2026-04-19 (segunda parte) — Sesión de rediseño: Estructura de dos ciclos y cartas de era

> **Movido a histórico:** [[12_Histórico de Eras y Cartas de Era]]
>
> Esta sesión documenta una línea de diseño archivada y se conserva solo como memoria del proceso.

---

### 2026-04-29 — Sesión de terminología: Arma, Ecos e Improntas

**Contexto:** al diseñar el Guerrero como campeón de arsenal tribal surgió una
ambigüedad fuerte: `Arma` estaba documentada como tipo de carta, pero el diseño
actual necesita que sea un símbolo/rasgo visible de ciertos Ataques. En paralelo
se formalizó la fantasía diegética de las cartas como Ecos, para explicar
recompensas, mazo de run y meta-progresión sin tratarlos como loot físico.

**Decisiones cerradas — Arma:**

1. **Arma deja de ser tipo de carta vigente.**
2. Los tipos funcionales vigentes para prototipo son **Ataque / Defensa / Arte / Don / Alma**.
3. **Arma** pasa a ser un símbolo visible de algunos Ataques.
4. Los Ataques básicos no tienen Arma.
5. Defensa, Arte, Don y Alma no tienen Arma.
6. Arma no tiene efecto inherente. Solo importa cuando una carta, trofeo,
   reliquia o regla la referencia.
7. Las armas pueden tener tendencias de diseño, pero no reglas automáticas por
   arma.
8. **?** queda confirmado como valor de Arma anómala.
9. Tooltip de Arma anómala: *"herramienta de origen desconocido."*
10. **?** no es categoría adicional: todas las cartas con **?** comparten la
    misma Arma.

**Decisiones cerradas — Ecos y fantasía diegética:**

11. Una carta no es un objeto físico ni loot del enemigo: es la forma jugable de
    un **Eco**.
12. **Eco** se define como **memoria de alma conservada en el Anima**.
13. **Resonancia** = momento en que el alma detecta un Eco compatible.
14. **Inscripción** = fijación temporal de un Eco al alma activa durante la run.
15. **Canalización** = uso de un Eco inscrito durante el combate; jugablemente,
    jugar una carta.
16. **Impronta** = huella persistente que queda al descubrir/despertar un Eco y
    permite que vuelva a aparecer en futuras runs.
17. La muerte o expulsión borra las inscripciones activas, pero no borra del todo
    las improntas.

**Frase rectora:**

> El Eco resuena.  
> El personaje lo inscribe.  
> La carta lo representa.  
> El combate lo canaliza.  
> La muerte borra la inscripción, pero no la impronta.

**Principio audiovisual:**

> El jugador no recibe cartas: inscribe Ecos.

Esta formulación debe guiar recompensa post-combate, tutorial, UI, sonido,
animación y pitch externo del sistema.

---

## 15. Cómo usar este documento

### Para el diseñador (Martin)

1. Antes de proponer un nombre nuevo, busca en secciones 3-9 si ya hay algo relacionado
2. Si detectas una tensión, anótala en sección 10
3. Cuando cierras una decisión, añádela a sección 14 con fecha
4. Si diseñas una carta nueva, consulta sección 6 (Paradoja) para asegurarte de diseñar también su forma paradoja (si es paradojable)
5. Si diseñas un enemigo, consulta [[21_Biblia del Mundo]] y [[22_Estratos de la Torre]] antes de proponer naming o framing

### Para los subagentes (Claude)

1. Antes de escribir cualquier término nuevo en un GDD, contrastar contra este documento
2. Si un nombre propuesto choca con un concepto establecido, proponer alternativas que respeten el registro
3. Al traducir al inglés, consultar sección 12 primero
4. Al buscar inspiración, citar obras de sección 13 cuando sea posible — mantiene el registro coherente
5. Al proponer mecánicas nuevas, verificar que no colisionen con sistemas ya establecidos (Sistema Alma, Paradoja, Mutación y Fusión)
6. Si se toma una decisión de diseño, añadirla a sección 14 con fecha
7. Si surge una tensión semántica o de diseño, añadirla a sección 10

---

## 16. Archivos relacionados

- [[11_Concepto del Juego]] — Concepto general del juego, pitch y alcance
- [[12_Mecánicas Centrales]] — Fuente de verdad mecánica actual
- [[13_Mutación y Fusión]] — Desarrollo específico subordinado
- [[21_Biblia del Mundo]] — Canon de mundo jugable
- [[22_Estratos de la Torre]] — Estructura macro de la Torre
- [[23_Sistema de Poder]] — Metafísica y sistema de poder
- [[24_Memoria Narrativa]] — Exploración narrativa viva
- [[25_Borrador de Elementales]] — Borrador de criaturas y fauna
- [[12_Histórico de Eras y Cartas de Era]] — Marco temporal archivado
- [[13_Histórico Archivado de Vocabulario]] — Decisiones y tensiones archivadas de esta nota




