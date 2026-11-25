# Eberth & Melida · Nuestra historia

Página de regalo con la estética de la referencia (azul noche + dorado): portada con sobre, nombres, foto con marco blanco, contador en vivo, mensaje privado, momentos, mapa, lista, vales y ruleta.

## Cómo verla

Abre `index.html` con doble clic. Funciona sin servidor; solo las tipografías se descargan de Google Fonts.

## Estructura

1. **Portada:** “UN REGALO PARA TI” → nombre → sobre con sello → “Toca para abrir”.
2. **Sitio (scroll):**
   - Nombres de los dos.
   - Foto con marco blanco y frase.
   - Contador: años, meses y días + reloj en vivo.
   - “Mensaje privado → Abrir carta” (modal con la carta).
   - Foto.
   - “Lo que más amo de ti”.
   - “Nuestros momentos” (línea de tiempo).
   - “Dónde empezó todo” (mapa con 3 lugares).
   - Foto.
   - “Nuestra lista” (checklist interactiva).
   - “Nuestros vales de amor” (se pueden canjear).
   - Ruleta de citas.
   - Cierre + firma.

## Personalizar

Todo el contenido está en el bloque de constantes al inicio del `<script>` de `index.html`:

```js
const ELLA = 'Melida';          // nombre de ella
const EL   = 'Eberth';          // tu nombre
const FECHA_INICIO = '2024-02-14';  // AAAA-MM-DD ("" oculta el contador)

const GUSTOS = [ ... ];         // "Lo que más amo de ti"
const MOMENTOS = [ ... ];       // capítulos de la línea de tiempo
const LUGARES = [ ... ];        // nombres y descripciones de los 3 lugares
const LISTA = [ ... ];          // cosas por hacer juntos
const VALES = [ ... ];          // vales de amor
const RULETA = [ ... ];         // opciones de la ruleta
```

También en el HTML: el `<title>`, las frases de las fotos (`<figcaption>`) y los textos de la carta (dentro del modal).

## Añadir fotos

En cada `<figure class="marco">` hay un bloque `.marco__vacio` con el icono de cámara. Sustitúyelo por una imagen:

```html
<div class="marco__foto">
  <img src="fotos/nosotros.jpg" alt="Nosotros">
</div>
```

Crea una carpeta `fotos/` al lado de `index.html` y usa imágenes verticales (4:5 funciona mejor). Se recortan solas con `object-fit: cover`.

## Publicar y compartir

1. **Netlify Drop** — https://app.netlify.com/drop (arrastra la carpeta).
2. **GitHub Pages** — Settings → Pages → rama `main` / root.
3. **Vercel** — `npx vercel` dentro de la carpeta.

Luego envía el enlace por WhatsApp. Mejor aún: genera un QR con ese enlace e imprímelo dentro de una tarjeta.

## Detalles técnicos

- Sin frameworks ni build: un solo `index.html`.
- Música suave opcional generada con Web Audio (sin archivos).
- Contador de días calculado en el navegador.
- Interacciones: modal de carta con foco atrapado, checklist, vales canjeables, ruleta con resultado consistente con la aguja.
- Responsive probado en 360 px, 412 px y escritorio; respeta `prefers-reduced-motion`.
