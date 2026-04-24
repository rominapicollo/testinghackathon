# Hackathon de Testing · Account Plan ABE v9 — Script de kickoff

**Uso:** este documento es el guion del kickoff. El facilitador lo lee, lo internaliza, o lo lleva impreso para apoyarse.
**Total de slides:** 15.
**Duración total del kickoff:** ~9–10 min (aprox. 35–45 seg por slide).
**Idioma:** español rioplatense, tono directo.

**Antes del kickoff, el facilitador tiene que haber decidido la Modalidad de cierre (A o B, ver §8 del documento de diseño).** El guion tiene bifurcaciones marcadas según la modalidad elegida.

**Paleta de referencia** (opcional, para quien arma el deck): navy `#1A1A2E` · deep-navy `#16213E` · accent-blue `#0066CC` · green `#1D9E75` · amber `#BA7517` · red `#C0392B` · light-bg `#F5F5F7` · dark-text `#1D1D1F` · muted `#6E6E73`.

---

## Slide 1 · Cover

**Qué muestra:** Cover oscuro full-bleed. Kicker "HACKATHON DE TESTING". Título grande "Account Plan ABE · v9". Subtítulo: *1h 15min · 1 squad = 1 equipo · Responsable de GTM Engineering aplicando fixes en vivo*. Tres cards al pie con las preguntas clave (¿Funciona? ¿Sirve? ¿Se entiende?).

**Guion:**

> Buenas. Arrancamos el hackathon de testing del Account Plan ABE, versión 9.
>
> En los próximos 75 minutos vamos a testear juntos el prototipo — vacío, de forma funcional — y vamos a responder tres preguntas concretas: ¿funciona?, ¿sirve?, ¿se entiende?
>
> Hoy somos squads trabajando en duplas de AD y CS, con algún rol de apoyo si hace falta. Y tenemos al responsable de GTM Engineering en la sala, aplicando fixes en vivo entre bloques. Eso es lo que hace distinto a este hackathon.

---

## Slide 2 · Por qué estamos acá

**Qué muestra:** Intro corta. Dos cards horizontales apilados, una por modalidad de cierre (A en azul, B en verde). Indicador visual grande de cuál está activa hoy.

**Guion:**

> El prototipo está listo para revisión. Hoy, con la evidencia que juntemos entre todos, decidimos si va a producción piloto o qué le falta resolver primero.
>
> Hay dos formas de cerrar la actividad y la definí antes del kickoff. Te cuento cuál es cuál y después confirmo con cuál vamos hoy:
>
> - **Modalidad A — Decisión en vivo.** Al final del hackathon, cada squad emite un voto con rúbrica: GO, GO CONDICIONAL o NO-GO. Nos vamos con la respuesta clara.
> - **Modalidad B — Cierre con backlog.** No votamos. Consolidamos todos los hallazgos, se los entregamos al responsable de GTM Engineering, y él define asincrónicamente — en 48 a 72 horas — cuándo lanza la próxima iteración.
>
> Hoy vamos con la **Modalidad [A / B]**.

---

## Slide 3 · Agenda · 75 minutos

**Qué muestra:** Timeline vertical. 4 bloques (Kickoff, Smoke, Primera mitad, Segunda mitad, Cierre) + 3 pitstops diferenciados con fondo ámbar e ícono de llave.

**Guion:**

> Este es el recorrido. 5 minutos de kickoff — lo que estoy haciendo ahora —, 8 minutos de smoke test para calibrar, 18 minutos de script de primera mitad, 20 de segunda mitad con retest, y 12 de cierre.
>
> Entre bloque y bloque hay pitstops. En cada uno, el scriba consolida los hallazgos y se los entrega al responsable de GTM Engineering. Él arranca a aplicar fixes mientras ustedes siguen testeando en el bloque siguiente.
>
> Dos cosas importantes: los pitstops son sagrados — sin pitstop no hay fixes aplicados. Y la duración parece justa, pero está calibrada para que no corra nadie. Si me ven cortando discusiones, es por esto.

---

## Slide 4 · Los equipos · 1 squad = 1 equipo

**Qué muestra:** Dos columnas. Izquierda (fondo claro): cómo funciona. Derecha (fondo oscuro): tres bloques con subtítulo + descripción explicando por qué así.

