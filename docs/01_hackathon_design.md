# Hackathon de Testing · Account Plan ABE v9
**Duración:** 1h 15min · **Equipos:** 1 por squad (AD + CS + rol de apoyo opcional) · **Responsable de GTM Engineering en vivo aplicando fixes** · **Output:** decisión GO / GO CONDICIONAL / NO-GO + backlog priorizado

---

## 1. Objetivo

En 75 minutos, con cada squad testeando el prototipo con una cuenta real que ya conocen, validar si el Plan de Cuenta ABE está listo para ir a producción piloto. El responsable de GTM Engineering está en la sala aplicando arreglos en vivo entre bloques, así que el hackathon funciona como un mini ciclo de iteración comprimido: testear → reportar → arreglar → retestear → decidir.

Al cierre, se define:
- **GO LIVE** (lanzamos piloto con cuentas reales),
- **GO CONDICIONAL** (salimos con lista corta de P0 resuelta en días), o
- **NO-GO** (volvemos a iterar y nuevo hackathon).

---

## 2. Estructura general

**Una novedad clave respecto a un hackathon tradicional:** el responsable de GTM Engineering está en la sala y **aplica fixes entre bloques**. Cada "pitstop" es una ronda rápida donde los equipos le pasan su batch de hallazgos y él los va resolviendo en paralelo mientras los equipos siguen testeando. En el bloque final se **retestea lo que ya se arregló**, lo que baja la severidad del backlog antes de la votación.

| # | Bloque | Duración | Qué hace cada actor |
|---|---|---|---|
| 0 | **Kickoff** | 5 min | Facilitador presenta objetivo, reglas, plantilla. Equipos se ubican. |
| 1 | **Smoke Test común** | 8 min | Equipos corren el smoke con su cuenta. Cargan primeros hallazgos. |
| — | **🔧 Pitstop 1** | 4 min | Scriba consolida. Responsable de GTM Engineering recibe **Batch 1** y arranca. |
| 2 | **Script · Primera mitad** (Setup + Financials) | 18 min | Equipos cargan Ficha/Squad/Contexto/Métricas/Nómina. |
| — | **🔧 Pitstop 2** | 5 min | Ronda rápida. Responsable de GTM Engineering entrega Batch 1 terminado, recibe Batch 2. |
| 3 | **Script · Segunda mitad + Retest** | 20 min | Equipos cargan las secciones restantes y retestean fixes del Batch 1. |
| — | **🔧 Pitstop 3** | 3 min | Último batch entregado al responsable de GTM Engineering. |
| 4 | **Cierre · GO/NO-GO + Backlog** | 12 min | Votación con rúbrica. Consolidación del backlog P0/P1/P2. |

**Total: 75 min.**

---

## 3. Cómo se dividen los equipos

- **1 equipo = 1 squad de cuenta real.** No hay personas artificiales, no hay casos ficticios: cada squad testea con **su propia cuenta**, la que conocen de memoria.
- 2–4 personas por equipo, idealmente con el AD del squad presente.
- El squad decide internamente quién escribe los hallazgos y quién carga datos — pero todos tocan el prototipo.
- Si un squad tiene varias cuentas, eligen **una sola** para el hackathon (la más representativa, no la más simple).

Esto tiene dos ventajas importantes. Primero, los hallazgos son complementarios sin diseñarlo así: una cuenta Mature estresa la nómina, una Customer estresa la Ficha, una Strategic estresa Expansión y Contrapartes. Naturalmente se cubre todo el prototipo sin asignar secciones. Y segundo, los hallazgos son reales: no son bugs de "¿y si alguien cargara 200 Acidians?", son problemas que aparecen con los datos del lunes.

---

## 4. Rol del responsable de GTM Engineering en vivo

El responsable de GTM Engineering no testea, no participa en los equipos y no se defiende. Su trabajo en los 75 minutos es:

- **Recibir batches** en los tres pitstops (no leer hallazgos sueltos durante los bloques).
- **Priorizar** qué atacar primero: bloqueadores y mayores con fix obvio y acotado.
- **Aplicar fixes** en paralelo mientras los equipos siguen testeando.
- **Avisar al facilitador** cuando un fix está listo y en qué sección, para que se pueda retestear.
- **No defender el diseño.** Si un equipo pregunta "¿por qué está así?", el facilitador corta: la intención se discute después.

Buena regla: el responsable de GTM Engineering ataca primero **bloqueadores con fix corto** (validaciones faltantes, cálculos mal, labels confusas). Reestructuraciones grandes (ej: persistencia, integración con Looker) se documentan como P0 para post-hackathon, no se intentan en vivo.

---

## 5. Script por bloque

