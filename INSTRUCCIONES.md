# ☕ CoffeeTime — Presentación interactiva

Presentación de **17 láminas** del simulador **CoffeeTime** de CompanyGame, generada a partir de la
plantilla maestra (`../plantilla-presentacion/`) y personalizada con la identidad de café y el logo
de **Simuladores de Negocios Colombia**.

> 🎯 **El centro de la formación es el cuadro de mando** — la lámina **9**: el
> **método de trabajo del equipo en cinco pasos** y el mapa de los **diez informes**, cada uno con su captura real, lo que
> informa, sus cifras del Periodo 0 y por qué importa.

> Esta carpeta ya **no** es la plantilla. Para una presentación de otro simulador, copia
> `../plantilla-presentacion/` de nuevo.

## Cómo verla

Abre `index.html` con doble clic (Chrome, Edge o cualquier navegador). No necesita servidor ni
instalación. Solo usa internet para las tipografías de Google Fonts; sin conexión se ve con la
fuente del sistema.

- **Avanzar / retroceder**: botones inferiores, flechas ← →, barra espaciadora o swipe en móvil.
- **Ampliar una captura**: clic sobre la imagen (lightbox; `Esc` o clic para cerrar).
- **Desplegar** factores y preguntas frecuentes: clic sobre la cabecera de color.

## Qué contiene

| # | Lámina | Bloque |
|---|--------|--------|
| 1 | Portada + contexto | — |
| 2 | Cartelera de simuladores CompanyGame | — |
| 3 | Ingreso a la plataforma | — |
| **4** | **Divisoria — 📖 El manual del participante** | **1** |
| 5 | ¿Qué es CoffeeTime? | 1 |
| 6 | Cadena de valor | 1 |
| 7 | Producción y costes | 1 |
| 8 | Áreas de decisión | 1 |
| 9 | Segmentos y competitividad | 1 |
| **10** | **Divisoria — 📊 Los informes del cuadro de mando** | **2** |
| 11 | Cuadro de mando — método en 5 pasos + los 10 informes | 2 |
| 12 | Valor de la Compañía | 2 |
| **13** | **Divisoria — 🕹️ Las decisiones del simulador** | **3** |
| 14 | Las decisiones — 8 pantallas reales | 3 |
| 15 | Métodos de implementación | — |
| 16 | Preguntas frecuentes | — |
| 17 | Cierre y contacto del distribuidor | — |

## Los tres bloques

El recorrido está señalizado en dos niveles para que siempre se sepa en qué parte se está:

1. **Tres láminas divisorias** a sangre sobre fondo café (4, 10 y 13), que rompen visualmente con
   las láminas de contenido —blancas— y anuncian qué viene y con qué frecuencia se usa.
2. **Una etiqueta de bloque** en la cabecera de cada lámina de contenido, inyectada por JS
   (`injectBlockLabels`) según el índice de la lámina. Si se añade o mueve una lámina hay que
   actualizar los rangos `desde`/`hasta` de ese script.

La numeración de la esquina cuenta **solo láminas de contenido**: las divisorias no llevan número
porque ya tienen el suyo de bloque (01, 02, 03).

Las cifras corresponden al **Periodo 0** del simulador y coinciden con las del deck de PowerPoint
`coffeetime_project/generate.js`, de donde procede todo el contenido de la lámina 9.

## El cuadro de mando (lámina 9)

Es el núcleo formativo y tiene dos partes.

**1 · El método de análisis en cinco pasos**, que se le pide al equipo *por escrito* cada periodo —
sirve como guía de taller y como rúbrica de evaluación:

`1 Leer` → `2 Diagnosticar` → `3 Cuantificar la brecha` → `4 Decidir con hipótesis` → `5 Contrastar`

Lo que se evalúa no es acertar a la primera, sino la calidad del razonamiento que conecta la cifra
con la decisión. Los pasos 2 a 4 son los que dejan rastro escrito.

**2 · El mapa de los diez informes**, en rejilla de tres columnas y orden numérico. Cada tarjeta
lleva título, `.cm-badge` con el número de informe, qué informa con sus cifras del Periodo 0, y un
bloque **«Por qué importa»**.

> **Análisis detallado retirado.** Hubo dos láminas más («Análisis del Cuadro de Mando · I y · II»)
> que recorrían los ocho informes uno a uno con gráficos de referencia, la lectura y las preguntas
> que debe responder el equipo. Se eliminaron por extensión. La versión que las contiene está en
> `_respaldo/index-con-analisis.html` — se puede recuperar de ahí.
>
> Su CSS sigue en `index.html` y **no se usa**: `.rep*`, `.ask`, `.mini*`, `.stack`, `.flow`.
> Se conserva por si se recupera el módulo.

## Las capturas

Todas las capturas están puestas. Los huecos siguen tolerando ausencias: si un archivo falta, su
imagen se oculta sola sin romper la tarjeta. Nombres exactos que usa el deck:

**Cuadro de mando (lámina 9) — ✅ ya incorporadas**
`cm-valor-compania.png` · `cm-indicadores.png` · `cm-produccion.png` · `cm-producto.png` ·
`cm-precios-segmentos.png` · `cm-canal.png` · `cm-mercado.png` · `cm-ventas.png` ·
`cm-ingresos.png` · `cm-margen.png`

> Originales en `Imagenes cuadro de mando/`. El cuadro de mando de la plataforma tiene **diez
> informes**, no ocho: se comprobó contra el demo del simulador. Mismo criterio de formato que en
> decisiones — marco fijo de 198 px con `object-fit:contain` para que la rejilla no se desalinee.

**Decisiones (lámina 14) — ✅ ya incorporadas**
`dec-07-capacidad.png` (va primera) · `dec-01-prevision-ventas.png` · `dec-02-precio-segmentos.png` ·
`dec-03-producto.png` · `dec-04-promocion-marca.png` · `dec-05-promocion-punto-venta.png` ·
`dec-06-canal-logistica.png` · `dec-08-presupuesto-grabar.png`

> El orden en pantalla es el del simulador: **decisiones estratégicas primero** (son irreversibles y
> condicionan al resto) y **grabar al final**. Los nombres de archivo conservan la numeración con
> que se capturaron, que ya no coincide con el orden de la lámina.

> Los originales están en `Imagenes decisiones/`. En `assets/` se guardaron con nombres sin
> acentos ni espacios (más seguros en web) y la lámina 14 se ordenó en **ocho bloques**, uno por
> pantalla real, en rejilla de dos columnas. Todas se muestran en un **marco fijo idéntico**
> (`height:210px` + `object-fit:contain`), porque sus proporciones van de 0,86:1 a 2,53:1 e igualar
> solo el ancho las dejaba unas altas y otras chatas. Con clic se abren a resolución original.

**Portada (intro y lámina 1)**
`portada.png` — imagen alusiva a CoffeeTime. Mientras no exista se muestra el emoji ☕.

## Logo del distribuidor

`assets/logo-sdn.png` (versión blanca) aparece en tres sitios:

1. **Intro y portada**, bajo el bloque de marca.
2. **Pie de cada lámina** (2 a 13), en la franja café inferior, junto al correo de contacto.
3. **Cierre**, a tamaño completo con el correo y el WhatsApp.

Si algún día se reemplaza el archivo, mantén el logo **blanco con fondo transparente**: las tres
ubicaciones lo colocan sobre fondo café.

## Editar

Todo vive en `index.html` (HTML + CSS + JS embebidos, sin dependencias). La paleta de CoffeeTime está
al principio del `<style>`, en `:root`. El detalle de componentes y convenciones está en `CLAUDE.md`.
