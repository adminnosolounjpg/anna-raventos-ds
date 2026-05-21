# Anna Raventós — Brand Guidelines

Guía oficial de uso de marca. Aplica a presentaciones, landings, emails, ads, banners, PDFs y cualquier comunicación visual.

> Crea un negocio simple que te da ingresos predecibles, paz y tiempo para disfrutar. La estética de Anna es **delicada, femenina, aireada y serena** — coherente con su propuesta de marketing alineado y sin agotamiento.

---

## 1. Logo

### Variantes disponibles

| Archivo | Uso |
|---|---|
| `assets/logos/logo-anna-28.png` | **Lockup principal** — navy + sparkle lila. Para navbar, footer, cover sobre fondo claro |
| `assets/logos/logo-anna-29.png` | Lockup lila brand — versión color, sobre fondos blancos cuando el navy es demasiado denso |
| `assets/logos/logo-anna-26.png` | Blanco — sobre fondos dark o lila brand sólido |
| `assets/logos/logo-anna-30.png` | Negro completo — solo b/n, imprenta económica |
| `assets/logos/logo-anna-22.png` | Isotipo "AR" navy + sparkle — favicon, avatar reducido |
| `assets/logos/logo-anna-23.png` | Isotipo "AR" lila brand — variante color isotipo |

### Espacio mínimo (clear space)

Mantén un margen libre alrededor del logo equivalente a la altura del sparkle. El feel aireado de Anna requiere whitespace generoso — no apurar márgenes.

### Tamaño mínimo

- **Digital:** 36px de altura (lockup) / 24px (isotipo)
- **Impreso:** 15mm de altura mínimo

### Prohibiciones (NO hacer)

- ❌ Estirar, comprimir o rotar
- ❌ Cambiar el color del sparkle (siempre lila brand `#7E69E3`)
- ❌ Sustituir el sparkle por otra figura
- ❌ Aplicar sombras o gradientes pesados (Anna es etérea, no corporativa)
- ❌ Colocar el logo sobre fondos con patrón muy denso

### Uso por contexto

- **Slides:** Anna pidió cover SIN logo. Los slides interiores tampoco lo llevan.
- **Landings:** logo en navbar (`logo-anna-28.png`) y footer (`logo-anna-28.png` también, sobre blanco).
- **CTA final sobre fondo lila brand:** usar `logo-anna-26.png` (blanco).
- **Emails:** isotipo `logo-anna-22.png` 24-32px en header.

---

## 2. Paleta de colores

### Paleta primaria (lila místico)

| Token | Hex | Uso |
|---|---|---|
| `--iw-primary` | `#7E69E3` | Lila brand principal — highlights, CTA, líneas, fondos de impacto |
| `--iw-primary-hover` | `#6A55D0` | Hover de CTA |
| `--iw-dark` | `#242B37` | Navy con tinte morado — texto principal |
| `--iw-light` | `#D4C9F4` | Lila claro — cards, badges (al 45-50% transparencia) |
| `--iw-light-soft` | `#F3F0FC` | Lila muy suave — fondos sutiles |
| `--iw-mid` | `#B5A2EE` | Lila medio — gradientes, decoración |
| `--iw-mid-dark` | `#9682E8` | Lila medio oscuro |

### Texto

| Token | Hex | Uso |
|---|---|---|
| `--iw-ink` | `#242B37` | Texto principal (navy con tinte morado) |
| `--iw-ink-soft` | `#4B5563` | Texto secundario |
| `--iw-on-dark` | `#FFFFFF` | Texto sobre fondos brand o lila intenso |

### Combinaciones permitidas

- **Navy `#242B37` + Lila brand `#7E69E3`** → patrón mitad-mitad en titulares
- **Lila brand `#7E69E3` → texto siempre BLANCO** (nunca navy sobre brand)
- **Lila medio `#B5A2EE` → texto BLANCO también** (mid es oscuro suficiente)
- **Lila claro `#D4C9F4` al 45% transparencia + texto navy** → cards delicados

### Combinaciones PROHIBIDAS

