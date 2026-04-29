---
type: product
status: active
tags: ["producto","mecanicas"]
updated: 2026-04-29
---

# Mecánicas Centrales — La Torre

*Documento maestro de mecánicas. Es la única fuente de verdad mecánica del proyecto.*
*Principio rector: las mecánicas definen al personaje, no al revés. El mundo de la Torre aporta el flavour mecánico; cada clase aporta un giro propio.*

*Created: 2026-04-15*
*Status: Documento maestro en consolidación*

---

## 0. Autoridad del documento

Este archivo gobierna:

- mecánicas base del juego
- sistema de cartas
- mecánicas prioritarias del proyecto
- submecánicas de clase
- mecánicas en experimentación
- decisiones mecánicas descartadas

Este archivo NO gobierna:

- lore estructural de la Torre ([[22_Estratos de la Torre]])
- canon de mundo jugable ([[21_Biblia del Mundo]])
- metafísica del mundo ([[23_Sistema de Poder]])
- nomenclatura, traducciones y memoria de decisiones ([[14_Vocabulario y Nomenclatura]])

Documentos subordinados:

- [[13_Mutación y Fusión]]
- [[11_Sistema de Temple]]

Documentos retirados o sin autoridad directa:

- [[10_Sistema de Carga]]

---

## 1. Estado de consolidación

### Núcleo estable

- Las tres capas del alma
- Identidad de las cartas como ecos
- Código audiovisual de resonancia
- Disciplina visual reactiva

### Provisional fuerte

- Sistema de cartas (tipología final aún en revisión)
- Mutación y Fusión
- Sistema Alma

### Submecánicas provisionales

- Temple
- Forja

### En experimentación

- Afinamiento
- Paradoja
- Keywords del mundo
- Arquetipos

### Congelado

- Tipología del alma y pentágono vivo
- Nombre final de la clase Guerrero

### Retirado

- Carga como sistema independiente
- Stand siempre activo
- Eras como estructura del juego
- Cartas de era

---

## 2. Principio fundacional

> **La fórmula del deckbuilder queda. Lo que evoluciona es la experiencia.**

Mecánicamente el juego se apoya en una base clara de roguelike deckbuilder por turnos. La diferenciación no viene de romper la gramática del género, sino de combinar:

- una ficción de alma, Anima y ecos coherente
- un mazo que puede transformarse durante la run
- una lectura audiovisual muy marcada
- una Torre que condiciona cómo se siente cada sistema

Objetivo: ser un deckbuilder de alma e identidad fuerte, no un sistema abstracto vestido de lore.

---

## 3. Base del juego

### 3.1 Las tres capas del alma

En el juego conviven tres capas que deben sentirse distintas tanto en lectura como en función:

| Capa | Qué es narrativamente | Qué hace mecánicamente | Dónde vive visualmente |
|------|-----------------------|------------------------|------------------------|
| **Alma propia** | El propio Guerrero. Lo que eres | HP, afinidad innata, capacidades que despiertan durante la run | Personaje |
| **Ecos** | Intenciones cristalizadas de otros seres | Las cartas del mazo | Cartas |
| **Anima** | Energía ambiental que satura la Torre | Recurso de combate | Fondo / entorno |

Tres verbos rectores:

- el Alma **sostiene**
- los Ecos **se canalizan**
- el Anima **fluye**

Regla de diseño crítica:

- estas tres capas no deben compartir la misma zona visual primaria de lectura

### 3.2 Identidad de las cartas

> **Las cartas son ecos.**

Una carta no es un objeto abstracto ni un hechizo genérico. Es la canalización temporal de una intención cristalizada en el Anima de la Torre.

Esto resuelve:

- por qué el mazo puede variar run a run
- por qué una carta expresa personalidad y experiencia
- por qué el jugador no “posee” totalmente ese poder

### 3.2.1 Gramática de resonancia

Definición vigente:

> Un Eco es una memoria de alma conservada en el Anima.

La carta es el medio jugable que permite al jugador entender, elegir y usar ese
Eco, pero no es un objeto físico que el enemigo suelta.

Términos operativos:

| Término | Qué significa | Traducción jugable |
|---------|---------------|--------------------|
| **Resonancia** | El alma detecta un Eco compatible | Aparecen opciones de recompensa |
| **Inscripción** | El Eco queda fijado temporalmente al alma activa | La carta entra al mazo de la run |
| **Canalización** | El Eco se usa durante el combate | El jugador juega la carta |
| **Impronta** | Huella persistente de un Eco descubierto/despertado | Desbloqueo/meta-progresión |

Secuencia rectora:

```text
El Eco resuena.
El personaje lo inscribe.
La carta lo representa.
El combate lo canaliza.
La muerte borra la inscripción, pero no la impronta.
```

