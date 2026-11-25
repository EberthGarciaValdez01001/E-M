# Marcelo & Melida · Nuestra historia

Página de regalo con la estética de la referencia (azul noche + dorado): portada con sobre, nombres, fotos con marco blanco, contador en vivo, mensaje privado, línea del tiempo real, mapa de la distancia, galería, lista, vales y ruleta.

## Cómo verla

Abre `index.html` con doble clic. Funciona sin servidor; las fotos están en `fotos/` y solo las tipografías se descargan de Google Fonts.

## Estructura

1. **Portada:** “UN REGALO PARA TI” → nombre → sobre con sello → “Toca para abrir”.
2. **Sitio (scroll):**
   - Nombres + “Tegucigalpa · El Salvador”.
   - Foto de su cumpleaños en Metro Mall.
   - Contador: **juntos desde el 14/07/2026** + reloj en vivo + días desde el primer saludo (27/11/2024).
   - “Mensaje privado → Abrir carta” (carta con las fechas reales).
   - Foto del primer encuentro (Centro Cívico).
   - “Lo que más amo de ti”.
   - **Línea del tiempo real:** 27/11/2024 22:13 → 14/07/2026 → 4/9/2026 12:00 → 5/9/2026 12:30 → 7/9/2026 5:30 → hoy.
   - **“Nuestra distancia”**: mapa Tegucigalpa ↔ El Salvador + los 3 lugares.
   - Foto de Metro Mall.
   - **Galería:** las fotos de los días 4 y 5 de septiembre de 2026.
   - “Nuestra lista” (checklist interactiva).
   - “Nuestros vales de amor” (se pueden canjear).
   - Ruleta de citas.
   - Cierre + firma.

## Personalizar

Todo el contenido está en el bloque de constantes al inicio del `<script>` de `index.html`:

```js
const ELLA = 'Melida';
const EL   = 'Marcelo';
const FECHA_INICIO = '2026-07-14';            // relación
const FECHA_SALUDO = '2024-11-27T22:13:00';   // primer saludo

const GUSTOS = [ ... ];
const MOMENTOS = [ { fecha, titulo, texto }, ... ];
const LUGARES = [ { nombre, detalle }, ... ];
const LISTA = [ ... ];
const VALES = [ ... ];
const RULETA = [ ... ];
```

## Fotos

Están en `fotos/` ya optimizadas (máx. 1400 px, JPEG ~82 %):

| Archivo | Contenido |
|---|---|
| `centro-civico-1.jpg` | Plaza del Centro Cívico |
| `centro-civico-2.jpg` | Vista de la plaza desde arriba |
| `centro-civico-3.jpg` | Bebidas y McDonald's (primer encuentro) |
| `centro-civico-4.jpg` | Pérgola y flores |
| `centro-civico-5.jpg` | Torre Chortí |
| `centro-civico-6.jpg` | Pasillo del Centro Cívico |
| `metro-mall-1.jpg` | Cumpleaños de Melida (velas) |
| `metro-mall-2.jpg` | Caminando por Metro Mall |
| `metro-mall-3.jpg` | Comida en Metro Mall |

Para cambiar una foto, reemplaza el archivo por otro con el mismo nombre o edita el `src` en el HTML. Los marcos recortan solos con `object-fit: cover`.

**Nota de privacidad:** el boleto de avión no se publicó porque muestra el número de pasaporte y el código QR. La historia del vuelo está contada en texto (fecha, hora y ruta). Si quieres incluir la foto, hay que tapar esos datos primero.

## Publicar y compartir

1. **Netlify Drop** — https://app.netlify.com/drop (arrastra la carpeta completa, con `fotos/`).
2. **GitHub Pages** — Settings → Pages → rama `main` / root. Las rutas son relativas, así que funciona igual.
3. **Vercel** — `npx vercel` dentro de la carpeta.

## Detalles técnicos

- Sin frameworks ni build: un solo `index.html` + `fotos/`.
- Música suave opcional generada con Web Audio (sin archivos).
- Contador de relación + contador de días desde el primer saludo.
- Interacciones: modal de carta con foco atrapado, checklist, vales canjeables, ruleta con resultado consistente con la aguja.
- Responsive probado en 360 px, 412 px y escritorio; respeta `prefers-reduced-motion`.
