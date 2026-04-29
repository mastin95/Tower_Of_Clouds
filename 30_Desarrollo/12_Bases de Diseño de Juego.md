---
type: dev
status: reference
tags: ["dev","guia"]
updated: 2026-04-24
---

# Guía de Conceptos de Game Design

*Para consulta rápida cuando necesites repasar los conceptos que usamos en el proyecto.*

---

## ¿Qué es un "sistema" en un juego?

Un sistema es una **pieza del juego que tiene sus propias reglas y puede funcionar
de forma autónoma**. Piensa en cada sistema como un engranaje de una máquina —
cada uno hace algo concreto, y juntos hacen funcionar el juego.

### Ejemplo con Slay the Spire

Cuando juegas un *Strike* contra un Jaw Worm, están interactuando varios sistemas
a la vez:

- **Sistema de energía**: ¿Tienes 1 energía para pagar la carta? → Se descuenta
- **Sistema de cartas**: El Strike dice "inflige 6 de daño" → el sistema lee eso
- **Sistema de targeting**: ¿A quién le pegas? → Al Jaw Worm que seleccionaste
- **Sistema de daño**: 6 de daño base + ¿tienes Strength? → calcula el daño final
- **Sistema de armadura**: ¿El Jaw Worm tiene Block? → absorbe parte del daño
- **Sistema de salud**: El daño restante le baja el HP
- **Sistema de deck**: El Strike va de tu mano al discard pile
- **UI de combate**: Los números de daño aparecen, la barra de HP baja, la carta se anima

Un solo click del jugador → 8 sistemas coordinándose. Pero cada uno tiene sus
propias reglas. El sistema de armadura no sabe nada de cartas — solo sabe que
le llegan X puntos de daño y tiene Y de shield.

---

## ¿Por qué separamos el juego en sistemas?

Porque si diseñas todo junto se vuelve un caos. Imagina intentar escribir TODAS
las reglas de Slay the Spire en un solo documento — cartas, reliquias, mapas,
enemigos, tienda, eventos, todo mezclado. Sería imposible de entender o modificar.

Al separar en sistemas:

- Puedes **diseñar uno a la vez** sin volverte loco
- Puedes **cambiar uno sin romper los demás** — si quieres cambiar cómo funciona
  la armadura, no necesitas reescribir las cartas
- Puedes **testear uno solo** — ¿funciona el combate? Pruébalo sin necesitar que
  la tienda exista aún

---

## Capas de dependencia

Las capas responden a una pregunta simple: **¿qué necesita existir antes para que
esto funcione?**

Imagina que estás construyendo una casa:

```
Capa 1 (Foundation):    Cimientos y suelo
Capa 2 (Core):          Paredes y estructura
Capa 3 (Feature):       Habitaciones, cocina, baño
Capa 4 (Presentation):  Pintura, muebles, decoración
Capa 5 (Polish):        Cuadros en la pared, plantas
```

No puedes poner muebles sin tener habitaciones. No puedes hacer habitaciones sin
paredes. No puedes poner paredes sin cimientos.

### En nuestro juego

```
Foundation:    HP, armadura, energía, mazo, estados
               ↓
Core:          Combate por turnos, sistema de cartas, campeones
               ↓
Feature:       Carga, Temple, AI enemigos, mapa, tienda, reliquias
               ↓
Presentation:  UI de combate, VFX, audio
               ↓
Polish:        Tutorial, ascensión
```

### ¿Por qué importa el orden?

**Ejemplo — Carga depende de Combate:**

El GDD de Carga dice "la carta cargada se dispara al inicio del turno siguiente".
Eso implica que el sistema de combate necesita tener un concepto de "turnos" y
"inicio de turno" bien definido. Si no has definido el combate primero, ¿qué
significa "turno siguiente"? ¿Cuándo exactamente se dispara? ¿Antes o después
de robar cartas?

Por eso Combate va en la Capa Core y Carga en la Capa Feature — Carga *necesita*
que Combate ya exista.

**Ejemplo inverso — ¿por qué Audio está en Presentation?**

El audio necesita saber qué está pasando en el juego para sonar: "suena este SFX
cuando una carta con Carga se dispara". Pero el combate funciona perfectamente
en silencio — el audio no es necesario para que las reglas funcionen. Por eso va
después.

---

## Cuellos de botella

Un cuello de botella es un sistema del que **muchos otros dependen**. Si ese
sistema tiene un problema de diseño, arrastra a todos los demás.

**Ejemplo: el sistema de combate es nuestro mayor cuello de botella.**

Dependen de él: Carga, Temple, AI de enemigos, bosses, recompensas, UI de combate,
VFX, audio de combate, tutorial...

Si a mitad de desarrollo decides cambiar el combate de "por turnos" a "tiempo
real", TODOS esos sistemas se rompen y hay que rediseñarlos. Por eso se diseña
primero y con mucho cuidado.