Implicación para recompensas:

- un combate no entrega loot físico en forma de carta;
- el Anima residual del combate resuena con el alma del personaje;
- la recompensa muestra varios Ecos compatibles;
- elegir una carta significa inscribir ese Eco en la run;
- al morir o ser expulsado, las inscripciones activas se pierden;
- las improntas explican por qué el pool desbloqueado permanece disponible en
  futuras runs.

Principio de presentación:

> El jugador no recibe cartas: inscribe Ecos.

### 3.2.2 Cartas, mutaciones e interpretación de clase

Regla transversal:

> Las cartas son identidad de clase. Las mutaciones son material de la Torre.
> Cada clase expresa ese material según su relación con el alma.

Implicaciones:

- una carta pertenece al pool y fantasía de una clase
- una mutación pertenece al ecosistema de la Torre y puede aparecer en varias clases
- la función base de una mutación debe ser reconocible entre clases
- la lectura visual, afinidad o pequeño modificador puede cambiar según clase

Contraste guía:

| Clase | Relación con el alma | Lectura de mutación |
|---|---|---|
| **Guerrero** | canaliza hacia dentro: cuerpo, técnica, impacto | la mutación se vuelve golpe, resistencia, ritmo marcial |
| **Mago** | expulsa alma hacia fuera como magia elemental | la mutación se vuelve forma externa, propagación, control del campo |

Esta regla no autoriza a diseñar versiones completamente distintas de cada
mutación por clase antes de prototipar. Primero se define la función universal;
después se añaden interpretaciones de clase si aportan identidad sin romper scope.

### 3.3 Flujo base del combate

Loop conceptual de un turno:

```text
Anima ambiental -> pago de coste -> canalización del eco -> resolución del efecto -> residuo vuelve al entorno
```

El jugador debe poder aprender esta lógica sin exposición textual dura.

---

## 4. Sistema de cartas

### 4.1 Rol del sistema

El sistema de cartas define:

- cómo se lee la mano
- qué tipo de decisión ofrece cada carta
- cómo se organizan sinergias y builds
- cómo se conectan las mecánicas prioritarias con el mazo

### 4.2 Estado actual

La **tipología final de cartas sigue en revisión**.

Ver también [[15_Sesión 2026-04-24 — Criterios de Mutación y Alma]].

Hoy conviven dos capas:

- una **capa funcional** heredada del lenguaje deckbuilder clásico
- una **capa semántica / de naming** que se está refinando en [[14_Vocabulario y Nomenclatura]]

Hasta que la taxonomía final quede cerrada, este documento usa una regla operativa:

- los **tipos de carta se deciden aquí por función jugable**
- los **nombres definitivos** se fijan y justifican en [[14_Vocabulario y Nomenclatura]]

Marco provisional de trabajo surgido en auditoría:

- **Ataque**
- **Defensa**
- **Arte**
- **Don**
- **Alma**

Actualización 2026-04-29:

- **Arma no es un tipo de carta vigente.**
- **Arma** es un rasgo visible de algunos Ataques.
- Ver [[14_Vocabulario y Nomenclatura]] para naming, tooltip y términos
  retirados.

Regla provisional para prototipo:

- cada carta tiene **un tipo principal**
- provisionalmente, ese tipo lo define **lo primero que hace la carta**
- esta regla queda pendiente de testeo y puede sustituirse por una regla de **función dominante**

### 4.3 Tipos de carta — criterio funcional actual

El juego necesita distinguir, como mínimo, entre estas funciones:

| Función | Lectura jugable |
|---------|-----------------|
| **Carta inmediata ofensiva** | se juega, impacta y sale del flujo normal del turno |
| **Carta inmediata defensiva / utilitaria** | se juega, modifica el estado del turno y sale |
| **Carta persistente** | queda activa durante el combate |
| **Carta invocadora** | crea una entidad o estado especial y altera el flujo normal |

### 4.4 Regla de autoridad

La taxonomía final no se considera cerrada hasta validar:

- claridad de mano
- claridad tutorial
- compatibilidad con Sistema Alma
- compatibilidad con Mutación y Fusión

### 4.5 Rasgo visible: Arma

**Arma** es un símbolo visible que puede aparecer en algunos Ataques.

Reglas:

- Arma no es un tipo de carta.
- Un Ataque puede tener Arma o no tenerla.
- Los Ataques básicos no tienen Arma.
- Defensa, Arte, Don y Alma no tienen Arma.
- Arma no tiene efecto inherente.
- Solo importa cuando una carta, trofeo, reliquia o regla la referencia.
- Las armas pueden tener tendencias de diseño, pero esas tendencias no son
  reglas automáticas.

