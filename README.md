
# Formación Desarrollo Web: Clon de navbar y media queries (HTML + CSS)

## Objetivo

- Mostrar cómo estructurar una navbar simple (clon del estilo de npm) usando HTML semántico.
- Enseñar el enfoque mobile-first y el uso de media queries para adaptar el diseño a distintos tamaños de pantalla.
- Explicar en detalle las reglas CSS relevantes (flexbox, orden en el flujo, ocultación de elementos, etc.).

## Estructura de archivos

- `index.html` — HTML principal. Contiene el header con la navegación dividida en dos secciones (`.nav-first-section` y `.nav-second-section`), una sección de demostración `.prueba` y un `footer` vacío.
- `css/style.css` — Estilos principales. Contiene: reset/base, utilidades para listas y flexbox, reglas de la navegación, estilos de botones y búsqueda, media queries y un bloque de demostración `.prueba`.
- `img/npm-logo.png` — Logo usado en la navbar (referenciado desde `index.html`).

## Resumen del HTML (puntos clave)

- Se usa `header > nav` como estructura semántica para la barra de navegación.
- La navegación está dividida en dos contenedores principales:
	- `.nav-first-section`: enlaces secundarios (Pro, Teams, Pricing, Documentation) y un icono de "heart".
	- `.nav-second-section`: logo, buscador (`.search-bar`) y botones de sesión (`.sign-buttons`).
- Los enlaces dentro de listas (`<ul>`) usan estilos flex para quedar alineados en línea.
- El buscador es un input + button; en el HTML no tiene funcionalidad JS: es visual y didáctico.

## Resumen del CSS (puntos clave y explicación didáctica)

1) Reset / base

- Se aplica `box-sizing: border-box` a todos los elementos para evitar cálculos de tamaño sorpresa.
- `body` tiene la fuente `Open Sans` (importada desde Google Fonts). Se mantienen márgenes en 0.

2) Layout de la navegación

- `.nav-ul` y `.sign-buttons` son `display: flex` para alinear los enlaces horizontalmente.
- `.nav-second-section` utiliza `display: flex` con `align-items: center; justify-content: space-between;` para distribuir logo, buscador y botones.

3) Orden visual y mobile-first

- Se usa la propiedad `order` en flexbox para controlar el orden visual de los elementos según el breakpoint. En la hoja de estilos original:
	- `.search-bar` tiene `order: 3` por defecto (en mobile aparece después en el flujo), y en `@media (min-width: 480px)` cambia a `order: 2` para situarlo más a la izquierda en pantallas más anchas.
	- `.sign-buttons` tiene `order: 2` por defecto y `order: 3` en pantallas >= 480px para situar los botones al final.

Esto es un patrón útil cuando quieres que la disposición en mobile sea diferente de la disposición en desktop sin cambiar el HTML.

4) Media queries usadas (explicación)

- `@media (min-width: 480px)`: enfoque mobile-first. Cuando la pantalla alcanza 480px o más:
	- `.search-bar` reduce su margen superior y se le asigna `width: 50%` y `order: 2`.
	- El `input` dentro del `.search-bar` recibe `width: 80%` para ocupar la mayor parte del espacio interno.
	- `.sign-buttons` cambia a `order: 3` para colocarse al final.

- `@media (max-width: 720px)`: en pantallas pequeñas (<= 720px) se aplican reglas para simplificar la UI:
	- `.heart { display: none; }` — elemento meramente decorativo, ocultado para ahorrar espacio en pantallas pequeñas.

Puntos didácticos:

- Preferir min-width (mobile-first) para añadir reglas cuando la pantalla crece. Esto facilita rendimiento y razonamiento (las reglas base se aplican a mobile por defecto).
- Usar las propiedades de flexbox (`order`, `flex-wrap`, `align-items`) para reorganizar visualmente los elementos sin tocar el HTML.
- Evitar esconder elementos críticos con `display:none` salvo que sean puramente decorativos o de poca importancia en mobile.

## Sección de demostración `.prueba`

- `.prueba` es un bloque rojo de 300x300px con un párrafo oculto que aparece en `:hover`. Es un ejemplo simple para mostrar reglas de interacción y pseudoclases.

## Buenas prácticas y observaciones

- Responsive:
	- Revisar los breakpoints para que coincidan con los dispositivos objetivos de los alumnos. En este proyecto se usan 480px y 720px como ejemplos pedagógicos.

- Código y mantenimiento:
	- Mantener el CSS organizado por secciones y con comentarios (como en el archivo `style.css`) facilita el aprendizaje.
	- Considerar variables CSS (`:root`) si se pretende escalar el proyecto (colores, tamaños, breakpoints).

## Cómo ver el proyecto

1. Abre `index.html` en un navegador moderno (Chrome, Edge, Firefox).
2. Cambia el ancho de la ventana para ver cómo actúan las media queries (prueba anchuras alrededor de 360px, 480px y 800px).
3. Inspecciona el DOM y las reglas CSS con las herramientas de desarrollo para observar `order`, `display` y `width` en distintos breakpoints.