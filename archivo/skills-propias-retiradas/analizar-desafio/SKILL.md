---
name: analizar-desafio
description: Usar cuando se revelan los desafíos de Talent Tech Hack (texto, foto o PDF del brief) o cuando el equipo debe elegir desafío, idea o alcance del MVP. Decodifica los desafíos, genera y puntúa ideas, recomienda una y deja la ficha de decisión en evento/decision.md en 45 minutos o menos.
---

# Analizar desafío

Objetivo: pasar del brief a una decisión firme (desafío + idea + MVP + guion de demo) en **45 minutos o menos**. Una decisión buena a las 10:30 vale más que una perfecta a las 12:00. Tú recomiendas; el equipo decide.

## Entrada

- Texto, foto o PDF de los 3 desafíos. Si es foto, transcríbela primero a `evento/desafios.md`.
- Lo que el equipo escuchó en la presentación: qué empresa presentó cada desafío, quién habló, qué dijo que le duele. Pregúntalo en una línea si no viene.
- Las bases y criterios de evaluación, si los entregaron. Si existen, **reemplazan** los pesos por defecto del paso 4.

## Paso 1 — Decodificar cada desafío (10 min, los 3 a la vez)

Una tabla por desafío:

| Campo | Contenido |
|---|---|
| Dueño | Empresa o área que lo propone |
| KPI real | Lo que mide el jefe del dueño: rotación, tiempo de contratación, cumplimiento Ley 21.015, denuncias Ley Karin, costo, NPS, productividad |
| Usuario final | Persona concreta, con nombre y contexto chileno (comuna, edad, situación) |
| Dolor en una frase | "Hoy [usuario] pierde [qué] porque [causa]" |
| Restricciones | Explícitas e implícitas: datos disponibles, regulación (Ley 21.719 de datos personales, Ley Karin, Ley 21.015, Ley 40 horas), presupuesto, adopción |
| Criterios | Explícitos, o inferidos de la redacción del desafío |
| Demostrable | ¿Se puede mostrar funcionando en 7 horas con una app web + IA? (alto / medio / bajo) |
| Competencia | ¿Cuántos equipos lo elegirán? El desafío más obvio es el más competido |

Usa los datos de `research_notes/Claves para ganar Talent Tech Hack/mercado_laboral_chile.md` para anclar el dolor en una cifra con fuente.

## Paso 2 — Preguntas para el dueño y los mentores (5 min)

Escribe 5 preguntas cortas cuya respuesta cambie la solución. El equipo sale a hacerlas mientras tú sigues. Base:

1. ¿Qué han probado ya y por qué no funcionó?
2. ¿Quién decidiría comprar o adoptar esto, y con qué presupuesto?
3. ¿Qué dato tienen hoy y no están usando?
4. ¿Cómo sabrían en 3 meses que funcionó?
5. ¿Qué es lo que **no** quieren ver otra vez?

## Paso 3 — Ideas (10 min)

Tres ideas por desafío, cada una con un patrón distinto:

- **Para el usuario final:** asistente o agente de IA (coach de carrera, simulador de entrevista, traductor a lectura fácil, guía por voz).
- **Para quien decide:** herramienta de gestión (dashboard, matching por habilidades, auditor de sesgo en avisos, control de cumplimiento).
- **Puente o proceso:** conectar oferta y demanda, credenciales verificables, ruta de reconversión.

Cada idea en este formato:

> **Nombre tentativo.** Para [usuario] que [dolor], [nombre] es [categoría] que [beneficio clave]. A diferencia de [alternativa actual], [diferenciador]. **Momento wow de la demo:** [lo que el jurado ve y recuerda].

Antes de recomendar, revisa `research_notes/Claves para ganar Talent Tech Hack/ecosistema_hrtech.md`. Si la idea ya existe en Chile, dilo y diferénciala explícitamente.

## Paso 4 — Puntuar (5 min)

Matriz ponderada, notas de 1 a 5:

| Criterio | Peso por defecto |
|---|---|
| Impacto en el KPI del dueño y en las personas | 25% |
| Factibilidad de una demo funcional en ~5 h | 20% |
| Claridad del problema (hay un dato duro que lo respalda) | 15% |
| Factor wow y diferenciación | 15% |
| Modelo de negocio claro (quién paga) | 15% |
| Ajuste al tema inclusión y mercado laboral | 10% |

Muestra la tabla con totales. Recomienda la ganadora y una alternativa. Agrega un **pre-mortem**: "Si perdemos con esta idea, será porque…" con 3 razones y cómo mitigar cada una.

## Paso 5 — MVP y guion de demo (10 min)

- Escribe el **guion de demo** (camino feliz en 5 pasos) **antes** de construir. Es la especificación del prototipo.
- Clasifica funciones:
  - **Construir:** lo que aparece en el guion.
  - **Simular:** lo que se finge de forma creíble (datos sintéticos, respuestas de IA pregeneradas).
  - **No hacer:** todo lo demás, por escrito.
- Reglas: máximo 3 pantallas y 1 momento wow.

## Salida

Escribe `evento/decision.md` con: desafío elegido, problema en una frase con cifra y fuente, usuario, idea en una línea, tabla de puntaje, MVP (construir / simular / no hacer), guion de demo, riesgos del pre-mortem y preguntas pendientes.

Cierra diciendo qué hace cada persona la próxima hora. Por defecto: **persona A** trabaja conmigo en el prototipo (skill `prototipo-express`); **persona B** valida con mentores y el dueño del desafío y empieza el modelo de negocio (skill `negocio-e-impacto`).
