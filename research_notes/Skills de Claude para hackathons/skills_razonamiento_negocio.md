# Skills y plugins de Claude existentes para razonamiento, ideación, producto, estrategia de negocio, impacto social y RR.HH. (shortlist para Talent Tech Hack 2026)

Notas de investigación al 26-oct-2026. Datos de estrellas y fecha de último push obtenidos de la API de GitHub ese día. Los "installs" vienen de la API de búsqueda de skills.sh (`https://skills.sh/api/search?q=...`), consultada el mismo día. Contenido de cada SKILL.md leído directamente desde raw.githubusercontent.com salvo que se marque "NO VERIFICADO".

---

## 1. Brainstorming e ideación (superpowers brainstorming, design thinking, SCAMPER, how-might-we, Crazy 8s)

### Takeaway
La skill de brainstorming más popular (obra/superpowers) **no es ideación divergente**: es un flujo para aclarar requisitos, que termina en un documento de diseño y en un plan de implementación pensado para software. Para un equipo sin programadores que necesita generar y descartar ideas rápido, encajan mejor (1) `product-brainstorming` del plugin oficial `product-management` de Anthropic y (2) `danium/lateral-thinking`, un router con SCAMPER, Six Hats, Worst Idea y Provocation. No encontré ninguna skill verificada de "Crazy 8s".

### Cited Findings
**Ranking propuesto (de mejor a peor encaje para la hackathon):**

