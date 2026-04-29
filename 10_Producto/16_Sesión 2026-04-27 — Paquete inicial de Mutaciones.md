---
type: decision
status: active
tags: [producto, decisiones, mutacion, guerrero]
updated: 2026-04-27
---

# Sesión 2026-04-27 — Paquete inicial de Mutaciones

## Propósito

Registrar el estado de cierre de la sesión sobre mutaciones y dejar el punto de
arranque de la próxima sesión.

---

## 1. Marco cerrado para testeo

La estructura provisional de mutaciones queda:

```text
Mutación = Familia + Linaje + Estrato + Grado
```

Regla central:

> Las cartas son identidad de clase. Las mutaciones son material de la Torre.
> Cada clase expresa ese material según su relación con el alma.

Implicación:

- una mutación amplía la expresividad de una carta dentro de su tipo funcional
- no debe convertir un Ataque en Arte, una Defensa en Ataque, etc.
- las excepciones podrán existir, pero deben ser deliberadas y especiales

---

## 2. Paquete activo de mutaciones para primer test

### Elemental

| Linaje | Menor | Mayor |
|---|---|---|
| Fuego / Quemadura | 2 stacks | 4 stacks |
| Agua / Empapado | 2 stacks | 4 stacks |
| Tierra / Agrietado | 2 stacks | 4 stacks |

### Fauna

| Linaje | Compatibilidad | Menor | Mayor |
|---|---|---|---|
| Colmillo | Ataques | +2 daño y 1 Sangrado | +4 daño y 2 Sangrado |
| Garra | Ataques | +1 daño; próximo Ataque este turno +1 daño | +2 daño; próximos 2 Ataques este turno +1 daño |
| Escama | Defensas | +3 Bloqueo | +6 Bloqueo |
| Tendón | Ataques / Defensas | próxima carta Ataque o Defensa cuesta 1 menos | próximas 2 cartas Ataque o Defensa cuestan 1 menos |

Alternativa guardada para Garra:

- si ya jugaste un Ataque este turno, esta carta inflige +3 / +6 daño

### Humanoide

| Linaje | Compatibilidad | Menor | Mayor |
|---|---|---|---|
| Mano | Artes / Dones / Defensas | roba 1 | roba 2 |
| Ojo | Artes / Dones | mira 1 carta superior; puedes descartarla | mira 2 cartas superiores; puedes descartar 1 |
| Pie | Artes / Defensas | la siguiente carta este turno otorga +2 Bloqueo | la siguiente carta este turno otorga +4 Bloqueo |
| Corazón | Dones / Defensas / Artes raras | cura 5 HP | cura 7 HP |

### Micónica / Vegetal

| Linaje | Compatibilidad | Menor | Mayor |
|---|---|---|---|
| Raíz | Defensas / Dones defensivos | +2 Bloqueo; conserva 2 Bloqueo al final del turno | +4 Bloqueo; conserva 4 Bloqueo al final del turno |
| Savia | Dones / Defensas / Artes raras | al inicio del próximo turno, cura 2 HP | al inicio del próximo turno, cura 4 HP |

### Anómala

Pospuesta fuera del primer paquete activo de testeo.

---

## 3. Fauna provisional del Estrato Primitivo

| Enemigo | Rol | Mutación asociada |
|---|---|---|
| Rascaraíz | DPS / remate | Colmillo |
| Zarpador Ciego | DPS / multi-hit | Garra |
| Corazacanto | Tank / placas | Escama |
| Sanguijuela de Anima | Disruptor / parásito | Tendón / Garra |

---

## 4. Guerrero — Punto donde se pausó

El Guerrero se está orientando hacia:

> Guerrero de arsenal tribal.

Notas activas:

- joven de unos 18 años de referencia, alto, fornido, extremidades largas
- estética corporal tipo JoJo en proporción / presencia
- base de espada y escudo, pero domina varias armas
- referencia funcional: arsenal tipo Firion de Final Fantasy II
- optimista, responsable, empático y cuidadoso
- su deber es traer honor y riqueza a su familia y pueblo
- al combatir entra en concentración extrema
- puede responder con precisión y contraatacar incluso a distancia
- el alma se manifiesta como aura contenida sobre la piel, más cercana al haki del manga de One Piece que a una aura estilo Dragon Ball

Punto no cerrado:

- todavía no se decidió keyword principal del Guerrero
- se propuso explorar algún tipo de contraataque, pero no se cerró
- el núcleo confirmado es más **arsenal tribal** que tanque defensivo

---

## 5. Próxima sesión recomendada

Objetivo:

> Definir la fantasía mecánica concreta del Guerrero antes de diseñar cartas.

Preguntas a resolver:

1. Qué significa exactamente "arsenal tribal" en gameplay.
2. Qué ramas de cartas tiene el Guerrero: espada, escudo, lanza, hacha, puño, etc.
3. Si existe una keyword de contraataque, cómo se llama y qué hace.
4. Cómo sus cartas dejan espacio para mutaciones sin depender de ellas.
5. Qué keywords propias necesita el Guerrero antes de crear el mini-pool de cartas.

