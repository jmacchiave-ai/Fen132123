# Marcos de razonamiento e ideación rápida para los primeros 60-90 minutos (Talent Tech Hack 2026, FEN U. de Chile, 4-5 nov 2026)

> Notas de investigación (26 oct 2026). Equipo de 2 personas, sin código, con asistente de IA como constructor. 3 desafíos de la industria (personas, inclusión, mercado laboral) se revelan el día 1. Hay ~7,5 h de construcción y pitch al día siguiente ante un jurado de escuela de negocios.
> Convención: "Cited Findings" = hechos con fuente. "Inferences" = síntesis propia, incluidas las plantillas y agendas con tiempos que armé combinando las fuentes (no vienen de una fuente única). "Gaps" = lo que no pude verificar en esta sesión.

---

## 1. Cómo decodificar el brief de un desafío (KPI real del dueño del desafío, restricciones, criterios implícitos, preguntas a mentores)

### Takeaway
No encontré un marco formal y citable para "decodificar briefs". La evidencia disponible (guías de hackathon y de evaluación) coincide en dos cosas: construir pensando en la rúbrica de evaluación, y definir temprano un problema abordable y qué significa "terminado", porque esas decisiones de las primeras dos horas suelen decidir quién gana. Para encontrar el KPI real del dueño, en el contexto chileno de inclusión hay una palanca regulatoria concreta: la Ley 21.015 (cuota del 1%).