1. **anthropics/knowledge-work-plugins → plugin `product-management` → skill `product-brainstorming`**
   - Repo oficial de Anthropic: 33.157 estrellas, último push 2026-10-26, licencia Apache-2.0. Está "construido para Claude Cowork, también compatible con Claude Code" — [README](https://github.com/anthropics/knowledge-work-plugins)
   - Instalación en Claude Code: `claude plugin marketplace add anthropics/knowledge-work-plugins` y luego `claude plugin install product-management@knowledge-work-plugins` (el README da como ejemplo `sales@knowledge-work-plugins`) — [README](https://github.com/anthropics/knowledge-work-plugins)
   - Qué instruye: actuar como "sharp product thinking partner" que cuestiona supuestos. Tiene modos Problem Exploration (preguntar "¿quién tiene el problema y qué hace hoy?", separar síntomas de causas raíz), Solution Ideation ("generate at least 5-7 distinct approaches before evaluating", incluir una opción "do the opposite" y otra que quite algo) y Assumption Testing. Técnicas: constraint removal, analogías, inversión, descomposición y user hat-switching — [SKILL.md](https://github.com/anthropics/knowledge-work-plugins/blob/main/product-management/skills/product-brainstorming/SKILL.md)
   - 5.684 installs en skills.sh — [skills.sh API "brainstorming"](https://skills.sh/api/search?q=brainstorming)
   - Sin scripts. Pero el plugin trae un `.mcp.json` con conectores MCP HTTP remotos (Slack, Linear, Asana, monday, ClickUp, Atlassian, Notion, Figma, Amplitude…), que pedirán autenticación si se usan — [.mcp.json](https://github.com/anthropics/knowledge-work-plugins/blob/main/product-management/.mcp.json)
   - El plugin también incluye: competitive-brief, metrics-review, roadmap-update, sprint-planning, stakeholder-update, synthesize-research, write-spec y el comando `/brainstorm` — [carpeta product-management](https://github.com/anthropics/knowledge-work-plugins/tree/main/product-management)

2. **danium/lateral-thinking** (de Bono para agentes)
   - 329 estrellas, MIT, último push 2026-09-13. Tiene 10 SKILL.md y ningún script — [repo](https://github.com/danium/lateral-thinking)
   - La skill `lateral` es un router con tabla de síntomas. "Ideas all feel the same" lleva a random-stimulus; "constraint feels unbreakable" a provocation; "solving the wrong problem" a concept-fan; "one idea and need variations" a scamper; "everyone agrees too fast" a six-hats; "everything feels timid" a worst-idea. Elige exactly one technique y la ejecuta en línea — [lateral/SKILL.md](https://github.com/danium/lateral-thinking/blob/HEAD/skills/lateral/SKILL.md)
   - `scamper` recorre las 7 transformaciones en orden fijo y requiere una idea existente ("not for blank-page ideation") — [scamper/SKILL.md](https://github.com/danium/lateral-thinking/blob/HEAD/skills/scamper/SKILL.md)
   - Instalación: `npx skills add danium/lateral-thinking`, o `/plugin marketplace add danium/lateral-thinking` + `/plugin install lateral-thinking@lateral-thinking` — [README](https://github.com/danium/lateral-thinking)
   - scamper: 324 installs (la skill SCAMPER más instalada en skills.sh) — [skills.sh API "SCAMPER"](https://skills.sh/api/search?q=SCAMPER)

3. **phuryn/pm-skills → plugin `pm-product-discovery`** (`brainstorm-ideas-new`, `brainstorm-experiments-new`, `identify-assumptions-new`, `prioritize-assumptions`)
   - `brainstorm-ideas-new` (46 líneas): 5 ideas desde cada perspectiva (PM, Product Designer, Software Engineer). Luego prioriza el top 5 por "core value delivery, speed to validate, differentiation" y lista supuestos a testear — [SKILL.md](https://github.com/phuryn/pm-skills/blob/main/pm-product-discovery/skills/brainstorm-ideas-new/SKILL.md)
   - 3.314 installs (brainstorm-ideas-new) y 3.039 (brainstorm-ideas-existing) — [skills.sh API "ideation"](https://skills.sh/api/search?q=ideation)

4. **product-on-purpose/thinking-framework-skills** (`think-brainwriting`, `think-question-burst`, `think-scamper`, `think-role-storming`, `think-far-analogy-ideation`, `think-problem-restatement`, `think-morphological-analysis`)
   - 22 estrellas, Apache-2.0, push 2026-10-26: muy nuevo y poco adoptado. Anuncia 63 frameworks con "evidence tier" — [repo](https://github.com/product-on-purpose/thinking-framework-skills)
   - Instalación: `/plugin marketplace add product-on-purpose/agent-plugins` + `/plugin install thinking-framework-skills@product-on-purpose`, o `npx skills add product-on-purpose/thinking-framework-skills` — [README](https://github.com/product-on-purpose/thinking-framework-skills)
   - La skill "how might we" más cercana que encontré: `product-on-purpose/pm-skills/tool-design-sprint-map-and-target` (620 installs) y `think-problem-restatement` (11 installs). Contenido NO VERIFICADO — [skills.sh API "how might we"](https://skills.sh/api/search?q=how%20might%20we)

5. **obra/superpowers → `brainstorming`** (la más popular, encaje bajo para ideación de negocio)
   - Repo: 305.462 estrellas, MIT, push 2026-10-23 — [repo](https://github.com/obra/superpowers). Skill con 406.528 installs — [skills.sh API "brainstorming"](https://skills.sh/api/search?q=brainstorming)
   - Está en el marketplace oficial de Anthropic `claude-plugins-official` (categoría "development") — [marketplace.json](https://github.com/anthropics/claude-plugins-official/blob/main/.claude-plugin/marketplace.json)
   - Qué instruye: "You MUST use this before any creative work… in software or out of it (a talk, a business, a renovation)". Hace una pregunta abierta a la vez. Expone 2-3 enfoques y recomienda uno. Escribe un design doc en `docs/superpowers/specs/YYYY-MM-DD-<topic>-design.md`, "committed", pide aprobación y luego invoca `superpowers:writing-plans`. Ofrece un "Visual Companion" que abre una pestaña del navegador con mockups — [SKILL.md](https://github.com/obra/superpowers/blob/main/skills/brainstorming/SKILL.md)
   - Scripts ejecutables: `skills/brainstorming/scripts/server.cjs`, `start-server.sh`, `stop-server.sh`, `helper.js` (servidor local del visual companion). El plugin además instala un hook `SessionStart` que ejecuta `hooks/run-hook.cmd session-start` e inyecta el contenido de `using-superpowers` en cada sesión — [hooks.json](https://github.com/obra/superpowers/blob/main/hooks/hooks.json), [session-start](https://github.com/obra/superpowers/blob/main/hooks/session-start)

Otras opciones encontradas, menos recomendadas:
- `bmad-code-org/BMAD-METHOD` `bmad-brainstorming`: 12.110 installs; repo de 54.578 estrellas, orientado a desarrollo ágil con IA — [skills.sh](https://skills.sh/api/search?q=brainstorming), [repo](https://github.com/bmad-code-org/BMAD-METHOD)
- `wondelai/skills` `design-sprint` (5.463 installs), en el plugin `product-innovation@wondelai-skills` — [skills.sh "jobs to be done"](https://skills.sh/api/search?q=jobs%20to%20be%20done), [marketplace.json](https://github.com/wondelai/skills/blob/HEAD/.claude-plugin/marketplace.json)
- Six Thinking Hats sueltas: `guia-matthieu/clawfu-skills/six-thinking-hats` (248 installs), contenido NO VERIFICADO — [skills.sh "six thinking hats"](https://skills.sh/api/search?q=six%20thinking%20hats)
- Design thinking IDEO/d.school de 5 fases: `melodic-software/claude-code-plugins/design-thinking`, listado en claudemarketplaces.com. Repo con 28 estrellas; contenido NO VERIFICADO — [listado](https://claudemarketplaces.com/skills/melodic-software/claude-code-plugins/design-thinking), [repo](https://github.com/melodic-software/claude-code-plugins)

### Inferences
- Para los primeros 45-60 minutos del día 1 (decodificar desafíos y generar ideas), la combinación `product-brainstorming` + `lateral` cubre divergencia y desbloqueo sin scripts ni hooks.
- Superpowers no conviene a un equipo no-técnico en modo ideación. Obliga a un ritual (design doc commiteado en git, writing-plans), su hook se activa en todas las sesiones y su visual companion levanta un servidor local. Solo tiene sentido si van a construir un prototipo de código, e incluso así agrega fricción en 7,5 h.
- El usuario ya tiene skills locales propias (`analizar-desafio`, `negocio-e-impacto`, etc.) con descripciones que se solapan con estas. Instalar demasiadas skills con triggers parecidos puede hacer que Claude cargue la equivocada.

### Gaps
- No hay skill verificada de **Crazy 8s**. La búsqueda en skills.sh devolvió rate-limit (HTTP 429) en "crazy 8s" y no apareció en ningún otro índice consultado.
- No verifiqué el contenido de las skills de design thinking de melodic-software ni de six-thinking-hats de clawfu.

---

## 2. Pensamiento crítico y toma de decisiones (first principles, pre-mortem, matriz de decisión, devil's advocate, red-team, mental models)

### Takeaway
Las más útiles y verificadas para "atacar la idea antes que el jurado" son `strategy-red-team` y `pre-mortem` de phuryn/pm-skills: alta adopción, cortas y orientadas a negocio. La sigue `the-fool` de Jeffallan, un devil's advocate de 5 modos. El catálogo más serio de mental models es `tjboudreaux/cc-thinking-skills` (28 skills con router y evals). Dos salvedades: todas sus skills tienen `disable-model-invocation: true`, así que el usuario debe invocarlas a mano, y su `thinking-red-team` es de seguridad de código, no de ideas.

### Cited Findings
1. **phuryn/pm-skills → `pm-execution/strategy-red-team`**
   - Qué instruye: extraer todas las afirmaciones del plan y separar las "load-bearing" de las cosméticas. Hacer "Steelman, then attack" y redactar cada falla como "Fails if ___". Rankear por impacto × probabilidad × lo barato que es testearla. "Never invent a weakness the plan doesn't have". Para cada supuesto devuelve la evidencia a conseguir esta semana, el kill criteria y el test más barato (72 líneas) — [SKILL.md](https://github.com/phuryn/pm-skills/blob/main/pm-execution/skills/strategy-red-team/SKILL.md)
   - 9.252 installs — [skills.sh "red team strategy"](https://skills.sh/api/search?q=red%20team%20strategy)
2. **phuryn/pm-skills → `pm-execution/pre-mortem`**
   - Imagina el lanzamiento a 14 días y que falla. Clasifica los riesgos en Tigers (reales), Paper Tigers (exagerados) y Elephants (no discutidos), y luego en launch-blocking, fast-follow o track — [SKILL.md](https://github.com/phuryn/pm-skills/blob/main/pm-execution/skills/pre-mortem/SKILL.md)
   - 10.188 installs, la pre-mortem más instalada — [skills.sh "pre-mortem"](https://skills.sh/api/search?q=pre-mortem)
   - Repo phuryn/pm-skills: 27.391 estrellas, MIT, push 2026-10-16. Sus únicos .py son de validación y tests del repo (`validate_plugins.py`, `tests/`), no de las skills — [repo](https://github.com/phuryn/pm-skills)
   - Instalación: `claude plugin marketplace add phuryn/pm-skills` + `claude plugin install pm-execution@pm-skills` (hay 9 plugins: pm-toolkit, pm-product-strategy, pm-product-discovery, pm-market-research, pm-data-analytics, pm-marketing-growth, pm-go-to-market, pm-execution, pm-ai-shipping). Las skills cargan automáticamente o se fuerzan con `/plugin-name:skill-name` — [README](https://github.com/phuryn/pm-skills)
3. **Jeffallan/claude-skills → `the-fool`**
   - "Use when challenging ideas, plans, decisions, or proposals… devil's advocate, run a pre-mortem, red team, or audit evidence and assumptions". Flujo: reformula la postura del usuario como tesis steelmanned, elige modo con `AskUserQuestion`, presenta los 3-5 desafíos más fuertes y espera respuesta antes de sintetizar una posición reforzada (125 líneas) — [SKILL.md](https://github.com/jeffallan/claude-skills/blob/HEAD/skills/the-fool/SKILL.md)
   - 4.381 installs — [skills.sh "devils advocate"](https://skills.sh/api/search?q=devils%20advocate)
   - El repo (12.072 estrellas, MIT) tiene 67 skills casi todas de desarrollo, además de 15 scripts y hooks del repo. Conviene instalar solo esta skill con `npx skills add jeffallan/claude-skills --skill the-fool` (el CLI admite `--skill` y `-a claude-code`) — [repo](https://github.com/jeffallan/claude-skills), [vercel-labs/skills README](https://github.com/vercel-labs/skills)
4. **tjboudreaux/cc-thinking-skills** (28 skills: first-principles, pre-mortem, second-order, steel-manning, socratic, reversibility, opportunity-cost, probabilistic, systems, cynefin, jobs-to-be-done, via-negativa, TRIZ, OODA, theory-of-constraints…)
   - 1.674 estrellas, MIT, push 2026-08-07. Se describe como "28 eval-informed mental models" — [repo](https://github.com/tjboudreaux/cc-thinking-skills)
   - Instalación: `/plugin marketplace add tjboudreaux/cc-thinking-skills` + `/plugin install thinking-skills@thinking-skills-marketplace`, o `npx skills add tjboudreaux/cc-thinking-skills`. El README pide leer la "catalog audit" antes de hacer claims de rendimiento — [README](https://github.com/tjboudreaux/cc-thinking-skills/blob/HEAD/README.md)
   - Router `thinking-model-router`: clasifica el problema (Diagnose / Decide / Understand / Create / Evaluate / Predict / Optimize), elige NONE o 1 skill (máximo 3) y puntúa la idoneidad con pesos (problem fit 30 %…) — [SKILL.md](https://github.com/tjboudreaux/cc-thinking-skills/blob/HEAD/skills/thinking-model-router/SKILL.md)
   - `thinking-pre-mortem`: marco de falla en pasado, top 3-5 riesgos concretos, invertir las condiciones en requisitos de prevención con dueño y checkpoint — [SKILL.md](https://github.com/tjboudreaux/cc-thinking-skills/blob/HEAD/skills/thinking-pre-mortem/SKILL.md)
   - Todas las skills revisadas (router, first-principles, red-team, steel-manning, jobs-to-be-done, reversibility, pre-mortem) declaran `disable-model-invocation: true`. Además, `thinking-red-team` es "for authorized security review of code, auth, or APIs" — [first-principles](https://github.com/tjboudreaux/cc-thinking-skills/blob/HEAD/skills/thinking-first-principles/SKILL.md), [red-team](https://github.com/tjboudreaux/cc-thinking-skills/blob/HEAD/skills/thinking-red-team/SKILL.md)
   - El repo trae harness de evals en JS (`evals/`, `experiments/`), que no forma parte de las skills — [repo tree](https://github.com/tjboudreaux/cc-thinking-skills)
   - Installs: thinking-first-principles 708, thinking-pre-mortem 660, thinking-triz 593 — [skills.sh "first principles"](https://skills.sh/api/search?q=first%20principles), [skills.sh "pre-mortem"](https://skills.sh/api/search?q=pre-mortem)
5. **anthropics/skills → `discernment-nudge`** (oficial)
   - Después de una respuesta sustantiva (plan, pitch, estimaciones, recomendación de negocio) agrega 2-3 preguntas cortas para verificar hechos, cuestionar el razonamiento y notar contexto faltante. Lo hace como máximo una vez por conversación (209 líneas) — [SKILL.md](https://github.com/anthropics/skills/blob/main/skills/discernment-nudge/SKILL.md)
   - Repo anthropics/skills: 183.924 estrellas, push 2026-10-09 — [repo](https://github.com/anthropics/skills)
6. **mattnowdev/thinking-partner**
   - 219 estrellas, MIT, push 2026-03-31. Una sola skill (321 líneas) más referencias `model-catalog.md` y `thinking-diagnostics.md`, con "150+ mental models". Su trigger es muy amplio ("Even casual phrases like 'what do you think about...'… should trigger") — [SKILL.md](https://github.com/mattnowdev/thinking-partner/blob/HEAD/skills/thinking-partner/SKILL.md)
   - 536 installs; instalación con `npx skills add mattnowdev/thinking-partner` — [skills.sh "thinking partner"](https://skills.sh/api/search?q=thinking%20partner), [repo](https://github.com/mattnowdev/thinking-partner)
7. **product-on-purpose/thinking-framework-skills** (63 frameworks con evidence tier)
   - Incluye think-premortem, think-red-team-light, think-swot, think-eisenhower-moscow-pareto, think-pairwise-comparison, think-minimax-regret, think-expected-value-decision-tree, think-fermi-estimation, think-issue-tree, think-pyramid-principle, think-what-would-have-to-be-true, think-ethical-matrix, think-veil-of-ignorance-reasoning y el router think-framework-advisor — [repo](https://github.com/product-on-purpose/thinking-framework-skills)
   - `think-red-team-light` declara su límite: "an AI red team is constructed, role-played dissent… does not match genuine dissent (Nemeth)" — [SKILL.md](https://github.com/product-on-purpose/thinking-framework-skills/blob/HEAD/skills/think-red-team-light/SKILL.md)
   - El repo tiene 114 archivos de script en `tests/` y `scripts/`, que son tooling del repo — [repo](https://github.com/product-on-purpose/thinking-framework-skills)
8. Mental models alternativos de baja adopción: `cyperx84/claude-skills-mental-models` (23 estrellas, MIT, 21 modelos con fuentes) — [repo](https://github.com/cyperx84/claude-skills-mental-models)

Matriz de decisión / priorización (ver también la sección 4): `phuryn/pm-skills/prioritization-frameworks` tiene 9.949 installs y `deanpeters/.../prioritization-advisor` 3.060 — [skills.sh "prioritization"](https://skills.sh/api/search?q=prioritization)

### Inferences
- Para la **defensa ante el jurado (día 2)**, el orden natural es: `strategy-red-team` sobre el pitch → `pre-mortem` → `the-fool` en modo devil's advocate para ensayar preguntas.
- `cc-thinking-skills` requiere que el equipo sepa qué slash-command escribir (p. ej. `/thinking-skills:thinking-first-principles`), porque Claude no las invocará solo. Para no-programadores esto es una barrera, aunque el contenido es de buena calidad.
- `thinking-partner` puede dispararse de más por su descripción tan amplia, y competir con las skills locales del equipo.

### Gaps
- No verifiqué la "catalog audit" de cc-thinking-skills (`analysis/AUDIT.md`), así que no puedo afirmar mejoras medidas.
- No encontré una skill verificada de "decision matrix" ponderada como tal. Los equivalentes más cercanos son think-pairwise-comparison, think-linear-model-aggregation y prioritization-advisor.

---

## 3. Encuadre de problemas e investigación de usuarios (personas, JTBD, síntesis de entrevistas, empathy maps, customer journey)

### Takeaway
Para encuadrar el problema, la opción más rigurosa es `deanpeters/Product-Manager-Skills`: problem-framing-canvas (MITRE), jobs-to-be-done, proto-persona y customer-journey-map. Son skills interactivas, pero tienen un modo "Best guess" rápido; su licencia es CC BY-NC-SA. Para artefactos visuales de UX en pocos minutos, la mejor es `Owl-Listener/designer-skills`, plugin `design-research` (empathy-map, journey-map, user-persona, interview-script, affinity-diagram). Para sintetizar entrevistas sirve `synthesize-research` (oficial Anthropic) y, para validar sin sesgo, `mom-test` (wondelai).

### Cited Findings
1. **deanpeters/Product-Manager-Skills**
   - 7.687 estrellas, push 2026-10-16, v0.84, 77 skills — [repo/README](https://github.com/deanpeters/Product-Manager-Skills)
   - **Licencia CC BY-NC-SA 4.0** (no comercial) — [LICENSE](https://github.com/deanpeters/Product-Manager-Skills/blob/main/LICENSE)
   - Instalación: en Claude Code, `/plugin marketplace add deanpeters/Product-Manager-Skills` + `/plugin install product-manager-skills@pm-skills`. Para Claude Desktop/Web hay ZIPs (pm-skills-starter-pack.zip, 02-discovery-pack.zip, 03-strategy-pack.zip…) que se suben como skills individuales — [README](https://github.com/deanpeters/Product-Manager-Skills)
   - `problem-framing-canvas` (480 líneas): guía el MITRE Problem Framing Canvas en 3 fases ("Look Inward"…) — [SKILL.md](https://github.com/deanpeters/Product-Manager-Skills/blob/main/skills/problem-framing-canvas/SKILL.md)
   - `jobs-to-be-done` (391 líneas): jobs funcionales, sociales y emocionales, pains y gains — [SKILL.md](https://github.com/deanpeters/Product-Manager-Skills/blob/main/skills/jobs-to-be-done/SKILL.md)
   - `proto-persona` (347 líneas) — [SKILL.md](https://github.com/deanpeters/Product-Manager-Skills/blob/main/skills/proto-persona/SKILL.md)
   - Protocolo común `workshop-facilitation`: modos Guided (una pregunta por turno), Context dump y Best guess ("infer missing details and label assumptions"), además de un "Fast path" para salida en un solo paso. Cierra con una lista "Assumptions to Validate" — [workshop-facilitation/SKILL.md](https://github.com/deanpeters/Product-Manager-Skills/blob/main/skills/workshop-facilitation/SKILL.md)
   - Installs: customer-journey-map 2.999 y customer-journey-mapping-workshop 2.721 — [skills.sh "customer journey"](https://skills.sh/api/search?q=customer%20journey)
2. **Owl-Listener/designer-skills → plugin `design-research`** (y `ux-strategy`)
   - 3.108 estrellas, MIT, push 2026-09-05, 111 skills. `design-research` incluye affinity-diagram, empathy-map, interview-script, jobs-to-be-done, journey-map, summarize-interview, survey-design, user-persona y usability-test-plan. `ux-strategy` incluye business-design, competitive-analysis, experience-map, north-star-vision, opportunity-framework, service-blueprint y stakeholder-alignment — [repo](https://github.com/Owl-Listener/designer-skills)
   - Instalación: `/plugin marketplace add Owl-Listener/designer-skills` + `/plugin install design-research@designer-skills`. El README menciona también un marketplace `Owl-Listener/inclusive-design-skills` (NO VERIFICADO) — [README](https://github.com/Owl-Listener/designer-skills)
   - `empathy-map` (40 líneas): cuadrantes Says/Thinks/Does/Feels (Dave Gray, XPLANE) más Goals y Pain Points. Advierte "Best created from actual research data, not assumptions" — [SKILL.md](https://github.com/Owl-Listener/designer-skills/blob/HEAD/design-research/skills/empathy-map/SKILL.md)
   - Installs: empathy-map 2.082, journey-map 2.139, user-persona 2.092, affinity-diagram 2.071, summarize-interview 2.034 — [skills.sh "empathy map"](https://skills.sh/api/search?q=empathy%20map), [skills.sh "user personas"](https://skills.sh/api/search?q=user%20personas), [skills.sh "interview synthesis"](https://skills.sh/api/search?q=interview%20synthesis)
   - Sus 7 scripts (build/check/generate) son tooling del repo — [repo](https://github.com/Owl-Listener/designer-skills)
3. **anthropics/knowledge-work-plugins → `synthesize-research`**: convierte notas de entrevistas, encuestas y tickets en temas rankeados por frecuencia e impacto. Usa thematic analysis, affinity mapping y triangulación (312 líneas) — [SKILL.md](https://github.com/anthropics/knowledge-work-plugins/blob/main/product-management/skills/synthesize-research/SKILL.md)
4. **wondelai/skills → `mom-test`** (v1.4.0, 233 líneas): reglas para entrevistar sin sesgo ("talk about their life not your idea, ask about specifics in the past"), commitment y advancement — [SKILL.md](https://github.com/wondelai/skills/blob/HEAD/mom-test/SKILL.md)
   - Repo: 2.509 estrellas, MIT, push 2026-09-10. Skills basadas en libros. Plugin `product-strategy@wondelai-skills` = jobs-to-be-done, negotiation, mom-test, monetizing-innovation, lean-analytics — [repo](https://github.com/wondelai/skills), [marketplace.json](https://github.com/wondelai/skills/blob/HEAD/.claude-plugin/marketplace.json)
   - Installs: jobs-to-be-done 6.848, mom-test 5.599 — [skills.sh "jobs to be done"](https://skills.sh/api/search?q=jobs%20to%20be%20done)
5. **phuryn/pm-skills → `pm-market-research`** (user-personas, customer-journey-map, market-segments, user-segmentation, sentiment-analysis, competitor-analysis) y `pm-product-discovery` (interview-script, summarize-interview) — [repo](https://github.com/phuryn/pm-skills). Installs: user-personas 2.959, customer-journey-map 3.081 — [skills.sh "user personas"](https://skills.sh/api/search?q=user%20personas), [skills.sh "customer journey"](https://skills.sh/api/search?q=customer%20journey)
6. **coreyhaines31/marketingskills → `customer-research`**: 115.121 installs. Cubre entrevistas, encuestas, JTBD, personas, review mining y "Reddit mining" (308 líneas). Repo con 56.638 estrellas, MIT — [SKILL.md](https://github.com/coreyhaines31/marketingskills/blob/HEAD/skills/customer-research/SKILL.md), [skills.sh](https://skills.sh/api/search?q=jobs%20to%20be%20done)

### Inferences
- En la hackathon no habrá tiempo para entrevistas reales extensas. Las skills que trabajan con supuestos etiquetados encajan mejor: el modo Best guess de deanpeters, o `proto-persona`, que por definición parte de supuestos. Hay que presentar esos supuestos como hipótesis ante el jurado.
- El modo Guided de deanpeters (una pregunta por turno, unas 10 preguntas y unos 7-10 min por skill según su propio aviso) consume tiempo. Conviene pedir "Context dump" o "Best guess" desde el inicio.
- La licencia CC BY-NC-SA de deanpeters no impide el uso estudiantil, pero podría importar si el proyecto se comercializa después.

### Gaps
- No leí completos journey-map ni user-persona de Owl-Listener (solo empathy-map).
- No verifiqué el marketplace `Owl-Listener/inclusive-design-skills`, potencialmente relevante para el eje de inclusión.

---

## 4. Product management (PRD, alcance de MVP, priorización RICE/ICE/MoSCoW, roadmaps)

### Takeaway
Para PRD y spec, las mejores son `write-spec` (oficial Anthropic) y `create-prd` (phuryn, la más instalada de las tres que se comparan aquí). Para priorizar, `prioritization-frameworks` (phuryn) y `prioritization-advisor` (deanpeters). Para recortar alcance con mentalidad de hackathon, `mvp` de Sahil Lavingia (slavingia/skills). `alirezarezvani/claude-skills` es enorme y depende de scripts Python, lo cual es poco práctico para no-programadores.

### Cited Findings
1. **anthropics/knowledge-work-plugins → `write-spec`**: transforma un problema o idea en PRD con Problem Statement, Goals, Non-Goals, User Stories, Requirements, métricas de éxito y criterios de aceptación. Incluye un paso "Pull Context from Connected Tools" — [SKILL.md](https://github.com/anthropics/knowledge-work-plugins/blob/main/product-management/skills/write-spec/SKILL.md)
2. **phuryn/pm-skills → `pm-execution`**: create-prd (10.798 installs), prioritization-frameworks (9.949), outcome-roadmap, job-stories, user-stories, brainstorm-okrs, stakeholder-map — [repo](https://github.com/phuryn/pm-skills), [skills.sh "PRD"](https://skills.sh/api/search?q=PRD), [skills.sh "prioritization"](https://skills.sh/api/search?q=prioritization)
3. **deanpeters → `prioritization-advisor`** (462 líneas): elige el framework (RICE, ICE, value/effort…) según etapa, contexto de equipo y datos disponibles — [SKILL.md](https://github.com/deanpeters/Product-Manager-Skills/blob/main/skills/prioritization-advisor/SKILL.md). También `prd-development` (4.697 installs) y `press-release` (Working Backwards, 290 líneas) — [skills.sh "PRD"](https://skills.sh/api/search?q=PRD), [press-release](https://github.com/deanpeters/Product-Manager-Skills/blob/main/skills/press-release/SKILL.md)
4. **slavingia/skills → `mvp`** (Minimalist Entrepreneur): "Build as little as possible", con tres etapas Manual → Processized → Productized (81 líneas) — [SKILL.md](https://github.com/slavingia/skills/blob/HEAD/skills/mvp/SKILL.md)
   - Repo: 10.990 estrellas, push 2026-04-14, **sin archivo de licencia**. 10 skills: company-values, find-community, first-customers, grow-sustainably, marketing-plan, minimalist-review, mvp, pricing, processize, validate-idea. Instalación: `/plugin marketplace add slavingia/skills` + `/plugin install minimalist-entrepreneur` — [repo](https://github.com/slavingia/skills)
   - mvp: 2.776 installs — [skills.sh "MVP scope"](https://skills.sh/api/search?q=MVP%20scope)
5. **alirezarezvani/claude-skills → `product-skills@claude-code-skills`**
   - 28.757 estrellas, MIT, push 2026-10-26. El repo tiene 5.768 archivos, 465 SKILL.md y 788 .py — [repo](https://github.com/alirezarezvani/claude-skills)
   - Instalación: `/plugin marketplace add alirezarezvani/claude-skills` + `/plugin install product-skills@claude-code-skills` ("12 product skills"); también hay `c-level-skills` (28) y `business-growth-skills` — [README](https://github.com/alirezarezvani/claude-skills)
   - `product-manager-toolkit` indica ejecutar `python scripts/rice_prioritizer.py sample_features.csv --capacity 15` y `python scripts/customer_interview_analyzer.py`. Revisé `customer_interview_analyzer.py`: solo importa stdlib (re, typing, collections, json) y no tiene llamadas de red — [SKILL.md](https://github.com/alirezarezvani/claude-skills/blob/HEAD/product-team/skills/product-manager-toolkit/SKILL.md)
   - Otros scripts en product-team: persona_generator.py, assumption_mapper.py, competitive_matrix_builder.py, okr_cascade_generator.py, sample_size_calculator.py… — [repo tree](https://github.com/alirezarezvani/claude-skills/tree/HEAD/product-team/skills)
6. Otros: `RefoundAI/lenny-skills` incluye `scoping-cutting` (1.601 installs), `roadmap-prioritization` y `writing-prds`. Se instala por git clone según su README — [skills.sh "MVP scope"](https://skills.sh/api/search?q=MVP%20scope), [repo](https://github.com/RefoundAI/lenny-skills)

### Inferences
- Para la hackathon basta con `write-spec` o `create-prd` para una "ficha de MVP", `mvp` para recortar alcance y `prioritization-frameworks` para justificar ante el jurado por qué se priorizó X. RICE con números inventados suele ser cuestionado; MoSCoW o value/effort se defienden mejor con poco dato.
- Los scripts de alirezarezvani son locales y stdlib, así que el riesgo es bajo. Aun así, cada ejecución pedirá permiso y agrega pasos técnicos que el equipo no necesita.

### Gaps
- No leí `outcome-roadmap` ni `prioritization-frameworks` de phuryn en detalle.
- **Posible colisión**: phuryn y deanpeters usan el mismo nombre de marketplace `pm-skills` (`…@pm-skills`). Es probable que no puedan registrarse ambos marketplaces a la vez con ese nombre; no lo probé.

---

## 5. Estrategia de negocio (lean canvas, BMC, propuesta de valor, TAM/SAM/SOM, competencia, pricing, GTM, unit economics) y skills de startup/founder

### Takeaway
El paquete más completo y liviano para el bloque de negocio son los plugins `pm-product-strategy` + `pm-market-research` + `pm-go-to-market` de phuryn/pm-skills (lean-canvas, startup-canvas, value-proposition, business-model, pricing-strategy, market-sizing, beachhead-segment, gtm-strategy). Como complemento cuantitativo sirve `startup-business-analyst` de wshobson/agents (market sizing con 3 métodos, modelo financiero, métricas). Si se quiere aritmética reproducible de TAM/SAM/SOM, está `tam-sam-som-calculator` de deanpeters, que incluye un script Python determinista.

### Cited Findings
1. **phuryn/pm-skills → `pm-product-strategy`** (ansoff-matrix, business-model, lean-canvas, monetization-strategy, pestle-analysis, porters-five-forces, pricing-strategy, product-strategy, product-vision, startup-canvas, swot-analysis, value-proposition) — [repo](https://github.com/phuryn/pm-skills)
   - `lean-canvas` (121 líneas): problem, solution, metrics, cost structure, UVP, unfair advantage, channels, segments y revenue, organizado en 3 secciones (Product Definition, Market & Traction, Economics & Validation) — [SKILL.md](https://github.com/phuryn/pm-skills/blob/main/pm-product-strategy/skills/lean-canvas/SKILL.md)
   - `value-proposition`: plantilla JTBD de 6 partes (Who, Why, What before, How, What after, Alternatives), con ejemplo de Canva — [SKILL.md](https://github.com/phuryn/pm-skills/blob/main/pm-product-strategy/skills/value-proposition/SKILL.md)
   - `startup-canvas`: Product Strategy (9 secciones) + Business Model (costos e ingresos), presentado como alternativa a BMC y Lean Canvas (3.227 installs) — [SKILL.md](https://github.com/phuryn/pm-skills/blob/main/pm-product-strategy/skills/startup-canvas/SKILL.md), [skills.sh "startup canvas"](https://skills.sh/api/search?q=startup%20canvas)
   - pricing-strategy: 2.962 installs — [skills.sh "pricing strategy"](https://skills.sh/api/search?q=pricing%20strategy)
2. **phuryn → `pm-market-research/market-sizing`** (90 líneas): TAM top-down y bottom-up con reconciliación, SAM, SOM a 1-3 años, proyección y mapa de supuestos. "Use web search to find current market data" (2.960 installs) — [SKILL.md](https://github.com/phuryn/pm-skills/blob/main/pm-market-research/skills/market-sizing/SKILL.md), [skills.sh "market sizing"](https://skills.sh/api/search?q=market%20sizing)
3. **phuryn → `pm-go-to-market`** (beachhead-segment, competitive-battlecard, growth-loops, gtm-motions, gtm-strategy, ideal-customer-profile) — [repo](https://github.com/phuryn/pm-skills)
4. **wshobson/agents → plugin `startup-business-analyst`**
   - Repo: 41.765 estrellas, MIT, push 2026-10-26 — [repo](https://github.com/wshobson/agents)
   - Contiene las skills competitive-landscape, market-sizing-analysis, startup-financial-modeling, startup-metrics-framework y team-composition-analysis; los comandos business-case, financial-projections y market-opportunity; y el agente startup-analyst. No tiene scripts — [carpeta del plugin](https://github.com/wshobson/agents/tree/main/plugins/startup-business-analyst)
   - `market-sizing-analysis`: TAM/SAM/SOM por top-down, bottom-up y "value theory (willingness to pay)" — [SKILL.md](https://github.com/wshobson/agents/blob/HEAD/plugins/startup-business-analyst/skills/market-sizing-analysis/SKILL.md)
   - Installs: market-sizing-analysis 11.787, startup-metrics-framework 11.292, competitive-landscape 11.109 — [skills.sh "market sizing"](https://skills.sh/api/search?q=market%20sizing), [skills.sh "unit economics"](https://skills.sh/api/search?q=unit%20economics), [skills.sh "competitive analysis"](https://skills.sh/api/search?q=competitive%20analysis)
5. **deanpeters → `tam-sam-som-calculator`** (457 líneas): incluye el helper `scripts/market-sizing.py` ("does not fetch data or write files"; solo importa argparse y sys). Su "Mode 3: Autonomous Research" etiqueta cada cifra como Fact/Inference/Assumption con cita — [SKILL.md](https://github.com/deanpeters/Product-Manager-Skills/blob/main/skills/tam-sam-som-calculator/SKILL.md)
   - Otras skills de negocio en el repo: positioning-statement, finance-based-pricing-advisor, swot-analysis, pestel-analysis, porters-five-forces, ansoff-matrix, saas-economics-efficiency-metrics, acquisition-channel-advisor — [carpeta skills](https://github.com/deanpeters/Product-Manager-Skills/tree/main/skills)
6. **anthropics/knowledge-work-plugins → `competitive-brief`**: brief competitivo con mapa del panorama y matriz de features (302 líneas) — [SKILL.md](https://github.com/anthropics/knowledge-work-plugins/blob/main/product-management/skills/competitive-brief/SKILL.md)
7. **Founder / startup (basadas en libros o podcasts):**
   - `RefoundAI/lenny-skills` (1.442 estrellas, MIT, push 2026-07-16; 86 skills de Lenny's Podcast). `evaluating-startup-ideas`: "hair-on-fire problem", "why now", "path to $100M", validar con experimentos manuales — [SKILL.md](https://github.com/RefoundAI/lenny-skills/blob/HEAD/skills/evaluating-startup-ideas/SKILL.md), [repo](https://github.com/RefoundAI/lenny-skills). startup-ideation: 2.544 installs — [skills.sh "ideation"](https://skills.sh/api/search?q=ideation)
   - `wondelai/skills` plugin `strategy-growth` (crossing-the-chasm, blue-ocean-strategy, traction-eos, obviously-awesome, good-strategy-bad-strategy, cold-start-problem) y `product-innovation` (lean-startup, design-sprint…) — [marketplace.json](https://github.com/wondelai/skills/blob/HEAD/.claude-plugin/marketplace.json). lean-startup 5.790, obviously-awesome 5.686 installs — [skills.sh](https://skills.sh/api/search?q=jobs%20to%20be%20done)
   - `getagentseal/founder-playbook` (776 estrellas, MIT; 16 skills de libros: lean-startup, mom-test, traction, blue-ocean, 100m-offers…), unos 640-665 installs cada una — [repo](https://github.com/getagentseal/founder-playbook), [skills.sh "startup founder"](https://skills.sh/api/search?q=startup%20founder)
   - `coreyhaines31/marketingskills`: pricing-strategy 61.162, launch-strategy 56.040, competitor-profiling 94.678 installs — [skills.sh "pricing strategy"](https://skills.sh/api/search?q=pricing%20strategy), [skills.sh "go-to-market"](https://skills.sh/api/search?q=go-to-market)
8. **Business Model Canvas** como skill dedicada: hay poca adopción. `scientiacapital/skills/business-model-canvas` tiene 402 installs (contenido NO VERIFICADO) — [skills.sh "business model canvas"](https://skills.sh/api/search?q=business%20model%20canvas)

### Inferences
- Para un jurado de escuela de negocios (FEN), la cadena `lean-canvas` o `startup-canvas` → `value-proposition` → `market-sizing` (bottom-up con datos chilenos) → `pricing-strategy` → `beachhead-segment` (todas de phuryn) da un relato coherente con un solo marketplace.
- El modelo de skills orientado a SaaS y EE. UU. (path to $100M, métricas SaaS) debe adaptarse al contexto chileno y B2B/B2G del mercado laboral. Hay que pedir explícitamente fuentes chilenas (INE, Mineduc, SENCE) al usar market-sizing.
- Los contadores de installs de skills.sh son señales débiles. Algunos publicadores (p. ej. mbfinotti) muestran cifras casi idénticas, unos 13.000, en muchas skills distintas, lo que sugiere instalaciones masivas o automatizadas.

### Gaps
- No verifiqué el contenido de `startup-financial-modeling` ni de `startup-metrics-framework` (wshobson).
- No verifiqué el nombre exacto del marketplace de wshobson/agents para `/plugin install startup-business-analyst@…`; hay que revisarlo en su README.

---

## 6. Medición de impacto social (teoría de cambio, métricas de impacto, ODS)

### Takeaway
No existe una skill popular y "estándar" de impacto social. La mejor verificada es `toc-builder` de `gasserane/personal-skills`. Es rigurosa (criterios DFID de Vogel 2012 y el modelo feminista de KIT), pero viene de un repo personal con 3 estrellas y sin licencia, y está orientada a programas MEL/SRHR. No encontré skills de ODS.

### Cited Findings
- **gasserane/personal-skills → `toc-builder`** (148 líneas): "A ToC is not a logic model with arrows". Pide 4 inputs obligatorios en un solo mensaje y, si faltan, procede declarando supuestos. Produce outcomes, precondiciones, supuestos (testeados y no testeados), contribution questions y plan de evidencia. Advierte cuando falta análisis de economía política feminista. Excluye logframes e indicadores — [SKILL.md](https://github.com/gasserane/personal-skills/blob/HEAD/org/toc-builder/SKILL.md)
  - Repo: 3 estrellas, sin licencia, push 2026-10-23, 54 skills y 45 scripts (algunas skills ejecutan Python, p. ej. `skills/literature/scripts/literature_cli.py`) — [repo](https://github.com/gasserane/personal-skills)
  - Installs: toc-builder 645, indicator-designer 656, mel-framework-citation 656, grill-mel 467 — [skills.sh "theory of change"](https://skills.sh/api/search?q=theory%20of%20change), [skills.sh "impact measurement"](https://skills.sh/api/search?q=impact%20measurement)
- Listados NO VERIFICADOS en skills-hub.ai: `impact-measurement` (logic model, indicadores, atribución causal, costo-efectividad) e `impact-org` (orientada a construir CRMs y plataformas para ONG) — [impact-measurement](https://skills-hub.ai/skills/impact-measurement), [impact-org](https://skills-hub.ai/skills/impact-org)
- `Mihir-Bhargav/OmniSkill` contiene un SKILL.md `theory-of-change` (repo de 1 estrella), NO VERIFICADO — [SKILL.md raw](https://raw.githubusercontent.com/Mihir-Bhargav/OmniSkill/main/extension/chrome-extension/public/skills/theory-of-change/SKILL.md), [repo](https://github.com/Mihir-Bhargav/OmniSkill)
- El listado "theory-of-change" de ClaudSkills está categorizado como security-misc, así que probablemente es otra cosa — [claudskills.com](https://claudskills.com/skills/theory-of-change/)
- `garethmanning/education-agent-skills/systems-wellbeing-impact-mapper` (109 installs), NO VERIFICADO — [skills.sh "social impact"](https://skills.sh/api/search?q=social%20impact)
- Referencias metodológicas externas útiles (no son skills): guía de teoría de cambio de GO Lab, Oxford — [PDF](https://golab.bsg.ox.ac.uk/documents/Creating-your-theory-of-change1.pdf); checklist de Bridgespan — [PDF](https://bridgespan.org/getmedia/a77a7344-1166-4606-bacf-4192e3dda2e1/theory-of-change-pressure-test-checklist.pdf)

### Inferences
- Para la hackathon, `toc-builder` puede usarse pidiendo explícitamente omitir el lente SRHR y feminista si no aplica, o aprovecharlo si el desafío trata brechas de género en el empleo, algo plausible en el eje inclusión. Al no tener licencia, el uso es técnicamente "todos los derechos reservados"; para uso personal el riesgo práctico es bajo.
- La skill local del equipo (`negocio-e-impacto`) ya cubre teoría de cambio e indicadores. Instalar `toc-builder` agregaría rigor pero también triggers solapados.

### Gaps
- No hay skill verificada de **ODS/SDG**. La búsqueda "SDG sustainable development" en skills.sh devolvió rate-limit (429), y ninguna otra fuente mostró una.
- No verifiqué `indicator-designer` ni las skills de skills-hub.ai.

---

## 7. RR.HH., personas, reclutamiento, DEI (relevante al eje mercado laboral)

### Takeaway
La opción más confiable es el plugin oficial `human-resources` de Anthropic (interview-prep, people-report con métricas de diversidad, org-planning, recruiting-pipeline, onboarding…). Está pensado para equipos de RR.HH. en empresas, lo que sirve para entender el flujo de trabajo de las empresas que proponen los desafíos. Para DEI específicamente, solo hay opciones de baja adopción: `tuanductran/hr-skills` (163 skills de RR.HH.; `hr-diversity-inclusion` es básicamente un listado de prompts) y skills sueltas de borghei, Refound y w95.

### Cited Findings
1. **anthropics/knowledge-work-plugins → plugin `human-resources`**
   - Skills: comp-analysis, draft-offer, interview-prep, onboarding, org-planning, people-report, performance-review, policy-lookup, recruiting-pipeline. Incluye un `.mcp.json` y `CONNECTORS.md` — [carpeta](https://github.com/anthropics/knowledge-work-plugins/tree/main/human-resources)
   - `people-report`: "Generate headcount, attrition, diversity, or org health reports… preparing diversity representation metrics". `interview-prep`: planes de entrevista por competencias y scorecards — [people-report](https://github.com/anthropics/knowledge-work-plugins/blob/main/human-resources/skills/people-report/SKILL.md), [interview-prep](https://github.com/anthropics/knowledge-work-plugins/blob/main/human-resources/skills/interview-prep/SKILL.md)
   - Installs: recruiting-pipeline 2.941, org-planning 2.895 — [skills.sh "recruiting"](https://skills.sh/api/search?q=recruiting), [skills.sh "design thinking"](https://skills.sh/api/search?q=design%20thinking)
   - Instalación: `claude plugin install human-resources@knowledge-work-plugins` (patrón del README) — [README](https://github.com/anthropics/knowledge-work-plugins)
2. **tuanductran/hr-skills**
   - 72 estrellas, MIT, push 2026-10-22, 163 SKILL.md y 181 scripts. Incluye hooks de proyecto en `.claude/hooks/` (block-push-to-main.sh, post-edit-*.sh) que solo aplican si se abre el propio repo como proyecto. Tiene marketplace en `.claude-plugin/marketplace.json` — [repo](https://github.com/tuanductran/hr-skills)
   - `hr-diversity-inclusion` (88 líneas): estrategia DEI, job descriptions inclusivas, sesgo inconsciente, ERGs, scorecard DEI y pay equity. Está estructurada como "Key prompts" — [SKILL.md](https://github.com/tuanductran/hr-skills/blob/HEAD/skills/hr-diversity-inclusion/SKILL.md)
   - Otras skills relevantes al tema: hr-job-description, hr-internal-mobility, hr-future-of-work, hr-accessibility-accommodation, hr-employee-journey-mapping, hr-design-thinking, hr-employer-branding, hr-candidate-experience — [repo](https://github.com/tuanductran/hr-skills)
   - Adopción muy baja: hr-diversity-inclusion 12 installs — [skills.sh "diversity inclusion"](https://skills.sh/api/search?q=diversity%20inclusion)
3. **borghei/Claude-Skills → `hr-operations/`** (talent-acquisition, people-analytics, hr-business-partner): 984 estrellas, licencia NOASSERTION, "906 stdlib Python tools" — [repo](https://github.com/borghei/Claude-Skills). Un marketplace la describe como productora de job descriptions inclusivas (NO VERIFICADO) — [claudemarketplaces.com](https://claudemarketplaces.com/skills/borghei/claude-skills/talent-acquisition)
4. **RefoundAI/lenny-skills**: writing-job-descriptions (1.575 installs), interviewing-evaluating-candidates, hiring-product-talent — [skills.sh "job description"](https://skills.sh/api/search?q=job%20description), [repo](https://github.com/RefoundAI/lenny-skills)
5. **w95/awesome-claude-corporate-skills**: 278 estrellas, MIT, push 2026-02-26; `dei-strategy` con 41 installs (NO VERIFICADO) — [repo](https://github.com/w95/awesome-claude-corporate-skills), [skills.sh "diversity inclusion"](https://skills.sh/api/search?q=diversity%20inclusion)
6. **wshobson/agents → `hr-legal-compliance`**: agentes hr-pro y legal-advisor; skills employment-contract-templates y gdpr-data-handling — [carpeta](https://github.com/wshobson/agents/tree/main/plugins/hr-legal-compliance)
7. **alirezarezvani → `c-level-skills`** incluye `chro-advisor` y `culture-architect` (contenido NO VERIFICADO) — [carpeta](https://github.com/alirezarezvani/claude-skills/tree/HEAD/c-level-advisor/skills)

### Inferences
- Las skills de RR.HH. sirven más para **simular al cliente** (cómo opera un equipo de reclutamiento o people analytics en la empresa del desafío) y para validar que la solución encaja en ese flujo, que para idear.
- El contexto legal de wshobson (GDPR, contratos de EE. UU.) no aplica directamente a Chile (Ley 21.015 de inclusión laboral, Ley 21.719 de datos personales). El equipo debería verificar normativa chilena por su cuenta.

### Gaps
- No encontré skills con foco en inclusión laboral de personas con discapacidad, migrantes o mercado laboral latinoamericano.
- No verifiqué `Owl-Listener/inclusive-design-skills`, que podría ser relevante para accesibilidad.

---

## 8. Transversal: instalación en Claude Desktop (Windows), seguridad y shortlist final

### Takeaway
En Windows, la vía más confiable para agregar marketplaces e instalar plugins sigue siendo el CLI (`claude plugin marketplace add …` / `claude plugin install …`) o copiar carpetas de skills a `~/.claude/skills/`. Hay reportes de que el `/plugin` falta en Claude Code Desktop, posteriores al cierre del issue. Ninguna de las skills recomendadas contiene código ofuscado ni llamadas de red propias. Los riesgos principales son de fricción: hooks (superpowers), scripts Python (alirezarezvani, deanpeters tam-sam-som), conectores MCP remotos (plugins de Anthropic) y triggers solapados.

### Cited Findings
- Issue "Claude Code Desktop Doesn't Have /plugin Command and cannot add plugin marketplaces": abierto el 2026-04-01 y cerrado como "completed" el 2026-08-25, pero comentarios del 2026-08-27 y 2026-09-11 dicen "Issue is still there" — [anthropics/claude-code#42142](https://github.com/anthropics/claude-code/issues/42142)
- Patrón documentado de instalación por CLI para el marketplace de Anthropic: `claude plugin marketplace add anthropics/knowledge-work-plugins` → `claude plugin install <plugin>@knowledge-work-plugins`. Tras instalar, "Skills fire when relevant, and slash commands are available" — [README](https://github.com/anthropics/knowledge-work-plugins)
- El CLI `npx skills` (vercel-labs) permite instalar una sola skill de un repo: `npx skills add <owner/repo> --skill <nombre> -a claude-code` — [vercel-labs/skills](https://github.com/vercel-labs/skills)
- cc-thinking-skills documenta que Claude Code carga skills desde `~/.claude/skills/` o `.claude/skills/` — [README](https://github.com/tjboudreaux/cc-thinking-skills/blob/HEAD/README.md)
- Superpowers tiene un hook SessionStart y un servidor local para el visual companion — [hooks.json](https://github.com/obra/superpowers/blob/main/hooks/hooks.json)
- Skill de organizador de hackathons que puede reutilizarse para simular la rúbrica del jurado: `samber/dev-event-organizer-skills/hackathon-judging` (criterios y pesos, escala, normalización, desempates; 5.058 installs; MIT; 330 líneas) — [SKILL.md](https://github.com/samber/dev-event-organizer-skills/blob/HEAD/skills/hackathon-judging/SKILL.md), [skills.sh "hackathon"](https://skills.sh/api/search?q=hackathon)

**Shortlist final sugerida (de mayor a menor prioridad):**

| # | Plugin / skill | Capacidad | Fuente / instalación | Scripts / riesgos |
|---|---|---|---|---|
| 1 | `product-management@knowledge-work-plugins` (product-brainstorming, write-spec, synthesize-research, competitive-brief) | Ideación, PRD, síntesis, competencia | [anthropics/knowledge-work-plugins](https://github.com/anthropics/knowledge-work-plugins) | Sin scripts; trae conectores MCP remotos |
| 2 | `pm-product-strategy`, `pm-market-research`, `pm-execution`, `pm-go-to-market` @pm-skills (phuryn) | Lean/startup canvas, value prop, TAM, pricing, GTM, red-team, pre-mortem, PRD, priorización | [phuryn/pm-skills](https://github.com/phuryn/pm-skills) | Sin scripts en las skills |
| 3 | `lateral-thinking@lateral-thinking` (danium) | SCAMPER, Six Hats, Worst Idea, provocación | [danium/lateral-thinking](https://github.com/danium/lateral-thinking) | Sin scripts |
| 4 | `the-fool` (Jeffallan, instalar solo esa skill) | Devil's advocate y red-team de ideas | [skill](https://github.com/jeffallan/claude-skills/blob/HEAD/skills/the-fool/SKILL.md) | Sin scripts en la skill; el repo es de desarrollo |
| 5 | `design-research@designer-skills` (Owl-Listener) | Empathy map, journey, personas, entrevistas | [Owl-Listener/designer-skills](https://github.com/Owl-Listener/designer-skills) | Scripts solo de tooling del repo |
| 6 | Skills sueltas de deanpeters (problem-framing-canvas, jobs-to-be-done, proto-persona, tam-sam-som-calculator, prioritization-advisor) | Encuadre riguroso | [deanpeters/Product-Manager-Skills](https://github.com/deanpeters/Product-Manager-Skills) | CC BY-NC-SA; script Python determinista en tam-sam-som; colisión de nombre `@pm-skills` |
| 7 | `startup-business-analyst` (wshobson) | Market sizing, modelo financiero, métricas | [wshobson/agents](https://github.com/wshobson/agents/tree/main/plugins/startup-business-analyst) | Sin scripts |
| 8 | `mvp` / `validate-idea` (slavingia) | Recorte de alcance, validación | [slavingia/skills](https://github.com/slavingia/skills) | Sin scripts; sin licencia |
| 9 | `human-resources@knowledge-work-plugins` | Contexto RR.HH. y diversidad | [carpeta](https://github.com/anthropics/knowledge-work-plugins/tree/main/human-resources) | Sin scripts; MCP |
| 10 | `toc-builder` (gasserane) | Teoría de cambio | [SKILL.md](https://github.com/gasserane/personal-skills/blob/HEAD/org/toc-builder/SKILL.md) | 3 estrellas; sin licencia; copiar solo esa carpeta |
| 11 | `discernment-nudge` (anthropics/skills) | Chequeo crítico ligero | [SKILL.md](https://github.com/anthropics/skills/blob/main/skills/discernment-nudge/SKILL.md) | Sin scripts |
| 12 | `thinking-skills@thinking-skills-marketplace` (tjboudreaux) | Mental models con router | [repo](https://github.com/tjboudreaux/cc-thinking-skills) | Invocación solo manual (`disable-model-invocation`) |
| — | `superpowers` (obra) | Brainstorming orientado a construir software | [repo](https://github.com/obra/superpowers) | Hook SessionStart y servidor local; **no recomendado** para la fase de negocio |

### Inferences
- Un set acotado (los ítems 1, 2, 3, 4 y opcionalmente 5) cubre casi todas las capacidades pedidas sin scripts ni hooks. Eso reduce los prompts de permisos y las colisiones de triggers durante las 7,5 h.
- Conviene instalar y probar todo **antes** del 4 de noviembre, verificando con `/plugins` o preguntando "¿qué skills tienes?" que estén cargadas. Si el `/plugin` falla en Desktop, usar el CLI en una terminal: la configuración de `~/.claude` es compartida.

### Gaps
- No verifiqué en esta sesión si la versión actual de Claude Desktop para Windows ya expone una UI de plugins; los últimos reportes públicos (sep-2026) dicen que no.
- No encontré hilos de Reddit (r/ClaudeAI) ni de Hacker News con rankings verificables de "mejores skills de negocio". Las roundups encontradas son blogs de un solo autor o de vendors ([Snyk](https://snyk.io/articles/7-claude-skills-product-managers/), [Coupler](https://blog.coupler.io/top-claude-skills/), [Intempt](https://intempt.com/blog/best-claude-skills-for-startups)), y no las usé para el ranking.
