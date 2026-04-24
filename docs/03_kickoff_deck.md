# Hackathon de Testing · Account Plan ABE v9 — Deck (contenido)

**Formato:** contenido slide-by-slide para armar en tu propio sistema de diseño.
**Total de slides:** 14.
**Duración sugerida del kickoff:** 5–8 min (pasar todo en ~30 seg por slide).
**Idioma:** español rioplatense, tono directo.

Cada slide tiene título, subtítulo, cuerpo y notas del presentador. El cuerpo está estructurado para que sea fácil de parsear — listas, tablas, y bloques con etiquetas claras.

**Paleta de referencia** (la del prototipo, opcional):
`navy #1A1A2E` · `deep-navy #16213E` · `accent-blue #0066CC` · `green #1D9E75` · `amber #BA7517` · `red #C0392B` · `light-bg #F5F5F7` · `dark-text #1D1D1F` · `muted #6E6E73`

**Motivo visual recomendado:** chip numerado de slide arriba-derecha, barra vertical de acento izquierda en covers, cards con color de estado para niveles (GO/CONDICIONAL/NO-GO, severidades).

---

## Slide 1 · Cover

**Layout:** dark cover full-bleed · título grande · 3 cards framing questions en el pie.

**Kicker (eyebrow):** HACKATHON DE TESTING
**Título principal:** Account Plan ABE · v9
**Subtítulo:** 1h 15min · 1 squad = 1 equipo · Responsable de GTM Engineering aplicando fixes en vivo

**Cards (3, en pie de slide):**

| Pregunta | Respuesta |
|---|---|
| ¿Funciona? | Se puede completar un plan sin romper nada |
| ¿Sirve? | Resuelve preguntas del día a día del squad |
| ¿Se entiende? | Un rol nuevo lo usa sin tutorial |

**Notas del presentador:**
En 75 minutos, con cuentas reales, vamos a responder estas tres preguntas. Al cierre, decidimos si el prototipo sale a producción piloto o qué le falta resolver primero.

---

## Slide 2 · Por qué estamos acá

**Layout:** texto intro + 3 cards horizontales apilados con color de estado.

**Número de slide:** 01
**Título:** Por qué estamos acá

**Intro:**
El prototipo del Plan de Cuenta ABE está listo para revisión. En los próximos 75 minutos vamos a decidir si va a producción piloto o qué le falta resolver primero.

**Subtítulo pre-cards:** Al cierre, votamos entre 3 resultados.

**Cards (3, con barra de color lateral):**

| Color | Tag | Descripción |
|---|---|---|
| 🟢 verde | ✅ GO LIVE | Todos los squads votan GO. Arranca piloto con 2–3 cuentas reales. |
| 🟡 ámbar | 🟡 GO CONDICIONAL | Mayoría GO pero queda backlog P0 con dueño y fecha. Una vez resuelto, habilita piloto. |
| 🔴 rojo | 🔴 NO-GO | Mayoría NO-GO o >3 bloqueadores abiertos. Vuelve a iteración. Nuevo hackathon en 2 semanas. |

**Notas del presentador:**
No es "aprobemos y salimos". Es "decidimos juntos con evidencia". La diferencia entre GO CONDICIONAL y NO-GO es si el backlog P0 se puede cerrar en días o requiere iteración estructural.

---

## Slide 3 · Agenda · 75 minutos

**Layout:** tabla/timeline vertical · filas con número en badge + nombre + duración + descripción · pitstops diferenciados visualmente (fondo ámbar claro + ícono llave).

**Número de slide:** 02
**Título:** Agenda · 75 minutos
**Subtítulo:** 4 bloques de testing + 3 pitstops donde el responsable de GTM Engineering aplica fixes en vivo

**Timeline:**

| # | Bloque | Duración | Descripción |
|---|---|---|---|
| 0 | Kickoff | 5 min | Contexto, reglas, presentación de equipos |
| 1 | Smoke Test común | 8 min | 6 steps básicos · calibra severidad entre equipos |
| 🔧 | **Pitstop 1** | 4 min | Responsable de GTM Engineering recibe Batch 1 y arranca fixes |
| 2 | Script · Primera mitad | 18 min | Secciones 01–05 · Ficha, Squad, Contexto, Métricas, Nómina |
| 🔧 | **Pitstop 2** | 5 min | Fixes del Batch 1 listos · se entrega Batch 2 |
| 3 | Script · Segunda mitad + Retest | 20 min | Secciones 06–11 + retest de fixes del Batch 1 |
| 🔧 | **Pitstop 3** | 3 min | Último batch · scriba cierra planilla |
| 4 | Cierre · GO/NO-GO | 12 min | Votación con rúbrica · consolidación del backlog P0/P1/P2 |