Ejemplo de lectura:

```text
Corte Compuesto
Tipo: Ataque
Arma: Espada
```

Arma anómala:

- **?** es un valor de Arma.
- **?** no es una categoría adicional.
- Todas las cartas con **?** comparten la misma Arma.
- Tooltip de referencia: "Arma anómala: herramienta de origen desconocido."

Regla de defensa:

- Los elementos defensivos pertenecen a **Defensa / Armadura**.
- Un golpe de escudo o una embestida defensiva se clasifica primero por función:
  si su función principal es defender, no participa en el sistema de Arma aunque
  también haga daño.

### 4.6 Poderes persistentes

La persistencia de una carta durante el combate no es solo una convención del género:

- representa un Eco que se fusiona temporalmente con el alma del Guerrero
- al final del combate esa integración se disuelve

---

## 5. Identidad audiovisual jugable

### 5.1 Código audiovisual de resonancia

> **Toda carta es luz que resuena.**

Jugar una carta no es “ejecutar una acción” sin más, sino hacer resonar una intención ajena dentro del alma del portador.

Gramática base:

| Tipo de lectura | Inspiración visual | Inspiración sonora |
|-----------------|-------------------|--------------------|
| **Impulso ofensivo** | chispazo direccional | crack percusivo corto |
| **Técnica / utilidad** | onda o gota de luz | campana o cuenco limpio |
| **Persistencia** | aura sostenida | drone grave / coral |

La misma gramática debe variar por clase sin romper coherencia global.

### 5.2 Disciplina visual reactiva

Reglas obligatorias:

1. jerarquía clara entre carta fuente y cartas afectadas
2. ripple en cascada cuando múltiples cartas reaccionan
3. evitar encender toda la mano cuando el mensaje real es “todo”
4. contención cromática: densidad mejor que saturación
5. ningún efecto reactivo desborda la silueta de la carta

Esto es contrato de UX, no adorno.

---

## 6. Mecánicas prioritarias

### 6.1 Sistema de Mutación y Fusión

Documento subordinado: [[13_Mutación y Fusión]]

Ver también [[15_Sesión 2026-04-24 — Criterios de Mutación y Alma]].

Estado:

- **Mutaciones**: línea prioritaria y bastante avanzada
- **Fusiones**: línea prioritaria pero todavía abierta

#### Función dentro del juego

El sistema existe para que el mazo no solo crezca, sino que **se transforme** durante la run.

#### Capa 1 — Mutaciones

Base actual:

- una carta puede recibir una mutación
- la mutación modifica esa carta concreta
- el jugador decide dónde aplicarla
- el sistema debe enseñar personalización del mazo sin sobrecargar el tutorial

Criterios provisionales fijados en auditoría:

- **Mutación** es una capa secundaria de run
- no debe cambiar la **identidad funcional** de la carta
- debe aparecer con cierta regularidad, pero sin saturar la run
- la fuente principal correcta es **recompensa de combate**
- **Ataque** y **Defensa** tienen afinidad más alta
- **Arte** y **Don** tienen afinidad menor, con payoff más orientado a valor / escalado
- el marco vigente para testeo es **Familia + Linaje + Estrato + Grado**
- los combates mutados son una fuente visible de riesgo-recompensa: más dificultad
  a cambio de recompensas de cartas mutadas
- los estratos modifican flavour, disponibilidad y complejidad; no deben obligar
  a reaprender sistemas de mutación nuevos
- las mutaciones tienen función universal, pero pueden tener interpretación de
  clase si eso refuerza identidad sin multiplicar el sistema

#### Capa 2 — Fusiones

Base actual:

- dos cartas pueden producir una síntesis nueva
- esta capa sigue abierta y no debe darse por cerrada

#### Regla de diseño

La causa diegética exacta del sistema **sigue abierta**. No debe enseñarse al jugador una causalidad falsa solo para simplificar el tutorial.

### 6.2 Sistema Alma

Estado:

- mecánica prioritaria
- opt-in
- ya no funciona como stand permanente

Ver también [[15_Sesión 2026-04-24 — Criterios de Mutación y Alma]].

#### Principios rectores

1. el deck es el centro
2. el sistema puede ignorarse y el jugador debe seguir pudiendo ganar
3. el sistema ofrece dos puertas de entrada:
   - **Arma de Alma**
   - **Huevo de Alma**

Dirección provisional más reciente:

- **Alma** se está reinterpretando como la **máxima expresión de clase**
- debe ser una capa **minimalista**, especial y de **alto potencial**
- una carta **Alma** no debe ganar sola; debe habilitar techos altos con el mazo adecuado
- el **tipo** sigue siendo `Alma`
- el **resultado visible** puede ser una **transformación / forma**
- solo debería haber **una forma Alma activa a la vez**

