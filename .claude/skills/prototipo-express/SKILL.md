---
name: prototipo-express
description: Usar para construir, modificar o pulir el prototipo de la hackathon (app web, chatbot, dashboard, simulador) a partir de evento/decision.md. Construye una app de un solo archivo HTML en español, accesible, con datos chilenos verosímiles y el flujo del guion de demo, la verifica en el navegador y la publica como Artifact para tener un link.
---

# Prototipo express

El equipo no programa: tú construyes todo. Explica solo lo necesario para que puedan presentarlo.

## Reglas

1. **Un solo archivo HTML** (HTML, CSS y JS en línea; librerías solo desde los CDN permitidos por el Artifact tool). Sin frameworks con compilación. Así abre sin internet y se publica como Artifact.
2. **La demo manda.** Construye exactamente los pasos del guion de `evento/decision.md`, en orden. Nada fuera del guion hasta que el guion funcione de punta a punta.
3. **Hitos:**
   - v0 navegable en 45 min: todas las pantallas, con datos falsos.
   - v1 con el flujo completo de punta a punta **a más tardar a las 12:45**. Es el hito duro del día.
   - **Congelar** a la hora acordada (por defecto 14:30 del día 1). Después, solo arreglos y pulido.
4. **IA en la demo:**
   - La página publicada **no puede llamar APIs externas**: la política de seguridad del Artifact bloquea todo `fetch` a otros dominios. Nada de OpenAI, ElevenLabs, Twilio ni APIs públicas desde la página.
   - Por defecto, **modo demo**: respuestas pregeneradas por ti para cada paso del guion, escritas con calidad real, con una latencia breve y efecto de escritura.
   - IA en vivo, como extra: carga la skill `artifact-capabilities` y usa la capacidad que permite a la página consultar a Claude, en su nivel rápido. Solo funciona para quien abre la página con sesión de Claude iniciada y gasta el uso de esa persona. Mantén siempre la respuesta pregenerada como respaldo si la llamada falla o tarda.
   - El micrófono dentro del Artifact no está verificado. No prometas voz en vivo sin haberla probado antes del evento.
   - Dile al equipo qué es real y qué está simulado. Si el jurado pregunta, se responde con la verdad: "En el prototipo esta parte está simulada; en el piloto se conecta a…".
5. **Datos:** sintéticos pero verosímiles y chilenos (nombres, comunas, cargos, sueldos en CLP, empresas ficticias). Nunca datos personales reales ni RUT reales.
6. **Diseño:** antes de escribir el archivo, carga `artifact-design` (lo exige el Artifact tool). Si queda tiempo después de congelar, pule con `impeccable` o `high-end-visual-design`.
7. **Accesibilidad visible** (el evento es sobre inclusión, el jurado lo notará):
   - `lang="es"`, contraste AA, texto base de 16 px o más, botones grandes.
   - Etiquetas en todos los campos, navegación con teclado, foco visible, texto alternativo.
   - Si calza con la idea: botón de lectura fácil, lectura en voz alta (Web Speech API) o tamaño de texto ajustable.
8. **Móvil:** debe funcionar a 375 px. El jurado puede abrir el link desde un QR.

## Proceso

1. Lee `evento/decision.md`. Si no existe, pide el guion de demo en 5 pasos o sigue el flujo "Elegir desafío e idea" de `CLAUDE.md`.
2. Escribe el archivo en `evento/prototipo/index.html`.
3. Verifica en el panel del navegador: recorre el guion completo, revisa la consola sin errores y prueba el ancho móvil.
4. Con la v1 lista, haz una pasada rápida con la skill `accessibility` y corrige solo lo que se vea en la demo.
5. Publica con el Artifact tool y entrega el link al equipo.
6. Cada cambio posterior: edita, vuelve a publicar en el mismo link y recorre de nuevo el guion.

## Al congelar

- Captura cada paso del guion y guárdalo en `evento/respaldo/`.
- Pide al equipo grabar un video de 60 a 90 segundos de la demo (Windows: Win+Alt+R con Xbox Game Bar). Es el plan B si falla el wifi.
- Escribe en `evento/demo-guion.md` el guion de clics: qué se hace, qué se dice y qué debe ver el jurado en cada paso.