**Notas del presentador:**
Los pitstops son sagrados. Sin pitstop, el responsable de GTM Engineering no arregla nada en vivo. La duración parece ajustada pero es real: lo calibramos para que no corra nadie.

---

## Slide 4 · Los equipos · 1 squad = 1 equipo

**Layout:** 2 columnas · izquierda con fondo light (Cómo funciona) · derecha con fondo dark (Por qué así).

**Número de slide:** 03
**Título:** Los equipos · 1 squad = 1 equipo
**Subtítulo:** Cada squad testea con SU cuenta real · sin personas artificiales · sin casos ficticios

**Columna izquierda · "Cómo funciona" (lista):**
- 2–4 personas por squad · idealmente con el AD presente
- El squad elige UNA cuenta propia, la más representativa
- Todos tocan el prototipo · el squad decide internamente quién carga y quién toma notas
- Se usa el script común · lo que cambia son los datos reales de cada cuenta

**Columna derecha · "Por qué así" (3 bloques con subtítulo + descripción):**

| Subtítulo | Descripción |
|---|---|
| Hallazgos complementarios sin diseñarlo | Una cuenta Mature estresa la Nómina. Una Customer estresa la Ficha. Una Strategic estresa Expansión. Se cubre todo el prototipo naturalmente. |
| Hallazgos reales | No son bugs de "¿y si alguien cargara 200 Acidians?". Son los problemas que van a aparecer el lunes, con tus datos. |
| Expertise en la sala | Cada squad conoce su cuenta como nadie. Detecta ausencias y redundancias que alguien de afuera no vería. |

**Notas del presentador:**
La división por squads no es aleatoria. Es la forma más rápida de cubrir todo el prototipo sin duplicar esfuerzo. Cada cuenta estresa partes diferentes del sistema.

---

## Slide 5 · El responsable de GTM Engineering en vivo

**Layout:** 5 pasos del flujo en horizontal (bloques alternando colores) + 2 columnas abajo (Sí hace / No hace).

**Número de slide:** 04
**Título:** El responsable de GTM Engineering en vivo · la novedad de este hackathon
**Subtítulo:** Mini ciclo de iteración comprimido en 75 min: testear → reportar → arreglar → retestear → decidir

**Flujo horizontal (5 bloques):**
1. Equipos testean *(color: azul light)*
2. Pitstop → *(color: ámbar light)*
3. Responsable de GTM Engineering arregla *(color: verde light)*
4. Pitstop → *(color: ámbar light)*
5. Retest *(color: azul light)*

**Dos columnas en mitad inferior:**

**✓ Qué SÍ hace** *(card con borde verde):*
- Recibe batches en los 3 pitstops (no lee hallazgos sueltos durante bloques)
- Prioriza bloqueadores y mayores con fix corto y acotado
- Aplica fixes en paralelo mientras los equipos siguen testeando
- Avisa al facilitador cuando un fix está listo para retestear

**✗ Qué NO hace** *(card con borde rojo):*
- No testea · no participa en los equipos
- No se defiende · si preguntan "¿por qué está así?", el facilitador corta
- No ataca reestructuraciones grandes (persistencia, integración Looker) — eso queda como P0 post-hackathon
- No improvisa fuera de los batches asignados

**Notas del presentador:**
Esta es la diferencia clave de este hackathon. La regla de oro es: el responsable de GTM Engineering ataca primero bloqueadores con fix corto y acotado. Nada de refactorear en vivo.

---

## Slide 6 · Principios del testing

**Layout:** grid 2×3 · cards con barra vertical azul a la izquierda · título bold + descripción muted/italic.

**Número de slide:** 05
**Título:** Principios del testing

**6 principios (2 columnas × 3 filas):**

| # | Principio | Descripción |
|---|---|---|
| 1 | Usen el prototipo como lo usarían el lunes a las 9am. | No es QA manual exhaustivo. Es testing de uso real con datos reales. |
| 2 | Si algo les hace fruncir el ceño, anótenlo. | La fricción es un hallazgo válido aunque nada esté "roto". |
| 3 | Un hallazgo = una fila. | Síntoma observable + sección + severidad. Sin ensayo literario. |
| 4 | Prohibido decir "quedaría lindo si…" | …sin decir qué problema concreto resuelve. |
| 5 | No discutir soluciones durante testing. | Solo capturar. El diseño viene después con el responsable de GTM Engineering y el facilitador. |
| 6 | Hallazgo repetido = señal fuerte. | Si dos squads reportan lo mismo, no es ruido — es prioridad. |

