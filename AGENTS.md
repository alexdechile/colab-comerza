# Reglas de Agentes — Colab-Comerza

Este archivo define las reglas de comportamiento y desarrollo específicas para los agentes de IA que trabajen en este proyecto.

## Reglas del Proyecto
1. **Documentación Maestra:** Mantener el archivo `alex.md` al día con la sección "Último Realizado" en la parte superior.
2. **Confirmación del Usuario:** No hacer commits a Git sin recibir confirmación explícita (ej. "funciona", "quedó bien").
3. **Tecnología Central:** El pipeline usa **PyMotion** (`pymotion-studio` v3.7.0) — NO MoviePy. No sugerir ni revertir a MoviePy.
4. **Formato:** Video 540×960 (9:16 vertical), 24fps, H.264/AAC, máximo 14 segundos.
5. **Textos:** Usar `TextClip` con parámetro `size` (no `font_size`). Fuente Montserrat descargada desde Google Fonts con ruta absoluta.
6. **Ken Burns:** Generar frames con PIL + remuestreo LANCZOS, ensamblar con ffmpeg, luego cargar como `pm.VideoClip`.
7. **Audio:** gTTS (tld="com.mx") para locución. Música sintética C-Am-F-G con batería. Mezcla con `pm.AudioMixer`.
8. **Notebook:** El archivo principal es `colab-comerza.ipynb`. Debe solicitar GPU en Colab y verificar Python 3.12+.
9. **Diseño:** Mantener la estética visual declarada en `mi-diseno.json` (2 textos + 1 imagen con efecto Ken Burns).
