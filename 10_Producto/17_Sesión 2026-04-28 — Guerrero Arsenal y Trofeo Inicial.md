---
type: decision
status: active
tags: [producto, decisiones, guerrero, arsenal, trofeos]
updated: 2026-04-29
---

# Sesión 2026-04-28 — Guerrero Arsenal y Trofeo Inicial

## Propósito

Registrar la dirección aprobada provisionalmente para el núcleo inicial del
Guerrero como usuario de arsenal tribal y fijar el primer trofeo para testeo.

---

## 1. Dirección del Guerrero

El Guerrero se orienta hacia una fantasía de:

> **Guerrero de arsenal tribal que destaca por variedad de armas.**

La intención no es que entre en posturas ni que cada carta explique un cambio de
arma. Las cartas deben seguir siendo independientes y limpias.

Principios acordados:

- El Guerrero debe destacar sobre otros campeones por usar muchas armas.
- Algunos Ataques pueden tener **Arma** como parte de su identidad visual.
- Otros campeones podrán tener armas propias, pero con mucha menor variedad.
- Las Armas deben servir como lenguaje reconocible del Guerrero.
- La diversidad de armas debe importar, pero sin convertir cada ataque en una
  keyword repetida.

### Actualización 2026-04-29 — término Arma

La expresión anterior `icono de arma` queda sustituida por **Arma**.

Regla vigente:

- Arma es el símbolo visible de algunos Ataques.
- Arma no es un tipo de carta.
- Arma no tiene efecto inherente.
- Los Ataques básicos no tienen Arma.
- Defensa, Arte, Don y Alma no tienen Arma.
- Solo importa cuando una carta, trofeo o reliquia la referencia.
- **?** es Arma anómala: herramienta de origen desconocido.

## 2. Problemas descartados

### Cartas dedicadas a cambiar de arma

Descartado como base.

Motivo:

- genera cartas de preparación potencialmente muertas;
- puede sentirse como impuesto antes de jugar;
- complica el orden de robo sin aportar suficiente claridad.

### Posturas de arma

Descartado como base.

Motivo:

- demasiadas posturas si el Guerrero usa muchas armas;
- desplaza el foco desde cartas independientes hacia gestión de estado;
- puede solaparse demasiado con el modelo de estancias de otros deckbuilders.

### Secuencias largas

Descartado como base.

Motivo:

- exige patrones concretos;
- reduce independencia de las cartas;
- puede hacer que el mazo se sienta como puzzle de orden fijo.

### Reliquia inicial que genera Cadencia

Descartado como primera solución.

Motivo:

- una reliquia inicial no debe crear directamente un recurso central;
- Cadencia, si existe, deberá decidirse después como keyword o sistema propio;
- el trofeo inicial debe ser una ayuda de early, no el motor completo del
  personaje.

## 3. Trofeo inicial aprobado para testeo

### Trofeo de Prueba

**Rol:** trofeo inicial del Guerrero.

**Función:** dar una ventaja pequeña en early y enseñar que variar armas importa.

**Regla provisional:**

```text
La primera vez cada combate que juegas un Ataque con Arma distinta
al primer Ataque con Arma que jugaste este combate, ese Ataque inflige +2 daño.
```

Lectura:

- El primer Ataque con Arma del combate fija el arma de referencia.
- El primer Ataque posterior con otra Arma activa el trofeo.
- Los Ataques sin Arma no fijan referencia ni activan el trofeo.
- El trofeo solo se activa una vez por combate.
- No genera Cadencia.
- No necesita líneas adicionales en las cartas.

Ejemplo:

```text
1. Juegas Ataque de Espada.
2. Juegas otro Ataque de Espada. No activa el trofeo.
3. Juegas Ataque de Lanza. Activa el trofeo: +2 daño.
4. El trofeo no vuelve a activarse este combate.
```

## 4. Razón de diseño

Este trofeo encaja mejor como reliquia inicial que las versiones que cuentan
varias Armas dentro del mismo turno, porque:

- funciona con solo dos armas iniciales;
- no depende de robo ni de una mano grande;
- recompensa pasar al ataque;
- enseña el valor de las Armas desde el primer combate;
- tiene un techo bajo, apropiado para early;
- puede quedarse corta en mid/late sin ser un problema.

El valor `+2 daño` queda provisional. Si durante testeo el trofeo se siente
demasiado flojo, puede subirse.