**Notas del presentador:**
El principio 5 es el más difícil de respetar. Cuando alguien encuentra algo, la tentación es debatir cómo arreglarlo. Córtenlo. Ese tiempo lo necesitamos después.

---

## Slide 7 · Bloque 1 · Smoke Test común

**Layout:** tabla de 3 columnas con header dark · filas alternadas light/white · caja de alerta roja al pie.

**Número de slide:** 06
**Título:** Bloque 1 · Smoke Test común · 8 min
**Subtítulo:** 6 steps rápidos · verifica que el prototipo carga en todas las máquinas y calibra severidad entre equipos

**Tabla:**

| # | Acción | Resultado esperado |
|---|---|---|
| S.1 | Abrir el HTML en Chrome | Header oscuro visible · 12 tabs · sección Ficha activa |
| S.2 | Click en cada una de las 12 tabs (00–11) | Cambia la sección · ninguna queda en blanco ni tira error |
| S.3 | Completar Cliente / Squad / Quarter en Ficha | El header superior se actualiza en vivo (título + chips) |
| S.4 | Elegir Madurez = Growth y Tier = B | Chips cambian · aparece descripción debajo de cada botón |
| S.5 | Métricas · Revenue=100000 · Margen=35 | DPRR se calcula a 35% y se refleja en header y sección |
| S.6 | Click en los 3 links externos (CRM / Kanban / Looker) | Alert "Próximamente" · comportamiento esperado, NO bug |

**Caja de alerta (rojo):**
⚠ Si S.1 a S.5 falla en algún equipo → bloqueador automático para GO LIVE. Se reporta y se sigue con el resto del hackathon.

**Notas del presentador:**
El smoke sirve para dos cosas: verificar que todos arrancan bien y que todos clasifican severidad con el mismo criterio. Si alguien dice "menor" de un bug que otros reportan como "bloqueador", hay que alinear ahora.

---

## Slide 8 · Bloque 2 · Script · Primera mitad

**Layout:** lista de 5 "section cards" (número grande en badge dark + nombre bold + descripción muted) · caja de "Mirar con lupa" al pie.

**Número de slide:** 07
**Título:** Bloque 2 · Script · Primera mitad · 18 min
**Subtítulo:** Setup + Financials · 5 secciones · cada squad con su cuenta real

**Secciones a testear (cada una con badge numérico):**

| N° | Sección | Tarea |
|---|---|---|
| 01 | Ficha | Completar todos los campos con datos reales · probar los 4 botones de Madurez y los 4 de Tier |
| 02 | Squad ABE | Cargar roles reales · usar "+ agregar" para sumar 1 CS, 1 GD, 1 DL adicionales |
| 03 | Contexto | Completar al menos 4 de las 8 áreas de madurez digital con notas reales · probar selector Alto/Medio/Bajo |
| 04 | Métricas | Revenue, Margen, posiciones, churn, NRR, share of wallet, pipeline · verificar DPRR en header |
| 05 | Nómina | Cargar al menos 5 Acidians reales (pueden ser iniciales) · probar "+ agregar" · verificar resumen superior |

**Caja "🔍 Mirar con lupa" (pie de slide, fondo light):**
¿La renta total de Nómina cuadra con Revenue? · ¿El DPRR se actualiza al cargar Nómina o solo en Métricas? · ¿Se pierde el foco al agregar filas? · ¿Los placeholders dan ejemplos útiles?

**Notas del presentador:**
En este bloque se carga la estructura base del plan. Ojo con las inconsistencias entre secciones — es donde más van a aparecer.

---

## Slide 9 · Bloque 3 · Script · Segunda mitad + Retest

**Layout:** lista de 6 section cards (más compacta que slide 8) · caja azul de retest al pie.

**Número de slide:** 08
**Título:** Bloque 3 · Segunda mitad + Retest · 20 min
**Subtítulo:** Operación y estrategia · 6 secciones · ≈3 min cada una · + retest de fixes del Batch 1

**Secciones a testear:**

