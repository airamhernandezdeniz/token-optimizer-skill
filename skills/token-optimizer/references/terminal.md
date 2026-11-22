# Terminal, archivos y subagentes

Ideas adaptadas de token-saver y token-shield (los datos sobre Claude Code son los que cita token-shield, verificados con la documentación oficial en agosto de 2026; si algo cambia, manda la documentación actual).

Cada llamada reenvía todo el contexto acumulado. Palancas por orden de impacto: caché, contexto pequeño, modelo adecuado y salida corta.

## Medir antes de optimizar
- Mide, no supongas. Con token-shield instalada, `/token-audit` da cifras reales; lo que no se pueda medir se dice como "sin datos".
- Compara ventanas del mismo tamaño y cambia una sola cosa cada vez.

## Sesiones y contexto
- Una tarea por sesión: el contexto ajeno se paga en cada llamada.
- Deja un punto de control en disco al cerrar un hito (hecho con su prueba, en curso, pendiente, dudas) antes de cambiar de sesión o compactar.
- Elige el límite según la intención: `/rewind` para abandonar un camino, `/recap` para orientarte, `/compact` en una pausa natural (no a mitad de tarea) y sesión nueva si la tarea no tiene relación.
- No cambies de modelo (`/model`) ni de esfuerzo (`/effort`) a mitad de sesión: cada uno tiene su propia caché y se recompone todo el contexto. Para una tarea más barata, usa un subagente.
- No conectes ni desconectes servidores MCP a mitad de sesión. Editar CLAUDE.md a mitad de sesión no se aplica hasta recargar.

## Herramientas y salida
- Agrupa las llamadas independientes en un solo mensaje.
- Lee con desplazamiento y límite; usa grep con límite de líneas y tail en builds.
- Logs ruidosos: guárdalos en un archivo y trae solo el código de salida, las líneas de error y un resumen. Si necesitas el texto exacto, repite ese comando sin comprimir.
- Esperas largas: ejecución en segundo plano con aviso al terminar. Nada de bucles que despiertan cada pocos segundos.
- Un script determinista antes que un subagente para un trabajo determinista.
- Texto antes que capturas de pantalla cuando ambos responden lo mismo.

## Subagentes
- Úsalos para sacar exploración voluminosa del contexto principal o para paralelismo real, no para lo que haría un script.
- Pide un informe de pocos cientos de tokens: hallazgos, pruebas y rutas, nunca la transcripción.
- Declara el nivel de modelo en cada encargo: fuerte para orquestar, juzgar y sintetizar; medio para implementar con una especificación precisa; ligero para trabajo mecánico. El ligero nunca verifica su propio trabajo.
- Fija un tope de tokens antes de una ejecución desatendida y no lances más subagentes al pasar el 80 %.

## Memoria y contexto fijo
- Guarda decisiones y estado en notas; el archivo siempre cargado lleva solo reglas duras y punteros a esas notas.
- Registro de desperdicio: una línea por incidente con fecha, coste y regla. Una regla pasa a fija solo si el fallo se repite y cabe en una línea.
- Mantén conciso CLAUDE.md, desactiva plugins y servidores sin uso, haz que los hooks de inicio sean silenciosos y no mantengas dos frameworks de skills solapados.
