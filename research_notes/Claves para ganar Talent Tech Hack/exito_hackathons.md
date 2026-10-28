# Factores de éxito, criterios de evaluación y errores comunes en hackathons cortas (1-2 días): negocios, impacto social y desafíos corporativos

> Notas de investigación (26-oct-2026) para un equipo de 2 personas, sin programación, que usará Claude como constructor principal en "Talent Tech Hack 2026" (EmprendeFEN, FEN U. de Chile, 4-5 nov 2026; tema "personas, inclusión y mercado laboral"; 3 desafíos de industria revelados el día 1; Día 1 construcción 9:00-16:30, Día 2 15:00-18:00).
> Advertencia de calidad: gran parte de la literatura práctica sobre "cómo ganar hackathons" son blogs de vendors o SEO (Reskilll, HackerEarth, Masai, etc.). Se priorizaron fuentes de jueces con nombre, bases oficiales y papers académicos, y se marca explícitamente cuando una fuente es débil, antigua (<2022) o no pudo verificarse.

## 1. ¿Cuáles son las rúbricas típicas y sus ponderaciones? (rúbricas publicadas reales, incluidas latinoamericanas/chilenas)

### Takeaway
No existe una rúbrica estándar: Devpost y MLH dejan los criterios a cada evento. El patrón recurrente son 4-6 criterios (innovación/originalidad, impacto/relevancia del problema, factibilidad/viabilidad, ejecución técnica/prototipo, modelo de negocio, pitch), a menudo con pesos iguales o con el "problema/impacto" y la "innovación" pesando 20-40% cada uno. En las bases chilenas y de concursos de emprendimiento, los criterios de negocio (oportunidad, modelo de negocio, escalabilidad, equipo) pesan mucho más que en hackathons de ingeniería.

### Cited Findings