**Contraste: Tutorial no es cuello de botella.**

Nadie depende del tutorial. Si lo cambias, lo borras, o lo rehaces de cero, nada
más se rompe. Por eso va al final.

---

## Prioridades: MVP → Vertical Slice → Alpha → Full Vision

Son **cuándo necesitas cada sistema** dependiendo de lo que quieras demostrar.

### MVP — "¿Esto es divertido?"

Lo mínimo para sentarte, hacer una run, y responder: **¿el loop de combate con
cartas mola?**

En Slay the Spire sería: Un personaje, unas cuantas cartas, unos enemigos, un
mapa básico. Sin reliquias, sin eventos, sin ascensión, sin arte final. Solo
pelear con cartas y ver si es satisfactorio.

**En nuestro juego**: El Guerrero con Carga y Temple, enemigos con AI básica, un
mapa de 2 zonas, recompensas de cartas. Nada más. **Si esto no es divertido,
nada de lo que añadas después lo va a arreglar.**

### Vertical Slice — "¿Esto es un juego completo?"

Una experiencia corta pero **completa**. El jugador ve todo lo que el juego ofrece,
aunque sea poco contenido.

**En nuestro juego**: MVP + un boss con mecánicas, la primera ciudad con un NPC,
una tienda, un evento narrativo, audio y VFX decentes. Un jugador lo prueba y
dice "ah, entiendo qué juego es esto".

### Alpha — "¿Están todas las mecánicas?"

Todas las features implementadas aunque con contenido placeholder. Misiones
secundarias, meta-progresión, momentos narrativos — todo funciona aunque falte
pulir.

### Full Vision — "¿Está listo para lanzar?"

Ascensión, el velo negro completo, tutorial pulido, todo el contenido, todo el
arte, todo el balance.

---

## Esfuerzo de diseño: S / M / L

Estimación de cuánto trabajo de **diseño** (no de programación) necesita cada sistema:

- **S (Small)**: Una conversación. "¿Cómo funciona tu energía? ¿Igual que Slay
  the Spire? Sí? Ok, documento listo." RogueEngine ya lo tiene y solo necesitas
  confirmar o ajustar valores.
- **M (Medium)**: 2-3 conversaciones. Hay decisiones de diseño que tomar, reglas
  que definir, interacciones que pensar. Como los GDDs de Carga y Temple — cada
  uno tomó una sesión de trabajo.
- **L (Large)**: 4+ conversaciones. Sistemas complejos con muchas partes
  interconectadas, o conceptos completamente nuevos como el velo negro o las ciudades.

---

## ¿Por qué el orden de diseño importa tanto?

El orden (combate → cartas → campeones → Carga → Temple) sigue una lógica simple:

1. **Primero lo que más cosas bloquea** — el combate bloquea 9 sistemas
2. **Luego lo que le da identidad a tu juego** — tus keywords son lo que te
   diferencia de StS
3. **Después lo que necesitas para testear** — sin enemigos con AI no puedes
   probar tus keywords

Si diseñaras el velo negro primero (que sería lo más emocionante creativamente),
no tendrías dónde probarlo porque no hay combate, ni mapa, ni campeón definido.

---

## Glosario rápido

| Término | Significado |
|---------|-------------|
| **Sistema** | Pieza del juego con reglas propias (combate, cartas, mapa...) |
| **GDD** | Game Design Document — documento que define un sistema al detalle |
| **Keyword** | Mecánica con nombre propio que aparece en cartas (Carga, Temple) |
| **Core loop** | Lo que el jugador hace una y otra vez (jugar cartas → ganar → elegir recompensa → siguiente nodo) |
| **Meta-progresión** | Lo que persiste entre runs (desbloqueos, campeones nuevos) |
| **Cuello de botella** | Sistema del que muchos otros dependen — diseñar con cuidado |
| **Dependencia** | "A depende de B" = A no puede funcionar sin que B exista |
| **Data-driven** | Valores de gameplay definidos en archivos de datos, no en código |
| **ScriptableObject** | Tipo de asset de Unity para almacenar datos de diseño (cartas, efectos, enemigos) |
| **Vertical Slice** | Demo corta pero completa que muestra toda la experiencia del juego |
| **MVP** | Minimum Viable Product — lo mínimo para probar si la idea es divertida |
| **Placeholder** | Contenido temporal (arte gris, sonido genérico) que se reemplazará después |
| **Run** | Una partida completa — desde el piso 1 hasta morir o ganar |
| **Build** | La combinación de cartas y reliquias que define tu estrategia en una run |
| **Sinergia** | Cuando dos cosas juntas son más fuertes que por separado (Carga + Temple) |
| **Juice** | Los efectos visuales y sonoros que hacen que las acciones se sientan satisfactorias |
| **Scope creep** | Cuando el proyecto crece sin control — "y si añadimos esto también..." |


