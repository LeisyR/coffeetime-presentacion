# CoffeeTime — Presentación (instancia de la Plantilla Maestra CompanyGame)

> ⚠️ **Esta carpeta YA NO es la plantilla.** Es la presentación de **CoffeeTime**, ya rellenada:
> no quedan tokens `[[...]]` ni bloques `.reserved` pendientes. Para un simulador nuevo, parte de
> `../plantilla-presentacion/`. Lo que sigue es la documentación de la plantilla de origen, útil
> como referencia de componentes y convenciones al editar esta presentación.
>
> **Cambios propios de esta instancia:**
> - **17 láminas en tres bloques** (manual / informes / decisiones), con divisoria propia cada uno.
>   La lámina 11 (Cuadro de Mando) es el núcleo formativo: método de análisis en cinco
>   pasos + mapa de los ocho informes. El contador del
>   nav es dinámico (`slides.length`); solo hay que mantener a mano el texto inicial `1 / 17` y las
>   insignias `.slide-number` (que van desfasadas −1: la lámina 2 muestra `01`).
>
>   ⚠️ **Al añadir o quitar una lámina** hay que tocar cuatro cosas: el `id="slideN"` de todas las
>   posteriores, sus insignias `.slide-number`, el texto `1 / N` del contador y las **referencias
>   cruzadas en el texto** («las dos láminas siguientes», «las láminas 9 a 11»).
> - Componentes nuevos en el CSS: `.rep` / `.rep-head` / `.rep-body` / `.rep-split` / `.rep-hero` /
>   `.rep-h` / `.rep-read` / `.ask` / `.rep-dec` (bloque de informe), `.cycle` / `.cycle-step`,
>   `.kpi-row` / `.kpi`, `.note`, `.sec-title` / `.sec-sub`, `.card-grid.cols5`, `.card-num`,
>   `.shot-pending`, `.fill-coffee`.
> - **Mini-gráficos en CSS puro, sin librerías**: `.mini-row` / `.mini-track` / `.mini-fill`
>   (barras de magnitud), `.stack` (coste vs margen), `.flow` (precio → descuento → neto).
>   Un solo tono `#7A4B28` porque miden magnitud, no identidad; `.mini-fill.soft` (`#C3A484`) para
>   las barras de referencia. Etiquetas siempre en tinta, fuera del color. `.mini-track` y
>   `.mini-fill` **necesitan `display:block`**: son `<span>` y en inline la altura no aplica.
> - **CSS sin uso** tras retirar el módulo de análisis detallado: `.rep*`, `.ask`, `.mini*`, `.stack`,
>   `.flow`. Se conserva por si se recupera desde `_respaldo/index-con-analisis.html`.
> - Paleta café en `:root`; pie `.slide-foot` con el logo `assets/logo-sdn.png` inyectado por JS en
>   las láminas de contenido (ni portada, ni cierre, ni divisorias); logo también en intro y portada.
> - Capturas de la lámina 9 con degradación elegante (`onerror`) mientras no existan.
> - `.slide.active` pasa a `display:flex` en columna para que el pie quede siempre abajo.
>
> **Regla al editar:** las cifras del Periodo 0 deben mantenerse consistentes con
> `coffeetime_project/generate.js`, que es la fuente del análisis.
>
> Distribuidor: **Simuladores de Negocios Colombia** (Grupo Edutec).

## Cómo se construye una presentación nueva

1. **Copiar** esta carpeta y renombrarla con el nombre del simulador.
2. Decirle a Claude: *"Esta presentación es para el simulador **[NOMBRE]**"* y darle la
   información del simulador (manual, capturas, datos).
3. Claude **reemplaza los tokens `[[...]]`** y **rellena los slides variables**, conservando
   los slides fijos tal cual.
4. Guardar las imágenes específicas en `assets/` (ver **Convenciones de imágenes** abajo).

## Convenciones de imágenes (estándar Corbatul — la presentación más pulida)

- **Formato y nombre descriptivo**: las capturas van en **`.jpg`** (pesan menos que PNG) con
  nombre que dice qué son, no numerado. Ej. Cuadro de Mando → `cm-valor.jpg`, `cm-marketing.jpg`,
  `cm-produccion.jpg`; Decisiones → `dec-capital.jpg`, `dec-ventas.jpg`, `dec-produccion.jpg`.
  (El logo, cartelera y avatares conservan su formato original.)
- **Siempre clicables (lightbox)**: cada `<img>` de captura lleva
  `onclick="openLightbox('assets/x.jpg','Título descriptivo')"` y `loading="lazy"`.
- **Tamaño / encuadre**:
  - Cuadro de Mando (`.cm-img img`): ocupa el 100 % del ancho de su tarjeta; no fijar alto.
  - Decisiones (`.dec-shot img`): 100 % de ancho con tope `max-width:920px` (centrada).
  - El lightbox muestra la imagen a `max-height:86vh` — no recortar capturas, se ven completas.
- **Organización del Cuadro de Mando**: usar **`.cm-masonry`** (no `.cm-grid`) cuando las capturas
  tengan alturas muy distintas; empaqueta las tarjetas en columnas sin huecos. Cada tarjeta lleva
  título + `.cm-badge` + `.cm-desc` + bloque **«Por qué importa»** (`.cm-why-label` + `.cm-why-text`).

