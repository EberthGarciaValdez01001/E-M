# Marcelo & Melida · Nuestra historia

Página de regalo con la estética de la referencia (azul noche + dorado): portada con sobre, nombres, fotos con marco blanco, contador en vivo, mensaje privado con **carta escrita a mano**, línea del tiempo real, mapa de la distancia, galería, lista, vales y ruleta.

## Cómo verla

Abre `index.html` con doble clic. Funciona sin servidor; las fotos están en `fotos/` y solo las tipografías se descargan de Google Fonts.

## Estructura

1. **Portada:** “UN REGALO PARA TI” → nombre → sobre con sello → “Toca para abrir”.
2. **Sitio (scroll):**
   - Nombres + “Guatemala · Honduras”.
   - Foto de su cumpleaños en Metro Mall.
   - **Tiempo de conocernos (primer saludo):** contador desde el 27/11/2024 22:13 + reloj en vivo + “Juntos desde el 14/07/2026”.
   - “Mensaje privado → Abrir carta”: la carta escrita, la firma y **la carta a mano del PDF** (se puede ampliar).
   - Foto del primer encuentro (Centro Cívico).
   - “Lo que más amo de ti”.
   - **Línea del tiempo:** 27/11/2024 22:13 → 14/07/2026 → 4/9/2026 12:00 → 5/9/2026 12:30 → 7/9/2026 5:30 → hoy.
   - **“Nuestra distancia”**: mapa Guatemala ↔ Honduras + los 3 lugares.
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
const FECHA_INICIO  = '2024-11-27T22:13:00';  // primer saludo (contador principal)
const FECHA_RELACION = '2026-07-14';          // inicio de la relación (línea de abajo)

const GUSTOS = [ ... ];
const MOMENTOS = [ { fecha, titulo, texto }, ... ];
const LUGARES = [ { nombre, detalle }, ... ];
const LISTA = [ ... ];
const VALES = [ ... ];
const RULETA = [ ... ];
```

## Fotos

Están en `fotos/` ya optimizadas (JPEG). Para cambiar una, reemplaza el archivo o edita el `src` en el HTML.

| Archivo | Contenido |
|---|---|
| `carta-mano.jpg` | Carta escrita a mano (desde el PDF `ELISAAA.pdf`) |
| `centro-civico-1.jpg` | Plaza del Centro Cívico |
| `centro-civico-2.jpg` | Vista de la plaza desde arriba |
| `centro-civico-3.jpg` | Bebidas y McDonald's (primer encuentro) |
| `centro-civico-4.jpg` | Pérgola y flores |
| `centro-civico-5.jpg` | Torre Chortí |
| `centro-civico-6.jpg` | Pasillo del Centro Cívico |
| `metro-mall-1.jpg` | Cumpleaños de Melida (velas) |
| `metro-mall-2.jpg` | Caminando por Metro Mall |
| `metro-mall-3.jpg` | Comida en Metro Mall |

**Carta a mano:** viene de `ELISAAA.pdf` (1 página escaneada). Se recortó, se convirtió a JPEG y se agregó al modal de “Abrir carta”, debajo del texto. Al tocarla se abre en un visor a pantalla completa y se puede acercar tocando la imagen.

**Nota de privacidad:** el boleto de avión no se publicó porque muestra el número de pasaporte y el código QR. La historia del vuelo está contada en texto.

## Publicar y compartir

1. **Netlify Drop** — https://app.netlify.com/drop (arrastra la carpeta completa, con `fotos/`).
2. **GitHub Pages** — Settings → Pages → rama `main` / root.
3. **Vercel** — `npx vercel` dentro de la carpeta.

## Detalles técnicos

- Sin frameworks ni build: un solo `index.html` + `fotos/`.
- Música suave opcional generada con Web Audio (sin archivos).
- Contador principal (desde el primer saludo) + línea con los días de relación.
- Interacciones: modal de carta con foco atrapado, visor de la carta a mano con zoom, checklist, vales canjeables, ruleta con resultado consistente con la aguja.
- Responsive probado en 360 px, 412 px y escritorio; respeta `prefers-reduced-motion`.

## Efectos de tulipanes

- **Jardín:** 8 tulipanes creciendo en las esquinas inferiores de la portada, meciéndose con el viento.
- **Pétalos cayendo:** capa de pétalos dorados, crema y rosa en toda la página.
- **Lluvia al abrir:** al pulsar “Toca para abrir” salen 32 pétalos desde el sobre.
- **Detalles:** tulipán en el divisor de los nombres, en el pie y como icono de la pestaña.
- Todo se oculta automáticamente si el dispositivo pide movimiento reducido.