La implementación concreta del Guerrero queda abierta; el modelo `Arma + Huevo` ya no debe considerarse estable.

#### Arquitectura jugable

| Elemento | Qué es |
|----------|--------|
| **Carta Alma** | carta del mazo que se juega y se exhausta en combate |
| **Arma de Alma** | estado aplicado al Guerrero |
| **Huevo de Alma** | entidad anímica en campo con evolución propia |

#### Reglas base

- las cartas Alma gastan energía del Guerrero
- se integran en el ciclo normal de deckbuilding
- no son obligatorias
- su complejidad debe entrar de forma progresiva

---

## 7. Submecánicas de clase

### 7.1 Temple

Estado:

- submecánica provisional del Guerrero
- pendiente de validación jugable real

Función actual:

- recompensar defensa ajustada y lectura del turno enemigo
- reforzar la fantasía de aguantar y templarse

Regla base actual:

- si una armadura marcada como Temple se rompe por daño enemigo, genera un beneficio para el siguiente turno

### 7.2 Forja

Estado:

- submecánica provisional
- no debe tratarse aún como mecánica firma cerrada

Función actual:

- expresar la relación del Guerrero con el poder de Arma
- ofrecer una capa de preparación / manifestación dentro del combate

Preguntas aún abiertas:

- qué cartas alimentan la forja
- cuánta centralidad merece dentro del kit del Guerrero
- si convive bien con Temple, Sistema Alma y el resto del mazo

---

## 8. Mecánicas en experimentación

### 8.1 Afinamiento

Idea:

- los ecos se refinan por uso durante la run

Estado:

- experimental
- no debe gobernar el diseño general hasta validar su coste cognitivo y su convivencia con Mutación y Fusión

### 8.2 Paradoja

Idea:

- una carta puede acceder a una forma alterada o invertida

Estado:

- experimental
- no debe contaminar el núcleo hasta decidir si aporta claridad o complejidad gratuita

### 8.3 Keywords del mundo

Estado:

- exploración abierta
- no se consideran sistema consolidado

### 8.4 Arquetipos

Estado:

- exploración abierta
- no deben estructurar todavía el proyecto

---

## 9. Pospuesto a testeo

Las siguientes decisiones no deben cerrarse sin prototipo y prueba:

- números de daño, bloqueo, costes y duraciones
- frecuencia de mutaciones
- ritmo de acceso a Sistema Alma
- peso real de Temple y Forja
- taxonomía final de tipos de carta
- si Afinamiento y Fusión conviven de forma sana

---

## 10. Congelado

Estas ideas no se trabajan ahora salvo reactivación explícita:

- tipología del alma y pentágono vivo
- nombre final de la clase Guerrero

Motivo:

- tienen potencial, pero hoy no mejoran el núcleo inmediato del juego

---

## 11. Retirado

### Retirado del diseño activo

- Carga como sistema independiente
- stand siempre activo
- eras como estructura del juego
- cartas de era

### Regla

Lo retirado no vuelve a considerarse parte del núcleo salvo rescate deliberado.

---

## 12. Decisiones tomadas

| Decisión | Estado actual |
|----------|---------------|
| La fórmula del deckbuilder se conserva | Vigente |
| Las cartas son ecos canalizados | Vigente |
| Eco = memoria de alma conservada en el Anima | Vigente |
| Resonancia / Inscripción / Canalización / Impronta explican recompensa, carta, uso y meta-progresión | Vigente |
| El combate se lee en tres capas: Alma / Ecos / Anima | Vigente |
| La identidad audiovisual es parte del sistema, no solo presentación | Vigente |
| Arma deja de ser tipo de carta y pasa a rasgo visible de algunos Ataques | Vigente |
| ? queda como Arma anómala: herramienta de origen desconocido | Vigente |
| Mutación y Fusión es una línea prioritaria | Vigente |
| Sistema Alma pasa a ser opt-in | Vigente |
| Temple baja a submecánica provisional | Vigente |
| Carga sale del diseño activo | Vigente |
| Pentágono vivo queda congelado | Vigente |

---

## 13. Preguntas abiertas

### Prioridad alta

- cuál es la taxonomía final de tipos de carta
- qué peso real tienen Mutación y Fusión dentro del juego final
- qué causa diegética sostiene Mutación y Fusión sin inducir una lectura falsa
- qué papel real merece Temple dentro del kit del Guerrero

### Prioridad media

- si Forja sobrevive y en qué escala
- si Afinamiento merece convivir con el resto de sistemas
- si Paradoja aporta valor suficiente como para mantenerse viva

### Prioridad baja

- nombre final de la clase Guerrero
- expansión futura de arquetipos y keywords
