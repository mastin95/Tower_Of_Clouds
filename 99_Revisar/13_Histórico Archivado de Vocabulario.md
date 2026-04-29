---
type: review
status: archived
tags: [revisar, historico, vocabulario]
updated: 2026-04-24
---

# Histórico Archivado de Vocabulario

> Extraído desde [[14_Vocabulario y Nomenclatura]] para dejar la nota viva centrada en naming y tensiones activas.
> Este contenido se conserva como memoria del proceso, no como diseño vigente.

### 10.4 Flecha del tiempo — ¿regresión o progresión?

**Problema:** El lore habla de "regresión del alma" (volver al pasado), pero la estructura del juego va prehistoria → futuro (progresión cronológica).

**Resolución actual:** "Regresión" se interpreta como "retorno / regresar" (no como "ir al revés"). El alma RETORNA al pasado (acto 1 = prehistoria), y luego evoluciona HACIA ADELANTE rememorando vidas. Compatible con prehistoria → futuro.

**Estado:** Resuelto narrativamente. Posible confusión semántica si no se enmarca bien en tutorial / lore drops.

### 10.5 Dónde termina cronológicamente el viaje

**Problema:** Si el Guerrero viene de una era medieval-ish (su tribu) y el juego lo lleva prehistoria → futuro, ¿hasta dónde llega? ¿Su propia era? ¿Un futuro post-humano?

**Estado:** Pendiente decisión de climax narrativo.


### 10.8 Aleatoriedad de eras en Ciclo 2 (2026-04-19)

**Problema:** en Ciclo 2 (caos), el orden cronológico de eras es fijo (prehistoria → intermedia → moderna). ¿Hay aleatoriedad dentro de cada rango de era, o las eras concretas son las mismas que Ciclo 1?

**Opciones en §4.5:**
- **A — Repetición estricta:** Ciclo 2 usa las mismas eras concretas que Ciclo 1. Rejugabilidad solo por mezcla de enemigos y pool unificado.
- **B — Aleatoriedad dentro del rango:** la era concreta se elige aleatoriamente entre las opciones del rango (más eras posibles en el juego = más rejugabilidad).
- **C — A/B test post-launch:** portal con elección, reservado.

**Depende de:** cuántas eras concretas haya en el juego y si se justifica diseñar contenido de eras no vistas en Ciclo 1.

**Estado:** Pospuesto hasta fijar el catálogo de eras concretas.

---


## 11.1 Preguntas archivadas ligadas al marco temporal antiguo

| # | Pregunta | Contexto | Dependencias |
|---|----------|----------|--------------|
| 2 | **Identidad narrativa del boss-agente-temporal** (§4.6.1) — nombre, aspecto, voz, conexión con entidad recurrente y velo negro | §4.6.1 / §4.6 | Afecta al clímax del Ciclo 1 y al lore de la Torre |
| 3 | **Naturaleza de los alter egos temporales del Guerrero** — ¿misma alma en distintas vidas? ¿ancestros biológicos? ¿ambos? | §4.11.1 | Afecta al lore del alma y a la ficción del pool de cartas de era |
| 4 | **Eras concretas del Ciclo 1** — qué eras específicas se presentan (prehistoria + cuáles intermedias + cuáles modernas) | §4.2 / §4.5 | Afecta al contenido inicial y al arte |
| 5 | **Diversidad de eras — qué opción** (A reliquias, D evolución condicionada, combinación, otra) | §7 | Decisión de sistema |
| 8 | **Aleatoriedad de eras en Ciclo 2** (A repetición / B aleatoriedad dentro del rango / C portal) | §4.5 / §10.8 | Afecta a rejugabilidad |
| 9 | **Qué pasa si el jugador muere en Ciclo 1** (A reinicio / B checkpoint / C inmortalidad narrativa / D dificultad baja) | §4.13.6 | UX de tutorial |
| 10 | **UX de transición Ciclo 1 → Ciclo 2** — cómo se comunica al jugador el cambio de modo | §4.13.4 | UX / feedback |
| 11 | **Número de actos por ciclo** (3 vs 3-4 vs más) | §4.2 / §4.13.2 | Afecta a duración de runs |
| 14 | **Tag/ícono de era visible en la carta** (sí o no) | §4.8 | Decisión de arte/UI |
| 15 | **Era final cronológica del viaje del Guerrero** | §10.5 | Afecta al climax narrativo |
| 18 | **Interacción simple pero efectiva/divertida de las cartas de era** — qué estructura toma (keyword única + estado / trigger contextual / huella temporal / sinergia intra-era) | §4.7 y conversación 2026-04-19 | Afecta al flavour mecánico de cada era |

