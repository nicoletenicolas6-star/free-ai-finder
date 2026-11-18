# Free AI Finder

Directorio interactivo de proveedores de inteligencia artificial con modelos y planes gratuitos: APIs gratis, chats sin pagar, generación de imagen y audio, y modelos que corren en tu propio PC.

Un solo archivo HTML, sin dependencias, sin build, sin backend. Funciona offline y se despliega en cualquier hosting estático.

## Qué incluye

- 35 proveedores con su límite gratuito real, modelos disponibles y advertencias.
- Buscador en vivo (atajo `/`, `Esc` para limpiar).
- Atajos por intención: para tu app, para chatear hoy, generar imágenes, correr en tu PC, sin tarjeta.
- Filtros por tipo: API gratis, chat, imagen, audio, local, créditos y trials.
- Filtro "sin tarjeta" y favoritos guardados en `localStorage`.
- Tema oscuro con acentos neón, responsive.

## Estructura

```
index.html              -> app (raíz del sitio)
free-ai-finder.html     -> copia idéntica, mismo contenido
vercel.json             -> cabeceras de caché y clean URLs
```

## Desplegar en Vercel

1. Entra a [vercel.com/new](https://vercel.com/new).
2. Importa este repositorio.
3. Framework preset: **Other**. Build command: vacío. Output directory: `.` (raíz).
4. Deploy. La página queda en `https://<proyecto>.vercel.app`.

No hay paso de build: Vercel sirve `index.html` tal cual.

## Desplegar en otros hostings

- **Netlify Drop**: arrastra `index.html` a [app.netlify.com/drop](https://app.netlify.com/drop).
- **GitHub Pages**: Settings → Pages → Deploy from branch → `main` / root.
- **Local**: abre `index.html` con doble clic. Funciona sin internet.

## Editar el catálogo

Todo el contenido vive en el array `DATA` dentro de `<script>`, al final del HTML. Cada entrada:

```js
{ n:"Nombre", full:"Producto", cat:"api", acc:"#b6ff3d", reco:90,
  tag:"Frase corta de qué es",
  free:"Qué te dan gratis, con los límites reales",
  models:"modelos disponibles",
  tags:["sin tarjeta","cuenta"],
  warn:"advertencia opcional",
  url:"https://...", verif:"dato de verificación" }
```

Categorías válidas: `api`, `chat`, `imagen`, `audio`, `local`, `creditos`.
`reco` ordena las tarjetas por recomendación (mayor primero).

## Aviso

Los planes gratuitos cambian constantemente y los límites exactos suelen verse solo dentro del panel de cada proveedor. Los datos se revisaron en noviembre de 2026 y sirven como guía, no como contrato. En casi todos los tiers gratuitos los prompts pueden usarse para entrenar el modelo: no subas datos privados ni de clientes.