**Plataformas y organizadores globales**
- Devpost no impone una rúbrica: cada hackathon define sus criterios y pesos en las reglas oficiales ("Judges & Criteria"). Ejemplo Okta en Devpost: una primera etapa pasa/no pasa de viabilidad mínima, y luego los finalistas se juzgan con criterios de igual peso (creatividad/originalidad e implementación, incluyendo cuántas funciones del sponsor se usaron). — [Okta Developer Forum](https://devforum.okta.com/t/what-are-the-judging-criteria-for-the-hackathon/15842)
- MLH (Hackathon Organizer Guide, "Judging Plan") no define criterios ni pesos. Recomienda "stack ranking": cada juez elige su top 3 (3, 2 y 1 puntos) y se suman los puntos de todos los jueces para normalizar entre jueces más o menos generosos. Luego se revisa el top 3-5 y se hace un control anti-trampa a los ganadores. — [MLH Organizer Guide – Judging Plan](https://guide.mlh.com/general-information/judging-and-submissions/judging-plan.md)
- MLH recomienda formato "feria de ciencias" (los jueces recorren las mesas), unos 4 min por proyecto (2 de demo, 1 de preguntas y puntaje, 1 de traslado), al menos 3 jueces por proyecto, y una final de unos 7 min por equipo (3-5 de presentación). Instruye a los jueces a mantener "only 3 minutes per team" y a privilegiar el aprendizaje y la creatividad sobre el potencial comercial. — [MLH Organizer Guide – Judging Plan](https://guide.mlh.com/general-information/judging-and-submissions/judging-plan.md)
- UH CodeRED (reglas basadas en MLH): cuatro criterios de igual peso, uno de ellos "Technology" (qué tan impresionante es técnicamente). — [UHCodeRED rules (GitHub)](https://github.com/UHCodeRED/rules)
- DiamondHacks 2021 (estilo MLH, ingeniería) prioriza las demos en vivo sobre el pitch y declara que no se juzga la calidad del pitch ni de la idea, sino lo construido. — [DiamondHacks21 Judging Criteria (GitHub)](https://github.com/annaowens/DiamondHacks21/blob/master/Judging%20Criteria.md)
- HackTheU (HackerEarth) usa Originality, Difficulty, Impact y Polish, pero aclara que los jueces pueden decidir finalmente "por intuición". — [HackTheU rules (HackerEarth)](https://www.hackerearth.com/challenges/hackathon/hacktheu-2/rules)
- UHack (hackathon universitaria con componente de negocio; sin año en la página): Business Model Canvas 15%, App 50% (UX, accesibilidad, enfoque técnico, estructura; si no hay app funcional se aceptan diseños de concepto detallados), Pitch Video de 3 min 15%, Innovation 10% y Potential for Impact 10% (alineado a temas de investigación de la universidad). El video de pitch es la principal vía de los jueces para evaluar todo lo demás. — [UHack Guide – Judging](https://uhack-guide.readthedocs.io/en/latest/event-info/judging/)
- Builderbase Hackathon Playbook: sugiere una escala de 20 puntos con cuatro criterios iguales, y que los eventos con foco de negocio integren potencial de mercado y modelo de negocio en el criterio de "impact and viability". — [Builderbase Playbook Ch. 15 – Judging rubrics](https://intercom.help/builderbase/en/articles/14831464-hackathon-playbook-ch-15-judging-rubrics)
- Guía de vendor (fuente débil): rúbrica "típica" de 5 criterios con innovación, implementación técnica e impacto en ~20-25% cada uno, demo/presentación 15-20% y completitud 10-15% (basada en hackathons de India, como SIH). — [Reskilll – What Hackathon Judges Look For](https://blogs.reskilll.com/?p=436)
- Mario Ottmann (fundador de la consultora de IA Gravitas y ex AI Ambassador de Google; ene-2026) sugiere pensar el pitch de una hackathon de IA como ~40% innovación técnica, ~40% ajuste problema-solución/viabilidad de negocio y ~20% demo. Menciona como factores de puntaje la IA responsable, la conciencia regulatoria (GDPR, EU AI Act) y un camino creíble a producción. Son estimaciones del autor, no una rúbrica oficial. — [Ottmann – AI Hackathons 2026 guide](https://marioottmann.com/articles/ai-hackathon-bucerius-2026-guide)

**Hackathons de impacto social (pesos publicados)**
- #LondonNeeds (2017, antigua): Social Impact 25%, Creativity 25%, Scalability 20%, Functionality 20%, Quality 10%. La escalabilidad se entiende como "¿funciona fuera de la hackathon?". Los pesos vienen del resumen del buscador; la página de jueces no los mostró al abrirla. — [HackerEarth #LondonNeeds](https://www.hackerearth.com/challenges/hackathon/londonneeds-powered-by-smartlondon/judges/)
- UST D3CODE Hackathon'24: en la fase de idea, impacto 30 puntos, escalabilidad 10 y factibilidad 10. En la fase de prototipo, completitud 40, alcance 25 y UX 15. — [UST D3CODE'24 evaluation criteria](https://www.hackerearth.com/challenges/hackathon/ust-d3code-campus-hackathon24/custom-tab/evaluation-criteria)
- Metro North Health, scorecard de hackathon de impacto social (2026): 7 criterios en escala 1-5 (total 35), entre ellos "Potential for sustainability" (¿puede seguir después de la hackathon?). — [Metro North social impact hackathon judging (PDF)](https://metronorth.health.qld.gov.au/extranet/wp-content/uploads/sites/10/2026/02/social-impact-hackathon-judging.pdf)
- AnitaB.org AI Hackathon: el impacto social vale 10 puntos, con subpreguntas sobre escalabilidad y "cambio medible" para las personas directamente afectadas. — [AnitaB AI Hackathon Judging Criteria](https://membership.anitab.org/page/AIHackathonJudgingCriteria)
- Ashoka evalúa sostenibilidad, escalabilidad, replicabilidad, cambio sistémico y mentalidad, sin pesos publicados. — [Ashoka (PDF)](https://www.ashoka.org/media/77323/download)
- Premio de innovación del BID: cuatro criterios (pertinencia del desafío, carácter innovador, impacto con costo-efectividad, utilidad del conocimiento para otros proyectos), evaluados por un panel de expertos externos y del BID. No es una hackathon, pero refleja el lenguaje evaluativo del BID. — [BID – noticia premio agencias ejecutoras](https://www.iadb.org/es/noticias/bid-reconoce-las-agencias-ejecutoras-de-los-proyectos-que-financia-con-el-premio)

**Chile y Latinoamérica**
- USACH "Ready, Set Hack" (Depto. Ingeniería Informática USACH + NTT DATA Chile, 2024): la propuesta se evalúa por creatividad, capacidad de respuesta al problema, factibilidad y simplicidad. El extracto no mostraba pesos. — [Bases Ready Set Hack (USACH)](https://array.diinf.usach.cl/storage/bases_ready_set_hack.pdf)
- Hackathon ACHS (Chile, 2021; salud mental y teletrabajo): cinco criterios (producto, oportunidad, modelo de negocio, equipo y pitch), cada uno con nota de 1 a 5. El PDF hoy da 404; el dato viene del extracto del buscador. — [Bases legales Hackathon ACHS](https://hackathon.achs.cl/base/Bases%20legales%20Hackathon.pdf)
- UDD, Facultad de Economía y Negocios (concurso de emprendimiento PEE 2021, no hackathon): jurado de exalumnos destacados de la FEN UDD; los criterios ponderados incluyen "Inspiración" 20% y "Escalabilidad" 30%. La versión 2023 define "Innovación" como grado de novedad y originalidad, con profesores en el jurado. — [Bases PEE 2021 UDD](https://negocios.udd.cl/files/2022/03/BASES-PEE-2021_Final.pdf); [Bases PEE 2023 UDD](https://negocios.udd.cl/files/2023/05/bases-pee-categoria-emprendedor-udd-2023.pdf)
- CORFO Semilla Expande 2022 (programa de startups, no hackathon): notas de 1,00 a 5,00; innovación pesa 40% y equipo 30%, con subcriterios como relevancia de mercado y plan de expansión. — [CORFO criterios Semilla Expande 2022 (PDF)](https://corfo.cl/sites/cpp/wp-content/uploads/2025/05/criteriosevaluacionsemillaexpande2022.pdf)
- CORFO O'Higgins 2022: evaluación en dos etapas (revisión técnica previa y luego "Demo Day" ante 3 jueces), con notas de 1 a 5. — [CORFO criterios PRAE O'Higgins 2022 (PDF)](https://corfo.cl/sites/cpp/wp-content/uploads/2025/06/criteriosdeevaluacionpraeohiggins2022.pdf)
- FEN U. de Chile ya tiene bases de concursos de pitch, por ejemplo "Concurso Pitch UChile – Banco Santander", firmado digitalmente en ago-2023 desde un correo @fen.uchile.cl. No se pudo extraer el texto del PDF (comprimido). — [Bases concurso Pitch UChile Banco Santander](https://pregrado.fen.uchile.cl/wp-content/uploads/2023/08/Bases-concurso-Pitch-UChile_Banco-Santander.pdf)
- Ejemplos hispanos con pesos explícitos: la hackathon de la Universidad de Burgos 2026 asigna 15% a cada criterio; la EcoHackUC24 (Cantabria) asigna 50% a la "calidad del proyecto presentado". — [Bases hackatón 2026 UBU](https://www2.ubu.es/catedra_michelin/sites/www2.ubu.es.catedra_michelin/files/imgs_ubu/Bases_hackaton_2026.pdf); [EcoHackUC 2024 bases](https://ecohackuc.unican.es/wp-content/uploads/2024/09/2024_Bases-del-concurso.pdf)
- Mobbeel Innovation Challenge (empresa, España, 2024): "Originalidad" 20%, cada criterio en escala 1-5. — [Bases Mobbeel Innovation Challenge](https://mobbeel.com/wp-content/uploads/2024/09/Bases-Legales-Mobbeel-Innovation-Challenge.pdf)
- UMaza (Argentina), Hackathon EduTech 360: innovación, aplicabilidad pedagógica, viabilidad técnica, impacto y pitch, con máximo 4 puntos cada uno (pesos iguales). — [Bases Hackathon EduTech 360 (UMaza)](https://www.umaza.edu.ar/archivos/BASES%20Y%20CONDICIONES-Hackathon%20EduTech%20360.pdf)
- UCSG (Ecuador, 2026), hackathon de investigación con datos: comunicación y pitch valen 10 de 100 puntos. — [Rúbrica de evaluación UCSG](https://www.ucsg.edu.ec/wp-content/uploads/2026/08/Rubrica-de-evaluacion.pdf)

**Lo que opinan los participantes (dato antiguo)**
- Según EventFlare, citando una encuesta de Devpost: 52% de los participantes cree que los jueces deberían priorizar creatividad e innovación y 28% el impacto potencial. Es opinión de participantes, posiblemente de ~2015 y no verificada. — [EventFlare – Crafting Effective Hackathon Judging Criteria](https://eventflare.io/journal/crafting-effective-hackathon-judging-criteria-a-step-by-step-guide)

### Inferences
- Para una hackathon en una facultad de negocios con desafíos de empresas, la combinación más probable es parecida a la ACHS/UDD/CORFO más un componente de prototipo: problema/oportunidad, innovación, impacto (social y para la empresa), factibilidad/modelo de negocio, prototipo/demo y pitch/equipo. Conviene preparar una respuesta explícita para cada uno.
- Como varias rúbricas usan escalas 1-5 con pesos iguales, ningún criterio puede quedar en 1-2. Un equipo "bueno en todo" suele ganarle a uno brillante en un eje y débil en otro (coincide con la observación de Kurbaitaev de que casi todos quedan en la mitad del rango, ver pregunta 2).
- El stack ranking de MLH significa que no basta un buen puntaje: hay que estar en el top 3 de cada juez. Lo memorable y diferenciador pesa más que en un promedio simple.

### Gaps
- No se encontraron bases públicas ni rúbrica de "Talent Tech Hack 2026" (EmprendeFEN), ni ediciones previas. El buscador no devolvió ninguna página del evento. La FEN sí publica bases de otros concursos y la U. de Chile listó en 2026 una "Hackatón Uchile – Amazon Breaking Barriers" ([Convocatorias pasadas UChile](https://uchile.cl/extension-y-cultura/oportunidades-uchile/convocatorias-pasadas)). **Acción: pedir la rúbrica a EmprendeFEN antes del 4-nov.**
- No se encontraron bases de hackathons de BID Lab, Fundación Chile, Start-Up Chile, PUC ni UAI con pesos explícitos. Las búsquedas solo devolvieron otros concursos de esas instituciones.
- Los PDFs de la SII, FEN-Santander, UDD 2023, UTP 2026 y Venture4Impact 2026 (Weatherhead) no pudieron leerse (texto comprimido o imagen).
- Un resumen de búsqueda atribuía a Fundación Copec "Aplica tu Idea" (2020) los pesos relevancia del problema 30%, innovación 25%, consistencia 15% y respaldo científico-tecnológico 15%, pero no se pudo identificar la URL de origen. Tratarlo como no verificado.

## 2. ¿Qué hacen distinto los equipos ganadores?

### Takeaway
Según jueces de 2026, lo que separa a los ganadores no está en la rúbrica. Pesan una demo que funciona de punta a punta, una primera frase que dice qué hace el producto y para quién, un alcance estrecho bien ejecutado, y la alineación con lo que quiere quien entrega el premio ("¿si premio esto, mi empresa queda bien?"). La evidencia académica añade que la preparación previa y las metas alcanzables fijadas temprano se asocian a mejores resultados.

### Cited Findings
- Magomed Kurbaitaev (juez en tres eventos de julio 2026, entre ellos MLH x DigitalOcean "AI for Social Good"): la mayoría de los equipos queda en la mitad del rango de la rúbrica, y los ganadores se separan por factores que la rúbrica no nombra. Los jueces comparan contra las demos que acaban de ver, no contra un ideal. — [Kurbaitaev, "What Judges Actually Score" (DEV, 2026)](https://dev.to/kurbaitaev/what-judges-actually-score-notes-from-a-year-of-hackathon-judging-3p4l)
- Kurbaitaev identifica tres diferenciadores. (1) Una demo en vivo de punta a punta le gana "almost every time" a un proyecto más ambicioso mostrado solo en slides. (2) Los equipos fuertes abren con una frase simple de qué hace el producto y para quién; los débiles abren con contexto y pierden un tercio de su tiempo. (3) Los proyectos acotados y bien hechos puntúan consistentemente más alto: la señal es el criterio bajo restricciones, no la ambición. — [Kurbaitaev (DEV, 2026)](https://dev.to/kurbaitaev/what-judges-actually-score-notes-from-a-year-of-hackathon-judging-3p4l)
- Kurbaitaev también señala lo que NO movió los puntajes: pulido más allá de lo legible, elección de framework o stack, tamaño del equipo o credenciales, y slides más allá de una captura de respaldo. — [Kurbaitaev (DEV, 2026)](https://dev.to/kurbaitaev/what-judges-actually-score-notes-from-a-year-of-hackathon-judging-3p4l)
- Las preguntas que hacía como juez: ¿para quién es, específicamente?, ¿qué parte construyeron durante el evento?, ¿qué se rompe primero al escalar? Nombrar una debilidad concreta subía el puntaje. — [Kurbaitaev (DEV, 2026)](https://dev.to/kurbaitaev/what-judges-actually-score-notes-from-a-year-of-hackathon-judging-3p4l)
- Jueces de la JetBrains x Codex Hackathon (jun-2026): hay que liderar con el problema y hacer que la audiencia lo sienta antes de mostrar la solución (Jono Bacon, Stateshift); ser claro en el problema y en cómo lo resuelve la entrega (Avi Press, Scarf). La preparación empieza antes de programar, con una lectura atenta de las reglas y del espacio del problema (Jan-Niklas Wortmann, JetBrains). — [JetBrains Blog, "How to Win a Hackathon: Notes From the Judging Table" (2026)](https://blog.jetbrains.com/ai/2026/06/how-to-win-a-hackathon-notes-from-the-judging-table/) (resumido vía búsqueda; la página dio 403 al abrirla)
- Del mismo artículo: enfocarse en una sola funcionalidad bien hecha; "un proyecto más simple con una demo clara y segura le gana a uno complejo y confuso"; partir de un problema que uno haya vivido y no de la herramienta de moda. Bonnie Xu (OpenAI) sugiere preguntarse qué se puede construir hoy que antes no era posible. — [daily.dev resumen del artículo JetBrains](https://daily.dev/posts/how-to-win-a-hackathon-notes-from-the-judging-table-wttxezbgq)
- Ray Deck (ganó varias hackathons en 2022; post de nov-2022): los proyectos ganadores respondían una pregunta, "If I reward this project, will my company look good?". El tema y la alineación con el sponsor importan más que la calidad técnica: "The sponsor is like a customer or a market". Su integración web3 para Hellosign perdió contra una entrada de IA alineada con la tendencia del momento. — [Ray Deck, "Lessons from Winning Five Hackathons" (2022)](https://sustained.substack.com/p/lessons-from-winning-five-hackathons)
- Deck: "You can only win if you deliver before the deadline"; hay que recortar ideas y features temprano ("cut bone to ship") para que el final sea solo pulir. El video o demo es la puerta de entrada de los jueces y suele usarse en el anuncio de ganadores, así que debe hacer quedar bien al sponsor. — [Ray Deck (2022)](https://sustained.substack.com/p/lessons-from-winning-five-hackathons)
- En el caso Infosys InStep BizHacks (24 h: idear una solución tecnológica a un problema de negocio, escribir un plan de negocio y presentar a un jurado), el equipo ganador, liderado por un MBA, se centró en viabilidad, deseabilidad y factibilidad, y destacó la sostenibilidad aunque no era criterio formal. — [Zicklin/Baruch news](https://zicklin.baruch.cuny.edu/zicklin_news/zicklin-mba-students-pull-all-nighter-to-win-infosys-global-business-challenge/)

**Evidencia académica**
- Nolte, Chounta y Herbsleb (2020, Proc. ACM HCI/CSCW), "What Happens to All These Hackathon Projects?": la continuidad de corto plazo se asocia a preparación técnica, número de tecnologías usadas y haber ganado. La de largo plazo depende de la diversidad de habilidades del equipo, la capacidad técnica relativa a las tecnologías y la intención de ampliar el alcance. La actividad intensiva de corto plazo se asoció a menor continuidad a largo plazo. — [Nolte et al. 2020 (NSF PAR)](https://par.nsf.gov/servlets/purl/10284449)
- Estudio de acción sobre mentoría (Nolte, Hayden y Herbsleb): los equipos que se apropiaron de su proyecto, fijaron metas alcanzables temprano y construyeron vínculo con su mentor, recibiendo apoyo orientado al aprendizaje, reportaron percepciones positivas de su proyecto. — [NSF PAR (URL según resultado de búsqueda; no se abrió el PDF)](https://par.nsf.gov/servlets/purl/10339913)
- Tesis de Alar Leemet (supervisada por Nolte), hackathon corporativa multisede de dos ediciones: la preparación, la relación del proyecto con activos existentes de la empresa y entregar prototipos funcionales aparecen como factores posibles de continuidad. — [Hackathons for Corporate Innovation – a Longitudinal Study (U. Tartu)](https://dspace.ut.ee/items/b83e06fb-b3e1-49c8-8f4e-04251bd15296/full)
- Tesis de Demchuk (U. Tartu, 2019): analizó unas 2.000 hackathons y más de 60.000 proyectos de Devpost con ML (incluido XGBoost) para predecir ganadores, superando una línea base de sentido común. No se pudieron extraer los predictores concretos. — [Häkatonide tulemuste ennustamine masinõppe abil (U. Tartu)](https://dspace.ut.ee/items/7b94a26a-d54b-4db7-b034-7d46c819a2fd)
- Un estudio de Hackster.io sobre 104 competencias y 5.863 proyectos de IoT describe los criterios de juicio como subjetivos, lo que hace difícil predecir ganadores. — [Data-Driven Strategies for Winning IoT Challenges](https://hu.edu.ye/hu-publications/journals/index.php/hujnas/ar/article/view/664)

### Inferences
- Para un desafío corporativo, la pregunta de Deck se traduce en: "¿si la empresa X premia esto, puede mostrarlo internamente o a la prensa como algo que mejora su KPI de inclusión o talento?". La propuesta debe nombrar el KPI de la empresa dueña del desafío.
- El hallazgo de Leemet (relación con activos existentes) sugiere construir sobre lo que la empresa ya tiene (sus datos, canales, programas de inclusión) en lugar de proponer algo que la obligue a empezar de cero.
- La regla práctica que combina Kurbaitaev y JetBrains: una frase de identidad del producto escrita antes de construir, y un único flujo de punta a punta que funcione.

### Gaps
- No hay estudios académicos que aíslen causalmente qué hace ganar en hackathons de negocios o de impacto social. La literatura académica se centra sobre todo en continuidad de proyectos, no en ganar.
- No se encontraron retrospectivas de ganadores de hackathons universitarias chilenas con detalle táctico.

## 3. ¿Cuáles son los errores más comunes?

### Takeaway
Los errores que más repiten los jueces son no dejar claro el problema, sobredimensionar el alcance y terminar sin demo funcional, abrir el pitch con contexto o con detalles técnicos, gastar la demo en el stack, responder vagamente quién es el usuario, pasarse del tiempo, y no leer ni re-leer las bases y la rúbrica.

### Cited Findings
- Según los jueces de JetBrains x Codex (2026), el error más común es no declarar claramente el problema que se resuelve. — [daily.dev resumen JetBrains](https://daily.dev/posts/how-to-win-a-hackathon-notes-from-the-judging-table-wttxezbgq)
- Errores observados por Kurbaitaev (2026): diagramas de arquitectura con componentes sin terminar; gastar el tiempo de demo en decisiones de stack; respuestas vagas sobre quién es el usuario o qué se construyó durante el evento; proyectos con varias funciones pero sin un centro claro, que los jueces no logran recordar después. — [Kurbaitaev (DEV, 2026)](https://dev.to/kurbaitaev/what-judges-actually-score-notes-from-a-year-of-hackathon-judging-3p4l)
- Ottmann (2026) lista: leer las slides textualmente, exceso de jerga, no tener un enunciado claro del problema, demo frágil, pasarse del tiempo, roles poco claros y no tener un factor "so what?". — [Ottmann (2026)](https://marioottmann.com/articles/ai-hackathon-bucerius-2026-guide)
- Ray Deck (2022): muchos participantes hacen grandes promesas y no entregan. No cumplir las reglas básicas (demo funcional, video, plazo) puede dejar a un equipo sin premio: "las reglas son un filtro, no un ranking". — [Ray Deck (2022)](https://sustained.substack.com/p/lessons-from-winning-five-hackathons)
- Recopilación de guías: ignorar el tema o las reglas, una idea demasiado ambiciosa ("la ambición mata más equipos que el mal código"), mala gestión del tiempo, no hacer demo en vivo, no prepararse para las preguntas (¿en qué se diferencia de las alternativas?, ¿qué harían con más tiempo?) y no re-leer la rúbrica durante el evento. Son fuentes de blog o vendor. — [Reskilll – How to Win a Hackathon in 2026](https://reskilll.com/blogs/how-to-win-a-hackathon-in-2026-reskillls-guide-from-5000-events/); [WhereUElevate](https://whereuelevate.com/blogs/how-to-prepare-for-hackathons-and-win); [PlacementPreparation](https://www.placementpreparation.io/blog/?p=17721)
- Terence Eden (2019, antigua): la demo es lo más importante; no bombardear con slides; no pasarse del tiempo. — [Terence Eden, "How to present at a hack day"](https://shkspr.mobi/blog/2019/11/how-to-present-at-a-hack-day/)
- Hablar "alrededor" de una funcionalidad que no existe se nota; ser franco sobre los vacíos se lee como confianza (atribuido al artículo de JetBrains 2026 en el resumen del buscador). — [JetBrains Blog (2026)](https://blog.jetbrains.com/ai/2026/06/how-to-win-a-hackathon-notes-from-the-judging-table/)
- Advertencia desde Chile: sin estrategia de negocio ni forma de medir valor alineada con la estrategia de la empresa, las hackathons producen "experimentos de bajo impacto" desconectados de resultados (María Francisca Yáñez, directora de empresas, DF, sep-2024). — [DF Lab Opinión, "¿Chile en modo hackathon?"](https://www.df.cl/df-lab/innovacion-y-startups/df-lab-opinion-chile-en-modo-hackathon)
- Error específico de la era IA: delegar la lluvia de ideas a un LLM, acumular funciones que el equipo no sabe explicar, diseño genérico "de un prompt" y voz en off generada por IA (ver pregunta 7). — [Simonean, HackerNoon (ene-2026)](https://hackernoon.com/from-the-judges-seat-standing-out-in-hackathons-in-the-age-of-ai)

### Inferences
- Para un equipo de negocios, los errores probables son simétricos a los de ingenieros: en vez de "pitch demasiado técnico", "pitch de puro deck/consultoría sin nada funcionando", o un modelo de negocio genérico sin conexión con el desafío.
- No responder "¿por qué ahora?" (qué hace posible hoy la IA que antes no) y "¿por qué ustedes?" se conecta con la pregunta de Bonnie Xu y con el criterio "equipo" de ACHS y CORFO.

### Gaps
- No se encontraron cifras cuantitativas (por ejemplo, el porcentaje de equipos que no termina la demo) de fuentes confiables.

## 4. ¿Cómo dividir roles y gestionar ~7,5 h de construcción más un segundo día de pitch (equipo de 2)?

### Takeaway
Las guías convergen en un reparto aproximado de 10% planificación, 55-60% construcción, 15% integración y pruebas, y 15-17% preparación de demo y pitch. Además: un flujo de punta a punta funcionando a mitad del tiempo, congelar funcionalidades ~1 h antes del cierre, y una demo de respaldo grabada. No se encontró una plantilla específica para equipos de 2 personas.

### Cited Findings
- Ottmann (2026), para un evento de 24 h: planificación e ideación ~2 h (8%), desarrollo central ~14 h (58%), integración y pruebas ~4 h (17%), preparación y ensayo de demo ~4 h (17%). En las primeras 4 h, 30 min cada uno para explorar el problema, idear, evaluar factibilidad y diseñar. En las últimas 4 h solo pulir, sin features nuevas. Antes del evento, 4-6 h de preparación de entorno y plantillas. — [Ottmann (2026)](https://marioottmann.com/articles/ai-hackathon-bucerius-2026-guide)
- Otra plantilla reparte ~10% planificación, 60% desarrollo central, 15% integración y 15% pulido y demo. Recomienda checkpoints (qué debe funcionar al almuerzo, a media tarde y en la última hora) y congelar funcionalidades una hora antes del cierre. — [GitScrum – hackathon projects](https://docs.gitscrum.com/en/how-to/how-to-use-gitscrum-for-hackathon-projects)
- Kurbaitaev (2026): tener un camino de punta a punta funcionando a la mitad del tiempo; ensayar en voz alta los primeros 30 segundos; grabar un screencast de 60 s como respaldo por si falla el Wi-Fi; preparar una respuesta honesta sobre qué se rompe primero. — [Kurbaitaev (DEV, 2026)](https://dev.to/kurbaitaev/what-judges-actually-score-notes-from-a-year-of-hackathon-judging-3p4l)
- Builderbase Playbook (agenda de un día, 8-10 h): puertas 8:30, apertura y equipos en la primera hora, construcción desde ~10:00, almuerzo ~12:00, checkpoint "faltan 2 horas" a las 15:00. — [Builderbase Playbook Ch. 14 – Schedule design](https://intercom.help/builderbase/en/articles/14831458-hackathon-playbook-ch-14-schedule-design)
- Pitch de 3 min sugerido por Ottmann: hook 20 s (problema concreto, no presentar al equipo), problema 30 s (por qué fallan las soluciones actuales, impacto cuantificado), solución 40 s, demo en vivo 60 s, aspectos técnicos 20 s, impacto y próximos pasos 10 s. Preparar 5-7 preguntas probables y ensayar las transiciones entre oradores. Probar el montaje y la red 30 min antes y tener respaldos offline (grabación, respuestas cacheadas). — [Ottmann (2026)](https://marioottmann.com/articles/ai-hackathon-bucerius-2026-guide)
- Tácticas de demo de jueces JetBrains (2026): algo funcionando "dentro de ~90 segundos", formularios pre-llenados, llamadas lentas a APIs simuladas (mock), mostrar la perspectiva del usuario y no el código, y ensayar el pitch en voz alta con cronómetro. — [daily.dev resumen JetBrains](https://daily.dev/posts/how-to-win-a-hackathon-notes-from-the-judging-table-wttxezbgq)
- Tener a alguien operando la demo mientras otro narra. — [Reskilll – Demo & presentation tips](https://blogs.reskilll.com/hackathon-demo-presentation-tips-pitch-3-minutes-win-2026/) (vendor)
- En una final típica estilo MLH, cada equipo tiene 3-5 min de presentación (unos 7 min por equipo con el cambio). En la ronda de feria, ~2 min de demo más 1 de preguntas por juez. — [MLH Judging Plan](https://guide.mlh.com/general-information/judging-and-submissions/judging-plan.md)
- Nolte et al.: las metas alcanzables fijadas temprano se asociaron a percepciones positivas de los equipos. — [NSF PAR (estudio de mentoría)](https://par.nsf.gov/servlets/purl/10339913)

### Inferences (propuesta adaptada, síntesis propia)
- **Día 1 (9:00-16:30 = 450 min):**
  - 9:00-9:45, entender y elegir el desafío (~10%): escuchar los 3 desafíos, preguntar a la empresa dueña sobre KPIs y restricciones (ver pregunta 6), elegir uno y escribir la frase de identidad ("X ayuda a [usuario específico] a [resultado] midiendo [KPI de la empresa]").
  - 9:45-12:45, construcción del flujo central con Claude (~40%). Hito duro a las 12:45: un flujo de punta a punta que funciona, aunque sea feo.
  - 12:45-14:45, una o dos mejoras de mayor impacto en la demo, datos de ejemplo realistas y pre-cargados, y validación rápida con 2-3 personas o mentores (~27%).
  - 14:45-15:30, congelar funcionalidades, grabar un video de respaldo de 60-90 s y capturas (~10%).
  - 15:30-16:30, borrador del pitch y del modelo de negocio o impacto, y primer ensayo cronometrado (~13%).
- **Roles para 2 personas:**
  - Persona A, "Builder/Producto": dirige a Claude, prueba el flujo y cuida la demo.
  - Persona B, "Negocio/Pitch": investiga el problema con la empresa y los mentores, arma los números (tamaño de mercado, costo-beneficio, KPI), el deck y el guion, y hace de usuario de prueba.
  - Se reúnen 5 min cada hora para revisar el alcance contra la frase de identidad.
  - Ambos deben poder explicar el producto entero: los jueces penalizan no entender lo propio (ver pregunta 7).
- **Entre días y Día 2 (15:00-18:00):** si las reglas lo permiten, usar la mañana del día 2 para pulir el pitch y no para agregar funcionalidades. Llegar temprano y probar el proyector y la red 30 min antes. Llevar respaldo offline. Ensayar Q&A con 5-7 preguntas probables: ¿quién es el usuario?, ¿qué construyeron hoy?, ¿qué se rompe primero?, ¿por qué ahora?, ¿por qué ustedes?, ¿cómo lo paga la empresa?, ¿cómo miden el impacto en inclusión?

### Gaps
- No se sabe si las bases de Talent Tech Hack permiten seguir trabajando entre el cierre del día 1 (16:30) y el día 2, ni la duración del pitch. Hay que confirmarlo con la organización.
- No se encontraron plantillas de run-of-show publicadas por equipos ganadores de 2 personas. Las plantillas encontradas son de organizadores o guías genéricas.

## 5. ¿En qué se diferencian las hackathons de escuelas de negocios de las de ingeniería en lo que premian los jueces?

### Takeaway
Las hackathons de ingeniería (MLH/Devpost) premian explícitamente lo construido, la dificultad técnica y la creatividad, y MLH pide a sus jueces privilegiar el aprendizaje sobre el potencial comercial. Las de negocios, y los concursos de emprendimiento chilenos, pesan mucho más el caso de negocio: oportunidad, mercado, disposición a pagar, modelo de negocio, escalabilidad, equipo y pitch. El prototipo funciona como prueba de factibilidad, no como fin.

### Cited Findings
- MLH instruye a los jueces a enfocarse en aprendizaje y creatividad por sobre el potencial comercial. — [MLH Judging Plan](https://guide.mlh.com/general-information/judging-and-submissions/judging-plan.md)
- DiamondHacks21 (ingeniería): no se juzga la calidad del pitch ni de la idea, sino lo construido. — [DiamondHacks21 Judging Criteria](https://github.com/annaowens/DiamondHacks21/blob/master/Judging%20Criteria.md)
- NUS Business Hackathon 2022: profundidad analítica, claridad, estrategia creativa y efectiva, y comunicación, con un CEO de la industria en el jurado. — [NUS BizBeat](https://bizbeat.nus.edu.sg/?p=6443)
- Competencia i2i (Beacom School of Business, U. South Dakota): peso social del problema, comprensión del mercado objetivo, disposición a pagar del cliente, factibilidad, ventaja competitiva y proyecciones financieras. — [USD Beacom i2i](https://www.usd.edu/academics/colleges-and-schools/beacom-school-of-business/south-dakotan-business/beacom-school-of-business-annual-i2i-competition-set-for-april-14)
- Concurso de planes de negocio Riata (Oklahoma State): puntaje repartido en partes iguales entre calidad de la idea, mercado y competencia, operaciones y finanzas, con pesos menores para el trabajo escrito y la impresión general. — [OSU Riata scoring criteria](https://business.okstate.edu/riata/business_plan_judging_scoring_criteria.html)
- Jurado de la hackathon Chubb/UNSW 2023: atención especial al caso de negocio, porque "una solución sin caso de negocio no es implementable". — [UNSW 2023 Chubb/UNSW Data Science Hub Hackathon](https://www.unsw.edu.au/news/2023/06/2023-chubb-unsw-data-science-hub-hackathon)
- Cornell Business Model Hackathon: 26 equipos de trasfondos académicos y profesionales mixtos; la diversidad se trató como ventaja. — [Cornell SC Johnson – Business Model Hackathon](https://business.cornell.edu/hub/2019/05/24/cloud-systems-business-model-hackathon) (2019, antigua)
- MBA Hackathon de EDHEC: 2 h para un desafío real de una organización internacional; el ganador se definió por voto de los estudiantes MBA. — [EDHEC MBA Hackathon](https://www.edhec.edu/en/news/mba-hackathon-global-mba-students-solve-real-life-challenges-top-international-organisations)
- Chile: ACHS 2021 evalúa producto, oportunidad, modelo de negocio, equipo y pitch (1-5 cada uno); UDD FEN (PEE) pondera escalabilidad 30% e inspiración 20%; CORFO pondera innovación 40% y equipo 30%. — [ACHS](https://hackathon.achs.cl/base/Bases%20legales%20Hackathon.pdf); [UDD PEE 2021](https://negocios.udd.cl/files/2022/03/BASES-PEE-2021_Final.pdf); [CORFO Semilla Expande](https://corfo.cl/sites/cpp/wp-content/uploads/2025/05/criteriosevaluacionsemillaexpande2022.pdf)
- UHack (híbrida): el Business Model Canvas vale 15% y debe mostrar necesidad, clientes, propuesta única, canal, cómo se cubren los costos y "ventaja injusta" del equipo; la app vale 50%. — [UHack Guide](https://uhack-guide.readthedocs.io/en/latest/event-info/judging/)
- Ottmann (2026) estima, sin fuente, que los equipos fuertes en lo técnico y en negocio puntúan "2-3x más". Es una opinión no verificada. — [Ottmann (2026)](https://marioottmann.com/articles/ai-hackathon-bucerius-2026-guide)

### Inferences
- En la FEN es razonable esperar un jurado mixto (académicos, empresas dueñas de los desafíos, ecosistema EmprendeFEN), que premiará la claridad del caso de negocio y del impacto tanto como el prototipo. El prototipo hecho con IA sirve para pasar de "idea" a "factible y demostrado".
- Ventaja comparativa del equipo: estudiantes de negocios con un prototipo funcional cubren ambos ejes, mientras que muchos competidores de la FEN probablemente lleguen solo con slides y otros solo con tecnología.
- Para el tema "inclusión y mercado laboral" conviene traer métricas de impacto concretas (por ejemplo, tiempo de colocación, tasa de retención, cumplimiento de la Ley 21.015 de inclusión laboral) más métricas de negocio para la empresa (costo de rotación, tiempo de contratación).

### Gaps
- No se encontraron rúbricas de hackathons de escuelas de negocios latinoamericanas (FEN UChile, UAI, PUC Business School) con pesos explícitos.
- No hay estudios comparativos formales entre jueces de hackathons de negocios y de ingeniería.
- La referencia a la Ley 21.015 es conocimiento de contexto y no se verificó en esta investigación.

## 6. ¿Cómo aprovechar a mentores y a la empresa dueña del desafío durante el evento?

### Takeaway
Mentores y sponsors son un recurso subutilizado. Las recomendaciones son preguntarles por sus dolores, KPIs y restricciones reales antes de proponer soluciones (presentarles marcos de problema primero), usar sus reacciones para decidir si seguir o pivotar, y alinear el resultado con lo que la empresa podría mostrar como logro propio.

### Cited Findings
- Un mentor y juez recomienda enfocarse en los dolores de los mentores y no presentarles soluciones terminadas, porque mostrar soluciones demasiado temprano sesga el problema. Las hackathons temáticas suelen traer personas que pueden describir el problema en detalle. — [e27, mentor/judge perspective (2019)](https://e27.co/how-to-do-well-in-a-hackathon-a-mentor-and-judges-perspective-20190901/) (resumen de búsqueda; la página dio 403; fuente antigua)
- Un equipo ganador cuenta que los mentores suelen pasarse por alto aunque su retroalimentación puede ser crítica. — [HackerNoon, "A challenge, a team and 24 hours"](https://hackernoon.com/a-challenge-a-team-and-24-hours-2ecf886336ad)
- Construir rapport con los sponsors sin excederse, usar sus reacciones para mantener o pivotar la idea, y calificar para varios tracks de sponsor a la vez. — [Push to Prod, "How To Win Hackathons"](https://getpushtoprod.substack.com/p/how-to-win-hackathons)
- En las hackathons corporativas (1-2 días) los mentores circulan durante el trabajo, suele haber un check-in de retroalimentación a mitad del evento, y las soluciones no siempre necesitan tecnología nueva. — [Hackathon.com – How to organize a corporate hackathon](https://corporate.hackathon.com/articles/how-to-organize-a-hackathon-a-step-by-step-guide-for-corporate-teams)
- Ray Deck: hay que tratar al sponsor como cliente o mercado y preguntarse qué valora. — [Ray Deck (2022)](https://sustained.substack.com/p/lessons-from-winning-five-hackathons)
- Nolte, Hayden y Herbsleb: los vínculos sociales con el mentor y el apoyo orientado al aprendizaje se asociaron a percepciones positivas del proyecto. — [NSF PAR](https://par.nsf.gov/servlets/purl/10339913)
- Tesis Leemet/Nolte: relacionar el proyecto con activos existentes de la empresa aparece como factor de continuidad. — [U. Tartu](https://dspace.ut.ee/items/b83e06fb-b3e1-49c8-8f4e-04251bd15296/full)
- DF (2024): las hackathons corporativas deben conectarse con la estrategia de la empresa y con métricas de valor, o quedan como experimentos de bajo impacto. — [DF Lab Opinión](https://www.df.cl/df-lab/innovacion-y-startups/df-lab-opinion-chile-en-modo-hackathon)

### Inferences
- Guion de 5 minutos para la empresa dueña del desafío (síntesis propia):
  1. ¿Qué KPI de personas o inclusión les preocupa más este año?
  2. ¿Qué intentaron antes y por qué no funcionó?
  3. ¿Qué restricciones tienen (datos personales, sistemas, presupuesto, sindicatos, regulación)?
  4. ¿Quién sería el usuario interno que lo adoptaría?
  5. ¿Qué tendría que mostrar este piloto para que lo financien?
- Volver a mitad de jornada con el flujo funcionando y preguntar "¿esto resuelve lo que nos contaron?". Así validan y además el juez de la empresa ya conoce el proyecto antes del pitch.
- Citar en el pitch, con permiso, lo que dijo la empresa ("nos contaron que el principal problema es X") es evidencia de validación con el usuario. Varias rúbricas de impacto social piden "cambio medible" y "funciona fuera de la hackathon".

### Gaps
- No se encontraron estudios cuantitativos sobre cuánto mejora el resultado interactuar con los mentores o la empresa. La evidencia es cualitativa o de autopercepción.
- No se sabe qué empresas presentarán los desafíos de Talent Tech Hack ni si estarán presentes durante la construcción del día 1.

## 7. ¿Qué rol tienen los prototipos construidos con IA en 2025-2026 y qué diferencia a los equipos cuando todos usan IA?

### Takeaway
En 2026 la IA es la línea base, no el diferenciador: casi todos construyen con IA, así que la complejidad técnica pesa menos. Los jueces diferencian por el problema elegido (específico y propio, no "genérico de LLM"), por cuánto entiende el equipo lo que construyó, por un diseño y una presentación auténticos (voz y cara propias), por una demo robusta y por un uso responsable de la IA. No se encontró ninguna política oficial de un gran organizador que penalice el uso de IA.

### Cited Findings
- Abgar Simonean (ingeniero de software y juez voluntario; HackerNoon, 5-ene-2026): las ideas generadas por IA siguen un patrón reconocible, una "bland variation" de conceptos conocidos. Los proyectos de un solo prompt (por ejemplo, con Lovable) se ven pulidos pero genéricos y restan autenticidad. Una voz en off generada por IA se valora peor que la voz y la cara del presentador. Los jueces notan cuando el equipo no tiene un modelo mental claro de su proyecto, y las slides pulidas no lo esconden. — [Simonean, "From the Judge's Seat: Standing Out in Hackathons in the Age of AI" (HackerNoon, 2026)](https://hackernoon.com/from-the-judges-seat-standing-out-in-hackathons-in-the-age-of-ai)
- Simonean recomienda hacer la lluvia de ideas uno mismo (problemas propios o de amigos), personalizar la UI/UX en lugar de aceptar el diseño de un prompt, presentar en persona y poder explicar cada parte. Para él la autenticidad es "the new gold standard". No está contra la IA: pide usarla con propósito. — [Simonean (HackerNoon, 2026)](https://hackernoon.com/from-the-judges-seat-standing-out-in-hackathons-in-the-age-of-ai)
- En Hacker News, un comentarista que ha sido juez dice que el volumen de entregas creció y que juzgar se volvió en gran parte juzgar la calidad de la herramienta que usaron. El vibe coding funciona bien para front-end y convence menos en proyectos complejos. — [Ask HN: Are hackathons still worth doing?](https://hn.nuxt.dev/item/47077312) (opinión anónima)
- En la "Vibe Coding Olympics" (PromptLayer, 2026) todo debía construirse con IA y se juzgó "purely on vibes". El organizador sostiene que, cuando la barrera para construir baja tanto, la complejidad técnica deja de ser el diferenciador. — [PromptLayer blog](https://blog.promptlayer.com/we-hosted-the-first-vibe-coding-olympics/)
- Guías SEO de 2026 afirman que "la IA ya no es el diferenciador, es la línea base", que los jueces "han visto cien GPT wrappers" y que los jueces ven 30-100 demos en un día. Son fuentes débiles, y el resumen del buscador no permite saber cuál de las dos dice cada frase. — [Masai School – How to win an AI Hackathon in 2026](https://www.masaischool.com/blog/how-to-win-an-ai-hackathon-in-2026-full-guide/); [Reskilll – Hackathon ideas that won 2026](https://blogs.reskilll.com/hackathon-ideas-that-won-2026-judges-actually-pick-examples/)
- Ottmann (2026) recomienda un enfoque híbrido: constructores de apps con IA (v0, Lovable, Replit) para la UI y el andamiaje, más lógica propia encima (~60% herramientas, ~40% custom). Menciona IA responsable, privacidad (GDPR/EU AI Act) y un camino creíble a producción como factores de puntaje. — [Ottmann (2026)](https://marioottmann.com/articles/ai-hackathon-bucerius-2026-guide)
- Jueces JetBrains x Codex (2026): elegir un problema vivido por uno mismo y no la herramienta de moda. Bonnie Xu (OpenAI): preguntarse qué se puede construir ahora que antes no era posible. — [daily.dev resumen JetBrains](https://daily.dev/posts/how-to-win-a-hackathon-notes-from-the-judging-table-wttxezbgq)
- Kurbaitaev (2026): el framework o stack no movió los puntajes, pero sí preguntar "¿qué parte construyeron durante el evento?". — [Kurbaitaev (DEV, 2026)](https://dev.to/kurbaitaev/what-judges-actually-score-notes-from-a-year-of-hackathon-judging-3p4l)
- Chile: en la primera hackathon de OpenAI en Latinoamérica, realizada en Chile, ganó un equipo del Poder Judicial con una propuesta apoyada en IA para una justicia más eficiente. Es decir, ganó el dominio del problema más la IA, no la IA sola. — [DF Lab Opinión (2024)](https://www.df.cl/df-lab/innovacion-y-startups/df-lab-opinion-chile-en-modo-hackathon)
- En temas sociales, algunas guías mencionan un estándar alto de uso responsable de IA generativa y protección de datos del usuario. — [resumen de búsqueda, guías 2026 (fuente débil)](https://www.masaischool.com/blog/how-to-win-an-ai-hackathon-in-2026-full-guide/)

### Inferences
- Para un equipo sin programación que usa Claude, el riesgo no es usar IA sino parecer genérico o no entender lo construido. Mitigaciones:
  - El problema y el insight vienen de la conversación con la empresa y de usuarios reales, no de pedirle ideas a Claude.
  - Personalizar la UI con la marca o el contexto del desafío.
  - Ambos integrantes deben poder explicar cómo funciona por dentro (qué datos usa, qué hace el modelo, qué pasa si se equivoca).
  - Presentar con voz propia.
- En un tema de inclusión laboral, tratar de forma visible los riesgos de la IA (sesgo en selección de personal, privacidad de datos de candidatos, accesibilidad para personas con discapacidad) puede ser un diferenciador de credibilidad ante jueces de negocios y RR.HH. Es inferencia, apoyada en que varias fuentes citan la IA responsable como factor.
- Ser transparente sobre el uso de IA ("lo construimos con Claude en X horas; esto es mock y esto es real") encaja con el consejo de franqueza sobre los vacíos y con la pregunta "¿qué construyeron hoy?".

### Gaps
- No se encontró ninguna política oficial de MLH, Devpost ni de universidades chilenas sobre la evaluación de proyectos generados con IA. Tampoco datos cuantitativos sobre cómo cambian los puntajes según el uso de IA.
- Las bases de la UTP 2026 (Perú) podrían incluir reglas sobre IA, pero el PDF no fue legible.
- No se sabe si Talent Tech Hack exige código propio, repositorio público o declaración de uso de IA. Hay que confirmarlo en las bases.