Cada squad trabaja con **su cuenta real**. El script es el mismo para todos; lo que cambia son los datos.

### Bloque 1 · Smoke Test común (8 min)

Sirve para verificar que el prototipo carga en todas las máquinas y para calibrar severidad entre equipos antes de los bloques densos. Cada equipo marca ✅/❌ en la plantilla:

| # | Acción | Resultado esperado |
|---|---|---|
| S.1 | Abrir el HTML en Chrome | Header oscuro visible + 12 tabs + sección Ficha activa |
| S.2 | Hacer click en cada una de las 12 tabs (00–11) | Cambia la sección. Ninguna queda en blanco ni tira error |
| S.3 | Completar Cliente / Squad / Quarter en Ficha | Header superior se actualiza en vivo (título + chips) |
| S.4 | Seleccionar Madurez = Growth y Tier = B | Chips cambian. Aparece descripción debajo de cada botón |
| S.5 | En Métricas, llenar Revenue=100000, Margen=35 | DPRR se calcula a 35% y se refleja en header y sección |
| S.6 | Click en los 3 links externos (CRM / Kanban / Looker) | Muestran alert "Próximamente" (comportamiento esperado, no bug) |

**Si S.1–S.5 falla en algún equipo → bloqueador automático para GO LIVE, se reporta.**

### 🔧 Pitstop 1 (4 min)

- **Facilitador:** va equipo por equipo, 30 segundos cada uno, para mencionar hallazgos del smoke.
- **Scriba:** marca en la planilla los hallazgos del Batch 1.
- **Responsable de GTM Engineering:** recibe el batch, define qué ataca primero.
- **Equipos:** mientras, leen el script de la primera mitad.

### Bloque 2 · Script · Primera mitad (18 min) — Setup + Financials

Foco: completar la estructura base del plan con datos reales. Cubre 5 secciones.

**Pasos a ejecutar en orden:**

1. **01 · Ficha** — completar todos los campos con datos reales de la cuenta elegida. Probar los 4 botones de Madurez y los 4 de Tier para ver si las descripciones son útiles.
2. **02 · Squad ABE** — cargar los roles reales. Usar el botón **"+ agregar"** para sumar 1 Client Success, 1 Growth Developer, 1 Delivery Lead adicionales.
3. **03 · Contexto estratégico** — completar al menos 4 de las 8 áreas de madurez digital con notas reales. Probar el selector Alto/Medio/Bajo.
4. **04 · Métricas** — cargar Revenue mensual, Margen, posiciones activas, churn %, NRR, share of wallet, pipeline. Verificar que el DPRR del header coincide con el de la sección.
5. **05 · Nómina** — cargar al menos **5 Acidians reales** (se pueden usar iniciales si se prefiere no cargar nombres completos). Probar el botón "+ agregar Acidian". Verificar que el resumen superior (Acidians activos / Renta total / Costo total / Margen) se calcula bien.

**Qué mirar con lupa:**
- ¿Se puede completar todo sin volver atrás? ¿La numeración 01→05 acompaña el flujo natural?
- ¿La renta total de Nómina cuadra con el Revenue de Métricas? ¿O hay doble captura?
- ¿El DPRR se actualiza cuando cargás Nómina, o solo cuando movés Revenue/Margen en Métricas?
- Al agregar filas/tarjetas, ¿se pierde el foco? ¿Se preservan los datos ya cargados arriba?
- Placeholders: ¿dan ejemplos útiles o son genéricos?

### 🔧 Pitstop 2 (5 min)

- **Facilitador:** ronda de 45s por equipo con hallazgos más relevantes.
- **Responsable de GTM Engineering:** avisa qué fixes del Batch 1 ya aplicó y en qué sección pueden retestear. Recibe Batch 2.
- **Equipos:** toman nota de qué retestear en el Bloque 3.

### Bloque 3 · Script · Segunda mitad + Retest (20 min) — Operación y estrategia

Foco: secciones operacionales + confirmación de fixes del Batch 1. Cubre 6 secciones.

**Pasos a ejecutar (≈ 3 min por sección):**

6. **06 · Contrapartes** — cargar al menos 3 contrapartes reales con Tier (T1/T2/T3), estado Q anterior, estado Q actual, share of wallet.
7. **07 · Churn** — cargar 1–2 registros de salidas reales del último trimestre (si las hay). Marcar "¿Es churn? Sí/No" y verificar que los contadores del tope actualizan.
8. **08 · Expansión** — cargar 2 hipótesis de farming reales (unidad, sponsor, propuesta, orden de magnitud).
9. **09 · Rentabilidad y salud** — cargar el semáforo de salud (verde/amarillo/rojo) para 3 Acidians. Ver si los contadores de arriba suman bien.
10. **10 · Stack tecnológico** — revisar si las tecnologías prellenadas tienen sentido. Agregar 1 área nueva con "+ agregar área".
11. **11 · Competencia** — cargar 1–2 vendors reales y 2 gerencias con Share of Wallet estimado.