**Guion:**

> Cómo se organizan los equipos: 1 squad = 1 equipo. Cada squad arma su equipo con **AD y CS**. Si necesitan sumar un rol de apoyo — un Growth Developer, un Delivery Lead, alguien más del squad — sumen. Pero el core es AD + CS.
>
> Importante: **todos testean sobre el prototipo vacío**, con datos de prueba cargados en vivo. No se traen datos reales de sus cuentas. El testing es funcional.
>
> Entonces, ¿para qué los dividimos en squads si todos tienen el mismo prototipo y los mismos datos de prueba? Por **diversidad de lente**. Cada squad trabaja diferente. Lo que para un AD es un flujo natural, para otro es un paso que falta. Esas diferencias de lectura son el hallazgo.

---

## Slide 5 · El responsable de GTM Engineering en vivo

**Qué muestra:** Flujo horizontal de 5 pasos (Equipos testean → Pitstop → GTM arregla → Pitstop → Retest). Abajo, dos columnas: Qué SÍ hace (borde verde) / Qué NO hace (borde rojo).

**Guion:**

> Esta es la novedad del hackathon. El responsable de GTM Engineering está en la sala. **No testea, no participa en los equipos, no se defiende.** Su trabajo en los 75 minutos es recibir batches de hallazgos en los pitstops y aplicar fixes en paralelo mientras ustedes siguen testeando.
>
> Regla de oro: ataca primero bloqueadores con fix corto. Nada de refactorear en vivo. Las cosas grandes — persistencia, integraciones — van al backlog como P0, no se intentan hoy.
>
> Y si alguien le pregunta "¿por qué está así?" durante el testing, yo corto. La discusión de diseño viene después. Hoy capturamos.

---

## Slide 6 · Principios del testing

**Qué muestra:** Grid 2×3 con los 6 principios. Cards con barra azul a la izquierda, título en bold, descripción muted.

**Guion:**

> Seis principios, rápido.
>
> Uno: usen el prototipo como lo usarían el lunes a las 9 de la mañana. No es QA manual exhaustivo — es testing funcional.
>
> Dos: si algo les hace fruncir el ceño, anótenlo. La fricción es un hallazgo válido aunque nada esté técnicamente roto.
>
> Tres: un hallazgo, una fila. Sin ensayo literario.
>
> Cuatro: prohibido decir "quedaría lindo si..." sin decir qué problema concreto resuelve.
>
> Cinco — este es el más difícil: no discutir soluciones durante testing. Solo capturar. El diseño viene después con el responsable de GTM Engineering. Si los veo debatiendo cómo arreglar algo, corto.
>
> Seis: hallazgo repetido es señal fuerte, no ruido. Si dos squads reportan lo mismo, es prioridad.

---

## Slide 7 · Bloque 1 · Smoke Test · 8 min

**Qué muestra:** Tabla de 3 columnas con 5 acciones (S.1 a S.5) y resultado esperado. Caja de alerta roja al pie.

**Guion:**

> Arrancamos con un smoke test común de 8 minutos. Son 5 pasos rápidos.
>
> Sirven para dos cosas: verificar que el prototipo carga bien en todas las máquinas, y calibrar entre equipos cómo clasificamos severidad. Si alguien dice "menor" a un bug que otros reportan como "bloqueador", lo alineamos ahora.
>
> Los 4 primeros pasos son los críticos. **Si alguno falla en algún equipo, es bloqueador automático para GO LIVE**, se reporta y seguimos. El paso 5 es clickear los 3 links externos — CRM, Kanban, Looker. Esos muestran un alert "Próximamente". Eso es comportamiento esperado, no es un bug.

---

## Slide 8 · Bloque 2 · Primera mitad · 18 min

**Qué muestra:** 4 section cards (badge numérico + nombre + tarea). Caja "Mirar con lupa" al pie.

**Guion:**

