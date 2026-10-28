---
name: defensa-jurado
description: Usar para preparar la defensa ante el jurado de la hackathon - generar el banco de preguntas probables con respuestas cortas, repartir quién responde qué, y simular al jurado en un ensayo de preguntas con puntaje y mejores versiones de cada respuesta.
---

# Defensa ante el jurado

El jurado de una facultad de economía y negocios pregunta más por negocio, validación e impacto que por tecnología. Prepara las dos cosas, pero prioriza esas tres.

## Modo 1 — Banco de preguntas

Lee `evento/decision.md`, `evento/negocio.md` y `evento/pitch-guion.md`. Genera **25 preguntas** específicas para este proyecto, repartidas en:

| Categoría | Ejemplos de ángulo |
|---|---|
| Problema y validación | ¿Cómo saben que existe? ¿Con quién hablaron? |
| Solución y tecnología | ¿Qué está funcionando de verdad? ¿Qué pasa si la IA se equivoca? |
| IA, ética y datos | Sesgo en contratación, explicabilidad, Ley 21.719 de datos personales, consentimiento |
| Negocio | ¿Quién paga? ¿Cuánto? ¿Costo de adquirir un cliente? |
| Competencia | ¿Por qué no lo hace ya una plataforma existente? |
| Implementación | ¿Cómo sería el piloto con la empresa del desafío? ¿Qué necesitan de ella? |
| Impacto | ¿Cómo se mide? ¿En cuánto tiempo? |
| Equipo | ¿Por qué ustedes? ¿Qué harían con el premio? |

Cada respuesta, de **30 segundos o menos**, con el marco ADD de Matt Abrahams (Stanford):

1. **Answer:** la respuesta directa en la primera frase.
2. **Detail:** un dato con fuente, algo que validaron hoy o algo que muestra la demo.
3. **Describe value:** por qué eso importa para el usuario o para la empresa del desafío.

Si no saben algo, se admite y se ofrece el siguiente paso: "Todavía no lo validamos; en el piloto de 30 días lo medimos con [indicador]". Nombrar una debilidad concreta con su plan **sube** el puntaje según jueces de 2026. Nunca inventar.

Para reforzar este modo:

- `board-prep`: dominar los números de memoria y preparar la narrativa que reconoce debilidades sin perder la sala.
- `strategy-red-team`: atacar los supuestos que sostienen el proyecto antes de que lo haga el jurado.
- Las cifras salen de `research_notes/Claves para ganar Talent Tech Hack/` con su fuente.

Marca quién responde cada pregunta (A: negocio e impacto; B: producto y tecnología). Guarda todo en `evento/preguntas-jurado.md`.

## Modo 2 — Simulación del jurado

Interpreta a tres jurados, de a una pregunta por vez:

- **Académica de la FEN (economía):** rigor, datos, supuestos, escala.
- **Gerente de personas de la empresa del desafío:** implementación real, costo, adopción, riesgo legal.
- **Emprendedora o inversionista:** modelo de negocio, diferenciación, por qué ahora.

Después de cada respuesta del equipo (escrita o dictada):

- Puntaje de 1 a 5 en claridad, evidencia y brevedad.
- Qué faltó, en una línea.
- Una versión mejorada de la respuesta, de 30 segundos o menos.

Cierra la ronda con las 3 preguntas que peor salieron, para ensayarlas otra vez.
