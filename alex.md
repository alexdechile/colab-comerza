# alex.md — Colab-Comerza

## Último Realizado

- [x] Fuentes Montserrat descargadas desde Google Fonts CSS2 API en runtime
  - Los TTFs ya NO viven en el repo (eliminados, `.gitignore` los excluye).
  - Se descargan de `fonts.googleapis.com` → CDN estable de Google (no depende de
    URLs de GitHub que cambian). Validación con magic bytes antes de usar.
- [x] v3.0: Migración completa a PyMotion (pymotion-studio v3.7.0)
  - Textos con FreeType+HarfBuzz (PyMotion TextClip) — textos nítidos sin boost
  - Ken Burns con PIL + ffmpeg (zoom/pan suave ease-in-out)
  - AudioMixer de PyMotion para mezcla estéreo (TTS + música)
  - VideoClip para background con Ken Burns
  - Render con preset h264_fast
  - Python 3.12+ check con fallback
- [x] v2.1: FONT_BOOST=2.8, música C-Am-F-G con bombo+hihat, clamping render
- [x] v2.0: 540x960, font boost 1.8, textwrap, 2 textos
- [x] v1.x: Múltiples versiones MoviePy con correcciones de imports, fuentes, música

## ¿Qué hace esta App?

Convierte un JSON de diseño gráfico (canva-lite) en un video animado 9:16 con:
- Efecto Ken Burns (zoom/pan suave sobre imagen de fondo)
- Textos animados con tipografía profesional (Montserrat, FreeType+HarfBuzz)
- Locución TTS en español neutro (gTTS)
- Música de fondo sintética (progresión de acordes C-Am-F-G)
- Máximo 14 segundos de duración
- Todo desde Google Colab con GPU

## Stack Técnico

- **PyMotion (pymotion-studio)** v3.7.0 — Composición, VideoClip, TextClip, AudioClip, AudioMixer
- **PIL (Pillow)** — Generación de frames Ken Burns (zoom/pan con remuestreo LANCZOS)
- **gTTS** — Locución español neutro (tld="com.mx")
- **FFmpeg** — Ensamblado de frames, combinación video+audio final
- **Montserrat** — Tipografía descargada en runtime (Google Fonts CSS2 API | fonts.gstatic.com)
- **Python 3.12+** requerido por PyMotion
- **Formato**: 540×960 (9:16 vertical), 24fps, H.264/AAC