**Retest obligatorio al final (≈ 3 min):**
- El facilitador le pregunta al responsable de GTM Engineering qué fixes aplicó del Batch 1.
- Cada equipo retestea los puntos fixados en **su planilla** y actualiza el estado del hallazgo a **"Verificado · fix OK"** o **"Verificado · fix incompleto"**.

**Qué mirar con lupa:**
- Cross-check: las contrapartes en estado "Dormido" o "Ex", ¿aparecen señalizadas en Rentabilidad y salud?
- Umbrales: si el churn supera el umbral del estado (Mature: 7%), ¿el sistema avisa?
- Placeholders: los campos de Expansión y Competencia, ¿dan ejemplos reales o son muy genéricos?
- Consistencia terminológica: "Contraparte" vs "Stakeholder" vs "Cliente" — ¿se usan intercambiables?
- ¿Los fixes retesteados realmente resuelven el problema reportado?

### 🔧 Pitstop 3 (3 min)

- **Facilitador:** último barrido express, 30s por equipo para hallazgos de último momento del Bloque 3.
- **Scriba:** cierra la planilla, deduplica hallazgos repetidos.
- **Responsable de GTM Engineering:** si hay un fix trivial que alcanza a aplicar, adelante; si no, lo deja documentado como P0.

### Bloque 4 · Cierre · GO/NO-GO + Backlog (12 min)

**Minuto 0–4 · Consolidación en pantalla.** El scriba proyecta la planilla. Pasan por la columna de severidad y ajustan si dos equipos reportaron lo mismo con severidades distintas.

**Minuto 4–7 · Votación por equipo.** Cada squad emite UN voto: GO / GO CONDICIONAL / NO-GO. Antes de votar, revisan mentalmente la rúbrica (ver §7).

**Minuto 7–10 · Priorización del backlog.** Se agrupan los hallazgos no resueltos durante el hackathon en:
- **P0** — obligatorio antes del piloto (bloqueadores + mayores críticos).
- **P1** — primer sprint post-launch (mayores + menores de alto impacto).
- **P2** — backlog general (menores + nice-to-have).

**Minuto 10–12 · Cierre.** Lámina final con: decisión, conteo de P0/P1/P2, dueño de cada P0, fecha del siguiente hito.

---

## 6. Plantilla de hallazgos

Archivo compartido (Google Sheet convertido desde el xlsx que se entrega con este documento). Todos los equipos cargan en la misma hoja.

**Columnas obligatorias:**

| Campo | Cómo se llena | Ejemplo |
|---|---|---|
| ID | `T{squad}-{N°}` | T1-07 |
| Squad | Nombre del squad que reporta | Financial Services |
| Bloque | 1 (Smoke) / 2 (Primera mitad) / 3 (Segunda mitad) | 2 |
| Sección | 00 a 11, o "Transversal" | 05 · Nómina |
| Tipo | Bug / UX / Contenido / Faltante / Inconsistencia / Performance | Bug |
| Descripción | Qué pasó, en 1–2 líneas | Margen = 200 pasa como válido, DPRR se calcula a 200% |
| Pasos | Pasos mínimos para reproducir | Métricas → Margen → 200 → tab |
| Severidad | 🔴 Bloqueador / 🟠 Mayor / 🟡 Menor / 🟢 Nice-to-have | Mayor |
| Impacto | Una línea: a quién afecta, cuánto duele | AD podría reportar un DPRR imposible en QBR |
| Estado | Abierto / En fix / Verificado fix OK / Verificado fix incompleto | En fix |
| Asignado a | Responsable de GTM Engineering (nombre) | Juan |
| Notas | Comentarios adicionales | Fix aplicado 11:40, ok tras retest |

**Regla de oro del scriba:** si dos squads reportan lo mismo, consolidar en una fila única con ambos IDs (ej: `T1-07 / T3-12`). Repeticiones = señal fuerte.

---

## 7. Rúbrica GO / GO CONDICIONAL / NO-GO

### Niveles de severidad

| Nivel | Definición | Ejemplo |
|---|---|---|
| 🔴 **Bloqueador** | Impide usar el prototipo, o produce un dato incorrecto que puede tomarse como verdad. | DPRR mal calculado · sección que no carga · pérdida de datos |
| 🟠 **Mayor** | Se puede trabajar alrededor, pero genera fricción significativa o riesgo de error humano. | Doble captura de dato · falta de validación · inconsistencia entre secciones |
| 🟡 **Menor** | Incomoda pero no compromete el uso. Cosmético o editorial. | Placeholder genérico · sigla sin definir · alineación |
| 🟢 **Nice-to-have** | Mejora de ambición, no de corrección. | Autocompletar desde CRM · resumen ejecutivo · export PDF |

