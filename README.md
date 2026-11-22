# Token Optimizer

**The best skill to stop wasting tokens. / La mejor skill para dejar de malgastar tokens.**

Made by **Airam Hernández Déniz** (Spain, Canary Islands). Free to use, improve and share. Credit is appreciated. See [LICENSE.md](LICENSE.md).

---

## English

Claude often spends tokens you do not need: long intros, repeated explanations, extra searches and huge chats. Token Optimizer cuts that waste without losing accuracy or quality.

**What it does**
- Short, direct answers, with no filler.
- 3 brevity levels: say "level 1", "level 2" or "level 3".
- Fewer tools and searches, only when really needed.
- Long chats under control: it tells you when to start a new chat and writes a handoff summary.
- Accuracy first: it never cuts figures, code or warnings that matter.
- Works in chat and in Claude Code / Cowork.

**How to install (Claude.ai)**
1. Download the latest ZIP from the [`releases/`](releases/) folder.
2. In Claude, go to **Customize > Skills**, click **+**, then **+ Create skill > Upload a skill**, and select the ZIP.
3. Make sure **Code execution and file creation** is enabled in Settings > Capabilities.
4. Done. Ask for "be concise", "save tokens" or "Token Optimizer". It also applies by default.

**Claude Code:** copy the `skills/token-optimizer` folder into your skills directory.

**Improve it:** anyone can modify and share it freely. Ideas or improvements you want me to implement: airamhernandezdenis@gmail.com

---

## Español

Claude a veces gasta tokens que no necesitas: introducciones largas, explicaciones repetidas, búsquedas de más y chats enormes. Token Optimizer recorta ese gasto sin perder precisión ni calidad.

**Qué hace**
- Respuestas cortas y directas, sin relleno.
- 3 niveles de brevedad: di "nivel 1", "nivel 2" o "nivel 3".
- Menos herramientas y búsquedas, solo cuando hacen falta.
- Chats largos bajo control: te avisa cuando conviene abrir un chat nuevo y escribe un resumen de traspaso.
- Primero la precisión: nunca recorta cifras, código ni avisos importantes.
- Funciona en el chat y en Claude Code / Cowork.

**Cómo instalarla (Claude.ai)**
1. Descarga el último ZIP de la carpeta [`releases/`](releases/).
2. En Claude, ve a **Personalizar > Skills**, pulsa **+**, luego **+ Crear skill > Subir una skill**, y elige el ZIP.
3. Comprueba que **Ejecución de código y creación de archivos** está activada en Ajustes > Capacidades.
4. Listo. Pide "sé conciso", "ahorra tokens" o "Token Optimizer". También se aplica por defecto.

**Claude Code:** copia la carpeta `skills/token-optimizer` en tu directorio de skills.

**Mejórala:** cualquiera puede modificarla y compartirla libremente. Ideas o mejoras que quieras que implemente: airamhernandezdenis@gmail.com

---

## Repository layout / Estructura

```
README.md          this page / esta página
CHANGELOG.md       every change by version / cambios por versión
LICENSE.md         license / licencia
skills/            the skill source / el código de la skill
releases/          ready-to-upload ZIPs / ZIPs listos para subir
```