| N° | Sección | Tarea |
|---|---|---|
| 06 | Contrapartes | Al menos 3 contrapartes reales con Tier, estado Q anterior, estado Q actual, share of wallet |
| 07 | Churn | 1–2 registros de salidas reales del último trimestre · marcar Churn Sí/No · verificar contadores del tope |
| 08 | Expansión | 2 hipótesis de farming reales · unidad, sponsor, propuesta, orden de magnitud |
| 09 | Salud | Semáforo verde/amarillo/rojo para 3 Acidians · ver si contadores superiores suman bien |
| 10 | Stack | Revisar tecnologías prellenadas · agregar 1 área nueva con "+ agregar área" |
| 11 | Competencia | 1–2 vendors reales · 2 gerencias con Share of Wallet estimado |

**Caja "🔄 Retest obligatorio al final (≈3 min)" (pie de slide, fondo azul light):**
El facilitador le pregunta al responsable de GTM Engineering qué fixes del Batch 1 aplicó. Cada equipo retestea en su cuenta y actualiza el estado en la planilla: "Verificado · fix OK" o "Verificado · fix incompleto".

**Notas del presentador:**
El retest es lo que cierra el loop. Si no retestean, los fixes del responsable de GTM Engineering no bajan la severidad del backlog y la votación final queda falseada.

---

## Slide 10 · Plantilla de hallazgos

**Layout:** tabla de 3 columnas (Campo, Cómo se llena, Ejemplo) · header dark · caja "Regla del scriba" en ámbar al pie.

**Número de slide:** 09
**Título:** Plantilla de hallazgos · una fila por hallazgo
**Subtítulo:** Google Sheet compartido con todos los squads · lo completan en vivo durante cada bloque

**Tabla:**

| Campo | Cómo se llena | Ejemplo |
|---|---|---|
| ID | T{squad}-{correlativo} | T1-07 |
| Squad | Nombre del squad que reporta | Financial Services |
| Bloque | 1 Smoke · 2 Primera mitad · 3 Segunda mitad | 2 |
| Sección | 00 a 11, o Transversal | 05 · Nómina |
| Tipo | Bug · UX · Contenido · Faltante · Inconsistencia · Performance | Bug |
| Descripción | Qué pasó, en 1–2 líneas | Margen=200 pasa como válido, DPRR se calcula a 200% |
| Pasos | Pasos mínimos para reproducir | Métricas → Margen → 200 → tab |
| Severidad | 🔴 Bloqueador · 🟠 Mayor · 🟡 Menor · 🟢 Nice-to-have | 🟠 Mayor |
| Impacto | A quién afecta, cuánto duele | AD podría reportar DPRR imposible en QBR |
| Estado | Abierto · En fix · Verificado fix OK · Descartado | En fix |

**Caja "📌 Regla del scriba" (pie de slide, fondo ámbar light):**
Si dos squads reportan lo mismo, se consolida en UNA fila con ambos IDs (ej: T1-07 / T3-12). Repeticiones = señal fuerte.

**Notas del presentador:**
Una fila por hallazgo. Sin ensayo literario. Con los pasos para reproducir bien claros, porque el responsable de GTM Engineering los va a leer rápido en los pitstops.

---

## Slide 11 · Rúbrica de severidad

**Layout:** 4 cards apiladas con barra de color lateral + fondo tintado del mismo color · dot icon + tag + definición + ejemplo (a la derecha, separado).

**Número de slide:** 10
**Título:** Rúbrica de severidad
**Subtítulo:** Consultar antes de clasificar · mejor pecar de crítico que dejar pasar un bloqueador

**Niveles:**

| Dot | Nivel | Definición | Ejemplo |
|---|---|---|---|
| 🔴 | Bloqueador | Impide usar el prototipo o produce un dato incorrecto que puede tomarse como verdad. | DPRR mal calculado · sección que no carga · pérdida de datos al refrescar |
| 🟠 | Mayor | Se puede trabajar alrededor, pero genera fricción significativa o riesgo de error humano. | Doble captura de dato · falta de validación · inconsistencia entre secciones |
| 🟡 | Menor | Incomoda pero no compromete el uso. Cosmético o editorial. | Placeholder genérico · sigla sin definir · alineación de columnas |
| 🟢 | Nice-to-have | Mejora de ambición, no de corrección. | Autocompletar desde CRM · resumen ejecutivo generado · export PDF |

**Notas del presentador:**
Si dudan entre dos niveles, suban uno. Mejor un Mayor que resulta ser Menor que al revés. La deduplicación final va a ajustar.

---

## Slide 12 · Criterios para votar GO

**Layout:** 4 filas con badge gigante tipográfico a la izquierda (dark) + pregunta + descripción · alerta roja al pie con regla del veto.

**Número de slide:** 11
**Título:** Criterios para votar GO
**Subtítulo:** Antes de votar, cada squad se hace estas 4 preguntas honestamente

