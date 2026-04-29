---
type: decision
status: active
tags: [producto, decisiones, mutacion, alma]
updated: 2026-04-24
---

# Sesión 2026-04-24 — Criterios de Mutación y Alma

## Propósito

Registrar los criterios acordados durante la revisión post-reorganización de:

- [[12_Mecánicas Centrales]]
- [[13_Mutación y Fusión]]
- [[14_Vocabulario y Nomenclatura]]

Esta nota no cierra el tuning ni el diseño final. Fija el marco de trabajo actual.

---

## 1. Tipos de carta — lectura provisional

La lectura provisional del sistema queda así:

- **Ataque** = daño directo.
- **Defensa** = bloqueo / respuesta defensiva.
- **Arte** = utilidad / técnica / manipulación no ofensiva ni defensiva directa.
- **Don** = persistencia tipo `Power` de *Slay the Spire*; poder externo, generalmente ajeno a la mecánica principal de clase.
- **Alma** = carta especial de clase; máxima expresión de una línea mecánica o fantasía de clase.

### Criterio provisional de clasificación

- Cada carta debe tener **un tipo principal**.
- Regla provisional para prototipado: el tipo lo define **lo primero que hace la carta**.
- Esta regla queda pendiente de testeo; si resulta arbitraria deberá sustituirse por una regla de **función dominante**.

---

## 2. Mutación — rol actual

### Función del sistema

- **Mutación** es una **capa secundaria de run**.
- Debe hacer que cada run sea un poco distinta y obligue a adaptarse.
- No debe sentirse como un sistema pegado ni como adorno.

### Frecuencia y peso

- Debe aparecer de forma **regular**, pero no constante.
- No debe dominar el combate ni la recompensa de cada nodo.
- Su valor está en pequeñas adaptaciones tácticas, no en redefinir la carta entera.

### Fuente principal de obtención

- La fuente base correcta es **recompensa de combate**.
- Debe llegar como **opción elegible entre recompensas**, no como subsistema aparte.
- Queda pendiente de testeo si debe ser:
  - asegurada con frecuencia controlada,
  - o frecuente pero no asegurada.

### Regla de identidad

- La mutación **no cambia la identidad funcional** de la carta.
- La capa que podría cambiar identidad funcional, si sobrevive, es **Fusión**.

---

## 3. Afinidad de mutación por tipo de carta

### Ataque

- Afinidad alta a mutaciones comunes.
- Las mutaciones aquí dan valor más directo e inmediato.

### Defensa

- Afinidad alta a mutaciones comunes.
- Las mutaciones aquí también deben tener lectura directa, pero sin convertir la carta en ataque.

### Arte

- Afinidad baja, pero no nula.
- Deben existir mutaciones menores y algunas de alto potencial.
- Su payoff ideal es más de utilidad/valor y más orientado a mid/late.

### Don

- Potencial parecido a **Arte**, pero con familias propias que lo diferencien.
- No debe sentirse como un Arte persistente sin más.

### Regla general

- Las mutaciones **incompatibles no deben salir** sobre una carta.
- El sistema debe permitir valorar en draft si conviene coger una carta con mejor afinidad de mutación aunque su efecto base no sea el mejor inmediato.

---

## 4. Curva de valor por tipo

- **Ataque / Defensa** = crecimiento más plano; empiezan fuertes y dan valor temprano más directo.
- **Arte / Don** = menor impacto inmediato, pero mayor potencial de escalado o valor compuesto.

Este contraste debe existir sin hacer que:

- Ataque/Defensa sean siempre la opción correcta.
- Arte/Don sean la opción “interesante pero peor”.

Queda pendiente de testeo.

---

## 5. Mutaciones humanas

- Las **partes humanas** siguen siendo **mutaciones**, no cartas.
- Son mutaciones raras y estructurales.
- Pueden actuar con reglas más amplias que las mutaciones comunes.

---

## 6. Fusión — rol actual

- **Fusión** sigue viva como idea.
- Su rol previsto es:
  - rara,
  - de mucho peso,
  - capaz de cambiar identidad funcional de la carta.
- A día de hoy sigue sin validación suficiente y no debe tratarse como sistema cerrado.

---

## 7. Sistema Alma — redefinición provisional

### Rol

- **Alma** es una capa **minimalista pero de alto potencial**.
- Representa la **máxima expresión de la clase**.
- No es imprescindible para ganar.
- Interactúa poco con otras clases; su identidad es muy propia.

### Qué habilita

- Puede ser la **culminación de una mecánica ya presente**.
- O la **culminación de una fantasía exclusiva de clase**.

### Perfil jugable

- Una carta Alma no debe matar sola.
- Debe ser una carta que, combinada con el resto del mazo adecuado, tenga **el mayor techo potencial**.
- Debe sentirse especial pronto en tutorial, sin meter seguimiento pesado.

### Distinción con Don

- **Alma** = poder interno; maestría o culminación de una línea de clase.
- **Don** = poder externo; concesión de un dios o entidad superior, generalmente ajena a la mecánica principal.

---

## 8. Alma como transformación

### Regla provisional

- El **tipo de carta** sigue siendo **Alma**.
- El **resultado** al jugarla es una **transformación** o **forma** concreta del personaje.
- La fantasía visible vive en el **nombre de la carta**, no en el tipo.

Ejemplo de estructura:

- Tipo: `Alma`
- Nombre: una forma o aspecto concreto del personaje

### Restricción importante

- Solo debe haber **una forma Alma activa a la vez**.
- Si entra una nueva, sustituye a la anterior.

Esto se considera necesario para:

- mantener legibilidad,
- evitar apilar demasiadas capas,
- y diferenciar Alma de Don.

---

## 9. Duda principal abierta del Guerrero

El sistema antiguo de `Arma de Alma + Huevo de Alma` ha quedado cuestionado.

Dirección provisional más sana:

- `Alma` no debe tratarse como un subsistema grande con demasiadas reglas propias.
- Debe entenderse primero como:
  - una carta especial de clase,
  - de bajo volumen,
  - alto potencial,
  - y con resultado de transformación o forma.

Queda pendiente decidir qué implementación concreta toma en el Guerrero.

---

## 10. Estado de estas decisiones

- **Marco útil para diseño y auditoría:** sí.
- **Diseño final cerrado:** no.
- **Tuning y viabilidad jugable:** pendiente de prototipo y testeo.