### 2026-04-18 — Sesión de brainstorm: stand, eras y Paradoja

**Contexto:** cierre de los sistemas grandes pendientes — stand (mecánica firma), sistema de eras (marco narrativo-mecánico), y Paradoja (keyword especial).

**Decisiones cerradas:**

**Stand / digihuevo (terminología provisional):**
1. Forma inicial = **huevo con arte propio atemporal** (NO es "huevo prehistórico")
2. Evoluciona en **3 formas**: huevo → forma media → forma final
3. Evolución ocurre **en transiciones de acto** (1→2 y 2→3), NO cada piso
4. Forma 2 y 3 adoptan la estética de la era del acto donde evolucionan
5. Stand tiene 3 cartas Alma iniciales con **subtipos internos invisibles** (Alma-Arma, Alma-Escudo, Alma-Arte)
6. Las cartas Alma evolucionan con el stand: 3 opciones por carta en cada evolución, el jugador elige 1
7. **Cartas Alma muestran SOLO al stand, no al Guerrero** (simplificación de arte y refuerzo visual)
8. Pool de Alma se puede expandir con reliquias, pero siempre manteniendo balance 1 Arma/1 Escudo/1 Arte

**Sistema de eras:**
9. Acto 1 **SIEMPRE prehistoria** (fijo)
10. Actos 2 y 3 con era **100% aleatoria** (filosofía Slay the Spire — anticipación y sorpresa)
11. Flecha del tiempo: **prehistoria → futuro** (siempre cronológico adelante)
12. **Portales interdimensionales** al vencer al boss — la Torre expulsa al Guerrero hacia adelante por inercia
13. Boss de cada acto = **manifestación de la era** (o reinterpretación de entidad recurrente)
14. **Arte único por carta, ~20 cartas por era, ~100-120 cartas totales en el juego base** (asumido como coste de producción)
15. **Trofeos = reliquias** (separadas de las cartas — resuelve el framing "One Piece de los amigos")
16. **Convergencias DESCARTADAS** (eran familia de cartas raras por diversidad de eras — redundantes con Paradoja)

**Paradoja — keyword definitivo y mecánica:**
17. Palabra elegida: **Paradoja** (sobre otras opciones como Memoria, Anacronía, Eco, etc.)
18. Paradoja es un **ESTADO aplicable a cartas** del mazo
19. Cuando una carta queda paradojada, su efecto se reemplaza por una **forma paradoja pre-diseñada por el diseñador** (inversión narrativa, no matemática)
20. **Todas las cartas son paradojables por defecto** EXCEPTO las cartas Alma
21. **Coste de diseño asumido**: 100-120 cartas × 2 efectos = 200-240 efectos totales
22. Adquisición por **2 canales**:
    - **Canal 1 — Eventos pasivos (común):** el jugador elige 1 de 3 cartas aleatorias de su mazo (idealmente una de cada rareza). Paradojada = **PERMANENTE** para el resto del run.
    - **Canal 2 — Eventos raros con cartas activas:** el jugador elige 1 de 3 cartas que USAN Paradoja activamente. Dos familias: Aplicadoras (paradojan durante combate, efecto **TEMPORAL**) y Amplificadoras (interactúan con cartas ya paradojadas).
23. **Distinción clave de permanencia**: eventos pasivos = permanente en run; cartas activas/poderes = solo el combate

**Descartado explícitamente:**
24. Paradoja dependiente de diversidad de eras (condicionaba cartas tempranas)
25. Paradoja como efecto automático sin elección (Opción A original)
26. Paradojar como acción activa obligatoria del jugador
27. Cartas ya paradojadas en el pool normal (diluiría la pool)
28. Modificación temporal por combate como modelo principal (los eventos pasivos son permanentes)
29. Inversión algorítmica automática de efectos (ambiguo, ej: ¿qué es el opuesto de veneno?)

**Principios y convenciones emergentes:**
30. Las cartas son **acciones del personaje** — el arte muestra lo que hace
31. El Guerrero aparece vestido/equipado según la era
32. Mismo color base de borde en todas las cartas normales, diseño distinto por era
33. Cartas Alma con borde especial (nunca muestra al Guerrero)
34. Cartas paradojadas con marcador visual específico (diseño pendiente)

**Próximas decisiones pendientes (al cierre de la sesión):**
- Nombre del stand/criatura
- Qué hace el stand en combate entre cartas Alma (pasivo mínimo?)
- Diversidad de eras — qué opción (A, D, combinación, otra)
- Resolver tensión ecos de alma → ecos de Anima
- Boss final — recurrente vs independiente

---