## Tokens a reemplazar (búscalos con `[[`)

| Token | Qué es | Ejemplo (FoodCompany) |
|-------|--------|------------------------|
| `[[SIMULADOR]]` | Nombre del simulador | FoodCompany |
| `[[SUBTITULO]]` | Subtítulo de portada | Simulador de Gestión de una Empresa del Sector Lácteo |
| `[[PARRAFO_CONTEXTO]]` | 2-3 frases de qué es | … dirige una compañía láctea … |
| `[[NIVEL]]` | Nivel / dificultad | Nivel 4 · Estratégico |
| `[[DURACION]]` | Duración | 16–32 horas |
| `[[LINEAS_PRODUCTO]]` | Badge de líneas/foco | 🥛🥣🧀 3 Líneas de Producto |
| `[[AREA_CONOCIMIENTO]]` | Área CompanyGame | Marketing y Ventas |
| `[[EMOJI]]` | Emoji de marca (cierre) | 🥛 |
| `[[SUBTITULO_*]]`, `[[TITULO_*]]`, `[[FACTORES_VALOR]]` | Títulos/subtítulos de slides variables | — |

## Estructura: 14 slides (NO cambiar la cantidad sin actualizar el contador del nav)

| # | Slide | Tipo | Notas |
|---|-------|------|-------|
| 1 | Portada + Contexto | **FIJO** (estructura) | Branding CompanyGame; cambia solo nombre/imagen vía tokens |
| 2 | Cartelera de Simuladores | **FIJO** | Usa `assets/cartelera.jpg` y `assets/avatares.png` (portafolio CompanyGame) |
| 3 | Ingreso a la Plataforma | **FIJO** | URL `plataforma.companygame.net`; idéntico en todas |
| 4 | ¿Qué es? | variable | Tarjetas `.card-grid cols4` |
| 5 | Cadena de Valor | variable | `.value-chain` + `.card-grid` |
| 6 | Producción / Insumos | variable | `.data-table` + tarjetas |
| 7 | Áreas de Decisión | variable | `.card-grid` |
| 8 | Segmentos y Competitividad | variable | `.two-col` + `.factor-accordion` |
| 9 | Cuadro de Mando | variable | `.cm-masonry` (o `.cm-grid`) · capturas `assets/cm-<nombre>.jpg` |
| 10 | Decisiones del Simulador | variable | `.dec-block` · capturas `assets/dec-<nombre>.jpg` |
| 11 | Valor de la Compañía | variable | `.factor-accordion` con % |
| 12 | Métodos de Implementación | **FIJO** | Genérico (deductivo/inductivo/mixto/alternos) |
| 13 | Preguntas Frecuentes | variable (semi) | Preguntas reutilizables; ajustar respuestas del simulador |
| 14 | Cierre / Gracias | **FIJO** | Contacto del distribuidor (email + WhatsApp + logo SDN) |

Cada slide variable trae un `<div class="reserved">` con instrucciones y un comentario
`<!-- VARIABLE · ... -->` que indica el componente recomendado.

## Componentes de estilo disponibles (ya en el CSS)

- **Tarjetas**: `.card-grid` / `.card-grid.cols4` + `.card` (variantes `bd-amber/green/teal/purple/red`)
- **Tabla**: `.data-table`
- **Flujo**: `.value-chain` + `.chain-box` (`cb-amber/green/teal`)
- **Acordeón de factores**: `.factor-accordion` + `.factor-item` (`factor-orange/amber/green/teal/purple/red/blue`)
- **Galería de informes**: `.cm-masonry` (alturas dispares, recomendado) o `.cm-grid` + `.cm-card`
- **Bloques de decisión**: `.dec-block` (con `.dec-num`)
- **Acordeón FAQ**: `.accordion` + `.accordion-item`
- **Dos columnas**: `.two-col` · **Segmentos**: `.seg-row` · **Badges**: `.badge` (`badge-orange/green/teal/amber/purple`)
- **Lightbox** de imágenes: `onclick="openLightbox('assets/x.jpg','Título')"` + `loading="lazy"`

## Paleta (identidad CompanyGame/FoodCompany — ajustable por simulador)

```
--primary:#F58220  --primary-dark:#E06D10  --amber:#F9A825
--accent-green:#7BC143  --accent-teal:#00B4D8  --accent-purple:#9B59B6
--cg-blue:#1A5276
```
Si el simulador tiene identidad propia, cambia estas variables en `:root`.

## Datos fijos del distribuidor (no cambian entre simuladores)

- Plataforma de acceso: **https://plataforma.companygame.net/**
- Email: **fidelizacion@simuladoresdenegocios.co**
- WhatsApp: **301 790 3086** (`https://wa.me/573017903086`)
- Logo distribuidor: `assets/logo-sdn.png`

## Tecnología

HTML5 + CSS3 + JS vanilla, todo embebido en `index.html`. Sin frameworks. Navegación por
flechas/teclado/swipe ya implementada. No tocar el `<script>` salvo que cambie el nº de slides.
