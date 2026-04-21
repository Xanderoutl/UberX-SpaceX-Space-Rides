# Fuentes — UberX × SpaceX

## Tipografía del proyecto

| Rol | Fuente | Pesos | Uso |
|-----|--------|-------|-----|
| Display / Títulos | **Orbitron** | 400, 600, 700, 900 | Logos, encabezados, números de precio |
| Body / UI | **Space Grotesk** | 300, 400, 500, 600, 700 | Texto general, labels, botones |
| Mono / Códigos | **Space Mono** | 400, 700 | Números de vuelo, tarjetas, coords |

---

## Opción 1 — Google Fonts (CDN, recomendado)

Añade en el `<head>` de cada pantalla, **antes** de cualquier CSS:

```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;600;700;900&family=Space+Grotesk:wght@300;400;500;600;700&family=Space+Mono:wght@400;700&display=swap" rel="stylesheet">
```

Ya está incluido en `app.css` con `@import`, pero el `<link>` en HTML es más performante.

---

## Opción 2 — Self-hosted (sin internet)

Descarga las fuentes en `/assets/fonts/` desde:
- https://fonts.google.com/specimen/Orbitron
- https://fonts.google.com/specimen/Space+Grotesk
- https://fonts.google.com/specimen/Space+Mono

Luego añade en `/css/app.css`:

```css
/* Orbitron */
@font-face {
  font-family: 'Orbitron';
  src: url('../assets/fonts/Orbitron-Regular.woff2') format('woff2');
  font-weight: 400;
  font-display: swap;
}
@font-face {
  font-family: 'Orbitron';
  src: url('../assets/fonts/Orbitron-SemiBold.woff2') format('woff2');
  font-weight: 600;
  font-display: swap;
}
@font-face {
  font-family: 'Orbitron';
  src: url('../assets/fonts/Orbitron-Bold.woff2') format('woff2');
  font-weight: 700;
  font-display: swap;
}
@font-face {
  font-family: 'Orbitron';
  src: url('../assets/fonts/Orbitron-Black.woff2') format('woff2');
  font-weight: 900;
  font-display: swap;
}

/* Space Grotesk */
@font-face {
  font-family: 'Space Grotesk';
  src: url('../assets/fonts/SpaceGrotesk-Light.woff2') format('woff2');
  font-weight: 300;
  font-display: swap;
}
@font-face {
  font-family: 'Space Grotesk';
  src: url('../assets/fonts/SpaceGrotesk-Regular.woff2') format('woff2');
  font-weight: 400;
  font-display: swap;
}
@font-face {
  font-family: 'Space Grotesk';
  src: url('../assets/fonts/SpaceGrotesk-Medium.woff2') format('woff2');
  font-weight: 500;
  font-display: swap;
}
@font-face {
  font-family: 'Space Grotesk';
  src: url('../assets/fonts/SpaceGrotesk-SemiBold.woff2') format('woff2');
  font-weight: 600;
  font-display: swap;
}
@font-face {
  font-family: 'Space Grotesk';
  src: url('../assets/fonts/SpaceGrotesk-Bold.woff2') format('woff2');
  font-weight: 700;
  font-display: swap;
}

/* Space Mono */
@font-face {
  font-family: 'Space Mono';
  src: url('../assets/fonts/SpaceMono-Regular.woff2') format('woff2');
  font-weight: 400;
  font-display: swap;
}
@font-face {
  font-family: 'Space Mono';
  src: url('../assets/fonts/SpaceMono-Bold.woff2') format('woff2');
  font-weight: 700;
  font-display: swap;
}
```

---

## Variables CSS ya definidas en app.css

```css
--font-display: 'Orbitron', sans-serif;
--font-body:    'Space Grotesk', sans-serif;
--font-mono:    'Space Mono', monospace;
```

### Uso recomendado

```css
/* Título de pantalla */
h1 { font-family: var(--font-display); font-weight: 700; }

/* Precio en tokens espaciales */
.price { font-family: var(--font-display); font-weight: 900; }

/* Cuerpo / labels */
p, button, input { font-family: var(--font-body); }

/* Número de vuelo, dígitos de tarjeta */
.flight-code { font-family: var(--font-mono); }
```

---

## Jerarquía tipográfica (tokens)

| Token | Valor | Uso |
|-------|-------|-----|
| `--fz-xs` | 10px | Badges, labels tiny |
| `--fz-sm` | 12px | Subtítulos secundarios |
| `--fz-base` | 14px | Texto de párrafo |
| `--fz-md` | 16px | Texto principal, botones |
| `--fz-lg` | 20px | Títulos de sección |
| `--fz-xl` | 28px | Títulos de pantalla |
| `--fz-2xl` | 36px | Precios grandes |
| `--fz-3xl` | 48px | Hero / Splash |