> Entramos al bloque de verdad. 18 minutos para cargar la estructura base del plan. Son 4 secciones: **01 Ficha, 02 Squad, 03 Contexto, 05 Nómina**.
>
> Van a notar que saltamos el 04. Esa sección la dejamos fuera del script hoy. Miren si esa ausencia les genera confusión — es parte de lo que queremos saber.
>
> Datos de prueba, no reales: iniciales, nombres ficticios, valores representativos. Lo que importa no son los números, sino si el flujo cierra.
>
> Qué mirar con lupa: si se pierde el foco al agregar filas, si los placeholders dan ejemplos útiles, y si saltar el 04 genera ruido.

---

## Slide 9 · Bloque 3 · Segunda mitad + Retest · 20 min

**Qué muestra:** 6 section cards (más compactas) + caja azul con el retest obligatorio.

**Guion:**

> 20 minutos para las 6 secciones de operación y estrategia: Contrapartes, Churn, Expansión, Salud, Stack y Competencia. Tres minutos por sección, así que ritmo sostenido.
>
> Al final del bloque hay 3 minutos de **retest obligatorio**. Yo les voy a avisar qué fixes aplicó el responsable de GTM Engineering en los pitstops 1 y 2. Ustedes retestean esos puntos y actualizan el estado en su planilla: "Verificado · fix OK" o "Verificado · fix incompleto".
>
> Si no retestean, el backlog final queda inflado y la decisión sale con ruido. Es el paso que cierra el loop.

---

## Slide 10 · Plantilla de hallazgos

**Qué muestra:** Tabla de 3 columnas (Campo / Cómo se llena / Ejemplo). Caja ámbar con la regla del scriba al pie.

**Guion:**

> Acá cargan los hallazgos. **Una fila por hallazgo.** Sin ensayo literario.
>
> Los campos que más importan: descripción breve, pasos para reproducir, sección, severidad. Ojo con los pasos — el responsable de GTM Engineering los va a leer rápido en los pitstops. Si no puede reproducir, no arregla. Sean claros.
>
> Regla del scriba: si dos squads reportan lo mismo, se consolida en **una sola fila** con los dos IDs. Repeticiones son señal de prioridad, no duplicación.

---

## Slide 11 · Rúbrica de severidad

**Qué muestra:** 4 cards apiladas con barra de color lateral (rojo, naranja, amarillo, verde) + definición + ejemplo.

**Guion:**

> Cuatro niveles de severidad. Lo más importante es clasificar con el mismo criterio entre equipos.
>
> **Bloqueador, rojo:** impide usar el prototipo o produce un dato incorrecto que se puede tomar como verdad. Ejemplo: un cálculo mal, una sección que no carga.
>
> **Mayor, naranja:** se puede trabajar alrededor, pero hay fricción significativa o riesgo de error humano. Ejemplo: doble captura, falta de validación, inconsistencia entre secciones.
>
> **Menor, amarillo:** incomoda pero no compromete el uso. Cosmético o editorial.
>
> **Nice-to-have, verde:** ambición, no corrección. Ejemplo: un export PDF.
>
> Regla simple: si dudan entre dos niveles, **suban uno**. Mejor pecar de crítico. La deduplicación al final va a ajustar.

---

## Slide 12 · Modalidad de cierre

**Qué muestra:** 2 cards grandes, una por modalidad, lado a lado. Indicador visual claro (tick, flecha, highlight) sobre la modalidad activa del día.

**Guion:**

> Antes de arrancar, clarifico cómo termina la actividad hoy. Ya lo mencioné en el Slide 2, pero lo repito con más detalle porque cambia qué esperar al cierre.
>
> Las dos modalidades consolidan el backlog. La diferencia está en si hay decisión en vivo o no.
>
> **Modalidad A — Decisión en vivo.** Consolidación en pantalla → votación por squad (GO / CONDICIONAL / NO-GO) con rúbrica → priorización del backlog P0/P1/P2 → cierre con la decisión proyectada.
>
> **Modalidad B — Cierre asincrónico.** Consolidación más extendida → priorización del backlog P0/P1/P2 → entrega formal del backlog al responsable de GTM Engineering. **Sin votación.** Él define en 48 a 72 horas cuándo lanza la próxima iteración y con qué alcance.
>
> Hoy cerramos con la **Modalidad [A / B]**. [Confirmar claramente.]

---

## Slide 13 · Criterios para votar GO · solo Modalidad A

