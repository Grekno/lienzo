# Lienzo

<img src="logo.png" alt="Logo de Lienzo" width="96" align="right">

Editor de diseño gráfico que funciona **entero en el navegador**, pensado para crear piezas para redes sociales a partir de plantillas y para **generar decenas de imágenes de golpe** (modo Lote) rellenando los textos desde una tabla.

- Sin servidor, sin cuentas, sin dependencias: la app es **un único `index.html`** (más sus tipografías en `fonts/`).
- **Código abierto** bajo licencia [MIT](LICENSE).
- Tus diseños, datos y plantillas se guardan en el propio navegador (`localStorage`).
- Interfaz en **español e inglés** y **8 temas** de color (el principal usa la paleta del logo).

---

## Índice

1. [Publicar en GitHub Pages](#publicar-en-github-pages)
2. [Vista general](#vista-general)
3. [Pestaña Diseñar](#pestaña-diseñar)
4. [Pestaña Lote](#pestaña-lote)
5. [Descargas y formatos](#descargas-y-formatos)
6. [Plantillas propias y Comunidad](#plantillas-propias-y-comunidad)
7. [Idioma y temas](#idioma-y-temas)
8. [Atajos de teclado](#atajos-de-teclado)
9. [Límites](#límites)
10. [Datos y privacidad](#datos-y-privacidad)
11. [Notas técnicas](#notas-técnicas)
12. [Estructura del repositorio](#estructura-del-repositorio)
13. [Vista previa del enlace y redes sociales](#vista-previa-del-enlace-y-redes-sociales)
14. [Apoyar el proyecto](#apoyar-el-proyecto)
15. [Licencia](#licencia)
16. [Problemas frecuentes](#problemas-frecuentes)

---

## Publicar en GitHub Pages

1. Crea un repositorio nuevo en GitHub (por ejemplo `lienzo`).
2. Sube a la **raíz** del repositorio los archivos de esta carpeta: `index.html`, `README.md`, `LICENSE`, `logo.png`, `og-image.png`, `.nojekyll` y la carpeta `fonts/` completa.
3. En el repositorio ve a **Settings → Pages**.
4. En *Build and deployment* elige **Source: Deploy from a branch**, rama **`main`** y carpeta **`/ (root)`**. Guarda.
5. Espera uno o dos minutos. La app quedará en `https://TU-USUARIO.github.io/lienzo/`.

Notas:

- `.nojekyll` evita que GitHub procese el sitio con Jekyll; no hace falta tocarlo.
- Hace falta **HTTPS** (GitHub Pages ya lo da) para que todo funcione con normalidad.
- Las tipografías van **incluidas en el repositorio** (`fonts/`), así que no se pide nada a servidores externos y funciona sin conexión una vez cargada la página.
- **Antes de compartir el enlace**, sustituye `TU-USUARIO` por tu usuario de GitHub en `index.html` (ver [Vista previa del enlace](#vista-previa-del-enlace-y-redes-sociales)).
- También funciona abriendo `index.html` directamente con doble clic, aunque algunos navegadores limitan el almacenamiento local en archivos `file://`.

---

## Vista general

Arriba, la barra principal:

| Elemento | Qué hace |
|---|---|
| Logo + **Lienzo** | Marca de la app |
| **Diseñar / Lote** | Cambia entre las dos herramientas (el número junto a *Lote* son las filas de la tabla) |
| Nombre del diseño | Se usa como nombre de los archivos descargados |
| ↶ ↷ | Deshacer / Rehacer (hasta 80 pasos) |
| Tamaño de exportación | Resolución o relación de aspecto de lo que se descarga |
| **Guardar plantilla** | Guarda el diseño actual como plantilla propia |
| **Descargar** | Descarga la imagen actual |
| Desplegables **idioma** y **tema** | Español/English y tema de color |

Todo lo que haces se guarda automáticamente: si recargas la página, vuelves al mismo punto.

---

## Pestaña Diseñar

Tres zonas: panel izquierdo (plantillas y elementos), lienzo en el centro y panel de propiedades a la derecha.

### Plantillas

Incluye 10 plantillas listas para usar, agrupadas por red:

| Red | Plantillas |
|---|---|
| X (antes Twitter) | Anuncio, Cita, Cifra, Cabecera, Foto de perfil |
| Instagram | Publicación, Historia |
| YouTube | Miniatura |
| LinkedIn | Banner |

Haz clic en una para aplicarla (puedes deshacerlo desde el aviso o con Ctrl+Z). Los filtros de arriba permiten ver solo una red o **Mías** (tus plantillas guardadas). Al aplicar una plantilla se cambia el tamaño de la página y, si la plantilla trae textos enlazados a columnas, esas columnas se crean en la tabla del Lote si no existían.

### Elementos

En la pestaña **Elementos** puedes añadir:

- **Texto**: título, subtítulo, cuerpo y etiqueta.
- **Formas**: rectángulo, círculo y línea.
- **Imagen**: botón *Subir imagen* o arrastrando un archivo sobre el lienzo (se reduce a 2400 px por lado como máximo).

### Trabajar sobre el lienzo

- **Seleccionar**: clic sobre un elemento. Pasar el ratón por encima lo resalta.
- **Mover**: arrastrar. Se imanta al centro y a los bordes de la página (aparecen guías rosas).
- **Redimensionar**: arrastra los tiradores de las esquinas y los lados. Con **Mayús** en una esquina mantiene la proporción (las imágenes siempre la mantienen).
- **Girar**: tirador circular encima del elemento. Con **Mayús** gira de 15° en 15°.
- **Zoom**: botones − / + y **Ajustar** en la barra inferior.
- **Vista previa**: el desplegable de la barra inferior muestra el diseño con los datos de una fila concreta de la tabla.
- **Doble clic** sobre un texto: pasa al cuadro de edición del texto.

### Menú rápido ⋯

Al seleccionar un elemento aparece un botón con tres puntitos en su esquina. Ofrece: **Vincular con columna…** (solo textos), **Editar texto**, **Duplicar**, **Traer al frente**, **Enviar al fondo** y **Eliminar**.

### Panel de propiedades

Sin nada seleccionado muestra la **Página**:

- **Formato**: 15 tamaños predefinidos (X, Instagram, YouTube, LinkedIn, TikTok, Facebook, Pinterest, Full HD, A4…) o *Personalizado* (de 16 a 6000 px por lado).
- Casilla **Adaptar elementos al nuevo tamaño**: reescala posiciones y tipografías al cambiar de formato.
- **Fondo**: color liso o degradado (dos colores y ángulo).
- **Capas**: lista de elementos; clic para seleccionar.

Con un elemento seleccionado muestra sus propiedades:

- **Posición y tamaño**: X, Y, ancho, alto, giro y opacidad.
- **Texto**: contenido, **dato del lote** (columna vinculada), fuente (Bricolage Grotesque, Anton, DM Serif Display, DM Mono, Caveat, Instrument Sans), grosor, tamaño, alineación horizontal y vertical, color, interlínea, espaciado de letras, MAYÚSCULAS, cursiva y *Reducir para que quepa en el cuadro*.
- **Formas**: relleno, borde (color y grosor) y radio de esquina (rectángulos). *Quitar* deja la forma sin relleno.
- **Imagen**: ajuste (*Rellenar* o *Mostrar entera*) y radio de esquina.
- **Orden**: al frente, subir, bajar, al fondo.

Todos los colores se pueden elegir con el selector **o escribiendo el código HEX** (`#FF5A36`, también en formato corto `#F53`). Si el HEX es inválido, el campo se marca en rojo y no se aplica.

> **Reducir para que quepa**: cuando está activo, el texto se encoge automáticamente hasta caber en su cuadro. Es lo que hace que frases largas y cortas queden bien en el Lote sin tocar nada. Al vincular un texto con una columna se activa solo.

---

## Pestaña Lote

El Lote convierte **un diseño + una tabla** en **una imagen por cada fila**.

### Flujo de trabajo

1. En **Diseñar** prepara el diseño (por ejemplo una plantilla de X).
2. En **Lote → Datos** rellena la tabla.
3. En **Conexiones** indica qué texto del diseño debe rellenar cada columna.
4. Revisa las miniaturas de **Resultado**, elige tamaño y formato y pulsa **Descargar lote (.zip)**.

### Datos

Botones de la tabla:

| Botón | Función |
|---|---|
| **Pegar de una hoja** | Abre un cuadro donde pegar una lista (una frase por línea) o filas copiadas de Excel/Google Sheets/CSV. El selector *Pegar como* permite crear una tabla nueva (la primera fila son los encabezados) o rellenar desde una columna concreta |
| **Importar CSV** | Carga un archivo `.csv`, `.tsv` o `.txt` (detecta tabulador, `;` o `,`). La primera fila son los encabezados |
| **+ Columna / + Fila** | Añade una columna o fila vacía |
| **Limpiar tabla ▾** | Vacía toda la tabla, **solo una columna**, o repite el valor de la fila 1 hacia abajo en una columna |

Detalles útiles:

- Puedes **editar cualquier celda** y renombrar columnas escribiendo en su cabecera. Los enlaces con textos se mantienen al renombrar.
- La **×** de la cabecera elimina la columna; la **×** del final de la fila, esa fila.
- **Pegar directamente sobre una celda** con varias líneas rellena hacia abajo desde esa celda y **crea las filas (y columnas) que falten**. Cada línea es una fila; si hay tabuladores, se reparten en columnas.
- Tras pegar, un aviso indica cuántas filas se pegaron, cuántas se crearon y si se alcanzó el máximo.
- Los avisos de limpieza incluyen **Deshacer**.

### Conexiones

Para cada columna aparecen como botones todos los textos del diseño. Marca el que debe rellenar esa columna:

- Un texto solo puede tomar **una** columna.
- Los textos sin vincular se repiten igual en todas las imágenes.
- También se puede vincular desde **Diseñar** con el menú ⋯ del texto o con el campo *Dato del lote* del panel.
- **Color de fondo**: elige una columna cuyo contenido sean colores HEX (`#FF5A36`) y cada imagen tendrá su propio fondo.

### Resultado

Muestra una miniatura por fila (se dibujan según aparecen en pantalla, así que tablas largas no ralentizan). Haz clic en una para verla **ampliada** y navegar con ← → o con las flechas del teclado; desde ahí puedes descargar solo esa imagen.

---

## Descargas y formatos

### Tamaño y relación de aspecto

El desplegable de tamaño (arriba y en *Resultado*) ofrece:

- **Tamaño original** del diseño: 0,5×, 1×, 1,5×, 2×, 3×, 4× y anchos de 1080 / 1920 (Full HD) / 3840 (4K) px.
- **Otras relaciones de aspecto** (1:1, 4:5, 3:4, 2:3, 9:16, 1:2, 5:4, 4:3, 3:2, 16:9, 2:1, 21:9, 3:1, 4:1), cada una en dos tamaños (1× y 2×).

Cuando eliges una relación distinta a la del diseño aparece **Ajuste**:

- **Adaptar composición**: recoloca y reescala los elementos para la nueva forma.
- **Con márgenes**: mantiene el diseño tal cual y rellena los bordes con el color de fondo.

Se ocultan las opciones que superarían los 8192 px por lado.

### Formato de imagen

El botón **Descargar lote** tiene una flecha ▾ para elegir formato:

| Formato | Característica |
|---|---|
| **PNG** | Sin pérdida, archivos más grandes (por defecto) |
| **JPG** | Más ligero, calidad alta (92 %) |
| **WebP** | El más ligero (calidad 90 %) |

El formato elegido se aplica también a la descarga de una sola imagen. Si el navegador no soporta WebP, guarda PNG automáticamente.

### Nombres de archivo y ZIP

- Dentro del zip cada imagen se llama **`columna_número.ext`**, por ejemplo `titulo_001.png`, `titulo_002.png`… La columna usada es la primera que tenga un texto vinculado.
- Para evitar descargas enormes, el lote se divide en **zips de hasta 80 imágenes**: 200 filas generan 3 archivos (80 + 80 + 40). La numeración continúa entre zips (`titulo_081` abre el segundo).
- Nombres de zip: `nombre-del-diseño-lote.zip` si es uno solo, o `nombre-del-diseño-lote-p1.zip`, `-p2.zip`… si son varios.
- Mientras se genera puedes **cancelar**. Si una parte falla o la cancelas, aparece la barra *Faltan por descargar* con un botón por cada parte pendiente.
- El texto bajo el título de *Resultado* indica cuántos zips se descargarán antes de empezar.

Al descargar varios zips seguidos, el navegador puede preguntar si permites **descargas múltiples**: acéptalo.

---

## Plantillas propias y Comunidad

- **Guardar plantilla** (barra superior) pide nombre y categoría (X, Instagram, YouTube, LinkedIn u Otros). Se guarda en tu navegador y aparece en **Plantillas → Mis plantillas** (filtro *Mías*). La × de cada tarjeta la elimina (con opción de deshacer).
- Se guardan tamaño, fondo, textos y formas (con sus enlaces a columnas). **Las imágenes no se incluyen.**
- La pestaña **Comunidad** muestra plantillas compartidas por otras personas, con filtro por categoría. Desde ahí puedes aplicarlas o **Guardar copia** en *Mis plantillas*; las que compartiste tú tienen *Quitar de la Comunidad*.

> **Importante:** la Comunidad necesita una base de datos compartida, que solo existe cuando Lienzo se ejecuta como artefacto dentro de Claude. **En GitHub Pages la pestaña Comunidad no tiene backend**: muestra un aviso y la opción *Compartir en la Comunidad* aparece desactivada. El resto de la app, incluidas «Mis plantillas», funciona igual. Si quieres una Comunidad propia en GitHub Pages necesitas conectar un servicio externo (por ejemplo Firebase o Supabase); el código está preparado para sustituir fácilmente esa parte (`ensureComm`, `publishTpl` y `unshare` en `index.html`).

Las plantillas recibidas de la Comunidad se **validan campo a campo** antes de usarse (tipos, colores, tamaños, textos recortados), de modo que una plantilla manipulada no puede inyectar código.

---

## Idioma y temas

Los dos desplegables de la barra superior se recuerdan entre visitas.

**Idioma**: Español e English. Se traduce toda la interfaz y los textos de ejemplo de las plantillas integradas. Nunca se traduce lo que escribes tú (columnas, textos, nombres). Por defecto usa el idioma del navegador.

**Temas**:

| Tema | Estilo |
|---|---|
| **Lienzo** (por defecto) | Oscuro con la paleta del logo: grafito y naranja |
| **Clásico** | El verde original; sigue el modo claro/oscuro del sistema |
| **Claro** / **Oscuro** | Versiones fijas del tema clásico |
| **Océano** | Claro, azul |
| **Atardecer** | Claro, cálido |
| **Lavanda** | Claro, violeta |
| **Medianoche** | Oscuro, azul |

El tema solo cambia la interfaz; los diseños que exportas no se ven afectados.

---

## Atajos de teclado

| Atajo | Acción |
|---|---|
| Ctrl/⌘ + Z | Deshacer |
| Ctrl/⌘ + Mayús + Z, Ctrl/⌘ + Y | Rehacer |
| Ctrl/⌘ + D | Duplicar el elemento |
| Supr / Retroceso | Eliminar el elemento |
| Flechas | Mover 1 px (con Mayús, 10 px) |
| Esc | Deseleccionar / cerrar menús y ventanas |
| ← → | Anterior / siguiente en la vista ampliada |

(Los atajos de edición no actúan mientras escribes en un campo de texto.)

---

## Límites

| Concepto | Límite |
|---|---|
| Filas de la tabla | 500 |
| Columnas | 30 |
| Imágenes por ZIP | 80 (se generan varios zips si hay más) |
| Pasos de deshacer | 80 |
| Tamaño de página | 16 – 6000 px por lado |
| Tamaño de exportación | 8192 px por lado |
| Imágenes subidas | se reducen a 2400 px por lado |
| Plantillas guardadas | las que quepan en el almacenamiento del navegador (unos 5 MB en total con el resto de datos) |

---

## Datos y privacidad

Todo se procesa **en tu navegador**; no se envía nada a ningún servidor. Se usa `localStorage` con estas claves:

| Clave | Contenido |
|---|---|
| `lienzo-v1` | Diseño actual, imágenes usadas, tabla del lote y ajustes de exportación |
| `lienzo-prefs` | Idioma y tema |
| `lienzo-tpls-v1` | Tus plantillas guardadas |

Para empezar de cero, borra los datos del sitio desde la configuración del navegador (o ejecuta `localStorage.clear()` en la consola). Los datos son por navegador y por dirección: en otro navegador o dispositivo no aparecerán.

Lienzo **no hace ninguna petición externa**: ni tipografías de terceros, ni analítica, ni cookies. Tus imágenes y tablas nunca salen de tu navegador.

---

## Notas técnicas

- **Sin compilación**: HTML + CSS + JavaScript sin librerías. El logo va incrustado y las tipografías se sirven desde `fonts/`.
- **Motor de dibujo**: todo se renderiza en `<canvas>` 2D. La misma función dibuja el editor, las miniaturas y la exportación, así que lo que ves es lo que descargas.
- **Texto**: se ajusta por palabras con medición real (`measureText`); la opción de reducir calcula el mayor tamaño que cabe en el cuadro.
- **ZIP**: se construye a mano en el navegador (método *store*, sin compresión, con CRC32 y nombres UTF-8). Las imágenes PNG/JPG/WebP ya están comprimidas, así que comprimir otra vez no aportaría casi nada.
- **Descargas**: con `<a download>` y URLs `blob:`. Cuando se ejecuta dentro de Claude usa en su lugar la capacidad `downloads` del artefacto (con reintento si el navegador limita las descargas seguidas).
- **Idioma**: diccionario español→inglés (`EN`) y función `tr()`. Los textos del usuario se marcan para no traducirlos.
- **Compatibilidad**: navegadores modernos (Chrome, Edge, Firefox, Safari recientes). El espaciado de letras requiere `ctx.letterSpacing` (Chrome/Edge/Safari recientes; en Firefox puede ignorarse en versiones antiguas).

---

## Estructura del repositorio

```
.
├── index.html     ← la aplicación completa
├── fonts/         ← tipografías .woff2 (Bricolage Grotesque, Anton, DM Serif Display, DM Mono, Caveat, Instrument Sans)
├── og-image.png   ← imagen de vista previa al compartir el enlace (1200×630)
├── logo.png       ← logo (también va incrustado en index.html)
├── LICENSE        ← licencia MIT
├── README.md      ← este documento
└── .nojekyll      ← desactiva Jekyll en GitHub Pages
```

---

## Vista previa del enlace y redes sociales

`index.html` incluye etiquetas *Open Graph* y *Twitter Card*, de modo que al pegar el enlace en WhatsApp, Telegram, X, LinkedIn, Facebook o Discord aparece una tarjeta con el título, la descripción y `og-image.png`.

Para que funcione hay que poner tu dirección real. En `index.html` busca `TU-USUARIO` y sustitúyelo por tu usuario de GitHub (si el repositorio no se llama `lienzo`, cambia también esa parte). Aparece en cuatro sitios: `canonical`, `og:url`, `og:image` y `twitter:image`. En Linux/Mac:

```
sed -i 's/TU-USUARIO/tuusuario/g' index.html
```

Notas:

- Las redes **guardan en caché** la vista previa de cada enlace. Si cambias la imagen o el texto, usa el depurador de la plataforma (p. ej. Facebook Sharing Debugger) para refrescarla.
- Instagram no muestra tarjetas de enlace; ahí pon la dirección en la biografía. El enlace sí mostrará la tarjeta cuando se comparta por mensaje directo, WhatsApp, X, etc.
- Puedes cambiar `og-image.png` por tu propia imagen manteniendo el tamaño 1200×630.

---

## Apoyar el proyecto

Lienzo es gratuito. Si te resulta útil, puedes invitar al autor a un café en [ko-fi.com/grekno](https://ko-fi.com/grekno). El enlace aparece en la parte inferior del panel derecho (pestaña Diseñar) y al final de la pestaña Lote. Es un simple enlace: no carga ningún script de Ko-fi y la app no hace peticiones externas hasta que lo pulsas. Si publicas tu propia copia, cambia o elimina el enlace buscando `ko-fi.com/grekno` en `index.html`.

---

## Licencia

Lienzo se distribuye bajo la licencia **MIT** (ver [LICENSE](LICENSE)): puedes usarlo, copiarlo, modificarlo y redistribuirlo, también con fines comerciales, conservando el aviso de copyright. Las tipografías incluidas se distribuyen bajo la licencia SIL Open Font License 1.1 (permite uso y redistribución libres).

---

## Problemas frecuentes

**La descarga no empieza / solo baja el primer zip.** Comprueba que el navegador no haya bloqueado las descargas múltiples (icono en la barra de direcciones). Los zips pendientes se pueden bajar uno a uno desde la barra *Faltan por descargar*.

**Las tipografías se ven distintas.** Comprueba que subiste la carpeta `fonts/` completa y que se llama exactamente así (en minúsculas). Si se ven con otra letra tras actualizar, recarga con Ctrl+F5.

**Se perdió mi trabajo.** El guardado es local al navegador y a la dirección. Borrar los datos del sitio, el modo privado o cambiar de navegador lo elimina. Descarga lo importante.

**Pegué 300 líneas y no se crearon todas.** Mira el aviso tras pegar: indica el número de filas pegadas y de caracteres. Si el origen (hoja de cálculo o web) recorta el portapapeles, el recorte ya viene de ahí. El límite de la app es de 500 filas.

**La pestaña Comunidad dice que no está disponible.** Es lo esperado fuera de Claude (ver [Plantillas propias y Comunidad](#plantillas-propias-y-comunidad)).