**Criterios:**

| Umbral (badge grande) | Pregunta | Nota |
|---|---|---|
| **0** | ¿Cuántos bloqueadores quedan sin resolver? | Si hay uno solo · no hay GO posible. |
| **≤ 5** | ¿Cuántos mayores quedan sin resolver? | …y con workaround aceptable documentado. |
| **≥ 10 / 12** | ¿Cuántas secciones se completan end-to-end sin tutorial? | Si más de 2 secciones requieren aclaración, falta trabajo editorial. |
| **Sí** | ¿Lo usarías el lunes con tu cuenta real sin avergonzarte? | La pregunta más honesta. Si dudás, es NO-GO. |

**Caja de alerta (rojo, pie):**
⚠ Veto técnico: un solo equipo puede forzar GO CONDICIONAL si tiene un bloqueador argumentado con pasos reproducibles.

**Notas del presentador:**
La cuarta pregunta es la más importante. Si algún equipo duda, es NO-GO. No hay presión social para votar GO. El veto técnico protege contra el consenso forzado.

---

## Slide 13 · Roles en la sesión

**Layout:** 4 cards verticales iguales en fila · dark con círculo azul arriba con número · título Georgia + descripción centrada.

**Número de slide:** 12
**Título:** Roles en la sesión

**Cards (4):**

| Círculo | Tag | Descripción |
|---|---|---|
| 1 | Facilitador | Dueño del tiempo. Rota entre equipos. Corta discusiones fuera de script. Modera la votación. |
| 1 | Scriba | Consolida hallazgos en la planilla en vivo. Deduplica. Proyecta en pantalla en pitstops. |
| 1 | Responsable de GTM Engineering | Aplica fixes en vivo entre bloques. Recibe batches. No defiende el diseño. |
| N | Equipo (squad) | Testea con su cuenta real. Completa la planilla. Vota al cierre. |

**Notas del presentador:**
Los tres roles individuales (facilitador, scriba, responsable de GTM Engineering) no pueden faltar. El scriba es el rol más subestimado y el más crítico: sin planilla viva, no hay decisión al final.

---

## Slide 14 · Closing · Arrancamos

**Layout:** dark cover full-bleed · barra azul izquierda · título gigante tipo statement · 3 bullets con dot azul al pie.

**Título principal:** Arrancamos.
**Subtítulo (azul):** En 75 minutos sabemos si este Account Plan va a producción o qué le falta.

**Recordatorios (3 bullets con dot azul):**
- Cada squad con SU cuenta real
- El responsable de GTM Engineering arregla en vivo entre bloques
- Al cierre votamos GO · GO CONDICIONAL · NO-GO

**Notas del presentador:**
Cierre breve. No recapitular — ya saben lo que hay que hacer. Solo reforzar que los 3 pilares están: cuenta real, fixes en vivo, decisión concreta al final.

---

## Notas generales para el diseño

**Sobre el flow narrativo:** los slides están pensados para leerse como un arco de 3 actos.
- **Acto 1 · Contexto** (slides 1–5): qué es, qué decidimos, cómo funciona, quién hace qué.
- **Acto 2 · Manual de uso** (slides 6–10): principios, scripts, plantilla.
- **Acto 3 · Decisión** (slides 11–14): rúbrica, criterios, roles, cierre.

**Sobre los motivos visuales recurrentes:**
- Chip numerado arriba-derecha en todos los slides de contenido.
- Badge circular o rectangular oscuro para "N° de sección" (slides 8, 9, 12, 13).
- Cards de color para estados (GO/CONDICIONAL/NO-GO y severidades) — **usar siempre los mismos 4 colores** para que la gente los asocie rápido.
- Footer discreto: `Acid Labs · Hackathon Account Plan ABE v9 · 1h 15min`.

**Sobre la tipografía:**
- Títulos: serif/display (Georgia, Playfair, similar) — para que los "Arrancamos" y "Por qué estamos acá" pesen.
- Cuerpo: sans limpio (Inter, Arial, similar).
- Badges numéricos grandes: display serif o display bold muy pesado.

**Sobre el tono:**
- Argentino/rioplatense directo. "Arranquemos", "Cada squad con SU cuenta", "Si dudás es NO-GO".
- Sin corporativismo. Sin "alineamiento estratégico". Sin "stakeholders".
- Cada slide tiene que poder leerse en 20–30 segundos.

---

**Fin del documento.** Los 14 slides contienen todo el contenido del kickoff original. Editar libremente tono, layout y motivos visuales en tu sistema de diseño.
