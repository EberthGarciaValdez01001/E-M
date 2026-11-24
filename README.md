# Un regalo para ti · Melida

Página web de regalo: portada con sobre dorado que se abre y revela una carta con los momentos de la relación.

## Cómo verla

Abre `index.html` con doble clic (funciona sin internet; solo las tipografías se descargan de Google Fonts).

## Cómo personalizarla

Todo el contenido está en un solo bloque al inicio del `<script>`, al final de `index.html`:

```js
const NOMBRE = 'Melida';            // nombre que aparece en la carta
const FECHA_INICIO = '2024-02-14';  // AAAA-MM-DD → activa el contador de días ("" lo oculta)
const FIRMA = 'Tu nombre';          // cómo firmas la carta
const MOMENTOS = [ ... ];           // capítulos de la línea de tiempo
const RAZONES = [ ... ];            // lista "Cosas que amo de ti"
```

Además, en el HTML:

- El título grande de la portada: `<h1 class="titulo">Melida</h1>`
- El subtítulo: `<p class="subtitulo">Un regalo para ti</p>`
- La dedicatoria: los dos primeros `<p>` dentro de `<article class="papel">`

## Añadir fotos (opcional)

Dentro de cada momento puedes insertar una imagen. Copia tus fotos a una carpeta `fotos/` y añade:

```html
<img src="fotos/playa.jpg" alt="Nosotros en la playa" style="width:100%;border-radius:10px;margin:10px 0">
```

…o edita el render de `MOMENTOS` para incluir `foto: 'fotos/playa.jpg'`.

## Publicarla y compartirla

1. **Netlify Drop** (lo más rápido): entra en https://app.netlify.com/drop y arrastra la carpeta del proyecto. Te da un enlace tipo `https://algo.netlify.app`.
2. **GitHub Pages**: sube el repo y activa Pages en Settings → Pages.
3. **Vercel**: `npx vercel` dentro de la carpeta.

Después envía el enlace por WhatsApp: se abre como una página normal y se puede añadir a la pantalla de inicio.

## Detalles incluidos

- Tulipán como icono de la pestaña y tulipanes flotantes de fondo.
- Sobre con sello de corazón y animación de apertura.
- Carta con contador de días, línea de tiempo, “cosas que amo de ti” y firma.
- Botón de música suave generada con Web Audio (sin archivos de audio).
- Diseño responsive (probado en 360 px, 412 px y escritorio) y respeto por `prefers-reduced-motion`.