- ❌ Brand puro sobre brand
- ❌ Mid sobre mid (sin contraste)
- ❌ Texto navy sobre fondo lila brand (siempre blanco)
- ❌ Usar el navy `#242B37` como fondo dominante de slides — Anna **NO usa fondos dark**. Para impacto, usar lila brand `#7E69E3` sólido.

---

## 3. Tipografía

### Familias

**Urbanist** (variable font 100-900) — sans-serif elegante, principal para todo el cuerpo.
**GiftenSans Italic** — serif display italic, EXCLUSIVAMENTE para highlights y palabras-bisagra.

Fallback CSS: `'Urbanist', system-ui, -apple-system, sans-serif`

### Jerarquía

| Estilo | Peso | Tamaño | Line-height | Uso |
|---|---|---|---|---|
| Display | 600 | 72-96px | 1.05 | Cover, hero principal |
| H1 | 600 | 48-60px | 1.10 | Titulares de slide / sección |
| H2 | 500 | 40-52px | 1.15 | Sub-titulares |
| H3 | 500 | 28-36px | 1.20 | Cards, sub-secciones |
| Lead | 400 | 24-28px | 1.50 | Subtítulos |
| Body | 400 | 18-22px | 1.55 | Cuerpo principal |

### Reglas críticas para Anna

- **Pesos MAX 600.** NUNCA heavy 800-900. Rompe el feel delicado de la marca.
- **GiftenSans italic** en `<span class="iw-hl">` para palabras-bisagra → a `0.85em` para compensar métricas mayores.
- **Strokes finos:** SVG `stroke-width: 1.5` (no 2 como otras marcas).
- **NUNCA eyebrow sobre headlines.** El título abre la slide directamente.
- **Letter-spacing -0.015em** en h1 — menos densidad que IW.

### Ejemplo del patrón mitad-mitad

```html
<h1>Crea un negocio simple <span class="iw-hl">que te da ingresos predecibles, paz y tiempo para disfrutar</span> sin publicar en las redes a diario</h1>
```

La segunda parte va en GiftenSans italic lila brand (`.iw-hl`).

---

## 4. Sistema de espaciado

Mismo sistema 8px de IW, pero más generoso en Anna (feel aireado).

| Token | Valor | Uso |
|---|---|---|
| `--iw-space-2xs` | 8px | Gaps mínimos |
| `--iw-space-xs` | 16px | Gaps entre elementos relacionados |
| `--iw-space-s` | 24px | Padding interno cards |
| `--iw-space-m` | 40px | Margen entre bloques |
| `--iw-space-l` | 64px | Separación entre secciones (Anna usa más espacio) |
| `--iw-space-xl` | 96px | Padding hero generoso |

### Border-radius

| Token | Valor | Uso |
|---|---|---|
| `--iw-radius-pill` | 12px | Pills |
| `--iw-radius-card` | 20px | Cards (más redondeado que IW por feel suave) |
| `--iw-radius-cardLg` | 28-32px | Cards grandes, media |
| `--iw-radius-circle` | 9999px | Avatares, CTAs pill |

---

## 5. Iconografía

### Doble sistema

Anna usa **dos tipos** de iconografía según el contexto:

1. **Lucide outline** — para iconos funcionales (navbar, alerts, inputs).
2. **Sparkles ⋆ + iconos ilustrativos** — para slides decorativas y bullets, en lugar del check típico.

### Specs Lucide

- **ViewBox:** `0 0 24 24`
- **Stroke-width:** **`1.5`** (más fino que IW)
- **Stroke-linecap:** `round`
- **Stroke-linejoin:** `round`
- **Fill:** `none`

### Sparkle (firma visual de Anna)

```html
<svg viewBox="0 0 24 24" fill="currentColor">
  <path d="M 12 2 L 16 8 L 22 12 L 16 16 L 12 22 L 8 16 L 2 12 L 8 8 Z"/>
</svg>
```

Usar en color `var(--iw-primary)` sobre claro, o **blanco** sobre fondo lila brand.

### Iconos en cards delicadas

Patrón habitual en Anna: sparkle decorativo + título (en lugar del círculo brand contenedor de IW).

---

## 6. Decoración visual

### Sparkles ⋆