**Qué muestra:** 4 criterios con badge tipográfico grande a la izquierda (0, ≤5, ≥10/12, Sí) + descripción. Caja roja al pie con la regla del veto técnico.

**Guion (si Modalidad A):**

> Este slide aplica si cerramos con Modalidad A. Antes de votar, cada squad se hace 4 preguntas honestamente.
>
> Uno: **cero** bloqueadores sin resolver. Si queda un solo bloqueador abierto, no hay GO posible.
>
> Dos: **hasta 5** mayores sin resolver, y con workaround aceptable documentado.
>
> Tres: **10 de 12** secciones completables end-to-end sin tutorial. Si más de 2 secciones requieren aclaración, es que falta trabajo editorial.
>
> Cuatro, la más honesta: ¿lo usarías el lunes con tu cuenta real sin avergonzarte? Si dudás, es NO-GO. No hay presión social para votar GO.
>
> Y un detalle: **veto técnico**. Un solo equipo puede forzar GO CONDICIONAL si tiene un bloqueador argumentado con pasos reproducibles. No se vota por encima de un hallazgo técnico sólido.

**Guion (si Modalidad B):**

> Este slide aplica solo a la Modalidad A, que no es la que usamos hoy. Lo saltamos. La decisión de GO / CONDICIONAL / NO-GO la toma el responsable de GTM Engineering asincrónicamente a partir del backlog que entreguemos al cierre.

---

## Slide 14 · Roles en la sesión

**Qué muestra:** 4 cards verticales en fila, cada una con círculo dark numerado arriba, título y descripción centrada.

**Guion:**

> Para cerrar antes de arrancar: hay 4 roles en la sesión.
>
> **Facilitador** — yo. Dueño del tiempo, rota entre equipos, corta discusiones fuera de script, modera los pitstops.
>
> **Scriba** — consolida los hallazgos en la planilla en vivo. Rol subestimado pero crítico: sin planilla viva no hay decisión útil al cierre.
>
> **Responsable de GTM Engineering** — aplica fixes entre bloques. No defiende el diseño.
>
> **Equipo por squad** — AD + CS + apoyo opcional. Testea el prototipo funcionalmente, completa la planilla, y vota al cierre si estamos en Modalidad A.

---

## Slide 15 · Arrancamos

**Qué muestra:** Cover oscuro full-bleed, barra azul izquierda, título statement "Arrancamos.", 3 bullets con dot azul al pie.

**Guion:**

> Tres cosas para no olvidar:
>
> - Cada squad testea el prototipo vacío funcionalmente, con su dupla AD + CS.
> - El responsable de GTM Engineering arregla en vivo entre bloques.
> - Al cierre, **[Modalidad A: votamos GO / CONDICIONAL / NO-GO con rúbrica] / [Modalidad B: entregamos el backlog consolidado al GTM, que define la próxima iteración asincrónicamente]**.
>
> En 75 minutos sabemos si este Account Plan va a producción o qué le falta. Arranquemos.

---

## Notas generales para el presentador

**Ritmo:** cada slide ~35–45 segundos. No te quedes clavado en uno. Si ves que te pasás, corta y pasá al siguiente — los pitstops se comen el tiempo rápido.

**Bifurcaciones por modalidad:** el slide 2, el 12, el 13 y el 15 tienen variantes según Modalidad A o B. Leé las dos antes del kickoff y marcá la que vas a usar.

**Cortes a hacer sin pedir permiso:**
- Cualquier debate sobre cómo arreglar algo durante el testing → "eso lo hablamos en el pitstop, sigan capturando".
- Cualquier pregunta "¿por qué está así el prototipo?" al responsable de GTM Engineering → "la defensa del diseño viene después, ahora captura".
- Cualquier intento de un squad de usar datos reales de su cuenta → "hoy testeamos con datos de prueba sobre el prototipo vacío, es testing funcional".

**Tono:** rioplatense directo. "Arranquemos", "ojo con X", "corto yo", "si dudás es NO-GO". Sin corporativismo, sin "alineamiento estratégico", sin "stakeholders".

---

**Fin del script.** El documento de diseño (`01_hackathon_design.md`) tiene el detalle operativo completo de cada bloque, la plantilla de hallazgos y la rúbrica. Esta presentación es solo el kickoff.