## 5. Pendientes

- Decidir si Cadencia existirá como keyword de cartas, como regla global o si se
  pospone.
- Definir cuántas Armas tendrá el Guerrero en el primer paquete de cartas.
- Decidir qué armas pertenecen al kit base y cuáles son desbloqueos posteriores.

## 6. Armas iniciales

Decisión provisional para testeo:

> El Guerrero empieza con **Espada + Arco** como sus dos Armas iniciales.

Razón:

- la Espada comunica el arma tribal directa, cuerpo a cuerpo y de prueba;
- el Arco introduce desde el inicio una contraposición clara dentro del mismo
  personaje: melee + distancia;
- la pareja muestra que el Guerrero no es solo espadachín, sino alguien ducho en
  armas en general;
- el Trofeo de Prueba puede activarse desde el primer combate con solo dos armas;
- visualmente ayuda a vender la fantasía de arsenal sin necesitar muchas armas
  desde el tutorial.

Pendiente:

- decidir si el Escudo sigue siendo parte del kit inicial defensivo o entra como
  carta defensiva posterior;
- definir cómo se representa el Arco dentro de la UI y en la silueta del Guerrero.

## 7. Cartas iniciales de arma

Decisión provisional para primer test:

El Guerrero empieza con dos cartas especiales de arma:

- **Corte Compuesto** — Espada
- **Disparo Acertado** — Arco

Estas cartas existen para:

- enseñar desde el inicio que las Armas importan;
- activar el Trofeo de Prueba de forma natural;
- comunicar que el Guerrero no es solo espadachín, sino usuario de arsenal;
- introducir la pareja conceptual melee + distancia.

### Corte Compuesto

**Tipo:** Ataque  
**Arma:** Espada  
**Coste:** 1  
**Efecto provisional:**

```text
Inflige 4 daño.
Roba 1 carta aleatoria de tu mazo de robo con Arma distinta.
```

Reglas provisionales:

- Si no hay carta válida en el mazo de robo, no roba.
- No busca en descarte, exhaust ni en toda la baraja.
- El valor `4 daño` queda abierto a testeo; rango considerado: 3-4.

Lectura de diseño:

- La Espada no es solo daño; funciona como enlace hacia otra arma.
- La carta representa una técnica compuesta, pensada para continuar el flujo de
  combate con otra herramienta del arsenal.
- En early debería tender a encontrar el Arco si está en el mazo de robo, ayudando
  al jugador a entender las Armas sin tutorial verbal.

Arte:

- Close-up del filo ejecutando un corte limpio sobre una extremidad o zona
  vulnerable del enemigo.
- Evitar gore gratuito; el foco es la precisión del corte, no la crudeza.
- La estela del filo o la postura del Guerrero debe sugerir continuidad hacia
  otra arma, no un golpe final.
- El arma secundaria puede insinuarse en la composición, por ejemplo el arco en
  la espalda o la mano libre preparándose.

### Disparo Acertado

**Tipo:** Ataque  
**Arma:** Arco  
**Coste:** 1  
**Efecto provisional:**

```text
Inflige 4 daño.
Roba 1 carta.
```

Lectura de diseño:

- El Arco representa precisión, lectura del enemigo y preparación.
- El robo expresa la concentración necesaria para detectar una apertura anímica
  o punto vulnerable.
- Debe sentirse como una acción deliberada que abre continuidad, no como daño
  bruto.

Arte:

- El Guerrero aparece concentrado, leyendo el alma o el punto vulnerable del
  enemigo antes de soltar la flecha.
- La diana no debe ser caricaturesca; mejor una marca de vulnerabilidad, grieta,
  círculo de Anima o centro vital detectado.
- La flecha impacta con precisión en el centro de esa lectura.
- El tono visual debe comunicar calma, distancia y exactitud.

## 8. Advertencias de testeo

- **Corte Compuesto** puede ser fuerte si el mazo inicial tiene pocas cartas con
  Arma y encuentra el Arco con demasiada consistencia.
- **Disparo Acertado** puede ser fuerte para una carta inicial si el robo acelera
  demasiado el mazo.
- El Trofeo de Prueba puede convertir la curva Espada -> Arco en demasiado valor
  early; revisar daño total efectivo.
- Si el paquete se siente demasiado consistente, primer ajuste sugerido:
  bajar Corte Compuesto a 3 daño antes de tocar la regla.