Firma visual principal de Anna. Aparecen en:
- Logo (parte del lockup)
- Bullets de cards (en lugar del check)
- Decoración alrededor de fotos del hero
- Separadores de sección (en el divisor del footer)

### Flor de vida

Patrón geométrico circular visible en los fondos (`fondos-10.jpg` y `fondos-12.jpg`). NO añadir más decoraciones de flor de vida fuera de los fondos — son sutiles, no protagonistas.

### Card de impacto

En lugar del "card dark" de IW, Anna usa **fondo lila brand sólido `#7E69E3`** para secciones de impacto:
- Card testimonial dark
- Stats band (en slides 26-stats-dark-6 ahora con fondo lila brand)
- CTA final con foto + fondo brand

### Fondos

- **Principal:** `assets/bg/fondos-10.jpg` (lila claro + flor de vida sup-izq)
- **Brand intenso:** `assets/bg/fondos-12.jpg` (lila intenso + flor de vida)
- **Cards delicadas:** `rgba(212, 201, 244, 0.45)` (light brand al 45%)

### Flechas

- ❌ NUNCA flechas hand-drawn
- ✅ Líneas finas (1.5 stroke) y sparkles como conectores

---

## 7. Fotografía

### Estilo

- **Femenina, natural, cálida.**
- Retratos de Anna en contextos serenos (consulta, hogar, naturaleza).
- Luz cálida o luz natural soft (no luz fría, no flash duro).
- Composiciones aireadas, mucho espacio negativo.

### Tratamiento

- **Border-radius:** 24-28px (rounded suave) o circular en el hero (con fondo flor de vida)
- **Aspect-ratio:** 4:5 retrato vertical, 1:1 cuadrado testimonial, 16:10 amplio
- **Object-fit: cover** para no deformar

### Prohibiciones

- ❌ Stock photos cliché de mujer "feliz fingida"
- ❌ Filtros instagram saturados
- ❌ Manipulación / esoterismo (cristales, tarot — NO encaja con el nicho real de business coaching)
- ❌ Overlay verde o saturado

### Si no hay foto propia

Usar Unsplash con keywords coherentes (ver README sección Imágenes con Unsplash):
`woman,entrepreneur,calm`, `meditation,morning`, `wellness,space`.

---

## 8. Voz y tono

> La voz se gestiona desde las skills de texto de la agencia.

Recordatorio rápido: tuteo cálido, frases que respiran, permiso antes de mandato, vocabulario de presencia/conexión/alineamiento. **NO usar lenguaje masculino-tech o promesas mágicas baratas.**

---

## 9. Reglas no negociables del sistema

1. **Pesos ≤ 600.** Nunca heavy 800-900.
2. **GiftenSans italic** para highlights, NO bold mono color como otras marcas.
3. **Sparkles ⋆** como bullets/decoración, no checks típicos.
4. **NUNCA fondos navy dark** como impacto — usar **lila brand `#7E69E3`** en su lugar.
5. **Lila brand puro y lila mid `#B5A2EE` → contenido siempre BLANCO.**
6. **CTA "Acceder" del navbar es NEGRO pill** (no lila brand, coherente con web real).
7. **Cover SIN logo** (decisión de Anna).
8. **Strokes SVG 1.5** (no 2 como otras marcas).
9. **NUNCA eyebrow sobre headlines.**
10. **Whitespace + aireación máxima.** Anna respira, no apreta.

---

## 10. Checklist antes de publicar

- [ ] Pesos tipográficos ≤ 600
- [ ] Highlights en GiftenSans italic, no bold mono color
- [ ] Sparkles ⋆ en lugar de checks típicos
- [ ] Fondos de impacto en lila brand, no navy dark
- [ ] CTA navbar Acceder en negro pill
- [ ] Iconos Lucide stroke 1.5
- [ ] Brand puro → texto blanco
- [ ] Fotografía cálida y femenina, sin cliché
- [ ] Aireación generosa, mucho whitespace
- [ ] Sin eyebrow sobre headlines

---

## Recursos

- **Tokens CSS:** `tokens.css`
- **Catálogo de slides:** `preview.html`
- **Catálogo de componentes:** `preview-components.html`
- **Repositorio:** https://github.com/adminnosolounjpg/anna-raventos-ds