### Cited Findings
- Una guía de Reskilll dice que todo hackathon publica rúbricas de puntaje y recomienda construir para maximizar esos criterios. Lista como error frecuente ignorar las reglas y criterios. — [Reskilll, How to Win a Hackathon in 2026](https://reskilll.com/blogs/how-to-win-a-hackathon-in-2026-reskillls-guide-from-5000-events/)
- HackerEarth recomienda elegir un problema abordable y acordar temprano qué es "terminado". Sostiene que los ganadores suelen definirse en las primeras dos horas, por esas decisiones iniciales. — [HackerEarth, 10 tips to win a hackathon](https://www.hackerearth.com/blog/10-tips-win-hackathon)
- Criterios típicos de jurado: valor de negocio (si la idea podría contribuir a una solución que genere dinero) y originalidad. — [Eventornado, How to judge a hackathon: 5 criteria](https://eventornado.com/blog/how-to-judge-a-hackathon-5-criteria-to-pick-winners); ver también [Hackathon.com, 4 criteria to apply when judging a hackathon](https://tips.hackathon.com/article/4-criteria-to-apply-when-judging-a-hackathon)
- Un equipo reportó que, en varios eventos, los jurados pesaron más que la idea fuera innovadora que la presentación o el código. — [TSL, 4 rules to win a hackathon](https://tsl.io/blog/4-rules-to-win-a-hackathon)
- KPI regulatorio chileno: la Ley 21.015 obliga a empresas privadas y organismos del Estado con 100 o más trabajadores a tener al menos 1% de trabajadores con discapacidad o asignatarios de pensión de invalidez. El plazo anual de acreditación ante la Dirección del Trabajo vence el 31 de enero. — [Reporte Minero, ene 2026](https://www.reporteminero.cl/noticia/inclusion/2026/01/inclusion-laboral-empresas-cumplen-ley-21015-cuota-1-porciento)
- En enero de 2026, el 48,8% de las empresas reportó cumplimiento por la plataforma electrónica de la DT, frente a 36,4% en 2024. — [Reporte Minero](https://www.reporteminero.cl/noticia/inclusion/2026/01/inclusion-laboral-empresas-cumplen-ley-21015-cuota-1-porciento); [Guía Minera](https://www.guiaminera.cl/el-48-de-las-empresas-ya-cumple-con-la-ley-de-inclusion-laboral/)
- La Fundación Miradas Compartidas advierte que el desafío no es solo llegar a la cifra, sino evitar que el proceso se reduzca a un trámite anual. — [Reporte Minero](https://www.reporteminero.cl/noticia/inclusion/2026/01/inclusion-laboral-empresas-cumplen-ley-21015-cuota-1-porciento)
- Una columna de opinión señala que en 2021 solo el 30,4% de las empresas obligadas envió su comunicación de cumplimiento, que la Ley 21.690 endureció las multas y que la DT reacciona a denuncias pero casi no fiscaliza de oficio. — [Diario Constitucional (columna)](https://www.diarioconstitucional.cl/contrapuntos/inclusion-laboral-de-las-personas-con-discapacidad-igualdad-efectiva-o-cumplimiento-formal/)
- Contexto del mercado laboral (INE, ENE): desocupación nacional de 9,6% en junio-agosto 2026, la más alta desde mayo 2021 (+1,0 pp en 12 meses). Mujeres 10,3% y hombres 9,1%. — [INE, 30 sep 2026](https://www.ine.gob.cl/sala-de-prensa/prensa/general/noticia/2026/09/30/la-tasa-de-desocupaci%C3%B3n-nacional-fue-9-6-en-el-trimestre-junio---agosto-de-2026)
- Participación laboral femenina de 53,7% en abril-junio 2026. — [INE, 31 jul 2026](https://www.ine.gob.cl/sala-de-prensa/prensa/general/noticia/2026/07/31/la-tasa-de-desocupaci%C3%B3n-nacional-fue-9-4-en-el-trimestre-abril---junio-2026)
- Tasa de informalidad de 26,3% y participación de 61,5% en junio-agosto 2026, según una fuente secundaria (Buk). Conviene contrastar con el boletín completo del INE. — [Buk, desempleo junio-agosto 2026](https://www.buk.cl/novedades/finanzas/desempleo-chile-junio-agosto-2026)

### Inferences
**Plantilla "Brief Decoder" (10 min por desafío; el asistente de IA puede hacer una primera pasada en 3 min y el equipo valida):**

| Campo | Pregunta guía | Respuesta |
|---|---|---|
| Dueño del desafío | ¿Qué empresa o área lo propone? ¿Quién dentro de ella "sufre" el problema (RR.HH., operaciones, finanzas, sostenibilidad)? | |
| KPI real (lo que mide su jefe) | ¿Qué número mejora si esto se resuelve? Ejemplos: tiempo de contratación, rotación a 90 días, % de cumplimiento de la Ley 21.015, brecha salarial, costo por contratación, ausentismo, multas evitadas | |
| KPI declarado vs. implícito | ¿El brief dice "inclusión" pero el dolor de fondo es cumplimiento, reputación (ESG) o costo? | |
| Usuario vs. comprador vs. beneficiario | ¿Quién usa la solución, quién paga y quién se beneficia? (ver sección 9) | |
| Restricciones | Datos disponibles, privacidad (datos sensibles de salud o discapacidad), regulación, sistemas actuales (HRIS como Buk), presupuesto | |
| Criterios implícitos del jurado | Escuela de negocios: modelo de negocio, impacto medible, viabilidad comercial, innovación | |
| Palabras repetidas en el brief | Las 3-5 palabras que más se repiten suelen apuntar al criterio oculto | |
| "Terminado" significa… | Una frase: "Al final de la demo, el jurado ve a [usuario] lograr [resultado] en [tiempo]" | |

**10 preguntas al dueño del desafío o a los mentores (usar 5-10 min del tiempo de mentoría):**
1. ¿Qué indicador mira hoy su gerencia sobre este problema y cuánto vale hoy?
2. Si resolvemos esto, ¿qué número cambia en 6 meses y quién lo celebra?
3. ¿Qué intentaron antes y por qué no funcionó?
4. ¿Quién decidiría comprar o pilotear una solución así? ¿Con qué presupuesto o área?
5. ¿Qué datos reales (anonimizados) existen? ¿Podemos usar datos sintéticos con la misma estructura?
6. ¿Qué restricción es innegociable (legal, privacidad, integración con su sistema actual)?
7. ¿Qué segmento de personas es el más afectado (mujeres, PcD, jóvenes, migrantes, 50+)?
8. ¿Qué haría que digan "esto lo piloteamos mañana"?
9. ¿Qué solución les parecería obvia o repetida? (para evitarla)
10. ¿El jurado evalúa más el prototipo, el modelo de negocio o el impacto?

### Gaps
- No encontré la rúbrica oficial de Talent Tech Hack 2026 en esta investigación. Hay que buscarla en las bases del evento o pedirla el día 1.
- No hay fuentes académicas sobre "decodificar briefs"; la plantilla es síntesis propia.
- No encontré cifras de ENDISC sobre empleo de personas con discapacidad en esta sesión.
- No encontré cifras oficiales consolidadas del cumplimiento 2025 de la Ley 21.015 más allá de la medición de enero de 2026.

---

## 2. Design thinking comprimido y adaptaciones del Design Sprint de GV para horas (LDJ, sprint en un día, Crazy 8s, HMW, dot voting), con tiempos

### Takeaway
El Design Sprint original dura 5 días: prototipo, prueba con clientes reales y decisiones rápidas. Para un hackathon, las dos piezas más comprimibles y probadas son la Lightning Decision Jam (LDJ) de AJ&Smart, de 30-90 min, con escritura y votación en silencio, y Crazy 8s (8 ideas en 8 minutos), seguidas de dot voting.

### Cited Findings
- El Design Sprint está diseñado para correr "en solo cinco días": pide despejar la agenda una semana y condensar meses de trabajo de producto y estrategia en una semana, con prototipo, prueba con clientes reales, entrevistas y decisiones rápidas. — [Character (Jake Knapp & John Zeratsky), The Design Sprint](https://www.character.vc/sprint)
- LDJ, estructura canónica de 8 pasos: (1) qué está funcionando, (2) capturar problemas, (3) priorizar problemas, (4) reformular como desafíos (HMW), (5) idear soluciones sin discusión, (6) priorizar soluciones, (7) decidir qué ejecutar y (8) volverlas accionables. Los tiempos son una guía. — [UX Planet, Lightning Decision Jam](https://uxplanet.org/lightning-decision-jam-a-workshop-to-solve-any-problem-65bb42af41dc)
- Las fuentes no coinciden en la duración de la LDJ: 30-45 min para el ejercicio central según UX Planet, 45-90 min según SessionLab. — [UX Planet](https://uxplanet.org/lightning-decision-jam-a-workshop-to-solve-any-problem-65bb42af41dc); [SessionLab, LDJ](https://www.sessionlab.com/methods/lightning-decision-jam-ldj)
- Versiones con tiempos por paso: una presentación de LDJ asigna ~7 min a problemas, ~7 min a soluciones y ~5 min a convertir soluciones en tareas. Una versión de 90 min usa 4 min de notas de problemas en silencio y 7 min de soluciones en silencio. — [Google Slides, Lightning Decision Jam](https://docs.google.com/presentation/d/1oo9DJmo88LGIjtD9_O_ldT_RfPGyWBlh8sPWxHMB7Qs/htmlpresent); [Softronic, LDJ en 90 minutos](https://softronic.dev/lightning-decision-jam)
- Existen variantes de "Mini-LDJ" de 30 minutos para problemas pequeños. Las reglas son time-boxes estrictos, escritura y voto en silencio, y sin discusión abierta. — [Muzli/Medium, LDJ](https://medium.muz.li/a-super-simple-exercise-for-solving-almost-any-product-design-challenge-f9e6c0019d7d?gi=d30961bf0b5a); [SessionLab](https://www.sessionlab.com/methods/lightning-decision-jam-ldj)
- Crazy 8s: cada persona dobla una hoja en 8 secciones y bosqueja 8 ideas distintas en 8 minutos (1 min por recuadro). Es individual, y lo desarrolló Jake Knapp. — [Google Design Sprint Kit, Crazy 8's](https://designsprintkit.withgoogle.com/methodology/phase3-sketch/crazy-8s); [Open Practice Library, Crazy 8s](https://openpracticelibrary.com/practice/crazy-8s/); [Sprintbase, Crazy 8s](https://sprintbase.io/instructions/crazy-8s/)
- En el sprint de GV, Crazy 8s ocurre en el día de bosquejo, después de las "lightning demos" (revisión de soluciones existentes como inspiración). Le sigue un dot voting sobre ideas y componentes, y las más votadas alimentan el "Solution Sketch". Los bosquejos solo necesitan comunicar la idea. — [Medium, Crazy 8's in Design Sprint](https://vishesht27.medium.com/crazy-8s-in-design-sprint-87a0ede5975); [Open Practice Library](https://openpracticelibrary.com/practice/crazy-8s/)

### Inferences
**"Mini-sprint" de 90 minutos para 2 personas + IA (síntesis propia sobre LDJ + Crazy 8s + dot voting):**

| Min | Bloque | Qué hacer | Salida |
|---|---|---|---|
| 0-10 | Leer los 3 briefs | Cada persona lee en silencio; la IA resume cada brief con la plantilla "Brief Decoder" (sección 1) | 3 fichas |
| 10-25 | Elegir desafío | Matriz de selección de desafío (sección 5) | 1 desafío |
| 25-35 | Mentor/dueño | 5 preguntas clave (sección 1) | KPI y restricciones validados |
| 35-42 | Problemas (LDJ paso 2) | 7 min en silencio: cada uno escribe dolores del usuario (1 por post-it o línea); la IA agrega 10 desde investigación previa | 20-30 dolores |
| 42-47 | Votar problemas (LDJ paso 3) | 3 votos cada uno, en silencio | Top 2-3 dolores |
| 47-52 | HMW (LDJ paso 4) | Reescribir el top dolor como "¿Cómo podríamos…?" (3 variantes, elegir 1) | 1 HMW |
| 52-55 | Lightning demo mínima | La IA lista 5 soluciones existentes (Chile/LatAm/global) para no reinventar | Referencias |
| 55-63 | Crazy 8s | 8 min, 8 ideas por persona (16) + la IA genera 15 más con el HMW | ~30 ideas |
| 63-70 | Dot voting | 3 votos por persona, en silencio; luego 2 min para que cada uno defienda una idea | Top 3 |
| 70-80 | Selección final | Impacto/esfuerzo + matriz ponderada alineada a la rúbrica (sección 5) | 1 idea |
| 80-90 | Alcance del MVP | MoSCoW + "qué fingir vs. qué construir" + pre-mortem de 5 min (secciones 6 y 9) | Alcance cerrado |

- Regla operativa: con solo 2 personas, la votación en silencio sirve sobre todo para evitar que uno arrastre al otro. Conviene que la IA actúe como tercer "votante" que justifica con criterios, sin desempatar sola.
- Plantilla HMW: "¿Cómo podríamos [verbo] para [usuario específico] de modo que [resultado medible] sin [restricción]?" Ejemplo: "¿Cómo podríamos ayudar a empresas de 100+ trabajadores a contratar y retener personas con discapacidad, de modo que cumplan el 1% con contrataciones que duren más de 6 meses, sin aumentar la carga del equipo de RR.HH.?"

### Gaps
- No pude abrir la página oficial de AJ&Smart sobre la LDJ (404). Los tiempos por paso vienen de fuentes secundarias que no coinciden entre sí.
- La página del Design Sprint Kit de Google no entregó el contenido completo al consultarla; los datos de Crazy 8s se confirmaron con fuentes secundarias consistentes.
- No encontré una fuente primaria del formato "Design Sprint en 1 día" con agenda minuto a minuto.

---

## 3. Jobs To Be Done, persona/mapa de empatía y pain points del journey: versiones más rápidas

### Takeaway
La forma más rápida y usable de JTBD es la "job story": "Cuando [situación], quiero [motivación], para poder [resultado]". Se complementa con la idea de Christensen de que los clientes "contratan" un producto para un trabajo en una circunstancia concreta (caso milkshake). La versión lista para usar: 1 job story + 1 mapa de empatía de 4 cuadrantes + 5 etapas del journey con 1 dolor cada una, en unos 15 min.

### Cited Findings
- Formato job story: "When [situation], I want to [motivation], so I can [expected outcome]". Reemplaza la user story tradicional ("As a [persona]…"). La cláusula "when" ancla la circunstancia, "want" la motivación y "so I can" el resultado. — [Koji, JTBD Framework guide](https://www.koji.so/docs/jobs-to-be-done-framework); [HelloPM, JTBD](https://hellopm.co/what-is-jobs-to-be-done-jtbd/)
- Caso milkshake (Christensen): la mayoría de los batidos se vendía antes de las 8:30 a.m. a commuters que no compraban otra cosa. Lo "contrataban" para hacer menos aburrido un viaje largo y aguantar hasta el almuerzo. Rivales como plátanos o donas cumplían peor ese trabajo. — [Sue Behavioural Design, JTBD milkshake](https://www.suebehaviouraldesign.com/en/blog/jobs-to-be-done-explained/); [HBS Online, JTBD examples](https://online.hbs.edu/blog/post/jobs-to-be-done-examples); [FullStory, Christensen JTBD](https://www.fullstory.com/blog/clayton-christensen-jobs-to-be-done-framework-product-development/)
- El Value Proposition Canvas divide los "trabajos" del cliente en funcionales, sociales, emocionales y de apoyo, lo que sirve para enriquecer rápido una job story. — [Wade Institute, Value Proposition Canvas](https://studio.wadeinstitute.org.au/tool-detail-value-proposition-canvas.html); [Agile Brand Guide, VPC](https://agilebrandguide.com/wiki/models/value-proposition-canvas-vpc/)
- Advertencia: las cifras de crecimiento de Intercom atribuidas a JTBD (p. ej., 500% en 18 meses) aparecen solo en una guía secundaria, sin fuente primaria. — [Koji](https://www.koji.so/docs/jobs-to-be-done-framework) (no verificado)

### Inferences
**Kit de empatía de 15 min (síntesis propia):**
1. **Job stories (5 min).** Escribir 2: una del usuario final (p. ej., la persona candidata) y otra del comprador (p. ej., jefa de RR.HH.).
   - "Cuando tengo que acreditar el 1% de la Ley 21.015 antes del 31 de enero y no tengo candidatos, quiero encontrar perfiles compatibles con mis vacantes rápido, para poder cumplir sin contratar 'para la foto'."
   - "Cuando postulo a un empleo y tengo una discapacidad, quiero saber qué ajustes razonables ofrece la empresa antes de postular, para poder decidir sin exponerme."
2. **Mapa de empatía de 4 cuadrantes (5 min).** Dice / Piensa / Hace / Siente, más una línea de "Dolores" y otra de "Ganancias". La IA propone un borrador desde el brief y el equipo corrige con lo que dijo el mentor.
3. **Journey de 5 etapas (5 min).** Ejemplo para contratación inclusiva: Descubrir vacante → Postular → Evaluar/entrevistar → Onboarding y ajustes → Permanencia a 6 meses. Anotar un dolor por etapa y marcar el más severo, que será el foco del MVP.
- **Proto-persona en 1 línea:** "[Nombre], [rol], [empresa/tamaño], que hoy [comportamiento] y pierde [costo] por [dolor]". Sirve para el pitch y para que la IA genere datos sintéticos coherentes.

### Gaps
- No obtuve en esta sesión la fuente primaria de Christensen (HBR 2016, "Know Your Customers' Jobs to Be Done") ni de Bob Moesta (entrevistas de "switch"). Las citas son de fuentes secundarias consistentes.
- No encontré una fuente con tiempos estándar para un mapa de empatía; los 5 min son estimación propia.

---

## 4. Selección de ideas: matriz impacto/esfuerzo, scoring ponderado alineado al jurado, RICE/ICE, "wow" vs. factibilidad, y cómo elegir entre 3 desafíos

### Takeaway
RICE = (Reach × Impact × Confidence) / Effort, y su utilidad clave para un hackathon son las escalas fijas de impacto y confianza. ICE = Impact × Confidence × Ease, con escalas de 1-10, y el "Confidence Meter" de Itamar Gilad obliga a admitir que la convicción propia vale casi cero como evidencia. Para elegir desafío conviene una matriz ponderada con los criterios del jurado más criterios estratégicos (encaje con IA, datos, competencia).

### Cited Findings
- RICE: Reach (personas o eventos por periodo, p. ej., clientes por trimestre), Impact (Massive = 3, High = 2, Medium = 1, Low = 0.5, Minimal = 0.25), Confidence (High 100%, Medium 80%, Low 50%; bajo 50% es "total moonshot") y Effort (persona-meses). El puntaje mide el impacto total por tiempo trabajado; "more effort is a bad thing, so it divides the total impact". — [Intercom, RICE](https://www.intercom.com/blog/rice-simple-prioritization-for-product-managers/)
- ICE (Itamar Gilad): ICE = Impact × Confidence × Ease. Cada factor se puntúa de 1 a 10 en escala relativa, consistente dentro del equipo. Ease es típicamente el inverso del esfuerzo. — [Itamar Gilad, The tool that will help you choose better product ideas](https://itamargilad.com/the-tool-that-will-help-you-choose-better-product-ideas/)
- Confidence Meter (Gilad), en su ejemplo trabajado: convicción propia + apoyo temático + opinión de otros = 0,1 ("Near Zero Confidence"). Convicción + apoyo anecdótico = 0,5 ("Low Confidence"). Estimaciones y planes suben a ~0,4-0,8. Datos de mercado (encuesta), ~1-1,5. Evidencia de clientes (usabilidad, entrevistas), ~2,5-3. Datos de uso de un MVP, hasta 6,5. Sobre la escala de 10, la evidencia de comportamiento real es lo que más sube la confianza. — [Itamar Gilad](https://itamargilad.com/the-tool-that-will-help-you-choose-better-product-ideas/)
- La matriz impacto/esfuerzo es uno de los pasos de priorización de soluciones de la LDJ (paso 6, antes de decidir qué ejecutar). — [UX Planet, LDJ](https://uxplanet.org/lightning-decision-jam-a-workshop-to-solve-any-problem-65bb42af41dc)
- Guías de hackathon: construir para la rúbrica, recortar el alcance de forma agresiva y evitar "construir demasiado". — [Reskilll](https://reskilll.com/blogs/how-to-win-a-hackathon-in-2026-reskillls-guide-from-5000-events/)
- Los jurados valoran la innovación (a veces más que la presentación o el código) y el valor de negocio. — [TSL](https://tsl.io/blog/4-rules-to-win-a-hackathon); [Eventornado](https://eventornado.com/blog/how-to-judge-a-hackathon-5-criteria-to-pick-winners)

### Inferences
**A. Matriz para elegir 1 de los 3 desafíos (15 min, síntesis propia).** Cada criterio se puntúa de 1 a 5 y se multiplica por su peso. Los pesos deben ajustarse a la rúbrica oficial si se publica.

| Criterio | Peso | Desafío A | Desafío B | Desafío C |
|---|---|---|---|---|
| Claridad del KPI del dueño (¿hay un número que mover?) | 20% | | | |
| Encaje con lo que la IA construye bien sin código (chat/asistente, clasificación, matching, generación de textos, dashboards con datos sintéticos) | 20% | | | |
| Disponibilidad de datos (reales, públicos como INE/DT, o sintéticos creíbles) | 15% | | | |
| Potencial de modelo de negocio claro (quién paga) — jurado de escuela de negocios | 15% | | | |
| Impacto social demostrable (ODS 8/10, población desatendida) | 15% | | | |
| Menor congestión esperada (¿cuántos equipos irán a lo "obvio"?) | 10% | | | |
| Afinidad y conocimiento del equipo | 5% | | | |

- Heurística de congestión: el desafío con el brief más "sexy" o más genérico (p. ej., "IA para reclutamiento") atrae más equipos. Uno con restricción regulatoria o de datos más árida (cumplimiento, permanencia, reconversión) suele tener menos competencia y un KPI más claro. Es una hipótesis: conviene preguntar a los organizadores o mentores cuántos equipos van por cada uno, si es posible.
- **Desempate "wow vs. factibilidad":** elegir la idea que se pueda demostrar end-to-end en vivo en 90 segundos (la guía Reskilll sugiere ~90 s de demo en el pitch) y que tenga un momento wow, como una IA que hace en 10 segundos algo que hoy toma días.

**B. Selección entre ideas finalistas (10 min).**
1. **Impacto/esfuerzo 2×2 (3 min):** descartar todo lo de alto esfuerzo y bajo impacto.
2. **ICE rápido (4 min)** sobre el top 3, con Ease = "¿se construye y demuestra en menos de 5 h con la IA?" y Confidence según el Confidence Meter (si solo hay convicción propia, máximo 1-2 de 10; si el mentor o dueño confirmó el dolor, 3-4).
3. **Matriz ponderada al jurado (3 min):** Innovación 25%, Impacto 25%, Modelo de negocio 20%, Factibilidad/demo 20%, Wow 10% (pesos a reemplazar por la rúbrica real).
- RICE es útil para la narrativa del pitch ("alcanza a X empresas o personas por trimestre"), pero para decidir en 10 minutos ICE es más rápido.

### Gaps
- No encontré datos sobre cuántos equipos eligen cada desafío en hackathons de este tipo ni sobre ediciones anteriores de Talent Tech Hack.
- La tabla completa del Confidence Meter de Gilad es una imagen; solo obtuve los valores del ejemplo trabajado.

---

## 5. Alcance del MVP: MoSCoW, Wizard of Oz, concierge, fake door; qué fingir y qué construir para una demo convincente

### Takeaway
Para una demo de hackathon, el patrón adecuado es Wizard of Oz: el usuario ve un producto que parece automatizado mientras parte del trabajo se hace "detrás" con datos precargados, prompts fijos o pasos manuales. Se combina con un fake door (botones o planes de precios que muestran demanda) y se recorta con MoSCoW hasta que el "Must" quepa en una demo de 90 segundos.

### Cited Findings
- **Concierge MVP:** se entrega el valor de forma manual y abierta, y el cliente sabe que hay humanos. Sirve para aprender qué necesita el cliente y funciona con muy pocos usuarios. — [Learning Loop, Concierge](https://learningloop.io/plays/concierge); [Exponentially, Concierge MVP](https://www.exponentially.com/concierge-mvp)
- **Wizard of Oz MVP:** el producto parece totalmente automatizado, pero humanos hacen el trabajo detrás. La diferencia con el concierge es que el humano está oculto. — [Exponentially, Wizard of Oz MVP](https://www.exponentially.com/wizard-of-oz-mvp); [Learning Loop](https://learningloop.io/plays/concierge)
- **Fake door (painted door / 404 test):** se presenta una función como si existiera, típicamente un botón o una landing, y se mide cuántos intentan "entrar" (clics o registros). Luego aparece un "próximamente". — [MVP Development, Fake Door MVP](https://mvpdevelopment.company/blog/fake-door-mvp)
- Regla práctica: fake door mide interés, concierge muestra qué construir y Wizard of Oz valida la adopción antes de automatizar. — [AINNA, Product experiments guide](https://ainna.ai/resources/faq/product-experiments-guide); [MVP Development, Types of MVP](https://mvpdevelopment.company/blog/types-of-mvp)
- Pitch sugerido por Reskilll: ~60 s problema, ~30 s enfoque, ~90 s demo en vivo y ~30 s impacto y próximos pasos. Recomienda mostrar primero la demo funcionando y después explicar cómo funciona. — [Reskilll](https://reskilll.com/blogs/how-to-win-a-hackathon-in-2026-reskillls-guide-from-5000-events/)

### Inferences
**MoSCoW de 10 min para el MVP (síntesis propia):**
- **Must (máximo 3):** el "camino feliz" de la demo, es decir, 1 usuario, 1 flujo, 1 resultado wow. Ejemplo: la empresa sube una vacante → la IA la reescribe con lenguaje inclusivo y ajustes razonables → muestra 3 candidatos compatibles con explicación del match → dashboard con el % de avance hacia el 1%.
- **Should:** una segunda vista (p. ej., la del candidato) y una métrica de impacto en pantalla.
- **Could:** login, múltiples roles, exportar a PDF.
- **Won't (esta vez):** integración real con HRIS (Buk, etc.), datos reales sensibles, pagos.

**Qué fingir vs. qué construir:**

| Construir de verdad (lo que el jurado toca o ve en vivo) | Fingir (Wizard of Oz / datos precargados) |
|---|---|
| La interacción central con IA (la "magia") con prompts probados | Base de candidatos y empresas: datos sintéticos realistas |
| Interfaz del flujo principal (3-4 pantallas) | Integraciones (HRIS, DT, bolsas de empleo): mockup con logo genérico y "conectado" |
| 1 dashboard con 3 KPIs de impacto | Históricos y tendencias: datos simulados coherentes con INE/DT |
| Página de precios (fake door: "Solicitar piloto") | Autenticación, permisos, pagos |

- Regla de oro: todo lo que se finja debe declararse en el pitch o en Q&A como "simulado para la demo; en el piloto se conecta con X". Ocultarlo frente a un jurado de negocios es un riesgo de credibilidad.
- Ensayar la demo con un "plan B" grabado (video de 90 s) por si falla la conexión o la IA.

### Gaps
- No obtuve una fuente primaria del método MoSCoW (DSDM/Agile Business Consortium) en esta sesión. La descripción Must/Should/Could/Won't es de conocimiento general y conviene verificarla en agilebusiness.org si se cita en el pitch.
- Los ejemplos clásicos (Airbnb concierge, Amazon y Zappos como Wizard of Oz, Dropbox con fake door por video) varían entre fuentes y deben tratarse como anecdóticos ([Exponentially](https://www.exponentially.com/wizard-of-oz-mvp); [Learning Loop](https://learningloop.io/plays/concierge)).

---

## 6. Lean Canvas y Value Proposition Canvas: llenado rápido; modelos B2B, B2B2C y B2G para RR.HH./inclusión; precios de SaaS de RR.HH.

### Takeaway
El Value Proposition Canvas se llena primero por el lado del cliente (trabajos, dolores, ganancias, priorizados) y después por el mapa de valor. El "fit" es una hipótesis. En Chile, el referente de precios de SaaS de RR.HH. es el modelo por colaborador al mes en UF (Buk: 0,15 UF hasta 40 trabajadores, bajando a 0,07 UF entre 501 y 1.000).

### Cited Findings
- **VPC:** el perfil del cliente tiene trabajos, dolores y ganancias; el mapa de valor tiene productos/servicios, aliviadores de dolor y creadores de ganancia. Viene del libro *Value Proposition Design* (2014, Osterwalder, Pigneur, Bernarda, Smith) y es complemento del Business Model Canvas. — [Wade Institute, VPC](https://studio.wadeinstitute.org.au/tool-detail-value-proposition-canvas.html); [Agile Brand Guide, VPC](https://agilebrandguide.com/wiki/models/value-proposition-canvas-vpc/)
- **Consejos de llenado del VPC:** perfil del cliente antes del mapa de valor; no cubrir todos los dolores y ganancias, solo los más severos y significativos, ordenados por importancia; las conexiones van de aliviadores a dolores, de creadores a ganancias y de productos a trabajos; el fit es una hipótesis hasta que los clientes lo confirmen. — [Agile Brand Guide](https://agilebrandguide.com/wiki/models/value-proposition-canvas-vpc/); [Wade Institute](https://studio.wadeinstitute.org.au/canvas-value-proposition-canvas.html)
- **Precios Buk (Chile, oficial):** valor mensual por colaborador activo, en UF, con tramos de 0,15 UF (1-40, mínimo 3 UF/mes), 0,11 UF (41-250), 0,08 UF (251-500) y 0,07 UF (501-1.000). Sobre 1.000, cotización directa. Incluye implementación y soporte. — [Buk/Chipax](https://info.buk.cl/chipax-buk-software-de-recursos-humanos); [Buk](https://www.buk.cl/)
- Buk tiene un tramo de entrada gratuito (Buk Starter) para remuneraciones de pequeñas empresas, una forma de freemium. — [Buk, software de remuneraciones](https://www.buk.cl/productos/administracion/software-de-remuneraciones)
- Una guía de software menciona ~CLP 4.000 por empleado al mes para Buk y referencias genéricas de PEPM de USD 5-10 (20-50 empleados) y USD 10-25 (50-200). Es una fuente secundaria y no coincide del todo con la tabla oficial. — [Guía de Software, RR.HH. para pymes 2026](https://www.guiadesoftware.com/blog/software-rrhh-nomina-pymes)

### Inferences
**Llenado rápido del Lean Canvas (20 min, orden sugerido en la práctica, ver Gaps):** 1) Segmento de clientes + early adopters → 2) Problema (top 3) + alternativas actuales → 3) Propuesta de valor única (1 frase) → 4) Solución (top 3 funciones = los "Must") → 5) Canales → 6) Ingresos → 7) Costos → 8) Métricas clave → 9) Ventaja injusta. Regla: escribir en bullets de máximo 10 palabras y dejar lo que no se sabe como "hipótesis a validar en piloto".

**Prompt para la IA (Lean Canvas):** "Con este desafío [pegar brief], esta job story [pegar] y esta idea [pegar], llena un Lean Canvas en el orden: segmento → problema → UVP → solución → canales → ingresos → costos → métricas → ventaja injusta. Máximo 3 bullets por caja, 10 palabras cada uno. Marca con (H) cada hipótesis no validada y propone cómo validarla en un piloto de 30 días."

**VPC en 15 min:** 5 min perfil (3 trabajos, 3 dolores, 3 ganancias, ordenados) → 5 min mapa de valor (1 aliviador por dolor y 1 creador por ganancia) → 5 min trazar las 3 conexiones más fuertes, que pasan a ser las 3 frases del pitch.

**Modelos de negocio relevantes (síntesis):**
- **B2B SaaS (paga la empresa):** el más natural para cumplimiento de la Ley 21.015, analítica de diversidad, onboarding inclusivo o retención. Precio PEPM en UF (anclado a la referencia de Buk) o tarifa plana por empresa y tramo de tamaño.
- **B2B2C (la empresa paga, la persona usa o se beneficia):** p. ej., una app de acompañamiento o empleabilidad para candidatos que financia la empresa que contrata, o la OTEC o caja de compensación que la ofrece a sus afiliados. Variante: comisión por colocación exitosa (success fee) que sobrevive al periodo de prueba.
- **B2G (paga el Estado):** municipios u OMIL, SENCE, Senadis o la DT como cliente o socio. Ciclos de venta largos y licitaciones; mejor presentarlo como canal de escalamiento futuro.
- **Marketplace o red de proveedores:** conectar empresas obligadas con fundaciones u OTEC de intermediación laboral; comisión por transacción.
- **Precio sugerido para el pitch:** un add-on de 0,02-0,05 UF por colaborador al mes (por debajo del costo de un HRIS completo) o un plan plano por tramo de empresa. Estos montos son hipótesis propias y deben presentarse como tales.

### Gaps
- No pude abrir la página oficial de Lean Canvas (leanstack.com redirige a leanfoundry.com y luego a leanspark.ai). El orden de llenado y la recomendación de Ash Maurya de completarlo en unos 20 minutos vienen de conocimiento previo y no se verificaron en esta sesión; conviene confirmarlos en https://leanspark.ai/leancanvas o en *Running Lean*.
- No encontré fuentes sobre precios de soluciones específicas de inclusión laboral en Chile (p. ej., consultoras de inclusión o plataformas para PcD).
- No verifiqué el valor actual de la UF (oct-nov 2026); hay que consultarlo en el SII o el Banco Central antes de convertir a CLP.

---

## 7. Medición de impacto social para el pitch: Teoría del Cambio corta, KPIs de impacto, SROI básico, alineación con ODS 8 y 10; cómo cuantificar con pocos datos

### Takeaway
Para un pitch bastan tres piezas: (1) una Teoría del Cambio de una línea, desde el problema y el cambio de largo plazo hacia atrás, explicitando supuestos; (2) 3 KPIs organizados con las 5 dimensiones del IMP (Qué, Quién, Cuánto, Contribución, Riesgo); y (3) un "SROI de servilleta" con descuentos explícitos por deadweight y attribution, que es lo que lo vuelve creíble.

### Cited Findings
- **Teoría del Cambio (Nesta DIY Toolkit):** comúnmente es un diagrama de cajas y flechas. Se parte identificando el problema y el cambio de largo plazo deseado, y luego se llenan las demás cajas, siendo específico en audiencia y punto de entrada. — [Nesta, Theory of Change](https://www.nesta.org.uk/toolkit/theory-change); [Nesta, DIY Toolkit](https://www.nesta.org.uk/toolkit/diy-toolkit/)
- Identificar supuestos es un elemento clave de la Teoría del Cambio y ayuda a planificar el riesgo. La plantilla está en la página 46 del DIY Toolkit. — [Open University, Theory of Change (DIY)](https://www.open.edu/openlearncreate/mod/oucontent/view.php?id=80572)
- **5 dimensiones del IMP:** Qué (qué resultado y cuán importante es), Quién (quién lo experimenta y cuán desatendido está), Cuánto (profundidad, escala y duración), Contribución (qué habría pasado sin nosotros) y Riesgo (probabilidad de que el impacto no ocurra como se espera). Se definieron en 2017 con más de 2.000 organizaciones, y las métricas IRIS+ del GIIN están alineadas a ellas. — [DCED, IMP brief](https://www.enterprise-development.org/wp-content/uploads/RM-Brief-IMP-Standard.pdf); [GIIN, IRIS+ and IMP](https://iris.thegiin.org/document/iris-and-impact-management-project/); [Umbrex, IMP dimensions](https://umbrex.com/resources/frameworks/strategy-frameworks/impact-management-project-dimensions/)
- **SROI:** razón entre el valor presente de los resultados y la inversión total, ajustada por deadweight (lo que habría pasado igual), attribution (parte atribuible a otros), displacement (valor desplazado o negativos) y drop-off (decaimiento en el tiempo, solo si se valoran varios años). — [Sopact, SROI](https://www.sopact.com/use-case/social-return-on-investment-sroi); [Wikipedia, SROI](https://en.wikipedia.org/wiki/Social_return_on_investment)
- Ejemplo de deadweight: si el 10% de los capacitados habría encontrado empleo igual, se resta 10% del valor. Los ajustes se aplican en secuencia y se componen: 20% y luego 25% sobre 10.000 deja 6.000, no 5.500. — [Sopact](https://www.sopact.com/use-case/social-return-on-investment-sroi)
- Las fuentes no coinciden en el número de principios del SROI: Sopact y Wikipedia hablan de 8 (Social Value International agregó "Be responsive" en 2021 y los renombró "Social Value Principles"), mientras que WeAreSALT habla de 7. — [Sopact](https://www.sopact.com/use-case/social-return-on-investment-sroi); [Wikipedia](https://en.wikipedia.org/wiki/Social_return_on_investment); [WeAreSALT](https://www.wearesalt.org/what-is-sroi-social-return-on-investment/)
- **ODS 8.5:** "lograr el empleo pleno y productivo y el trabajo decente para todas las mujeres y los hombres, incluidos los jóvenes y las personas con discapacidad, así como la igualdad de remuneración por trabajo de igual valor" (2030). Sus indicadores son 8.5.1 (ingreso medio por hora por sexo, ocupación, edad y discapacidad) y 8.5.2 (tasa de desempleo por sexo, edad y discapacidad), con la OIT como agencia custodia. — [Agenda 2030 LAC, meta 8.5](https://agenda2030lac.org/en/sdg/8-decent-work-and-economic-growth/targets/85); [InforMEA, target 8.5](https://www.informea.org/en/goals/sustainable-development-goals/goal-8-decent-work-and-economic-growth/target-85)
- Línea base nacional útil (INE): desocupación de 9,6% (jun-ago 2026), con 10,3% en mujeres. — [INE](https://www.ine.gob.cl/sala-de-prensa/prensa/general/noticia/2026/09/30/la-tasa-de-desocupaci%C3%B3n-nacional-fue-9-6-en-el-trimestre-junio---agosto-de-2026)

### Inferences
**Teoría del Cambio en 1 línea (5 min):** "Si [actividad del producto] para [quién, desatendido], entonces [output medible en el piloto], lo que lleva a [outcome a 6-12 meses], contribuyendo a [impacto de largo plazo, ODS 8.5/10.2], siempre que [supuesto crítico]."
- Ejemplo: "Si una IA ayuda a empresas de 100+ trabajadores a adaptar vacantes y hacer match con personas con discapacidad, entonces aumentan las contrataciones de PcD que superan 6 meses, lo que mejora el cumplimiento sustantivo, no solo formal, de la Ley 21.015 y reduce la brecha de empleo de PcD (ODS 8.5), siempre que las empresas implementen los ajustes razonables sugeridos."

**3 KPIs de impacto con las 5 dimensiones del IMP (5 min):**

| Dimensión IMP | KPI de ejemplo (contratación inclusiva) |
|---|---|
| Qué | Contrataciones de PcD con permanencia ≥6 meses (no solo contrataciones) |
| Quién | % de colocaciones en grupos desatendidos (PcD, mujeres 50+, migrantes) |
| Cuánto | N.º de personas × meses de empleo × diferencial de ingreso |
| Contribución | % de colocaciones que no habrían ocurrido sin la herramienta (supuesto explícito de deadweight) |
| Riesgo | Tasa de salida antes de 6 meses; riesgo de "contratar para la foto" |

**SROI de servilleta (5 min, para Q&A, no para la diapositiva principal):**
1. Outcome bruto = N.º de colocaciones adicionales × valor anual por colocación (p. ej., sueldo anual menos subsidios evitados; el valor por persona debe salir de una fuente chilena y citarse).
2. Restar deadweight (p. ej., 30% "habría ocurrido igual"), luego attribution (p. ej., 20% atribuible a fundaciones u OTEC) y luego drop-off si se proyectan años. Aplicar en secuencia.
3. Dividir por la inversión (costo del programa o licencia). Presentarlo como rango (conservador / base) y como "ratio indicativo, no SROI evaluado", porque un SROI formal requiere verificación y participación de stakeholders.
- Con pocos datos, la credibilidad se logra con tres cosas: (a) partir de una línea base oficial (INE, DT), (b) mostrar los descuentos explícitamente y (c) dar rangos en vez de cifras puntuales.

### Gaps
- No verifiqué en esta sesión el texto oficial de la meta ODS 10.2. Por conocimiento previo, es "potenciar y promover la inclusión social, económica y política de todas las personas, independientemente de su edad, sexo, discapacidad, raza, etnia, origen, religión o situación económica u otra condición"; confirmar en https://sdgs.un.org/goals/goal10.
- No obtuve los campos exactos de la plantilla de Teoría del Cambio de Nesta (página 46 del DIY Toolkit) ni fuentes del Center for Theory of Change.
- No consulté directamente las "Social Value Principles" en socialvalueint.org; hay conflicto entre 7 y 8 principios.
- No encontré valores monetarios chilenos estandarizados (proxies financieros) por colocación laboral de PcD para el SROI.

---

## 8. Dimensionamiento rápido de mercado (TAM/SAM/SOM top-down y bottom-up) con un ejemplo para un producto de RR.HH./inclusión en Chile

### Takeaway
La forma más defendible de dimensionar un producto de inclusión laboral en Chile es bottom-up: N.º de empresas obligadas por la Ley 21.015 (100+ trabajadores) × precio anual por empresa. No encontré un conteo oficial reciente de empresas con 100+ trabajadores. Hay proxies de "empresas grandes" por ventas (≈13.000-14.000) y una referencia oficial de precio PEPM (Buk), así que el ejemplo debe presentarse con supuestos explícitos.

### Cited Findings
- El SII clasifica las empresas por ventas, no por trabajadores. Sus tablas (años comerciales 2014-2015) muestran unas 6.000 empresas "Grande 1", 4.900 "Grande 2", 1.100 "Grande 3" y 2.100 "Grande 4" (≈14.100 grandes), sobre ≈1,05 millones de empresas y ≈8,9 millones de trabajadores dependientes. — [SII, Estadísticas de empresas por tamaño según ventas](https://www.sii.cl/estadisticas/empresas_tamano_ventas.htm)
- Según CORFO (datos 2020), Chile tenía 1.279.937 empresas registradas, unas 1.039.914 activas, y las microempresas eran el 61,6%. — [CORFO, Chile y sus regiones en datos económicos 2022](https://wapp4.corfo.cl/archivos/WCSCONTI/IP/GRC/Chile%20y%20sus%20regiones%20en%20datos%20economicos%20Gerencia%20de%20Redes%20y%20Territorios%20CORFO%202022.pdf)
- La Séptima Encuesta Longitudinal de Empresas (ELE-7) reporta 13.448 empresas grandes (≈3%) sobre un marco de ≈409.300 empresas. — [Ministerio de Economía, Informe ELE-7](https://www.economia.gob.cl/wp-content/uploads/2024/12/informe-de-resultados-ele7-final.pdf)
- La Ley 21.015 aplica a empresas y organismos públicos con 100+ trabajadores (cuota del 1%), y en enero 2026 reportó cumplimiento el 48,8% de las empresas. — [Reporte Minero](https://www.reporteminero.cl/noticia/inclusion/2026/01/inclusion-laboral-empresas-cumplen-ley-21015-cuota-1-porciento)
- Referencia de precio: Buk cobra 0,07-0,15 UF por colaborador al mes según tramo. — [Buk/Chipax](https://info.buk.cl/chipax-buk-software-de-recursos-humanos)

### Inferences
**Ejemplo ilustrativo (todos los números marcados con (H) son supuestos propios para el pitch, no datos):**

*Producto:* módulo SaaS de contratación y retención inclusiva, con cumplimiento sustantivo de la Ley 21.015, para empresas de 100+ trabajadores.

**Bottom-up (preferido por jurados de negocios):**
- **TAM (Chile):** ~13.400 empresas grandes (proxy ELE-7; "grande" por ventas no equivale a 100+ trabajadores, ver Gaps) × precio (H) de 120 UF/año por empresa (≈10 UF/mes) ≈ **1,6 millones de UF/año**.
- **SAM:** empresas obligadas que hoy no cumplen o cumplen solo formalmente. Si el 48,8% reporta cumplimiento, ~51% no lo reporta (proxy de dolor activo) → ~6.800 empresas × 120 UF ≈ **0,82 millones de UF/año**.
- **SOM (3 años):** 1-2% del SAM (H) → 70-140 empresas × 120 UF ≈ **8.400-16.800 UF/año**.
- **Variante PEPM:** empresa promedio de (H) 300 trabajadores × 0,03 UF (H, add-on bajo la tarifa de Buk) × 12 = 108 UF/año por empresa, coherente con el supuesto de 120 UF.

**Top-down (para triangular):** ≈8,9 millones de trabajadores dependientes (SII 2015, dato antiguo) × % en empresas grandes (H) × gasto en RR.HH. tech por trabajador (H). Es menos defendible porque requiere más supuestos sin fuente.

**Expansión (no sumar al TAM principal, mencionarla como upside):** organismos públicos obligados (B2G), mercados regionales de LatAm con cuotas similares y otros grupos (mujeres, 50+, migrantes).

**Prompt para la IA:** "Construye TAM/SAM/SOM bottom-up para [producto] en Chile. Usa como datos: [pegar cifras citadas]. Marca cada supuesto con (H), da un rango conservador/base/optimista y una frase de 20 palabras para la diapositiva."

### Gaps
- No encontré el número oficial de empresas obligadas por la Ley 21.015 (100+ trabajadores). La DT debería tenerlo (registro de comunicaciones electrónicas); conviene buscarlo o preguntarlo a los mentores. Los proxies del SII y la ELE-7 clasifican por ventas, no por dotación.
- Los datos del SII por tamaño son de 2014-2015 (última actualización 2016).
- No verifiqué el valor de la UF ni encontré datos de gasto en tecnología de RR.HH. por empresa en Chile.

---

## 9. Modelos mentales y checklists críticos para evitar malas ideas (pre-mortem, mapeo de supuestos, quién paga / quién usa / quién se beneficia)

### Takeaway
Dos herramientas de 10-20 minutos cubren casi todo: el pre-mortem de Gary Klein (asumir que el proyecto ya fracasó y listar por qué) y el mapeo de supuestos de David Bland (deseabilidad, factibilidad y viabilidad en un 2×2 de importancia vs. evidencia). Se complementan con el chequeo "quién usa / quién paga / quién se beneficia", crítico en inclusión, donde esos tres actores casi nunca son la misma persona.

### Cited Findings
- **Pre-mortem (Klein, HBR 2007):** a diferencia de un análisis de riesgos, parte de que el "paciente" ya murió y pregunta qué salió mal, no qué podría salir mal. — [HBR, Performing a Project Premortem](https://hbr.org/2007/09/performing-a-project-premortem); [Wikipedia, Pre-mortem](https://en.wikipedia.org/wiki/Pre-mortem)
- Pasos comunes: el líder presenta el plan y declara que fracasó; cada persona lista razones en silencio; se recogen en ronda; la lista queda como puntos probables de falla. Puede tomar 20-30 minutos. Una variante posterior, ausente en la columna original, puntúa cada problema por probabilidad, impacto y facilidad de prevención. — [Lilach Bullock, Premortem step by step](https://www.lilachbullock.com/premortem/)
- Hay discusión sobre una cifra muy citada del pre-mortem (~30% de mejora en identificar razones de resultados futuros), que según una fuente secundaria suele citarse mal. Conviene no usarla en el pitch. — [Frameworklist, Premortem](https://frameworklist.com/frameworks/premortem)
- **Mapeo de supuestos (David J. Bland):** se listan supuestos de deseabilidad (¿lo quieren?), factibilidad (¿podemos construirlo y entregarlo?) y viabilidad (¿podemos ganar dinero?), con post-its de colores (naranja, azul y verde). Luego se ubican en un 2×2 de importante vs. no importante y con vs. sin evidencia. — [Mural, Intro to assumptions mapping](https://www.mural.co/blog/intro-assumptions-mapping); [Google Design Sprint Kit, Assumptions Mapping](https://designsprintkit.withgoogle.com/methodology/phase2-define/assumptions-mapping); [Vaughan Broderick, Assumptions Mapping](https://vaughanbroderick.com/assumptions-mapping/)
- Strategyzer agrega una cuarta categoría de "adaptabilidad" que no está en el planteamiento original de Bland. — [Strategyzer, Assumptions mapping](https://www.strategyzer.com/library/how-assumptions-mapping-can-focus-your-teams-on-running-experiments-that-matter)
- El Confidence Meter de Gilad refuerza el mismo principio: la convicción propia y la opinión de colegas valen casi cero como evidencia (≈0,1 de 10). — [Itamar Gilad](https://itamargilad.com/the-tool-that-will-help-you-choose-better-product-ideas/)
- Señal de alerta en inclusión: la crítica de que la Ley 21.015 corre el riesgo de reducirse a un "trámite anual" o a un cumplimiento formal. Las soluciones que solo ayudan a "llenar la cuota" pueden ser vistas como poco éticas o de bajo impacto. — [Reporte Minero](https://www.reporteminero.cl/noticia/inclusion/2026/01/inclusion-laboral-empresas-cumplen-ley-21015-cuota-1-porciento); [Diario Constitucional](https://www.diarioconstitucional.cl/contrapuntos/inclusion-laboral-de-las-personas-con-discapacidad-igualdad-efectiva-o-cumplimiento-formal/)

### Inferences
**Pre-mortem exprés (5 min, al cierre del bloque de 90 min):** "Es el 5 de noviembre a las 18:00 y no ganamos. ¿Por qué?" Cada uno escribe 5 razones en 2 min y la IA otra lista; se juntan, se marcan las 3 más probables y a cada una se le asigna una mitigación concreta en el plan de construcción.
- Causas típicas a revisar: demo que falla en vivo; idea "genérica de IA"; no responde al KPI del dueño; sin modelo de pago claro; impacto no medible; problema de privacidad (datos de salud o discapacidad); el jurado no entiende al usuario.

**Mapeo de supuestos exprés (7 min):** 3 supuestos por categoría (D/F/V) → ubicarlos en el 2×2 → el cuadrante "importante + sin evidencia" define (a) qué preguntarle al mentor y (b) qué decir en el pitch como "lo validaremos en el piloto con [métrica]".

**Checklist "quién usa / quién paga / quién se beneficia" (3 min):**

| Rol | ¿Quién es? | ¿Qué gana? | ¿Por qué pagaría o usaría hoy? |
|---|---|---|---|
| Usuario | (p. ej., analista de RR.HH. o candidata) | | |
| Comprador / pagador | (p. ej., gerencia de personas, sostenibilidad, Estado) | | |
| Beneficiario | (p. ej., persona con discapacidad, mujer 50+) | | |
| Bloqueador potencial | (p. ej., legal/compliance, jefaturas, sindicato) | | |

- Regla: si no se puede nombrar al pagador con cargo y presupuesto, el modelo de negocio no está listo para un jurado de FEN.

**Checklist anti-mala-idea (2 min, sí/no):**
1. ¿Mueve el KPI del dueño del desafío?
2. ¿El beneficiario es un grupo desatendido identificable (ODS 8.5/10.2)?
3. ¿Hay un pagador claro?
4. ¿Se demuestra end-to-end en ≤90 s?
5. ¿La IA es esencial, o es "IA de adorno"?
6. ¿Evita el cumplimiento cosmético ("contratar para la foto")?
7. ¿Maneja con cuidado los datos sensibles (salud, discapacidad, origen)?
8. ¿No es la primera idea obvia que tendrán 10 equipos?
9. ¿Se puede pilotear en 30 días con el dueño del desafío?
10. ¿Puede explicarse en una frase sin jerga?

Con menos de 8 "sí", volver al top 3 de ideas.

### Gaps
- No pude leer el texto completo del artículo HBR de Klein (la cita de pasos viene de una fuente secundaria consistente con el resumen de Wikipedia).
- No encontré una fuente formal del chequeo "quién usa / quién paga / quién se beneficia"; es síntesis de práctica común en modelos B2B2C.
- Calidad de fuentes: varias de las guías de hackathon (HackerEarth, Reskilll, TSL) son blogs de plataformas con interés comercial, y sus recomendaciones no vienen de datos sobre rúbricas. Úsenlas como heurísticas, no como evidencia.
