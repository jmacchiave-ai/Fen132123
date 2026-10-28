# Skills y plugins de Claude existentes para pitch, defensa ante jurado y prototipado web rápido (Talent Tech Hack 2026)

Notas de investigación. Fecha de corte: 26-oct-2026. Método: búsqueda web + verificación directa vía GitHub API (`gh api`) de cada repo (estrellas, último push, licencia) y lectura del SKILL.md real cuando fue posible. "Último push" = fecha del último commit en el repo completo (no necesariamente de esa skill), salvo donde se indica fecha por carpeta. Las cifras de estrellas son del 26-oct-2026.

Comandos de instalación genéricos (Claude Code): `/plugin marketplace add <owner>/<repo>` y luego `/plugin install <plugin>@<marketplace>`. Alternativa manual: copiar la carpeta de la skill (la que contiene SKILL.md) a `C:\Users\<usuario>\.claude\skills\<nombre>\`.

---

## 1. Contenido del pitch deck y storytelling (narrativa, pitch de startup/inversionista, escritura persuasiva, copywriting)

### Takeaway
Lo mejor verificado: **coreyhaines31/marketingskills** (copywriting, marketing-psychology, launch; 56,6k estrellas, muy mantenido) para el copy persuasivo, y **OneWave-AI pitch-deck-reviewer** para auditar el deck con ojo de inversionista y predecir objeciones. Para la estructura narrativa, **RefoundAI/lenny-skills** (public-speaking, executive-communication) aporta marcos sólidos (Bow & Arrow, SCR/Pirámide). Las skills "pitch-deck" de un solo autor (Stevekaplanai, marcusnelson, lionelsimai) son pequeñas y de baja tracción; útiles como referencia, no imprescindibles.

### Cited Findings
**A. coreyhaines31/marketingskills (RECOMENDADA #1 para copy)**
- Repo: https://github.com/coreyhaines31/marketingskills — 56.638 estrellas, licencia MIT, último push 2026-10-22, descripción "Marketing skills for Claude Code and AI agents. CRO, copywriting, SEO, analytics, and growth engineering." — [GitHub API repo](https://github.com/coreyhaines31/marketingskills)
- Contiene ~50 skills, entre ellas: `copywriting`, `copy-editing`, `marketing-psychology`, `launch`, `product-marketing`, `offers`, `pricing`, `customer-research`, `competitors`, `public-relations`, `sales-enablement`, `video`, `events` — [carpeta skills/](https://github.com/coreyhaines31/marketingskills/tree/main/skills)
- `copywriting` (v2.3.1) se presenta como "expert conversion copywriter"; secciones: Diagnose the Situation First, Drafting Protocol, Copywriting Principles, Writing Style Rules, **No AI Tells**, Page Structure Framework, CTA Copy Guidelines, Voice and Tone; trae `references/ai-tells.md`, `copy-frameworks.md`, `natural-transitions.md` y `evals/evals.json` (339 líneas) — [SKILL.md copywriting](https://github.com/coreyhaines31/marketingskills/blob/main/skills/copywriting/SKILL.md)
- `marketing-psychology` (455 líneas) y `launch` (385 líneas) también existen y son extensas — [skills/marketing-psychology](https://github.com/coreyhaines31/marketingskills/tree/main/skills/marketing-psychology), [skills/launch](https://github.com/coreyhaines31/marketingskills/tree/main/skills/launch)
- Instalación: marketplace `marketingskills`, plugin `marketing-skills` → `/plugin marketplace add coreyhaines31/marketingskills` y `/plugin install marketing-skills@marketingskills` — [marketplace.json](https://github.com/coreyhaines31/marketingskills/blob/main/.claude-plugin/marketplace.json)
- Scripts: en las carpetas revisadas (copywriting, launch) solo hay Markdown y archivos `evals.json`; no se vieron scripts ejecutables — [árbol del repo](https://github.com/coreyhaines31/marketingskills)

**B. OneWave-AI/claude-skills → pitch-deck-reviewer (RECOMENDADA para revisar el deck)**
- Repo: https://github.com/OneWave-AI/claude-skills — 382 estrellas, MIT, último push 2026-10-20, "200+ production-ready Claude Code skills…" — [GitHub](https://github.com/OneWave-AI/claude-skills)
- SKILL.md: revisa decks "con rigor de VC"; lee PDF/PPTX/imágenes; puntúa 8 dimensiones (narrativa, claridad problema/solución, mercado, competencia, finanzas, equipo, claridad del "ask"…); feedback slide por slide; **predice ≥5 objeciones de inversionistas con severidad, gatillo, respuesta verbal sugerida y arreglo del deck**; compara con ≥2 decks de referencia; top-5 mejoras; genera `pitch-review.md`. Calibra por etapa (pre-producto: pesa problema/solución, equipo, mercado). Regla: "Verify any market-size, revenue, or growth claim with WebSearch… Never fabricate metrics" — [SKILL.md](https://github.com/OneWave-AI/claude-skills/blob/main/pitch-deck-reviewer/SKILL.md)
- Contenido: SKILL.md + `references/evaluation-framework.md`, `objections-and-benchmarks.md`, `output-template.md`; sin scripts. Frontmatter declara `tools: Read, Glob, Grep, Bash, Write, Edit, WebSearch, WebFetch` — [árbol pitch-deck-reviewer](https://github.com/OneWave-AI/claude-skills/tree/main/pitch-deck-reviewer)
- Página del producto: [onewave-ai.com pitch-deck-reviewer](https://www.onewave-ai.com/resources/claude-skills/pitch-deck-reviewer)
- Marketplace: `onewave-skills` (3 plugins) — [marketplace.json](https://github.com/OneWave-AI/claude-skills/blob/main/.claude-plugin/marketplace.json)

**C. RefoundAI/lenny-skills (marcos de narrativa y comunicación ejecutiva)**
- Repo: https://github.com/RefoundAI/lenny-skills — 1.442 estrellas, MIT, último push 2026-07-16; "86 product management skills from Lenny's Podcast" — [GitHub](https://github.com/RefoundAI/lenny-skills)
- Skills relevantes: `public-speaking`, `executive-communication`, `fundraising`, `positioning`, `written-communication`, `evaluating-startup-ideas`, `idea-validation`, `naming-and-branding`, `ai-assisted-prototyping` — [carpeta skills/](https://github.com/RefoundAI/lenny-skills/tree/main/skills)
- `executive-communication`: estructura con **SCR (Situation-Complication-Resolution)** y **SCQA / Pirámide de Minto**, "Start from the obvious", "Frame tradeoffs by goals", "Dinosaur Brain Executive Reviews", "Buy-in Meeting Narrative Structure"; basado en 9 invitados/posts — [SKILL.md](https://github.com/RefoundAI/lenny-skills/blob/main/skills/executive-communication/SKILL.md)
- Formato: Markdown puro (SKILL.md + `references/artifacts.md`), sin scripts; repo **sin marketplace.json** (instalación manual copiando la carpeta) — [repo](https://github.com/RefoundAI/lenny-skills)

**D. viktorbezdek/skillstack → storytelling / storytelling-for-stakeholders / pitch-sprint**
- Repo: https://github.com/viktorbezdek/skillstack — 14 estrellas, MIT, último push 2026-06-05 — [GitHub](https://github.com/viktorbezdek/skillstack)
- `storytelling-for-stakeholders`: convierte resultados en narrativa para liderazgo/inversionistas/clientes con marcos 3 actos, SparkLines (Duarte), SCR; regla "report = qué pasó; story = causalidad → qué significa para el negocio"; indica usar `pitch-sprint` para un pitch de inversión completo. Prerrequisitos: `/plugin marketplace add viktorbezdek/skillstack`, `/plugin install storytelling@skillstack` (+ creative-problem-solving, outcome-orientation) — [SKILL.md](https://github.com/viktorbezdek/skillstack/blob/main/skillstack-workflows/skills/storytelling-for-stakeholders/SKILL.md)
- Listado en directorios: "storytelling" (Hero's Journey, Story Circle, StoryBrand) — [skillselion](https://skillselion.com/skills/viktorbezdek/skillstack/storytelling)

**E. Skills de pitch deck de autores individuales (baja tracción)**
- Stevekaplanai/pitch-deck-mastery-skill — 9 estrellas, MIT, push 2026-08-16. SKILL.md: marco de 12 slides (Title, Problem, Solution, Why Now, Market TAM/SAM/SOM, Product, Traction, Business Model, Competition, Team, Financials, Ask), ajustes por etapa (pre-seed 8-10 slides), reglas "One idea per slide", "Lead with the headline", "10-word rule"; delega el archivo al skill `pptx`; `references/resources.md` — [GitHub](https://github.com/Stevekaplanai/pitch-deck-mastery-skill)
- marcusnelson/presentation-writing-claude-skill — 5 estrellas, **sin licencia**, push 2026-06-02. El repo solo trae README + un paquete `powerpoint-keynote-presentation.skill` (zip); no hay SKILL.md legible en el repo. Según README: convierte notas en outline slide-by-slide con tesis por slide, ≤3 evidencias, transiciones, "ask" final, speaker notes "for the mouth"; andamios "The Pitch", "The Case", "The Board Meeting", "The Keynote", "The Report-Out"; sección anti-"copy que suena a IA" — [GitHub](https://github.com/marcusnelson/presentation-writing-claude-skill)
- lionelsimai/claude-skills-collection (pitch-deck-creator) — 34 estrellas, MIT, push 2026-02-08; según búsqueda genera decks con speaker notes y plantilla de 12 slides (no leído) — [SKILL.md](https://github.com/lionelsimai/claude-skills-collection/blob/main/skills/pitch-deck-creator/SKILL.md)
- eyhshen/pitch-deck-brainstorm-skill — 1 estrella; planifica contenido y produce un prompt Markdown para otro agente (no construye slides) — [GitHub](https://github.com/eyhshen/pitch-deck-brainstorm-skill)
- Otros vistos: drobotmax/claude-skill-deck (HTML estilo McKinsey, 1 estrella), aqeeljundiy/m-deck-skills (agencia), PrznTPerfect "Prznt Deck" (PPTX, MIT) — [búsqueda](https://github.com/drobotmax/claude-skill-deck), [m-deck-skills](https://github.com/aqeeljundiy/m-deck-skills), [przntperfect](https://www.przntperfect.com/post/claude-skill-pitch-deck)
- Gabberflast/academic-pptx-skill — 1.361 estrellas, MIT, push 2026-07-14; presentaciones académicas y **defensas de tesis**, "action titles", argumento estructurado; complementa al skill pptx de Anthropic (no se leyó el SKILL.md) — [GitHub](https://github.com/gabberflast/academic-pptx-skill)

### Inferences
- Ranking sugerido para este equipo: (1) marketingskills `copywriting` + `marketing-psychology` (tagline, propuesta de valor, frases de cierre); (2) OneWave `pitch-deck-reviewer` (auditoría final del deck + objeciones probables, muy alineado con la defensa del día 2); (3) lenny-skills `executive-communication` (jurado de escuela de negocios = audiencia ejecutiva, SCR/Pirámide); (4) Stevekaplanai `pitch-deck-mastery` solo como checklist de 12 slides (casi todo ya lo cubre el skill `slides` instalado).
- El pitch de hackathon de impacto social no es un pitch de inversión: varias de estas skills (Financials, Ask de ronda, Series A) deben adaptarse a "piloto con la empresa del desafío / métricas de impacto". El reviewer de OneWave lo permite ("adjust for stage").
- En la sesión ya existen skills propias del proyecto (`pitch-ganador`, `defensa-jurado`, `negocio-e-impacto`, `analizar-desafio`, `prototipo-express`) que se solapan con esta categoría; las skills externas sirven como complemento/segunda opinión, no como reemplazo.

### Gaps
- No obtuve cifras de instalaciones (skills.sh) para `copywriting`, `pitch-deck-reviewer` ni lenny-skills.
- No pude leer el SKILL.md de marcusnelson (está dentro de un `.skill` zip) ni el de lionelsimai/pitch-deck-creator: contenido no verificado.
- No encontré una skill específica y bien mantenida de "Story Spine" (Pixar) como tal.

---

## 2. Entrega de la presentación y coaching de oratoria (guion hablado, ensayo, tiempos)

### Takeaway
La única skill de oratoria con contenido sólido y verificable es **RefoundAI/lenny-skills `public-speaking`** (Bow & Arrow, Accordion para comprimir a 30 s, ADD para Q&A, pausa vs. muletillas, puntos de apoyo en vez de guion memorizado). No existe una skill madura que "escuche" el ensayo y mida tiempos automáticamente; el cronometraje y feedback de ensayo deben hacerse conversacionalmente.

### Cited Findings
- lenny-skills `public-speaking`: "insights from 12 guests"; pasos: diagnosticar el obstáculo (preparación, ansiedad, slides, entrega), aplicar marcos, simular entrega con juegos, refinar humor/visuales. Principios: visualización completa, "five-second moment" (Matthew Dicks), pausa para eliminar muletillas, **"Use flexible talking points over scripts"** (memorizar palabra por palabra provoca bloqueos) — [SKILL.md](https://github.com/RefoundAI/lenny-skills/blob/main/skills/public-speaking/SKILL.md)
- Marcos incluidos: **Bow and Arrow** (una sola frase que la audiencia recordará + 2-3 "bookmarks"; "make the slide title exactly the one thing"), **Accordion Method** (hablar la charla en 3 min → 2 → 1 → 30 s y volver a expandir; ~15 min por ciclo), **Three Tactical Tweaks** (Think Up, End Strong…), **Conviction Prompts Game**, **ADD (Matt Abrahams) para responder preguntas en Q&A**, "5 Ways to Add Stakes" — [references/artifacts.md](https://github.com/RefoundAI/lenny-skills/blob/main/skills/public-speaking/references/artifacts.md)
- "Public Speaking Rehearsal" (EduHub/DeepTutor): coach de planificación, ensayo, tiempos, nervios y práctica de Q&A; se instala con `eduhub skills install public-speaking-rehearsal` o `deeptutor skills install …`; **sin repo GitHub propio**, licencia "Unknown", conteo de instalaciones inconsistente (0 vs 26), actualizado 13-jul-2026; el cuerpo del SKILL.md no es visible — [aiskill.market](https://aiskill.market/skills/public-speaking-rehearsal)
- "Giving Presentations" atribuida a refoundai en skillsdirectory (Grade A) — [skillsdirectory](https://www.skillsdirectory.com/skills/refoundai-giving-presentations); no aparece entre las 86 skills actuales de RefoundAI/lenny-skills — [carpeta skills/](https://github.com/RefoundAI/lenny-skills/tree/main/skills)
- "Public Speaking Presentation" en claudecowork.im es un **subagente** (va en `~/.claude/agents/`), no una skill — [claudecowork.im](https://claudecowork.im/resources/public-speaking-presentation)
- marcusnelson/presentation-writing: speaker notes "written for the mouth, not the page" (ver §1) — [README](https://github.com/marcusnelson/presentation-writing-claude-skill)

### Inferences
- Recomendación: instalar solo lenny-skills `public-speaking` (Markdown puro, sin scripts). El "Accordion Method" encaja perfecto para un pitch con tiempo fijo (p.ej. comprimir a 3 min y a 1 min "elevator").
- Para ensayos cronometrados: Claude puede construir un Artifact HTML con cronómetro por sección y el guion en teleprompter (sin skill adicional); ninguna skill encontrada lo hace.
- Descartar "Public Speaking Rehearsal" (fuente no verificable, sin repo, licencia desconocida).

### Gaps
- No encontré ninguna skill que analice audio/video del ensayo (ritmo, muletillas, palabras por minuto) dentro de Claude Code.
- No pude verificar el contenido ni el origen de "Giving Presentations" (posible versión antigua/renombrada de lenny-skills).

---

## 3. Defensa en Q&A, manejo de objeciones, debate, negociación, comunicación ejecutiva

### Takeaway
Las mejores opciones verificadas son **alirezarezvani/claude-skills → plugin `executive-mentor`** (`/em:board-prep`, `/em:challenge` pre-mortem, `/em:stress-test`), muy útiles para anticipar preguntas duras del jurado; **anthropics/knowledge-work-plugins `sales/handle-objection`** (oficial, clasificación de objeciones, pero pensado para CRM); y el **pitch-deck-reviewer** de OneWave (objeciones con respuesta verbal). El `debate-simulator` de OneWave es una plantilla vacía de baja calidad.

### Cited Findings
**A. alirezarezvani/claude-skills → executive-mentor (RECOMENDADA)**
- Repo: https://github.com/alirezarezvani/claude-skills — 28.758 estrellas, MIT, último push 2026-10-26 (hoy), "380 Claude Code skills…" — [GitHub](https://github.com/alirezarezvani/claude-skills)
- Marketplace `claude-code-skills` con 104 plugins, entre ellos `executive-mentor`, `c-level-skills`, `demo-video`, `a11y-audit`, `marketing-skills`, `product-skills` — [marketplace.json](https://github.com/alirezarezvani/claude-skills/blob/main/.claude-plugin/marketplace.json). Instalación: `/plugin marketplace add alirezarezvani/claude-skills` → `/plugin install executive-mentor@claude-code-skills`.
- `board-prep`: "Board meeting preparation for the adversarial scenario, not the friendly one. Forces numbers-cold mastery, anticipates hard questions, builds a narrative that acknowledges weakness without losing the room"; fases: Numbers Cold, Anticipate the Hard Questions, Build the Narrative, Adversarial Preparation, Director-by-Director Prep, checklist pre-reunión, durante y después — [SKILL.md](https://github.com/alirezarezvani/claude-skills/blob/main/c-level-advisor/executive-mentor/skills/board-prep/SKILL.md)
- `challenge` (`/em:challenge <plan>`): pre-mortem ("imagina que el plan fracasó en 12 meses"), extrae supuestos (mercado, ejecución, cliente, competencia, financieros, dependencias), los califica confianza × impacto, mapea vulnerabilidades y cadenas de dependencia; uso explícito "before presenting to a board or investor" — [SKILL.md](https://github.com/alirezarezvani/claude-skills/blob/main/c-level-advisor/executive-mentor/skills/challenge/SKILL.md)
- `stress-test` (`/em:stress-test <assumption>`): aislar el supuesto, buscar contra-evidencia ("If a smart skeptic was looking at this, what would they point to?"), modelar escenarios base/bear/-50%/-80%, sensibilidad — [SKILL.md](https://github.com/alirezarezvani/claude-skills/blob/main/c-level-advisor/executive-mentor/skills/stress-test/SKILL.md)
- Las tres son Markdown (156-204 líneas c/u); no se observaron scripts en esas carpetas — [carpeta executive-mentor](https://github.com/alirezarezvani/claude-skills/tree/main/c-level-advisor/executive-mentor)

**B. anthropics/knowledge-work-plugins → sales/handle-objection (oficial Anthropic)**
- Repo oficial: 33.157 estrellas, Apache-2.0, push 2026-10-26; "plugins primarily intended for knowledge workers to use in Claude Cowork" — [GitHub](https://github.com/anthropics/knowledge-work-plugins)
- `handle-objection`: clasifica la objeción en precio/valor, timing/prioridad, comparación competitiva, riesgo/confianza, autoridad, statu quo; distingue objeción vs. movida de negociación; respuesta de 3-5 frases "acknowledgment first", con una prueba y cerrando con una pregunta. Está diseñado para CRM/transcripciones/email (todos opcionales, con fallback a contexto pegado) y tiene reglas largas de conectores — [SKILL.md](https://github.com/anthropics/knowledge-work-plugins/blob/main/sales/skills/handle-objection/SKILL.md)
- Instalación: marketplace `knowledge-work-plugins`, plugin `sales` — [marketplace.json](https://github.com/anthropics/knowledge-work-plugins/blob/main/.claude-plugin/marketplace.json)

**C. OneWave-AI**
- `pitch-deck-reviewer` genera ≥5 objeciones de inversionista con "suggested verbal response" (ver §1) — [SKILL.md](https://github.com/OneWave-AI/claude-skills/blob/main/pitch-deck-reviewer/SKILL.md)
- `debate-simulator`: 59 líneas; crea 2-3 personas expertas con apertura, réplicas, contrainterrogatorio y cierre, pero el resto es boilerplate genérico ("Trigger Phrases: 'Help me with [use case]'", "Example Request: [Sample user request here]") — [SKILL.md](https://github.com/OneWave-AI/claude-skills/blob/main/debate-simulator/SKILL.md)
- Existen también `objection-pattern-detector` y `raise-negotiation-prep` (no leídos) — [repo](https://github.com/OneWave-AI/claude-skills)

**D. lenny-skills**
- `public-speaking` incluye ADD (Matt Abrahams) para responder preguntas en Q&A — [references](https://github.com/RefoundAI/lenny-skills/blob/main/skills/public-speaking/references/artifacts.md)
- `executive-communication` (SCR, Pirámide, "Project assertive confidence", controlar la narrativa de malas noticias) — [SKILL.md](https://github.com/RefoundAI/lenny-skills/blob/main/skills/executive-communication/SKILL.md)
- `negotiating-compensation` existe pero es de negociación salarial (no aplica) — [carpeta skills/](https://github.com/RefoundAI/lenny-skills/tree/main/skills)

### Inferences
- Para la defensa ante jurado de FEN: `executive-mentor` (board-prep + challenge + stress-test) es lo más cercano a "simular un jurado adversarial" entre las skills existentes; combinado con el reviewer de OneWave cubre "preguntas probables + respuestas cortas".
- `handle-objection` es de calidad oficial pero orientado a ventas con CRM; sirve como marco de clasificación, no merece instalarse solo por esto (trae todo el plugin `sales`, ~37 skills).
- No instalar `debate-simulator` (calidad baja, plantilla sin contenido).
- La skill propia `defensa-jurado` ya cubre banco de preguntas + simulación con puntaje; las externas aportarían sobre todo el ángulo pre-mortem/stress-test de supuestos de negocio.

### Gaps
- No encontré una skill específica de "defensa ante jurado de hackathon" o "mock judge panel" de buena calidad.
- No leí `objection-pattern-detector` ni `raise-negotiation-prep` (OneWave).

---

## 4. Prototipado web rápido y construcción de apps (frontend-design, web-artifacts-builder, otros)

### Takeaway
**anthropics frontend-design** es la skill de diseño frontend más instalada del ecosistema (1,0 M instalaciones en skills.sh, 3/3 auditorías aprobadas, sin scripts), pero se solapa con las skills de diseño ya instaladas. **web-artifacts-builder** (React+Vite+shadcn vía scripts bash/pnpm) es excesivo para un equipo sin programación que publica HTML de un solo archivo. El plugin oficial **playground** (HTML de un solo archivo con controles y vista previa en vivo) sí encaja con el formato.

### Cited Findings
**A. anthropics/skills (oficial)**
- Repo: 183.924 estrellas, último push 2026-10-09; skills: academy-guide, algorithmic-art, brand-guidelines, canvas-design, claude-api, discernment-nudge, doc-coauthoring, docx, **frontend-design**, internal-comms, mcp-builder, pdf, pptx, skill-creator, slack-gif-creator, theme-factory, **web-artifacts-builder**, **webapp-testing**, xlsx — [skills/](https://github.com/anthropics/skills/tree/main/skills)
- Licencia: muchas skills Apache 2.0; docx/pdf/pptx/xlsx "source-available" — [README](https://github.com/anthropics/skills)
- Instalación: `/plugin marketplace add anthropics/skills` → `/plugin install example-skills@anthropic-agent-skills` (marketplace `anthropic-agent-skills`, plugins `document-skills` y `example-skills`) — [README](https://github.com/anthropics/skills), [marketplace.json](https://github.com/anthropics/skills/blob/main/.claude-plugin/marketplace.json)
- **frontend-design**: "design lead at a design studio known for giving every client a distinct visual identity"; anclar el diseño en el tema, hero con lo más característico del mundo del sujeto, tipografía con personalidad, proceso planificar → revisar contra el brief → construir → autocrítica; último cambio en la carpeta 2026-09-03; solo SKILL.md + LICENSE — [SKILL.md](https://github.com/anthropics/skills/blob/main/skills/frontend-design/SKILL.md)
- frontend-design en skills.sh: **1,0 M instalaciones**, primera vez visto 19-ene-2026, auditorías Gen Agent Trust Hub / Socket / Snyk: **Pass** las tres — [skills.sh](https://skills.sh/anthropics/skills/frontend-design)
- También existe como plugin en el marketplace oficial `claude-plugins-official` (plugin `frontend-design`, autor Anthropic) → `/plugin install frontend-design@claude-plugins-official` — [plugins/frontend-design](https://github.com/anthropics/claude-plugins-official/tree/main/plugins/frontend-design)
- **web-artifacts-builder**: "Suite of tools for creating elaborate, multi-component claude.ai HTML artifacts using … React, Tailwind CSS, shadcn/ui… not for simple single-file HTML/JSX artifacts". Pasos: `bash scripts/init-artifact.sh` → editar → `bash scripts/bundle-artifact.sh` (Parcel + html-inline → `bundle.html`). Stack React 18 + TypeScript + Vite + Parcel + Tailwind 3.4.1 + 40+ componentes shadcn; Node 18+; instala pnpm globalmente si falta (`npm install -g pnpm`), usa `sed -i`, incluye un binario `shadcn-components.tar.gz`; último cambio 2026-04-20 — [SKILL.md](https://github.com/anthropics/skills/blob/main/skills/web-artifacts-builder/SKILL.md), [scripts/](https://github.com/anthropics/skills/tree/main/skills/web-artifacts-builder/scripts)

**B. anthropics/claude-plugins-official (marketplace oficial, 44.700 estrellas, Apache-2.0, push 2026-10-26, 315 plugins)** — [GitHub](https://github.com/anthropics/claude-plugins-official)
- **playground**: "Creates interactive HTML playgrounds — self-contained single-file explorers with visual controls, live preview, and prompt output with copy button"; plantillas design-playground, data-explorer, concept-map, document-critique, diff-review, code-map; requisitos "Single HTML file. Inline all CSS and JS. No external dependencies"; "Live preview… No 'Apply' button"; tras escribir el HTML ejecuta `open <archivo>.html` (comando macOS) — [SKILL.md](https://github.com/anthropics/claude-plugins-official/blob/main/plugins/playground/skills/playground/SKILL.md)
- **project-artifact**: genera y publica una página de estado de proyecto con pestañas vía la herramienta Artifact (claude.ai) — [plugin.json](https://github.com/anthropics/claude-plugins-official/blob/main/plugins/project-artifact/.claude-plugin/plugin.json)

**C. Otros**
- lenny-skills `ai-assisted-prototyping`: guía conceptual (elegir entre v0/Lovable o Cursor, iterar con PRD/screenshots, validar con usuarios), 15 invitados; no construye código — [SKILL.md](https://github.com/RefoundAI/lenny-skills/blob/main/skills/ai-assisted-prototyping/SKILL.md)
- obra/superpowers (305.462 estrellas, MIT, push 2026-10-23): metodología de desarrollo (brainstorming, writing-plans, executing-plans, test-driven-development, systematic-debugging, verification-before-completion…) — [skills/](https://github.com/obra/superpowers/tree/main/skills)
- affaan-m/ECC (ex everything-claude-code; 289.482 estrellas, MIT, push 2026-10-26): "agent harness performance optimization system", origen en un ganador de hackathon de Anthropic según su autor — [GitHub](https://github.com/affaan-m/ECC), [apiyi blog](https://help.apiyi.com/en/everything-claude-code-plugin-guide-en.html)
- vercel-labs/agent-skills (33.041 estrellas, push 2026-10-14): colección oficial de Vercel (React best practices, etc.) — [GitHub](https://github.com/vercel-labs/agent-skills)

### Inferences
- Para single-file HTML publicado como Artifact, `frontend-design` es opcional (bajo riesgo, sin scripts, muy popular) pero redundante con impeccable / design-taste-frontend / high-end-visual-design ya instaladas. Si se instala una sola cosa de esta categoría, `playground@claude-plugins-official` aporta un patrón nuevo (simulador con controles + vista previa en vivo) útil para demos tipo "simulador de empleabilidad"; su paso `open` es de macOS y en Windows no aplica (se publicaría como Artifact).
- **No instalar web-artifacts-builder**: depende de Node/pnpm/bash, descarga paquetes npm, y el propio SKILL.md dice que no es para artifacts simples de un archivo. Riesgo de perder horas en instalación durante 7,5 h de build.
- superpowers y ECC son marcos para desarrolladores; sobredimensionados para dos estudiantes sin programación (solo `brainstorming` de superpowers podría servir para idear).

### Gaps
- No encontré una skill independiente y bien evaluada de "prototipo de hackathon en 1 archivo HTML" distinta de las ya instaladas.
- No verifiqué conteos de instalación de `playground`.

---

## 5. Probar el prototipo en un navegador (webapp-testing / Playwright): dependencias y Windows sin saber programar

### Takeaway
Todas las opciones Playwright requieren instalar runtimes (Python o Node.js) y descargar Chromium; **webapp-testing** de Anthropic tiene advertencias (Warn) de Socket y Snyk. En esta sesión de Claude desktop ya existe un navegador integrado (herramientas `mcp__Claude_Browser__*` + skill `built-in-browser`), por lo que para HTML de un archivo probablemente **no hace falta instalar nada**.

### Cited Findings
- **anthropics webapp-testing**: "To test local web applications, write native Python Playwright scripts"; helper `scripts/with_server.py` (lanza servidores con `subprocess.Popen(..., shell=True)`); árbol de decisión: si es HTML estático, leer el HTML para obtener selectores; ejemplos con `from playwright.sync_api import sync_playwright`, Chromium headless; último cambio 2026-04-20 — [SKILL.md](https://github.com/anthropics/skills/blob/main/skills/webapp-testing/SKILL.md), [with_server.py](https://github.com/anthropics/skills/blob/main/skills/webapp-testing/scripts/with_server.py)
- webapp-testing en skills.sh: 188,8 K instalaciones; auditorías Gen Agent Trust Hub **Pass**, Socket **Warn**, Snyk **Warn** — [skills.sh](https://skills.sh/anthropics/skills/webapp-testing)
- **lackeyjb/playwright-skill** (3.239 estrellas, MIT, push 2026-10-01, v5.0.0): "Requires Node.js 20+, npm, and network access on first setup to install Playwright and Chromium"; `npm run setup` = `npm install && npx playwright install chromium`; dependencia `playwright ^1.62.0`; `allowed-tools: Bash(node:*) Bash(npm:*)`; screenshots, chequeos responsive, validación UX, links rotos; marketplace `playwright-skill` — [SKILL.md](https://github.com/lackeyjb/playwright-skill/blob/main/skills/playwright-skill/SKILL.md), [package.json](https://github.com/lackeyjb/playwright-skill/blob/main/skills/playwright-skill/package.json)
- **Plugin oficial `playwright`** (claude-plugins-official, autor Microsoft): MCP server lanzado con `npx @playwright/mcp@latest` (versión sin fijar) — [.mcp.json](https://github.com/anthropics/claude-plugins-official/blob/main/external_plugins/playwright/.mcp.json); microsoft/playwright-mcp tiene 38.659 estrellas, push 2026-10-22 — [GitHub](https://github.com/microsoft/playwright-mcp)
- Alternativas CLI: microsoft/playwright-cli (14.641 estrellas) — [GitHub](https://github.com/microsoft/playwright-cli); vercel-labs/agent-browser (44.626 estrellas, "Browser automation CLI for AI agents") — [GitHub](https://github.com/vercel-labs/agent-browser)
- alirezarezvani `playwright-pro` (generate, fix, coverage, browserstack, testrail…): orientado a suites de test profesionales — [árbol](https://github.com/alirezarezvani/claude-skills/tree/main/engineering-team/playwright-pro)

### Inferences
- Windows sin programación: webapp-testing exige Python + `pip install playwright` + `playwright install chromium`; lackeyjb exige Node 20+; el plugin MCP exige Node/npx. Claude puede ejecutar los comandos, pero cada instalación agrega puntos de falla y permisos. Recomendación: **no instalar**; usar el navegador integrado de la app (presente en esta sesión) para abrir el Artifact, hacer clic, leer la página y revisar consola. Si se quiere una opción Playwright, la menos fricción es `lackeyjb/playwright-skill` (Node, un solo `npm run setup`) o el plugin oficial `playwright` (pero `@latest` sin versión fija es un riesgo de cadena de suministro menor).
- Las advertencias Socket/Snyk de webapp-testing probablemente se deben a la ejecución de comandos de shell arbitrarios (`shell=True`); no indican malware, pero confirman que ejecuta código.

### Gaps
- No probé ninguna de estas skills en Windows en esta sesión; la compatibilidad Windows se infiere de dependencias y código.
- No encontré el detalle de las alertas Socket/Snyk de webapp-testing.

---

## 6. Auditoría de accesibilidad (WCAG 2.2)

### Takeaway
La mejor opción popular y liviana es **addyosmani/web-quality-skills → `accessibility`** (WCAG 2.2 + Lighthouse, MIT, ~3 k estrellas, solo Markdown). La más rigurosa en contenido es **84emllc/claude-wcag-skill** (WCAG 2.2 A/AA, texto normativo W3C literal, tabla de criterios nuevos de 2.2), pero con 0 estrellas y licencia no estándar. Las de Anthropic (knowledge-work design) y OneWave siguen en **WCAG 2.1**.

### Cited Findings
- **addyosmani/web-quality-skills** (2.991 estrellas, MIT, push 2026-08-24): skill `accessibility` v2.0 "Audit and improve web accessibility following WCAG 2.2 guidelines"; flujo con evidencia: auditoría Lighthouse (o axe), snapshot del árbol de accesibilidad, prueba con teclado, corregir y re-auditar; advierte "a score of 100 is not WCAG conformance"; referencias `WCAG.md` y `A11Y-PATTERNS.md`, sin scripts en la carpeta; otras skills: performance, core-web-vitals, seo, best-practices, web-quality-audit; marketplace `addy-web-quality-skills`, plugin `web-quality-skills` — [SKILL.md](https://github.com/addyosmani/web-quality-skills/blob/main/skills/accessibility/SKILL.md), [repo](https://github.com/addyosmani/web-quality-skills)
- **84emllc/claude-wcag-skill** (0 estrellas, licencia NOASSERTION, push 2026-08-05): `wcag-2.2-aa`; principio "a11y is a build requirement verified with tooling, never a self-assessed claim"; 4 pasadas obligatorias (escaneo automático axe/Lighthouse/WAVE, solo teclado, contraste + zoom 320px/400%, lector de pantalla); reporte "criterio → elemento → arreglo"; tabla "New in WCAG 2.2" (2.4.11 Focus Not Obscured, 2.5.7 Dragging Movements, 2.5.8 Target Size 24×24…), nota que 4.1.1 Parsing fue eliminado; `references/wcag-2.2-full.md` (spec W3C literal) y `running-axe.md`; scripts `build-reference.sh` y `validate.mjs` (para CI) — [SKILL.md](https://github.com/84emllc/claude-wcag-skill/blob/main/SKILL.md), [repo](https://github.com/84emllc/claude-wcag-skill)
- **anthropics/knowledge-work-plugins → design/accessibility-review**: "/accessibility-review" "Run a WCAG 2.1 AA accessibility audit on a design or page"; referencia rápida (1.4.3 contraste 4.5:1, 2.1.1 teclado, 2.4.7 foco visible, "2.5.5 Touch target >= 44x44"), 8 problemas comunes, enfoque de prueba (automático ~30 %, teclado, lector de pantalla, contraste, zoom 200 %) — [SKILL.md](https://github.com/anthropics/knowledge-work-plugins/blob/main/design/skills/accessibility-review/SKILL.md)
- **OneWave accessibility-auditor**: lleva a "WCAG 2.1 AA compliance"; CLI scans, jest-axe o Playwright, teclado, NVDA/VoiceOver; referencias wcag-checklist, common-fixes, aria-patterns — [SKILL.md](https://github.com/OneWave-AI/claude-skills/blob/main/accessibility-auditor/SKILL.md)
- **Community-Access/accessibility-agents** (428 estrellas, MIT, push 2026-09-23): "Eleven specialists that enforce WCAG 2.2 AA compliance"; incluye `scripts/install.mjs` y `scripts/install-hooks.js` (instala hooks) — [GitHub](https://github.com/Community-Access/accessibility-agents)
- **mrKanoh/wcag-accessibility-audit-skill** (8 estrellas, MIT, push 2026-10-19): WCAG 2.1/2.2, remediación, ARIA, plan de pruebas manuales, **inglés/español**; el repo incluye una copia de skill-creator con scripts Python — [GitHub](https://github.com/mrKanoh/wcag-accessibility-audit-skill)
- alirezarezvani tiene plugin `a11y-audit` en su marketplace (no leído) — [marketplace.json](https://github.com/alirezarezvani/claude-skills/blob/main/.claude-plugin/marketplace.json); wshobson/agents `accessibility-compliance` (WCAG 2.2, `npx skills add wshobson/agents/accessibility-compliance --agent claude-code`) según directorio — [getclaudeskills](https://www.getclaudeskills.com/skills/accessibility-compliance-wshobson)

### Inferences
- Ranking: (1) addyosmani `accessibility` (popular, WCAG 2.2, sin scripts, fácil); (2) 84emllc `wcag-2.2-aa` si se quiere citar criterios exactos ante el jurado (tema "inclusión": mostrar cumplimiento WCAG 2.2 AA es argumento fuerte), aceptando la baja tracción; (3) mrKanoh por el soporte en español (contenido no verificado a fondo).
- La skill de Anthropic `accessibility-review` etiqueta 2.5.5 (44×44) como AA dentro de su referencia "WCAG 2.1 AA"; según mi conocimiento del estándar, 2.5.5 Target Size es nivel AAA y el criterio AA de WCAG 2.2 es 2.5.8 (24×24). Igualmente, 84emllc fecha WCAG 2.2 como Recomendación del 12-dic-2024, cuando la primera Recomendación fue en oct-2023 (dic-2024 fue una actualización). Ambos puntos no fueron verificados con fetch a W3C en esta sesión.
- Evitar Community-Access/accessibility-agents para este caso: 11 agentes + instalador con hooks = configuración persistente y más superficie de riesgo.
- `impeccable` y `web-interface-guidelines` ya instaladas cubren parte de a11y; una skill WCAG 2.2 dedicada sigue aportando checklist formal.

### Gaps
- No obtuve conteos de instalación de skills.sh para las skills de accesibilidad.
- No leí el SKILL.md completo de mrKanoh ni de wshobson.

---

## 7. Grabación de video/demo o guion de demo

### Takeaway
Existen opciones reales pero pesadas: **alirezarezvani `demo-video`** (guion + escenas HTML + narración; renderiza con Playwright + edge-tts + ffmpeg si están disponibles, o entrega archivos para hacerlo manual) y **heygen-com/hyperframes** (HTML → video, 72,8 k estrellas, plugin oficial de su repo). **remotion-dev/skills** requiere un proyecto Remotion (Node/React). Para una demo en vivo de hackathon, lo valioso es el **guion de demo**, que `demo-video` estructura bien.

### Cited Findings
- **alirezarezvani demo-video**: "Orchestrates playwright, ffmpeg, and edge-tts MCPs"; estructuras: Classic Demo 30-60 s (Hook 3s → Problem 5s → Magic Moment 5s → Proof 15s → Social Proof 4s → Invite 4s), Problem-Solution 20-40 s, Teaser 15 s; reglas de narración ("One idea per scene", "Lead with the verb", "No jargon", contraste "24 tabs. One click. 5 groups."); salida `demo-output/` con `scenes/*.html` (1920×1080), `narration/*.txt`, `scenes.json`, `build.sh`; modo manual si faltan herramientas — [SKILL.md](https://github.com/alirezarezvani/claude-skills/blob/main/engineering/demo-video/skills/demo-video/SKILL.md). Plugin `demo-video` en marketplace `claude-code-skills` — [marketplace.json](https://github.com/alirezarezvani/claude-skills/blob/main/.claude-plugin/marketplace.json)
- **heygen-com/hyperframes** (72.804 estrellas, Apache-2.0, push 2026-10-26): "Write HTML. Render video. Built for agents."; para Claude Code: `claude plugin marketplace add heygen-com/hyperframes` y `claude plugin install hyperframes@hyperframes`, o `npx skills add heygen-com/hyperframes` / `npx hyperframes skills update`; skills `/slideshow`, `/remotion-to-hyperframes`, `/figma` se instalan a demanda — [README](https://github.com/heygen-com/hyperframes)
- **remotion-dev/skills** (5.736 estrellas, push 2026-10-26): 12 skills (remotion-create, remotion-render, remotion-captions, remotion-saas, remotion-studio…) — [GitHub](https://github.com/remotion-dev/skills)
- OneWave `hyperframes-sales-demo-builder` existe (no leído) — [repo](https://github.com/OneWave-AI/claude-skills)
- coreyhaines31/marketingskills incluye una skill `video` (no leída) — [skills/](https://github.com/coreyhaines31/marketingskills/tree/main/skills)

### Inferences
- Para este equipo: usar `demo-video` solo en "modo manual" como generador de guion de demo y escenas (sin instalar ffmpeg/edge-tts). Un video de respaldo grabado con la grabadora de pantalla de Windows (Win+Alt+R, Xbox Game Bar) o un GIF del navegador puede bastar como plan B si la demo en vivo falla.
- hyperframes y remotion implican Node + render de video; demasiado tiempo para 7,5 h de build salvo que el video sea un entregable obligatorio.

### Gaps
- No verifiqué si las bases de Talent Tech Hack 2026 exigen video de demo.
- No leí el SKILL.md principal de hyperframes ni su política de telemetría/red.

---

## 8. Skills o plugins específicos para hackathons

### Takeaway
El único plugin de hackathon con respaldo institucional es **Devpost "hackathon-in-a-plugin"** (repo challengepost/devpost-curriculum), pero es un **currículo de aprendizaje de desarrollo guiado por especificación** (onboard → scope → PRD → spec → checklist → build → iterate → reflect), no un kit de pitch/jurado; baja tracción (40 estrellas) y sin licencia. Lo demás encontrado (hackathon-skills-marketplace, ECC "de un ganador de hackathon") es de bajo encaje o de desarrollo puro.

### Cited Findings
- **challengepost/devpost-curriculum → hackathon-in-a-plugin** v0.2.0, autor "Devpost": "A complete hackathon curriculum delivered as eight slash commands. Walk through spec-driven development from idea spark to working app in 3-4 hours." Marketplace `devpost-curriculum` (categoría education) — [plugin.json](https://github.com/challengepost/devpost-curriculum/blob/main/plugins/hackathon-in-a-plugin/.claude-plugin/plugin.json), [marketplace.json](https://github.com/challengepost/devpost-curriculum/blob/main/.claude-plugin/marketplace.json). Instalación inferida: `/plugin marketplace add challengepost/devpost-curriculum` → `/plugin install hackathon-in-a-plugin@devpost-curriculum`.
- Repo: 40 estrellas, **sin licencia declarada**, último push 2026-04-01 — [GitHub](https://github.com/challengepost/devpost-curriculum)
- `hackathon-guide` (skill de fondo, `user-invocable: false`): "You are a hackathon coach guiding a learner through spec-driven development… brisk, encouraging, substantive"; mantiene `process-notes.md`, documentos en `docs/`, guardrails de prerequisitos, feedback ✓/△ de 2-4 frases, y pide `/clear` entre comandos; referencias `eval-rubric.md`, `prd-guide.md`, `spec-patterns.md` y plantillas (scope, PRD, spec, checklist, reflection) — [SKILL.md](https://github.com/challengepost/devpost-curriculum/blob/main/plugins/hackathon-in-a-plugin/skills/hackathon-guide/SKILL.md)
- `/build`: ejecuta `docs/checklist.md` en modo paso a paso o autónomo — [SKILL.md](https://github.com/challengepost/devpost-curriculum/blob/main/plugins/hackathon-in-a-plugin/skills/build/SKILL.md)
- ClaudePluginHub: 39 estrellas, 0 copy clicks, 1 repo público lo usa, "confidence score 23/100 (Limited)", sin README; no lista scripts/hooks/MCP — [claudepluginhub](https://www.claudepluginhub.com/plugins/challengepost-hackathon-in-a-plugin-plugins-hackathon-in-a-plugin)
- asadullah48/hackathon-skills-marketplace: "39+ production-ready skills… hackathon projects", 3 estrellas, push 2026-01-11 (contenido no verificado) — [GitHub](https://github.com/asadullah48/hackathon-skills-marketplace)
- affaan-m/ECC: colección de configuración de "Anthropic hackathon winner" (Anthropic x Forum Ventures, sep-2025, según el autor, no verificado independientemente) — [apiyi blog](https://help.apiyi.com/en/everything-claude-code-plugin-guide-en.html), [GitHub](https://github.com/affaan-m/ECC)

### Inferences
- hackathon-in-a-plugin está pensado para aprender a construir (con muchos documentos y `/clear` entre pasos); para un equipo que necesita ganar en 7,5 h, su `eval-rubric.md` y plantilla de scope pueden servir de referencia, pero el flujo completo es lento. Las skills propias del proyecto (`analizar-desafio`, `prototipo-express`, `pitch-ganador`, `defensa-jurado`) ya están más ajustadas al evento.
- No encontré ningún skill de "hackathon pitch" o "judging" con tracción significativa.

### Gaps
- No leí `eval-rubric.md` del plugin de Devpost (podría tener una rúbrica de jurado útil).
- No verifiqué el contenido de hackathon-skills-marketplace.

---

## 9. Shortlist consolidada para instalar (prioridad, riesgo, encaje)

### Takeaway
Instalación mínima recomendada (todo Markdown, sin scripts, bajo riesgo): **(1) lenny-skills `public-speaking` + `executive-communication`**, **(2) alirezarezvani `executive-mentor`**, **(3) OneWave `pitch-deck-reviewer`**, **(4) coreyhaines31 `marketing-skills`** (o solo `copywriting` + `marketing-psychology`), **(5) addyosmani `accessibility`**. Opcionales: `playground@claude-plugins-official`, `frontend-design` (redundante). No instalar: web-artifacts-builder, webapp-testing/Playwright (ya hay navegador integrado), debate-simulator, Public Speaking Rehearsal, accessibility-agents.

### Cited Findings
| # | Skill / plugin | Fuente | Mantenedor | Popularidad | Último push | Scripts / deps | Encaje hackathon |
|---|---|---|---|---|---|---|---|
| 1 | `public-speaking`, `executive-communication` (lenny-skills) | [repo](https://github.com/RefoundAI/lenny-skills) | RefoundAI | 1.442 ★ | 2026-07-16 | No (Markdown); instalación manual | Alto (ensayo, Q&A ADD, SCR) |
| 2 | `executive-mentor` (board-prep, challenge, stress-test) | [repo](https://github.com/alirezarezvani/claude-skills) | Alireza Rezvani | 28.758 ★ | 2026-10-26 | No en esas carpetas | Alto (jurado adversarial) |
| 3 | `pitch-deck-reviewer` | [SKILL.md](https://github.com/OneWave-AI/claude-skills/blob/main/pitch-deck-reviewer/SKILL.md) | OneWave AI | 382 ★ | 2026-10-20 | No; usa WebSearch/WebFetch | Alto (revisión + objeciones) |
| 4 | `marketing-skills` (copywriting, marketing-psychology, launch) | [repo](https://github.com/coreyhaines31/marketingskills) | Corey Haines | 56.638 ★ | 2026-10-22 | No (Markdown + evals) | Medio-alto (copy, tagline) |
| 5 | `accessibility` (web-quality-skills) | [SKILL.md](https://github.com/addyosmani/web-quality-skills/blob/main/skills/accessibility/SKILL.md) | Addy Osmani | 2.991 ★ | 2026-08-24 | No | Alto (tema inclusión) |
| 6 | `wcag-2.2-aa` | [repo](https://github.com/84emllc/claude-wcag-skill) | 84EM LLC | 0 ★ | 2026-08-05 | Scripts solo de CI | Medio (rigor, baja tracción) |
| 7 | `playground` | [SKILL.md](https://github.com/anthropics/claude-plugins-official/blob/main/plugins/playground/skills/playground/SKILL.md) | Anthropic | marketplace oficial 44.700 ★ | 2026-10-26 | No | Medio (simuladores 1 archivo) |
| 8 | `frontend-design` | [skills.sh](https://skills.sh/anthropics/skills/frontend-design) | Anthropic | 1,0 M instalaciones | 2026-09-03 (carpeta) | No; 3/3 auditorías Pass | Bajo-medio (redundante) |
| 9 | `demo-video` (modo manual) | [SKILL.md](https://github.com/alirezarezvani/claude-skills/blob/main/engineering/demo-video/skills/demo-video/SKILL.md) | Alireza Rezvani | 28.758 ★ (repo) | 2026-10-26 | Opcional: playwright, edge-tts, ffmpeg, build.sh | Medio (guion de demo) |
| 10 | `storytelling` / `storytelling-for-stakeholders` | [SKILL.md](https://github.com/viktorbezdek/skillstack/blob/main/skillstack-workflows/skills/storytelling-for-stakeholders/SKILL.md) | Viktor Bezdek | 14 ★ | 2026-06-05 | No visto | Medio (narrativa) |
| — | NO: `web-artifacts-builder` | [SKILL.md](https://github.com/anthropics/skills/blob/main/skills/web-artifacts-builder/SKILL.md) | Anthropic | — | 2026-04-20 | bash, Node 18+, pnpm global, tarball | Bajo |
| — | NO por ahora: `webapp-testing` | [skills.sh](https://skills.sh/anthropics/skills/webapp-testing) | Anthropic | 188,8 K inst.; Socket/Snyk Warn | 2026-04-20 | Python + Playwright + Chromium | Bajo (hay navegador integrado) |
| — | NO: `debate-simulator` | [SKILL.md](https://github.com/OneWave-AI/claude-skills/blob/main/debate-simulator/SKILL.md) | OneWave | — | — | No | Plantilla vacía |
| — | NO: hackathon-in-a-plugin | [repo](https://github.com/challengepost/devpost-curriculum) | Devpost | 40 ★, sin licencia | 2026-04-01 | No | Bajo (currículo de aprendizaje) |

### Inferences
- Seguridad: ninguna de las 5 recomendadas principales trae scripts ejecutables; todas son Markdown legible (revisar igual antes de instalar). Las que ejecutan código: webapp-testing (Python, `shell=True`), web-artifacts-builder (bash + npm/pnpm desde la red + binario tar.gz), lackeyjb playwright-skill (Node + descarga Chromium), plugin `playwright` (`npx @playwright/mcp@latest` sin versión fija), demo-video (`build.sh` con ffmpeg/edge-tts), hyperframes (npx), Community-Access (instalador de hooks). No se detectó contenido ofuscado en lo leído.
- Instalar plugins completos trae muchas skills extra (p.ej. el plugin `marketing-skills` trae ~50; `executive-mentor` trae 6-7); demasiadas skills activas pueden competir en el disparo con las skills propias `pitch-ganador`/`defensa-jurado`. Alternativa: copiar solo las carpetas puntuales a `C:\Users\<usuario>\.claude\skills\`.
- Prioridad temporal (hoy 26-oct, evento 4-5 nov): instalar y probar esta semana, no el día del evento.

### Gaps
- No verifiqué el comportamiento de `/plugin` dentro de Claude Code en la app de escritorio de Windows para cada marketplace.
- Las fechas de "último push" son a nivel repo; salvo anthropics/skills, no obtuve la fecha de modificación por skill.
