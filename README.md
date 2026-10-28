# Fen-HackTech

Preparación para **Talent Tech Hack 2026** (EmprendeFEN, Facultad de Economía y Negocios, Universidad de Chile, 4 y 5 de noviembre de 2026). Equipo de 2 personas que trabaja sin código, con Claude Code como motor.

## Qué hay aquí

| Carpeta o archivo | Contenido |
|---|---|
| `CLAUDE.md` | Instrucciones para Claude: el evento, cómo trabajar, el flujo del día paso a paso y qué skill usar en cada momento |
| `reports/Claves para ganar Talent Tech Hack.md` | Informe consolidado: criterios del jurado, cómo elegir la idea, datos de Chile, ecosistema, herramientas, pitch, plan de preparación y plan del día |
| `research_notes/Claves para ganar Talent Tech Hack/` | Notas de investigación con fuentes: éxito en hackathons, pitch y defensa, marcos de decisión, mercado laboral chileno, ecosistema HR tech, stack no-code + IA |
| `research_notes/Skills de Claude para hackathons/` | Investigación sobre qué skills existentes instalar y por qué |
| `.claude/skills/` | Skills que Claude Code carga en este proyecto |
| `archivo/skills-propias-retiradas/` | Skills propias reemplazadas por skills externas; no se usan |
| `Talent Tech Hack 2026 · Luma.pdf` | Página del evento en Luma |

## Cómo usarlo

Abrir esta carpeta en Claude Code (app de escritorio, pestaña Code). Claude lee `CLAUDE.md` y las skills de `.claude/skills/` automáticamente.

## Skills y su origen

Dos skills son propias: `prototipo-express` y `defensa-jurado`. Las demás son de terceros, copiadas sin cambios salvo lo indicado, cada una con su licencia original en su carpeta.

| Skills | Fuente | Licencia |
|---|---|---|
| `lean-canvas`, `value-proposition`, `pricing-strategy`, `market-sizing`, `user-personas`, `prioritization-frameworks`, `pre-mortem`, `strategy-red-team` | [phuryn/pm-skills](https://github.com/phuryn/pm-skills) | MIT |
| `public-speaking`, `executive-communication` | [RefoundAI/lenny-skills](https://github.com/RefoundAI/lenny-skills) | MIT |
| `pitch-deck-reviewer` | [OneWave-AI/claude-skills](https://github.com/OneWave-AI/claude-skills) | MIT |
| `accessibility` | [addyosmani/web-quality-skills](https://github.com/addyosmani/web-quality-skills) | MIT |
| `lateral`, `analogy`, `concept-fan`, `inversion`, `provocation`, `random-stimulus`, `scamper`, `six-hats`, `worst-idea` | [danium/lateral-thinking](https://github.com/danium/lateral-thinking) | MIT |
| `product-brainstorming`, `interview-prep`, `recruiting-pipeline` | [anthropics/knowledge-work-plugins](https://github.com/anthropics/knowledge-work-plugins) | Apache-2.0 |
| `copywriting` | [coreyhaines31/marketingskills](https://github.com/coreyhaines31/marketingskills) | MIT |
| `board-prep` | [alirezarezvani/claude-skills](https://github.com/alirezarezvani/claude-skills) | MIT |

Cambios hechos a skills de terceros:

- `pitch-deck-reviewer`: se quitaron las líneas `tools:` y `model:` del encabezado, que daban permisos que la skill no usa.
- `copywriting`: se quitaron cifras de conversión sin fuente verificable, y no se copió la carpeta `evals/`.
