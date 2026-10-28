# Stack no-code + IA para prototipar en ~7 horas (Talent Tech Hack 2026, FEN U. de Chile, 4-5 nov 2026)

> Notas de investigación al 26-oct-2026. Los precios y límites de planes cambian muy rápido: todo lo que diga "precio", "créditos" o "límite" debe re-verificarse en la página oficial la semana del evento. Marco con **[VERIFICAR]** lo que tiene fuentes en conflicto o solo de terceros, y con **[POSIBLE DESACTUALIZADO]** lo anterior a mediados de 2026.
> Nota de método: algunas citas apuntan a archivos locales del entorno Claude Code del usuario (el "contrato runtime" de Artifacts v0.2.91). Son fuente primaria de lo que *esta* cuenta puede hacer hoy, pero están en una carpeta temporal y pueden desaparecer o cambiar de versión.
> No encontré ninguna página pública del evento "Talent Tech Hack 2026" de la FEN (ver Gaps de la sección 8).

## 1. Constructores de apps con IA (Lovable, Bolt.new, v0, Replit Agent, Google AI Studio / Firebase Studio, Claude Artifacts, Cursor/Claude Code): para qué sirve cada uno, planes gratis, velocidad, deploy y confiabilidad en demos

### Takeaway
Para un equipo sin programación que ya tiene Claude, el camino de menor riesgo es **Claude Code (en la app de escritorio) publicando un Artifact de una sola página**: tiene link público sin login para lo estático, puede llamar a Claude con la cuenta del que mira (sin API keys) y no cuesta nada aparte del plan Pro. Lovable/Bolt/v0/Replit sirven como plan B para apps multipágina con login y base de datos, pero sus planes gratis se acaban en un día de hackathon. Firebase Studio está en retirada y no conviene usarlo.

