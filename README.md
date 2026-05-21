# Anna Raventós — Design System

Sistema de diseño completo para presentaciones, landings y comunicación visual de Anna Raventós. Pensado para conectarse a [Claude Design](https://claude.ai/design) (vía GitHub) y para uso directo del equipo.

## Estructura

```
anna-raventos/
├── tokens.css              ← Fuente única de verdad: paleta, tipografía, componentes
├── preview.html            ← Catálogo visual de todas las plantillas y diagrams
├── README.md               ← Este archivo
├── assets/
│   ├── fonts/              ← Urbanist (variable, 100-900) + GiftenSans (display italic)
│   ├── logos/              ← Variantes del logo (lockup, isotipo, color, b/n, blanco)
│   └── bg/                 ← Fondos originales (lila claro / lila brand, con flor de vida)
├── lib/
│   └── iw-interact.js      ← Sistema de interactividad (hover, dimming, stagger)
├── slides/                 ← 10 plantillas base
└── diagrams/               ← 19 smart diagrams
```

## Tokens de marca

| Token | Valor | Uso |
|---|---|---|
| `--iw-primary` | `#7E69E3` | Lila brand — acentos, highlights, CTA, líneas |
| `--iw-dark` | `#242B37` | Texto principal, fondos hero |
| `--iw-light` | `#D4C9F4` | Cards, pills, badges (al 45-50% transparencia) |
| `--iw-mid` | `#B5A2EE` | Tono lila medio (con texto blanco si fondo) |
| `--iw-ink` | `#242B37` | Texto principal |
| `--iw-ink-soft` | `#4B5563` | Texto secundario |
| Fuente principal | Urbanist | Variable 100 → 900 |
| Fuente display | GiftenSans italic | Highlights (`iw-hl`) a 0.85em |
| Ratio slides | 16:9 (1920×1080) | Lienzo base |

Cualquier modificación de marca se hace en **`tokens.css`** y se propaga a todas las plantillas.

## Detalles específicos de la identidad

- **Pesos suavizados:** 900 → 600, 800 → 500 (Anna no usa heavy weights — todo más delicado)
- **Strokes finos:** SVG con `stroke-width: 1.5` en lugar de 2
- **Estrella sparkle** como sustituto del dot en bullets/diagrams. Path: `M 12 2 L 16 8 L 22 12 L 16 16 L 12 22 L 8 16 L 2 12 L 8 8 Z`
- **GiftenSans italic** en `.iw-hl` a 0.85em (compensa métricas altas vs Urbanist)
- **Cover sin logo** (decisión de Humberto/Anna)

## Cómo previsualizar

### Servidor local (recomendado)

```bash
cd anna-raventos
python -m http.server 8765
```

Luego abre [http://localhost:8765/preview.html](http://localhost:8765/preview.html).

### Opción directa

Doble click sobre `preview.html`. Si el navegador bloquea fuentes locales con `file://`, usa el servidor.

## Cómo añadir contenido nuevo

### Reemplazar el placeholder vacío por una imagen

Cualquier `<div class="iw-media">…</div>` acepta una imagen:

```html
<div class="iw-media">
  <img src="../assets/photos/anna-portada.jpg" alt="Anna Raventós">
</div>
```

### Crear una nueva diapositiva

1. Copia la plantilla más cercana (ej: `slides/02-content-bullets.html`).
2. Renómbrala.
3. Cambia el contenido. Reutiliza componentes globales (`iw-h1`, `iw-checklist`, `iw-pill`, etc.).
4. Si necesitas un componente nuevo, añádelo a `tokens.css` con prefijo `iw-`.

## Conexión con Claude Design

Al crear un design system para Anna Raventós:

1. **Link code on GitHub:** apunta a este repo.
2. **Add fonts, logos and assets:** sube manualmente los logos de `assets/logos/`.
3. **Any other notes:** la voz y tono del cliente se gestiona desde las skills de texto de la agencia, no en este repo.

## Reglas no negociables del sistema

- **Logo solo en portada (slide 01).** (Excepción: Anna pidió cover SIN logo).
- **Fondo de marca en TODOS los slides:** `assets/bg/fondos-10.jpg`.
- **Fondos lavanda con 40–50% transparencia.** Excepción: círculos contenedores de iconos sólidos.
- **Nunca flechas hand-drawn SVG.**
- **Iconos estilo Lucide** (viewBox 24, stroke 1.5 para Anna, line caps redondos).
- **Minimalismo extremo:** whitespace > densidad.
- **Jerarquía visual obligatoria.**
- **Pesos ≤ 600.** Nunca heavy 800-900 (rompe el feel delicado).
- **Highlights con GiftenSans italic**, no con bold mono color como las otras marcas.
- **Brand puro `#7E69E3` y mid `#B5A2EE` → contenido siempre blanco.**
- **NUNCA usar eyebrow/kicker/texto sobre los headlines**. Los títulos abren la slide sin texto encima — la diapositiva empieza directamente por el h1. Composición limpia.

## Imágenes con Unsplash

Cuando una presentación necesite fotografía (hero, testimonios, slides emocionales) y no tengamos foto propia, usa Unsplash. El sistema soporta dos modos:

**Modo 1 — Sin API key (default, out-of-the-box):**

```html
<img src="https://source.unsplash.com/1600x900/?KEYWORD1,KEYWORD2"
     alt="Descripción"
     style="width:100%; height:100%; object-fit:cover;">
```

Devuelve una foto aleatoria que matchea las keywords. Sin registro, sin key.

**Modo 2 — Con API key (cuando el cliente tenga su `UNSPLASH_ACCESS_KEY`):**

```
GET https://api.unsplash.com/photos/random?query=KEYWORD&orientation=landscape
Headers: Authorization: Client-ID {access_key}
```

**Keywords sugeridos para Anna Raventós** (femenino, sereno, business para coaches/terapeutas):

- Hero: `woman,entrepreneur,calm`, `professional,woman,smile`
- Testimonio: `portrait,woman,natural,light`
- Proceso/calma: `meditation,morning`, `wellness,space`, `plant,leaf,soft`
- Crecimiento: `growth,plant,light`, `path,nature`

**No usar:** fotos cliché de manifestación esotérica, gente con cristales o tarot. La estética es delicada y femenina, pero el contenido es BUSINESS para coaches/terapeutas. Preferir composiciones naturales con luz cálida.

## Mantenimiento

- **Source of truth:** este repo. Cualquier cambio se commitea aquí.
- **Distribución:** `git pull` en local. Claude Design re-lee al refrescar.
- **Cambios visuales:** en `tokens.css`. NO en cada slide individual.