### Criterios para votar GO

Cada squad, antes de votar, contesta honestamente:

| Criterio | Umbral |
|---|---|
| Bloqueadores sin resolver al final del hackathon | **0** |
| Mayores sin resolver | **≤ 5** con workaround aceptable |
| Secciones que se pudieron completar end-to-end sin tutorial | **≥ 10 de 12** |
| ¿Lo usarías el lunes con tu cuenta real sin avergonzarte? | **Sí** |

### Resultados posibles

- **✅ GO LIVE** — todos los squads votan GO. Arranca piloto con 2–3 cuentas reales.
- **🟡 GO CONDICIONAL** — mayoría GO pero queda backlog P0. Se cierra lista corta de P0 con dueño y fecha; una vez cerrados, habilita el piloto sin nuevo hackathon.
- **🔴 NO-GO** — mayoría NO-GO, o más de 3 bloqueadores abiertos. Vuelve a diseño e iteración; nuevo hackathon en 2 semanas.

**Veto técnico:** un solo equipo puede forzar GO CONDICIONAL si tiene un bloqueador argumentado con pasos reproducibles. No se vota por encima de un hallazgo técnico sólido.

---

## 8. Roles en la sesión

| Rol | Responsabilidad | Cuántos |
|---|---|---|
| **Facilitador** | Dueño del tiempo. Rota entre equipos. Corta discusiones fuera de script. Moderará la votación final. | 1 |
| **Scriba** | Consolida hallazgos en la planilla en vivo. Deduplica. Proyecta en pantalla en los pitstops. | 1 |
| **Responsable de GTM Engineering** | Aplica fixes en vivo entre bloques. Recibe batches en los pitstops. No defiende el diseño. | 1 |
| **Equipo (por squad)** | Testea con su cuenta real. Completa la planilla. Vota al cierre. | 1 squad por equipo |

---

## 9. Checklist del facilitador

**Día previo:**
- [ ] Planilla de hallazgos (xlsx) convertida a Google Sheet y compartida con permiso de edición a todos los squads
- [ ] HTML del prototipo enviado por mail a cada squad
- [ ] Confirmación de squads participantes y sala/Zoom
- [ ] Facilitador, scriba y responsable de GTM Engineering asignados y alineados
- [ ] Pantalla compartida lista para pitstops y cierre
- [ ] Cronómetro visible con los bloques precargados

**Durante:**
- [ ] Cortar debates que superan 1 min fuera de script
- [ ] Asegurarse que el scriba consolida en tiempo real, no al final
- [ ] Comunicar al inicio de cada pitstop qué fixes del batch anterior ya están listos
- [ ] Captura de pantalla del backlog final y la decisión

**48h después:**
- [ ] Planilla limpia y compartida con decisión y backlog final
- [ ] Tickets P0 abiertos en el board del equipo con dueño
- [ ] Comunicación al CCO con el resultado
- [ ] Fecha agendada del siguiente hito (piloto o próximo hackathon)

---

## 10. Riesgos conocidos (seeds) — uso interno del facilitador

Puntos que ya se detectaron en revisión técnica del prototipo. **No mencionarlos en kickoff.** Si ningún squad los encuentra, es un hallazgo meta sobre la rúbrica.

1. Selector de margen en Nómina: las opciones **"Crítico (30-40%)"** y **"Estable (30-40%)"** tienen el mismo rango — ambigüedad de clasificación.
2. Los 3 links externos (CRM / Kanban / Looker) muestran `alert("Próximamente")` — ¿aceptable para piloto?
3. **Sin persistencia** — un F5 pierde todo el plan. ¿Cómo se resuelve para piloto?
4. El **DPRR del header** solo se actualiza al editar Revenue/Margen en Métricas, no al cargar Nómina. Posible inconsistencia visible.
5. **Integración con Looker** se menciona como fuente, pero es captura manual. ¿Flujo definido para producción?
6. La **Guía de uso (00)** es larga — validar si los placeholders de campos se bastan solos.
7. No hay **validación de rangos** en campos numéricos (margen negativo, porcentajes >100, etc.).
8. **Responsive / mobile** no está probado — el squad también trabaja desde el celular.

---

**Fin del documento.** El xlsx acompaña este diseño con la plantilla de hallazgos lista para convertir a Google Sheet, y el pptx contiene los slides del kickoff y los pitstops.