### Cited Findings
**Claude Code Artifacts (lo más relevante para este equipo)**
- Un artifact es "una página web interactiva y en vivo" que Claude Code publica desde la sesión a una URL privada en claude.ai, y se actualiza en el mismo lugar cuando la sesión sigue trabajando. Disponible en planes Pro, Max, Team y Enterprise, con la sesión iniciada vía `/login` — [Claude Code Docs: Share session output as artifacts](https://code.claude.com/docs/en/artifacts)
- Funciona en la CLI o en la **app de escritorio de Claude versión 1.13576.0 o superior**; las sesiones con API key, token de gateway o credenciales de nube no pueden publicar; no funciona vía Bedrock/Vertex/Foundry — [Claude Code Docs](https://code.claude.com/docs/en/artifacts)
- Compartir: un artifact nuevo es visible solo para ti; se comparte desde el botón **Share**. En Pro/Max se puede compartir "públicamente", con un link que cualquiera en internet abre **sin iniciar sesión en claude.ai**. Cada publicación es una versión y se puede elegir qué versión ven los demás — [Claude Code Docs](https://code.claude.com/docs/en/artifacts)
- Restricciones de la página: un solo HTML autocontenido, sin backend ni múltiples rutas; CSP estricta. Solo se pueden cargar fuentes de Google Fonts y scripts de cdnjs, unpkg, los CDN de Tailwind y jQuery, y rutas como `/npm/` de jsDelivr. **`fetch`, XHR y WebSocket solo llegan al propio origen de la página** (o sea, no se puede llamar a OpenAI, ElevenLabs, Twilio, etc. desde el artifact). Las imágenes externas están bloqueadas y se embeben como data URI. Tamaño máximo renderizado: 16 MiB. La página no puede iniciar descargas sola, salvo con la capacidad "downloads" — [Claude Code Docs](https://code.claude.com/docs/en/artifacts)
- Conectores MCP desde artifacts (Pro+ y Claude Code ≥ v2.1.209): cada llamada usa la **cuenta del que mira**, se pide permiso la primera vez, y **para alguien que abre el link público sin iniciar sesión, o desde fuera de la organización, no corren las llamadas**: ve la página sin sus secciones en vivo — [Claude Code Docs](https://code.claude.com/docs/en/artifacts)
- Plantillas: Claude Slides (presentación), Claude Design (canvas de diseño) y Claude Docs; se exportan a PowerPoint, PDF o Word; `/slides` y `/design` requieren Claude Code v2.1.265+. Están en beta y activadas por defecto en Pro, Max y Team — [Claude Code Docs](https://code.claude.com/docs/en/artifacts)
- Help Center (2026): los artifacts pueden llamar a Claude directamente: "No API keys are required, and there's no cost to you"; los usuarios entran con su cuenta y el uso se descuenta de su propio plan. Almacenamiento (Pro+) personal o compartido, solo texto, tope de 20 MB por artifact. Los conectores leen y escriben apps conectadas. Tipos: Docs, Slides, Design, Dashboards (beta, Pro+) y Motion (beta, exporta MP4; solo Team y Enterprise). **Los artifacts "legacy" creados antes del 16-sep-2026 siguen funcionando, pero ya no se pueden crear nuevos** — [Claude Help Center: What are artifacts](https://support.claude.com/en/articles/17153992-what-are-artifacts-and-how-do-i-use-them)
- Artículo de compartir (23-sep-2026): normalmente quien mira necesita cuenta de Claude, salvo un artifact legacy de chat publicado en Free/Pro/Max. "Artifacts that connect to your apps or use Claude can't be shared by link" (aplicado a ese flujo de compartir); el almacenamiento compartido es visible para todos los que abren el artifact; despublicar borra los datos de forma permanente — [Claude Help Center: Discovering, publishing, customizing and sharing artifacts](https://support.claude.com/en/articles/9547008-discovering-publishing-customizing-and-sharing-artifacts)
- Contrato runtime en esta cuenta (v0.2.91): capacidades declarables `artifact`, `assets`, `comments`, `db`, `downloads`, `files`, `mcp`, `room`, `sample`, `user` (más `permissions`, que viene integrada). **No aparece ninguna capacidad de micrófono/cámara/voz** en el contrato local (busqué "microphone|camera|speech|audio" y no hubo coincidencias) — [skill local artifact-capabilities, contrato 0.2.91](file:///C:/Users/jojon/AppData/Local/Temp/claude/bundled-skills/2.1.308/28b6634fe4f00ba2a43cf26b79336fb4/artifact-capabilities/)
- `sample` (preguntarle a Claude desde la página): gasta el **uso de Claude del que mira**; la primera llamada pide consentimiento; cada llamada es sin memoria (hay que mandar instrucciones + datos + formato en el input); admite imágenes si se declara `{sample:{images:true}}`; con tier "quick" un prompt corto responde en 1-2 s, y con "default"/"complex" el primer texto tarda normalmente 5-60 s (hasta 2 min con prompts largos). Hay caché de 5 min para inputs idénticos y un exceso de llamadas devuelve `rate_limited`. Si la página no está dentro de un visor de Claude, `use("sample")` devuelve `null` — [sample.d.ts local](file:///C:/Users/jojon/AppData/Local/Temp/claude/bundled-skills/2.1.308/28b6634fe4f00ba2a43cf26b79336fb4/artifact-capabilities/0.2.91/sample.d.ts)
- Historial: Claude Code Artifacts se lanzó en beta el 18-jun-2026 para Team/Enterprise y llegó a Pro/Max en julio de 2026 (fuente secundaria) — [AI Catchup](https://aicatchup.com/news/claude-code-artifacts-pro-max); los "AI-powered artifacts" originales son de julio de 2025 y en su lanzamiento no tenían llamadas a APIs externas ni almacenamiento persistente **[POSIBLE DESACTUALIZADO]** — [Anthropic: Claude-powered artifacts](https://anthropic.com/news/claude-powered-artifacts)
- Plan Claude: Pro ~US$20/mes (US$17 anual), Max US$100 o US$200; Claude Code viene en Pro; Pro y Max comparten un solo pozo de uso entre chat, Claude Code y Cowork. En abril de 2026 Anthropic probó quitar Claude Code de Pro al 2% de las altas nuevas y lo revirtió en un día **[VERIFICAR en claude.com/pricing]** — [Zenken: Claude Pro deep dive](https://ai.zenken.co.jp/en/post/claude-pro-plan-deep-dive/); [Superblocks: Claude Code pricing](https://www.superblocks.com/blog/claude-code-pricing)

**Lovable**
- Plan Free: 5 créditos de build diarios (hasta 30/mes), 20 créditos Cloud/mes y 4 créditos para funciones de IA dentro de las apps; los créditos diarios no se acumulan. Hay descuento para estudiantes con email universitario en lovable.dev/students (la página no dice el monto). La página no mostró los precios de los planes — [Lovable Pricing](https://lovable.dev/pricing)
- Terceros: los proyectos gratis son solo públicos; Pro cuesta ~US$25/mes **[VERIFICAR]** — [Dyad: Free AI app builders compared](https://www.dyad.sh/blog/free-ai-app-builders-compared); [DEV: Lovable vs Bolt vs Replit vs v0 2026](https://dev.to/devtoolpicks/lovable-vs-bolt-vs-replit-vs-v0-in-2026-best-vibe-coding-tool-for-solo-developers-d88)
- Posicionamiento: pensado para fundadores no técnicos que hacen apps full-stack con Supabase — [MeshWorld comparison](https://meshworld.in/blog/ai/v0-vs-lovable-vs-bolt-vs-replit-ai-2026/)
- Evidencia de hackathon: un estudiante de primer año de Stanford hizo una herramienta musical funcional ("Beatify") en dos horas solo con el chat de Lovable (la nota no dice si ganó) — [CreateWith](https://www.createwith.com/tool/lovable/updates/stanford-freshman-builds-music-ai-tool-in-two-hours-using-lovable-at-hackathon); experiencia de primera prueba en hackathon — [Product Experience Substack](https://productexperience.substack.com/p/lovable-ai-prototype-hackathon-experience)

**Bolt.new**
- Free: US$0, 1M tokens/mes con tope de 300K/día, hosting incluido sin dominio propio, bases de datos ilimitadas y marca Bolt en el sitio. "Free forever, no card required". Pro: US$18/mes facturado anual (US$25 mensual, deducido de US$300→216/año), 10M tokens/mes sin tope diario y con acumulación (rollover) — [Bolt Pricing](https://bolt.new/pricing)

**v0 (Vercel)**
- Free: US$0, 7 mensajes/día, deploy a Vercel, Design Mode y sync con GitHub; US$5 en créditos únicos para usuarios nuevos. Plus: US$30/usuario/mes con US$30 en créditos más US$2 diarios al iniciar sesión — [v0 Pricing](https://v0.app/pricing)
- Es solo frontend, sin backend incluido; los terceros estiman 3-8 prompts/día de trabajo real en el plan gratis — [Dyad](https://www.dyad.sh/blog/free-ai-app-builders-compared); [DEV comparison](https://dev.to/devtoolpicks/lovable-vs-bolt-vs-replit-vs-v0-in-2026-best-vibe-coding-tool-for-solo-developers-d88)

**Replit Agent**
- La página oficial muestra Core a US$20/mes (US$18 anual) y Pro a US$100/mes; **no mostró ningún plan Starter gratuito** — [Replit Pricing](https://replit.com/pricing); terceros hablan de un "Starter (Free)" con créditos diarios del Agent y 1 app publicada, o de una prueba que expira **[CONFLICTO / VERIFICAR]** — [DEV comparison](https://dev.to/devtoolpicks/lovable-vs-bolt-vs-replit-vs-v0-in-2026-best-vibe-coding-tool-for-solo-developers-d88)
- Replit es la plataforma todo-en-uno más amplia, pero su costo real suele sorprender — [Lovable guide: Bolt vs Replit vs Lovable](https://lovable.dev/guides/bolt-vs-replit-vs-lovable) (fuente con sesgo, es de un competidor)

**Google AI Studio (Build) / Firebase Studio**
- AI Studio Build (ai.studio/build) se puede usar sin datos de pago; según VentureBeat, el deploy a Cloud Run y Veo requieren API key pagada — [VentureBeat](https://venturebeat.com/ai/googles-new-vibe-coding-ai-studio-experience-lets-anyone-build-deploy-apps); un blog de Google Cloud del 21-may-2026 titula "full-stack vibe coding with Cloud Run, Firebase, and Cloud SQL, no credit card required" **[CONFLICTO: no está claro si el deploy es gratis]** — [Google Cloud Blog](https://cloud.google.com/blog/products/databases/vibe-coded-ai-studio-apps-with-firestore-firebase-cloud-sql)
- AI Studio soporta runtimes full-stack, con lógica de servidor, manejo de secretos y paquetes npm — [Google AI: Build apps in AI Studio](https://ai.google.dev/gemini-api/docs/aistudio-build-mode?hl=en)
- **Firebase Studio**: anunciaron su cierre el 19-mar-2026; desde el 22-jun-2026 no se pueden crear workspaces nuevos y se apaga el 22-mar-2027. Sus funciones pasan a AI Studio (prototipado en el navegador) y Antigravity (código agéntico) — [Firebase: Studio sunset](https://firebase.google.com/docs/studio/migrating-project); [Storyboard18](https://www.storyboard18.com/digital/google-to-shut-firebase-studio-in-2027-shifts-focus-to-ai-studio-and-antigravity-92922.htm)
- Gemini API gratis: los límites son por proyecto (no por key), se miden en RPM/TPM/RPD, el RPD se reinicia a medianoche hora del Pacífico y cambian por modelo. Terceros estiman ~5-10 RPM en el tier gratis, y algunos modelos muestran límite 0 **[VERIFICAR en AI Studio > Dashboard]** — [Google AI: billing](https://ai.google.dev/gemini-api/docs/billing?authuser=9); [Fast.io](https://fast.io/resources/gemini-api-rate-limit/); [Google AI forum](https://discuss.ai.google.dev/t/gemini-api-requests-failing-on-a-brand-new-api-key/121839)

**Cursor / Claude Code**
- No investigué precios de Cursor. Claude Code viene incluido en Claude Pro (ver arriba).

### Inferences
- **Recomendación por defecto:** Claude Code en la app de escritorio → un Artifact HTML de una sola página (Tailwind/Chart.js/pdf.js desde cdnjs o jsDelivr) que usa `sample` para la IA. No necesita API keys ni deploy, y Claude lo itera en minutos. El link público muestra la UI a cualquiera, pero la IA solo funciona para quien tiene sesión iniciada en Claude (y gasta *su* uso). En la práctica: **la demo en vivo se hace desde el laptop del equipo, con sesión iniciada**, y para jurados que abran el link sin cuenta se agrega un "modo demo" con respuestas precalculadas.
- Como la CSP bloquea llamadas externas, cualquier integración "real" (WhatsApp, ElevenLabs, APIs del gobierno) **no puede vivir dentro del artifact**. Se resuelve con datos embebidos, audio pregenerado como data URI o una herramienta aparte.
- Lovable es el mejor plan B si el jurado valora "app real con login + base de datos + URL propia", pero 5 créditos/día no alcanzan para 7 horas: habría que pagar 1 mes de Pro (o usar el descuento estudiantil) y practicar antes. Bolt Free (300K tokens/día) aguanta más, pero es arriesgado en una jornada intensa.
- Hay que **evitar Firebase Studio** (no admite workspaces nuevos). Google AI Studio Build es la alternativa gratis si se quiere Gemini (por ejemplo, para multimodal), pero el free tier de la API tiene RPM bajos y el riesgo de un 429 en plena demo es real.
- Los tutoriales de YouTube de 2025 sobre "Publish artifact" en el chat de claude.ai describen el flujo *legacy*, que desde el 16-sep-2026 ya no permite crear artifacts nuevos. No hay que guiarse por ellos.
- Conviene que **ambos integrantes tengan Claude Pro**: el uso es por cuenta y compartido entre chat y Claude Code, así que si uno llega al límite a mitad de la jornada, el otro sigue construyendo o presentando.

### Gaps
- No encontré benchmarks independientes de confiabilidad en demos en vivo (tasa de caídas) para Lovable, Bolt, v0 o Replit en 2026.
- No conseguí el precio exacto de Lovable Pro ni el monto del descuento estudiantil desde la página oficial (no cargaron las tarjetas de planes).
- No está confirmado si un artifact de Claude Code puede usar el micrófono (`getUserMedia` / Web Speech) dentro del iframe sandbox de claude.ai. Hay que probarlo antes del evento.
- No revisé precios de Cursor ni de Antigravity.
- No sé si `sample` funciona para quien abre un link público *con* sesión iniciada pero desde otra cuenta Pro/Free (las docs lo describen para conectores; para `sample` solo dice que se usa la cuenta del que mira). Hay que probarlo con la cuenta del compañero.

## 2. Constructores no-code (Glide, Softr, Bubble, FlutterFlow, Framer, Webflow, Typeform/Tally, Airtable, Notion): cuándo usar cada uno en una demo

### Takeaway
En una hackathon de 7 horas con Claude como constructor principal, los no-code "clásicos" sirven como piezas puntuales: **Tally** para formularios reales (gratis e ilimitado), **Glide/Softr** si se quiere una app sobre una planilla con usuarios, y **FlutterFlow** solo si se necesita una app móvil nativa. Bubble, Webflow y Framer tienen demasiada curva o limitaciones en el plan gratis para este plazo.

### Cited Findings
- **Glide**: el plan gratis permite apps borrador con hasta 25.000 filas y 1 editor, y está pensado más para aprender. La sincronización con Airtable/Excel parte en el plan Business — [Jotform: Softr vs Glide 2026](https://www.jotform.com/blog/softr-vs-glide/); en cambio, Noloco (jul-2025) dice que el plan gratis incluye 1 app de escritorio publicada **[CONFLICTO]** — [Noloco](https://noloco.io/softr-vs-glide-comparison)
- **Softr**: el plan gratis tiene 10 usuarios de la app y 5.000 registros, con 1 app publicada — [ToolQuestor](https://toolquestor.com/vs/glide-vs-softr); [Noloco](https://noloco.io/softr-vs-glide-comparison)
- **Bubble**: interfaz, base de datos y lógica en una sola plataforma, con curva empinada para apps complejas y sin exportación de código. Gratis: 50.000 workload units, 1 editor, **sin deploy en vivo** y con marca Bubble (tabla de Jet Admin, sep-2026, no verificada con el proveedor) — [Jet Admin: Bubble vs FlutterFlow](https://www.jetadmin.io/blog/bubble-vs-flutterflow/); [Softr: Bubble vs FlutterFlow](https://www.softr.io/blog/bubble-vs-flutterflow)
- **FlutterFlow**: es frontend, así que necesita un backend externo (Firebase/Supabase), y está orientado a apps nativas iOS/Android. Gratis: editor visual completo, hasta 2 proyectos y publicación web (Jet Admin, no verificado) — [Jet Admin](https://www.jetadmin.io/blog/bubble-vs-flutterflow/)
- **Tally**: el plan gratis tiene formularios, envíos y preguntas ilimitados, con lógica condicional y campos calculados. Pro cuesta US$29/mes (fuente: el propio Tally) — [Tally Help](https://tally.so/help/free-typeform-alternatives). **Typeform** gratis: 10 respuestas/mes — [CleverX](https://cleverx.com/blog/typeform-vs-tally-form-builders-compared)

### Inferences
- **Typeform gratis (10 respuestas/mes) no sirve** si el jurado o el público van a responder en vivo; Tally sí.
- Un artifact de Claude con la capacidad `db` reemplaza a Airtable/Notion como "base de datos de demo" (filas compartidas que Claude puede sembrar), sin cuentas extra. Eso sí, solo funciona para usuarios con sesión iniciada.
- Glide/Softr tienen sentido si la propuesta es "portal para RR.HH./candidatos con login" y el equipo ya los conoce. Si no, aprenderlos el mismo día compite con el tiempo de construcción.
- Framer y Webflow sirven para landing pages de marketing; en una hackathon de 7 horas, un artifact o el template Claude Design cumple el mismo rol.

### Gaps
- No obtuve datos verificados 2026 de los planes gratis de Framer, Webflow, Airtable ni Notion (no los investigué en profundidad).
- Las cifras de Glide/Softr/Bubble/FlutterFlow vienen de comparativas de terceros, varias con sesgo comercial (Jet Admin, Softr, Noloco son competidores). **[VERIFICAR]**

## 3. Automatización y agentes de IA (Make, Zapier, n8n, Relevance AI, Voiceflow, Botpress) y demos de bot de WhatsApp (sandbox de Twilio, números de prueba de Meta)

### Takeaway
Un bot de WhatsApp *real* es posible gratis con el **Twilio Sandbox** o el **número de prueba de Meta (Cloud API)**, pero tiene fricción: los usuarios tienen que unirse con un código o estar preverificados (máx. 5 números en Meta), hay límites de ritmo y tokens que expiran. Para una demo de 7 horas, lo más seguro es una **interfaz de chat "estilo mensajería" dentro de un artifact con Claude** y, como complemento opcional, un video grabado (o un teléfono preconfigurado) con el bot real.

### Cited Findings
**WhatsApp**
- **Twilio Sandbox for WhatsApp**: sin límite de mensajes ni de tiempo de uso, pero las cuentas de prueba (trial) tienen tope de 50 mensajes/día. El número del sandbox envía solo 1 mensaje cada 3 segundos y es para pruebas funcionales. Solo llega a usuarios que se unieron enviando "join <palabra clave>" (si no, aparece el error 63015), y la sesión expira 3 días después de unirse. Los mensajes iniciados por la empresa requieren plantillas (el sandbox trae 3 preconfiguradas). Hay ventana de 24 h para respuestas libres. El número compartido puede estar bloqueado temporalmente en algunos países (por ejemplo Brasil e Indonesia) — [Twilio Docs: WhatsApp Sandbox](https://twilio.com/docs/whatsapp/sandbox); [Twilio: Rules and Best Practices](https://support.twilio.com/hc/en-us/articles/360017773294-Rules-and-Best-Practices-for-WhatsApp-Messaging-on-Twilio)
- **Meta WhatsApp Cloud API**: al agregar el producto WhatsApp a una app se crea una cuenta de prueba con un número de prueba que envía mensajes gratis a **hasta 5 números destinatarios**, verificados con un código que llega por WhatsApp. Se prueba con la plantilla `hello_world` — [Meta: Cloud API Get Started](https://developers.facebook.com/docs/whatsapp/cloud-api/get-started/)
- Un desarrollador reporta que en las cuentas de prueba el token expira cada 24 h y que la lista de números de prueba no se puede cambiar una vez creada **[BAJA CONFIANZA / VERIFICAR]** — [whatsappcloud (PyPI)](https://pypi.org/project/whatsappcloud/0.0.4)
- Hay proveedores que ofrecen rutas no oficiales vía QR (por ejemplo Whapi). Son publicidad y pueden violar los términos de Meta — [Whapi.Cloud](https://whapi.cloud/blog/how-to-use-whatsapp-api-without-meta-business-verification)

**Plataformas de automatización y bots**
- **Make**: el plan Free da 1.000 créditos/mes y 1 MB de almacenamiento (1 data store). Los créditos son la unidad de cobro "As of August 27" (sin año en la página, probablemente 2025) — [Make Pricing](https://www.make.com/en/pricing)
- **n8n**: Cloud no tiene plan gratis permanente, solo una prueba de 14 días con 1.000 ejecuciones, sin tarjeta. Starter cuesta ~€/US$20/mes (2.500 ejecuciones) y Pro ~€/US$50/mes. La Community Edition auto-hospedada es gratis y sin límites, pero requiere un servidor **[VERIFICAR en n8n.io/pricing]** — [Selfhost.dev](https://selfhost.dev/blog/n8n-pricing/); [NoCode MBA](https://www.nocode.mba/articles/n8n-pricing); n8n suele necesitar un frontend de chat aparte — [Dealism: Botpress alternatives](https://dealism.ai/blog/best-botpress-alternatives)
- **Botpress**: el plan Pay-as-you-go cuesta US$0 base, con 500 mensajes entrantes/mes, 1 asiento y US$5/mes de crédito de IA ("AI Spend" a costo del proveedor). Una fuente pone el canal WhatsApp en el plan Plus (~US$89/mes), y además se paga el fee del canal **[CONFLICTO / VERIFICAR]** — [eesel: Botpress pricing](https://www.eesel.ai/blog/botpress-pricing); [Lindy: Botpress pricing](https://wf.lindy.ai/blog/botpress-pricing)
- **Botpress vs Voiceflow**: Botpress tiene más integraciones y canales, pero cuesta más para principiantes; Voiceflow es más intuitivo y soporta voz y telefonía — [Chatimize](https://chatimize.com/botpress-vs-voiceflow/)
- **Voiceflow**: el plan Starter es gratis con 100 créditos/mes, 1 editor y 2 agentes (abr-2026); Pro cuesta US$60/mes y Business US$150/mes — [Ringly: Voiceflow pricing](https://www.ringly.io/blog/voiceflow-pricing). Un post de sep-2026 dice que el sistema de créditos cambió (créditos gratis/mes = valor del plan) **[CONFLICTO]** — [Macha](https://www.getmacha.com/blog/voiceflow-pricing-explained)

### Inferences
- **Para la demo principal no conviene un WhatsApp real.** Cada jurado tendría que enviar "join xxx" al sandbox de Twilio (o estar preverificado entre los 5 números de Meta), el ritmo es de 1 mensaje cada 3 s y la cadena WhatsApp→Twilio→Make/n8n→LLM tiene 4 puntos donde puede fallar con el Wi-Fi del evento. Además, como el artifact no puede hacer fetch externo, la IA del bot real tendría que venir de otro proveedor (por ejemplo Gemini con key gratis, con RPM bajos) o de la API de Claude (prepago, aparte del plan Pro).
- **Patrón recomendado:** (1) un artifact con un "teléfono" y una UI de chat genérica estilo mensajería, conectada a Claude con `sample`: es lo que se muestra en vivo; (2) opcionalmente, un video de 30-60 s del bot real en WhatsApp (sandbox de Twilio + Make) grabado antes de la presentación, para demostrar que el canal es factible; (3) en el pitch, explicar el camino a producción (WhatsApp Business API con número propio y plantillas aprobadas).
- No hay que usar el logo ni la marca de WhatsApp en la maqueta: basta con "chat por mensajería". Así se evitan problemas de marca y que la publicación del artifact se rechace por imitar a una organización real.
- Si el equipo insiste en un bot real, la ruta más simple sin programar es **Twilio Sandbox + Make (escenario webhook→LLM→respuesta)**. Hay que crearla y probarla **antes** del 4-nov y dejar unido el teléfono que se usará en el escenario (recordando que la sesión expira a los 3 días: hay que volver a unirse la mañana del evento).
- Chile no aparece entre los países bloqueados en el texto de Twilio, pero se debe confirmar con un mensaje de prueba desde un número +56.

### Gaps
- No investigué Zapier ni Relevance AI (planes gratis 2026).
- No confirmé si el sandbox de Twilio entrega bien a números chilenos +56 en 2026.
- No hay fuente oficial confirmada sobre cuánto dura el token temporal de Meta (24 h según un tercero).

## 4. Voz y accesibilidad con IA (STT/TTS: ElevenLabs, OpenAI, Web Speech API; LSCh; lectura fácil; lectores de pantalla; checklist WCAG 2.2)

### Takeaway
Para la voz en la demo, la opción gratuita y sin keys es la **Web Speech API del navegador** (Chrome/Edge). El reconocimiento de Chrome envía el audio a los servidores de Google (necesita internet), aunque desde Chrome 139 existe una opción on-device. Si se quiere una voz premium, hay que pregenerar audios con ElevenLabs (10.000 créditos gratis/mes, sin licencia comercial). La **traducción automática a Lengua de Señas Chilena (LSCh) no está madura** (precisión académica ~0,75): no hay que prometerla en vivo. En accesibilidad, conviene mostrar 4-5 criterios WCAG 2.2 concretos.

### Cited Findings
**Web Speech API**
- Chrome tiene soporte completo de SpeechRecognition y envía el audio a los servidores de Google. Edge funciona igual (Chromium). Safari lo soporta desde 14.1 (macOS) y 14.5 (iOS) con el prefijo `webkitSpeechRecognition`. En Firefox está detrás de un flag — [AssemblyAI: Web Speech API](https://www.assemblyai.com/blog/speech-recognition-javascript-web-speech-api); Mozilla confirma que Chrome, Edge, Safari y Opera soportan una forma de la API y Firefox no **[POSIBLE DESACTUALIZADO]** — [Mozilla Wiki](https://wiki.mozilla.org/Web_speech_api); al depender del servidor, requiere estar online — [Twilio blog](https://www.twilio.com/en-us/blog/speech-recognition-browser-web-speech-api)
- **Chrome 139 (ago-2025)** agregó reconocimiento on-device: los sitios pueden consultar si está disponible por idioma, pedir la instalación de recursos y elegir entre on-device o nube — [Chrome 139 release](https://developer.chrome.com/blog/new-in-chrome-139?hl=en); con `processLocally = true` el reconocimiento debe hacerse en el dispositivo, y hay estado "downloadable" cuando el paquete de idioma no está descargado — [MDN: processLocally](https://developer.mozilla.org/docs/Web/API/SpeechRecognition/processLocally)
- Edge (v150) lista para on-device inglés, alemán, italiano, portugués (pt-PT), **español (es-ES)** y coreano — [Microsoft Learn: Edge speech recognition](https://learn.microsoft.com/fi-fi/microsoft-edge/web-platform/speech-recognition-api)
- Un reporte anecdótico (era Chrome 160) dice que la demo de Web Speech de Google dejó de procesar el micrófono en una máquina Windows — [H5P forum](https://h5p.org/taxonomy/term/337)

**ElevenLabs**
- El plan gratis da 10.000 créditos/mes (~10 min de voz), sin licencia comercial (solo evaluación). Starter cuesta ~US$5-6/mes **[VERIFICAR]** — [Dupple: Is ElevenLabs free](https://dupple.com/learn/is-elevenlabs-free); [BigVU: ElevenLabs pricing 2026](https://bigvu.tv/blog/elevenlabs-pricing-2026-plans-credits-commercial-rights-api-costs/)

**Lengua de Señas Chilena (LSCh)**
- Chile reconoció la LSCh en 2021 como lengua natural y patrimonio de la comunidad sorda — [El Mostrador (2024)](https://www.elmostrador.cl/agenda-pais/agenda-inclusiva/2024/10/12/el-derecho-a-la-lengua-de-senas-desafio-clave-para-una-educacion-inclusiva/); la U. Santo Tomás cita la **Ley 21.303** como reconocimiento oficial — [UST Diplomado LSCh](https://www.postgradoust.cl/programas/diplomados/lengua-senas-para-comunicacion-inclusiva/)
- **DeafApp (Duoc UC)**: plataforma comunitaria para recolectar, validar y reconocer señas LSCh con LSTM y visión computacional, hecha con la comunidad sorda; tiene repositorio público — [GitHub DeafAPP-LSCH](https://github.com/Biizcochito/DeafAPP-LSCH)
- **DialogApp (UTFSM, equipo SevenPulse)**: app de traducción en tiempo real señas↔texto, presentada en la 32ª Feria de Software (oct-2024) — [USM Noticias](https://usm.cl/noticias/nueva-aplicacion-facilita-la-comunicacion-para-la-comunidad-sorda/)
- Investigación de la U. de Valparaíso (Ingeniare): reconocimiento aislado de LSCh con Transformers, **precisión 0,75 en LSCh frente a 0,94 en el corpus argentino LSA64** — [Ingeniare (UTA)](https://ingeniare.uta.cl/index.php/inge/article/view/1459)

**WCAG 2.2 (criterios nuevos)**
- 2.4.11 Focus Not Obscured (Minimum), AA: el elemento con foco debe verse al menos en parte. 2.4.12 (Enhanced, AAA). 2.4.13 Focus Appearance, AAA. 2.5.7 Dragging Movements, AA: toda acción de arrastre necesita una alternativa con un solo puntero. **2.5.8 Target Size (Minimum), AA: objetivos de al menos 24×24 px CSS** o con espacio suficiente. 3.2.6 Consistent Help, A. 3.3.7 Redundant Entry, A: no pedir de nuevo datos ya entregados. 3.3.8 Accessible Authentication (Minimum), AA: el login no puede exigir pruebas cognitivas sin alternativa. 3.3.9 (Enhanced, AAA). Se eliminó 4.1.1 Parsing — [W3C: What's new in WCAG 2.2](https://www.w3.org/WAI/standards-guidelines/wcag/new-in-22/)

### Inferences
- **Voz en un artifact:** `speechSynthesis` (TTS) corre en el navegador y no necesita fetch, así que es compatible con la CSP. `SpeechRecognition` en Chrome usa los servidores de Google (lo gestiona el navegador, no la página). Falta confirmar si el iframe sandbox de claude.ai concede el micrófono. Hay que probarlo con `lang = "es-CL"` y, si falla, con `es-419` o `es-ES`. Plan B: un botón "dictar" que use el dictado del sistema operativo (Win+H en Windows) sobre un campo de texto.
- Para una voz "wow" sin depender de la red, conviene generar con ElevenLabs (free) 3-5 frases clave del guion de demo, descargarlas y embeberlas como data URI en el artifact (cuidando el tope de 16 MiB). Para un prototipo de hackathon no comercial alcanza con el free, pero si el proyecto sigue hay que pasar a Starter.
- **LSCh:** prometer "traductor LSCh en tiempo real" es arriesgado y éticamente delicado: la precisión académica es baja y existen proyectos chilenos previos. Una propuesta más honesta y defendible es una "capa de accesibilidad" (subtítulos, lectura fácil, conexión con intérpretes LSCh, videos de señas grabados por personas sordas) y mencionar DeafApp/DialogApp como ecosistema y posibles socios, con co-diseño con la comunidad sorda.
- **Lectura fácil:** Claude vía `sample` puede reescribir ofertas o contratos en "lectura fácil" con un prompt fijo (frases cortas, una idea por línea, sin jerga), y la UI puede mostrar el antes y el después. Es una función barata, muy demostrable y alineada con el tema de inclusión.
- **Checklist WCAG rápida para la demo** (derivada de W3C + buenas prácticas): contraste suficiente; foco visible y no tapado (2.4.11); botones de ≥24×24 px (2.5.8, ideal 44 px en móvil); sin drag obligatorio (2.5.7); textos alternativos en imágenes; navegación completa con teclado; etiquetas en los campos; no pedir datos dos veces (3.3.7); login sin captchas cognitivos (3.3.8); idioma `lang="es-CL"`. Vale la pena mostrar al jurado 10 segundos de navegación con teclado o lector de pantalla (Narrador de Windows, Ctrl+Win+Enter).

### Gaps
- No encontré una lista oficial de idiomas de Chrome para el reconocimiento on-device ni confirmación de soporte específico de `es-CL`.
- No investigué el STT/TTS de OpenAI (Whisper/TTS) ni sus precios 2026; igual no se pueden llamar desde un artifact por la CSP.
- No encontré una herramienta de IA pública y lista para usar que genere video o avatar en LSCh.
- No hay norma chilena de lectura fácil citada (por ejemplo, una adaptación local de la UNE 153101 EX); queda pendiente.

## 5. Ayudas de diseño y presentación (Figma, Canva, Gamma, Pitch.com, slides HTML hechas por Claude, mockups, imágenes de personas)

### Takeaway
Con el entorno actual, lo más rápido es hacer la presentación con **Claude Slides** (`/slides` en Claude Code o la plantilla en claude.ai), que exporta a PowerPoint, PDF o Google Slides, y **Claude Design** (`/design`) para mockups. El equipo además tiene **Canva conectado** como conector en esta sesión. Gamma es una buena alternativa gratis (400 créditos únicos), aunque la marca de agua en las exportaciones está en disputa.

### Cited Findings
- Claude Slides: presentaciones que se editan, se presentan en Claude y se exportan a PowerPoint, PDF o Google Slides. Disponible en todos los planes (Docs, Slides y Design) — [Claude Help Center: artifacts](https://support.claude.com/en/articles/17153992-what-are-artifacts-and-how-do-i-use-them)
- `/slides` crea un artifact Claude Slides desde un brief; `/design` dibuja artboards en un canvas (UI, flujos, landing, poster) y cada artboard se exporta a PNG/PDF; requieren Claude Code v2.1.265+ (beta) — [Claude Code Docs](https://code.claude.com/docs/en/artifacts)
- Motion (beta, explicadores animados exportables a MP4) solo está en Team/Enterprise, no en Pro — [Claude Help Center](https://support.claude.com/en/articles/17153992-what-are-artifacts-and-how-do-i-use-them)
- Gamma: el plan gratis da 400 créditos de IA **únicos** (no mensuales) y exporta a PDF, PPTX y PNG en todos los planes; la exportación PPTX vuelve estáticos los elementos interactivos. Hay conflicto sobre si las exportaciones gratis llevan marca "Made with Gamma". Plus cuesta ~US$8-10/mes **[VERIFICAR]** — [Gamma guide](https://gamma.app/explore/content/guides/best-ai-presentation-tools-export-beyond-live-link); [Dupple: Gamma review](https://dupple.com/reviews/gamma); [FrankX Gamma workflow 2026](https://www.frankx.ai/blog/ultimate-gamma-workflow-2026)
- Conectores claude.ai activos en la sesión de este usuario: Claude Docs, Gmail, **Canva**, Google Drive y Google Calendar (el conector de Canva expone herramientas como generate-design, create-design, export-design y generate-image) — [skill local artifact-capabilities, listado de conectores de la sesión](file:///C:/Users/jojon/AppData/Local/Temp/claude/bundled-skills/2.1.308/28b6634fe4f00ba2a43cf26b79336fb4/artifact-capabilities/)

### Inferences
- **Flujo sugerido:** (1) Claude Slides para el pitch de 3-5 minutos, exportado también a PDF y PPTX como respaldo offline; (2) Claude Design o el artifact mismo para capturas o mockups; (3) Canva (vía conector) para un afiche o una imagen de persona/visual si se necesita algo más "marketero".
- Las "personas" (perfiles de usuario) conviene ilustrarlas con avatares SVG o ilustraciones antes que con fotos realistas generadas por IA de personas con discapacidad: así se evitan estereotipos y críticas del jurado por "caras falsas". Hay que dejar explícito que los perfiles son ficticios.
- Un artifact HTML puede funcionar como presentación y demo a la vez (scroll por secciones con anclas `#problema`, `#demo`, `#impacto`), con lo que no hay que cambiar de ventana durante el pitch.

### Gaps
- No investigué los límites del plan gratis de Canva 2026 (Magic Design / Canva AI), Pitch.com ni Figma (Figma Make / First Draft).
- No verifiqué la calidad de la exportación PPTX de Claude Slides ni si su exportación a Google Slides está disponible en el plan Pro de este usuario.

## 6. Datos para demos realistas (datos sintéticos de CVs, ofertas y encuestas; datasets públicos chilenos: datos.gob.cl, INE, Bolsa Nacional de Empleo)

### Takeaway
La mejor combinación es **datos sintéticos generados por Claude** (CVs, ofertas y encuestas de clima con nombres y regiones chilenas, marcados como ficticios) anclados en **2-3 cifras oficiales reales** (INE ENE, ENDIDE 2022, Ley 21.015) que den credibilidad. La Bolsa Nacional de Empleo no tiene un dataset o API abierta confirmada; el INE publica bases ENE en CSV y Stata y tiene un portal .Stat.

### Cited Findings
- **INE – Encuesta Nacional de Empleo (ENE):** las bases de datos se publican en **Stata (.dta) y CSV**, y los cuadros en Excel. El dato más reciente que aparece es una tasa de desocupación nacional de **9,6% en el trimestre móvil junio-agosto 2026** (noticia del 30-09-2026). Recursos: Banco de Datos ENE (http://bancodatosene.ine.cl/), SIMEL (https://de.ine.gob.cl/) y datos abiertos .Stat (https://stat.ine.cl/?lang=es) — [INE: Ocupación y desocupación](https://www.ine.gob.cl/estadisticas/sociales/mercado-laboral/ocupacion-y-desocupacion)
- Existe un paquete R (`calidad`) con una versión reducida de la ENE (2020-efm: sexo, región, fuerza de trabajo, ocupación), útil como muestra pequeña — [CRAN calidad::ene](https://search.r-project.org/CRAN/refmans/calidad/html/ene.html)
- **SENCE – Observatorio Laboral / SABE:** SABE (Sistema de Análisis de Bolsas de Empleo, desarrollado por SENCE, ISCI-U. de Chile y OTIC SOFOFA) analiza 6 portales de empleo y clasifica avisos por ocupación con minería de texto. Hay un informe del 1er semestre de 2025 — [SENCE: Informe SABE 2025-I](https://cdn-site.sence.gob.cl/sites/default/files/informe_sabe_2025-i.pdf); el Termómetro Laboral usa la ENE y SABE — [SENCE: Termómetro Laboral mar-2023](https://cdn-site.sence.gob.cl/sites/default/files/noticias-files/termometro_laboral_nacional_-_marzo_2023_rev.pdf)
- **Bolsa Nacional de Empleo (bne.cl):** plataforma gratuita de intermediación con ofertas de empresas y de las OMIL — [Mintrab](https://www.mintrab.gob.cl/mas-de-50-mil-personas-encontraron-trabajo-en-2013-gracias-a-la-bolsa-nacional-de-empleo/); en las búsquedas no apareció una API ni un dataset descargable de BNE.
- **Inclusión laboral – Ley 21.015:** obliga a contratar o mantener al menos 1% de personas con discapacidad o pensionadas por invalidez en organismos públicos y empresas de 100 o más trabajadores — [Servicio Civil / Fundación Descúbreme: Guía de inclusión laboral](https://www.serviciocivil.cl/wp-content/uploads/2022/01/Guia-de-inclusion-laboral-de-personas-con-discapacidad-para-el-sector-publico-Fund-Descubreme.pdf)
- **ENDIDE 2022** (citada por UNAB): ~2,7 millones de adultos con discapacidad, 59,1% inactivos, y una tasa de empleo formal citada en ~6% — [IPP UNAB: Panel Laboral N°30 (nov-2025)](https://ipp.unab.cl/wp-content/uploads/2025/12/20251205-IPP-UNAB_Informe-Panel-Laboral-UNAB_Encuesta-N30_noviembre.pdf); Reporte Minero da ~5,8% de empleo formal **[CIFRAS DISCREPANTES ENTRE FUENTES]** — [Reporte Minero (2024)](https://www.reporteminero.cl/noticia/eventos/2024/10/expo-inclusion-2024-ofertas-laborales)

### Inferences
- **Recetas de datos sintéticos para pedirle a Claude** (antes del evento, guardadas como JSON o CSV en el proyecto):
  - 30-50 CVs ficticios en español chileno (nombres diversos, regiones, comunas, educación en CFT/IP/universidad, brechas laborales, discapacidad declarada o no, migrantes con títulos por convalidar, personas mayores de 50).
  - 20-40 ofertas tipo BNE/portal (cargo, comuna, renta en CLP, requisitos, ajustes razonables disponibles, modalidad).
  - Una encuesta de clima/inclusión de 200 respuestas tipo Likert para el dashboard de RR.HH.
  - Todo marcado "datos ficticios" en la UI.
- Hay que incluir 2-3 datos reales con su fuente en pantalla (por ejemplo "desocupación 9,6%, INE jun-ago 2026" y "cuota 1% Ley 21.015") y re-verificar el último boletín ENE (probablemente sale uno nuevo a fines de octubre de 2026) antes del pitch.
- Los CSV del INE se pueden descargar antes y resumir con Claude a tablas pequeñas que se embeben en el artifact. No hay que cargar microdatos completos (riesgo de superar los 16 MiB y tokens innecesarios).
- No hay que usar datos personales reales de CVs. En el pitch, mencionar el cumplimiento de la Ley 19.628 o la nueva ley de datos personales suma puntos (inferencia: no verifiqué el estado de esa ley).

### Gaps
- No pude confirmar URLs directas de descarga de los CSV de la ENE ni datasets de empleo específicos en datos.gob.cl.
- No encontré API ni datos abiertos de la Bolsa Nacional de Empleo.
- No encontré el portal oficial de microdatos de ENDIDE 2022 (Ministerio de Desarrollo Social / SENADIS); las cifras vienen de un informe secundario.
- No investigué herramientas específicas de datos sintéticos (Mockaroo, Faker); Claude cubre la necesidad.

## 7. Gestión de riesgo en la demo en vivo (fallbacks offline, video de respaldo con Loom/OBS, Wi-Fi caído, límites de API, hotspot)

### Takeaway
Hay que asumir que el Wi-Fi va a fallar y que la IA puede tardar 5-60 s o devolver un rate limit. Toda demo debe tener **tres capas**: en vivo (artifact con Claude), "modo demo" (respuestas precalculadas en el mismo HTML) y **video grabado** (Loom gratis permite 5 min por grabación). Además, hotspot del teléfono y PDF de las slides en un pendrive.

### Cited Findings
- Grabar la demo mientras funciona y tener capturas y slides de respaldo; preguntarse qué hacer si se cae el Wi-Fi — [AngelHack: 10 tips](https://angelhack.com/blog/10-tips-to-help-you-rock-your-next-hackathon-demo/); [Hackathon Survival Guide](https://www.slideshare.net/slideshow/hackathon-survival-guide-24044514/24044514)
- El Wi-Fi del lugar es una dependencia más: conviene evaluar si el proyecto puede no depender de internet y llevar los screencasts en un USB junto a las slides — [Lorna Jane: Live Demo Risks and Rewards](https://lornajane.net/?p=3720)
- Los jurados entienden que la tecnología falla y valoran a quien lo maneja con calma; no decir "normalmente funciona" ni mostrar funciones a medio hacer. Pitch típico de ~3 min, con la demo como parte central — [Reskilll: Hackathon demo tips 2026](https://blogs.reskilll.com/hackathon-demo-presentation-tips-pitch-3-minutes-win-2026/); probar en el hardware del lugar y en móviles — [Hackathon quick reference](https://www.mintlify.com/azlan18/Hackathon-Resources/quick-reference); consejos de demos — [PostHog: 24 tips for S-tier demos](https://posthog.com/newsletter/how-to-demo.md)
- **Loom gratis (Starter):** 25 videos por persona, 5 minutos por grabación, hasta 720p — [Trainn: Loom pricing (ago-2026)](https://trainn.co/blog/loom-pricing/); [Tella: Loom pricing explained](https://www.tella.com/blog/loom-pricing-explained.md)
- Latencia de Claude en artifacts: con "quick" 1-2 s, con "default/complex" 5-60 s para el primer texto; caché de 5 min para inputs idénticos; una ráfaga de llamadas devuelve `rate_limited` — [sample.d.ts local](file:///C:/Users/jojon/AppData/Local/Temp/claude/bundled-skills/2.1.308/28b6634fe4f00ba2a43cf26b79336fb4/artifact-capabilities/0.2.91/sample.d.ts)
- Si una red corporativa o del evento bloquea `*.claudeusercontent.com`, `claude.ai` o los CDN de scripts, el artifact no carga o pierde sus librerías (sin fallback) — [Claude Code Docs: allowlist](https://code.claude.com/docs/en/artifacts)
- El RPD de la Gemini API se reinicia a medianoche hora del Pacífico y los límites son por proyecto — [Google AI billing](https://ai.google.dev/gemini-api/docs/billing?authuser=9)

### Inferences
- **Usar `modelTier: "quick"` en la demo en vivo** para respuestas de 1-2 s, y aprovechar la caché de 5 min: si se ensaya el input exacto justo antes de presentar, la respuesta en el escenario sale instantánea desde la caché.
- **"Modo demo" en el mismo HTML:** un interruptor (o detección de `sample === null` o error) que muestre respuestas pregrabadas y realistas para los 2-3 casos del guion. Así el link público también "funciona" para jurados sin cuenta de Claude.
- **Copia local:** guardar el HTML final en el escritorio y en el pendrive. Se abre con doble clic y la UI, los datos embebidos y el modo demo funcionan; la IA (`window.claude`) no, porque solo existe dentro del visor de claude.ai. Las librerías desde CDN necesitan internet, así que conviene pedirle a Claude que las incruste inline en la copia offline, si caben.
- **Video:** grabar el flujo completo en ≤5 min (Loom free) o con OBS Studio / la grabación de pantalla de la Herramienta Recortes de Windows 11 (sin verificar en esta investigación). Grabar dos veces: al terminar la mañana (hito "MVP") y antes del pitch.
- **Red:** cada integrante con hotspot 4G/5G probado (Entel/Movistar/WOM con datos suficientes); no depender del Wi-Fi de la FEN. Ojo: algunas redes universitarias bloquean dominios de terceros, así que hay que probar claude.ai desde el lugar apenas se llegue.
- **Límites de uso de Claude:** construir con una cuenta y **presentar con la otra** (la que tiene más uso restante), o reservar a propósito el uso de una cuenta para el pitch.

### Gaps
- No encontré información sobre la conectividad o el Wi-Fi específico de la FEN (Diagonal Paraguay).
- No verifiqué la información de OBS Studio ni de la grabadora de Windows con fuentes en esta ronda.
- No hay datos públicos sobre la tasa de errores o rate limits del `sample` de artifacts bajo carga.

## 8. Checklist de preparación previa al evento y stacks recomendados por defecto: (a) web app con chat/análisis IA, (b) bot estilo WhatsApp, (c) dashboard de RR.HH., (d) app con look móvil

### Takeaway
El stack por defecto para los cuatro casos es el mismo núcleo, **Claude Code (escritorio) → Artifact HTML con `sample`/`db` + modo demo + Claude Slides**, con variaciones de UI. Los 9 días previos (26-oct a 3-nov) se deben usar para crear cuentas, verificar versiones, probar micrófono, `sample` y el link público, y dejar listos una "plantilla base" HTML, los datasets sintéticos y un guion de demo ensayado.

### Cited Findings
- Requisitos para publicar artifacts: plan Pro/Max/Team/Enterprise, sesión con `/login` (no API key), app de escritorio ≥ 1.13576.0, proveedor Anthropic API; las redes con proxy o VPN deben dejar pasar `api.anthropic.com` — [Claude Code Docs](https://code.claude.com/docs/en/artifacts)
- Se necesita activar "Cloud code execution and file creation" en Settings para los artifacts — [Claude Help Center](https://support.claude.com/en/articles/17153992-what-are-artifacts-and-how-do-i-use-them)
- Las Dashboards (beta) como tipo de artifact están disponibles en Pro, Max, Team y Enterprise — [Claude Help Center](https://support.claude.com/en/articles/17153992-what-are-artifacts-and-how-do-i-use-them)
- El sistema de diseño (colores, tipografía, espaciado) se puede fijar en CLAUDE.md para que todos los artifacts salgan consistentes — [Claude Code Docs](https://code.claude.com/docs/en/artifacts)
- Los conectores llamados desde el artifact corren con la cuenta del que mira y piden permiso; quien no está conectado ve la página sin las secciones en vivo — [Claude Code Docs](https://code.claude.com/docs/en/artifacts)
- Capacidades del runtime disponibles en esta cuenta: `sample` (Claude), `db` (filas compartidas que Claude puede sembrar y leer), `assets` (subida de archivos: imágenes, PDF, CSV, hasta 20 MiB), `downloads` (descarga confirmada por el usuario), `room` (presencia y eventos en tiempo real entre quienes tienen la página abierta), `user`, `mcp` — [skill local artifact-capabilities](file:///C:/Users/jojon/AppData/Local/Temp/claude/bundled-skills/2.1.308/28b6634fe4f00ba2a43cf26b79336fb4/artifact-capabilities/)
- No encontré información pública del evento "Talent Tech Hack 2026" de la FEN; en las búsquedas solo aparecieron otros eventos (por ejemplo Ingenia TP UACh, 26-28 nov 2026) — [Ecosistema Startup](https://ecosistemastartup.com/?p=81726)

### Inferences
**Checklist previo (26-oct → 3-nov)**
1. **Cuentas:** Claude Pro para **ambos** integrantes; Google (AI Studio, plan B); Loom; Tally; Canva (ya conectado); Gamma (opcional); Twilio y Make solo si se decide mostrar WhatsApp real. Lovable con descuento estudiantil solo si se elige como plan B.
2. **Versiones:** actualizar la app de escritorio de Claude (≥1.13576.0) y Claude Code (≥ v2.1.265 para `/slides` y `/design`); hacer `/login` con la cuenta claude.ai, no con API key; activar "Cloud code execution and file creation".
3. **Pruebas técnicas (en los dos laptops y en los teléfonos):** publicar un artifact de prueba, compartirlo con link público y abrirlo en un teléfono sin sesión; probar `sample` con la cuenta propia y con la del compañero; probar micrófono y Web Speech `es-CL` dentro del artifact; probar `speechSynthesis` con voces en español; probar subir un PDF/imagen de CV y extraer texto (pdf.js desde cdnjs) o enviarlo como imagen a `sample`; probar exportar Claude Slides a PDF y PPTX.
4. **Plantilla base:** pedirle a Claude que deje lista una "plantilla" HTML con el sistema de diseño (colores, tipografía, `lang="es-CL"`, foco visible, objetivos de 44 px), un componente de chat con streaming y botón "Detener", un componente de carga de archivo, un interruptor "Modo demo", un layout con marco de teléfono y una sección de dashboard con Chart.js. El día del evento solo se adapta al problema elegido.
5. **Datos:** generar y guardar los CVs, ofertas y encuestas sintéticos, además de 2-3 cifras oficiales con fuente (INE ENE, Ley 21.015, ENDIDE).
6. **Prompts:** dejar escritos los prompts de sistema de cada función de IA (matching CV↔oferta con justificación, lectura fácil, detección de sesgos en ofertas, entrevista simulada) y probarlos en `quick` y `default`.
7. **Logística:** hotspot probado, cargadores y alargador, pendrive con HTML offline y slides en PDF, video de respaldo (se graba el día 1), guion de demo de 2 minutos ensayado con cronómetro, y división de roles (uno "piloto" de Claude y otro de pitch, datos y diseño).
8. **Ensayo general:** hacer una mini-hackathon de 3 horas antes del 4-nov con un problema ficticio, para medir cuánto uso de Claude se consume y dónde se traba el flujo.

**Stacks por defecto**
- **(a) Web app con chat/análisis de IA** (por ejemplo, "copiloto de empleabilidad inclusiva"): Claude Code → Artifact HTML + Tailwind (CDN) + `sample` (Claude: análisis de CV, matching, lectura fácil) + `assets` o pdf.js para subir CVs + `db` para guardar postulaciones + modo demo. Presentación en Claude Slides. Plan B: Lovable (Supabase + auth) o Google AI Studio Build (Gemini).
- **(b) Bot estilo WhatsApp:** artifact con marco de teléfono y chat genérico estilo mensajería (sin marca WhatsApp) + `sample` (`modelTier` "quick") + TTS del navegador para leer respuestas en voz alta + botones de respuesta rápida (accesibles). Opcional: video del bot real con Twilio Sandbox + Make + LLM, preparado antes y con el teléfono unido al sandbox ≤3 días antes del pitch. Alternativa no-code: Botpress o Voiceflow (planes gratis limitados).
- **(c) Dashboard/analytics para RR.HH.** (por ejemplo, brechas de inclusión, cumplimiento de la Ley 21.015, clima): artifact con Chart.js + encuesta sintética embebida + KPIs + botón "Explicar con IA" (`sample` resume hallazgos en lenguaje simple) + filtros accesibles por teclado + `downloads` para exportar CSV. Alternativa: tipo Dashboard (beta) de Claude si los datos vienen de un conector. Se pueden mostrar 1-2 cifras reales del INE como contexto.
- **(d) App con look móvil:** el mismo artifact con layout mobile-first dentro de un marco de teléfono en desktop, que al abrirse en un celular real por link público se ve a pantalla completa (lo estático funciona sin login; la IA requiere sesión). Para mockups estáticos adicionales, `/design` (Claude Design). Alternativas: FlutterFlow (si de verdad hace falta una app nativa) o Glide (si los datos viven en una planilla).
- **Reparto del tiempo sugerido (7 h):** 0:00-0:45 problema, usuario y guion de demo; 0:45-4:00 construcción iterativa con Claude, publicando cada 30-45 min; 4:00-5:00 modo demo, accesibilidad y datos; 5:00-5:45 grabar video y hacer slides; 5:45-7:00 ensayos del pitch y buffer para imprevistos.

### Gaps
- No hay información pública del evento (bases, criterios de evaluación, si se permite trabajo previo o plantillas, duración exacta del pitch, si habrá Wi-Fi o enchufes). Es crítico revisar las bases oficiales de la FEN: si **prohíben código o plantillas preparadas antes**, la "plantilla base" del punto 4 podría quedar limitada a pruebas técnicas y prompts.
- No verifiqué si las plantillas Claude Slides o Design están activas en la cuenta concreta del usuario (son beta).
- No probé en vivo ninguno de los flujos (micrófono en artifact, `sample` con cuenta ajena, link público en móvil); estas notas las listan como pruebas pendientes.
