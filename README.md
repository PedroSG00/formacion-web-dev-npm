# formacion-web-dev-npm

Este repositorio contiene un clon sencillo para formación sobre HTML, CSS y, en concreto, media queries.

Qué he cambiado (sin alterar contenido funcional):

- He reordenado el HTML (`index.html`) para mejorar su claridad y añadí comentarios didácticos en español explicando cada bloque (head, nav, main, footer).
- He reorganizado el CSS (`css/style.css`) en secciones: import de fuentes, reset/base, navegación, utilidades, componentes y media queries. También añadí comentarios explicativos sobre por qué y cómo funcionan las media queries.

Objetivos didácticos:

- Mostrar una estructura HTML limpia y semántica.
- Enseñar cómo agrupar y comentar CSS para facilitar el aprendizaje.
- Explicar el uso de media queries con ejemplos concretos (orden de elementos, ocultar elementos en pantallas pequeñas, etc.).

Cómo probar localmente:

1. Abre `index.html` en tu navegador (doble clic o arrastrar al navegador).
2. Para un test más realista, puedes servir el directorio con un servidor estático. Con PowerShell (Windows) usa:

```pwsh
# Desde la raíz del proyecto
python -m http.server 8000
```

Luego abre http://localhost:8000 en tu navegador.

Notas y recomendaciones:

- En `index.html` mantuve los enlaces con `target="_blank"` y `rel="noopener noreferrer"` tal como estaban. En producción revisa si realmente necesitas abrir en nueva pestaña.
- El CSS está comentado con explicaciones: revisa la sección "Media queries" en `css/style.css` para entender cómo y por qué cambian el orden de los elementos.
- Siguientes pasos sugeridos: añadir más ejemplos de media queries (por ejemplo, breakpoints 320px, 768px, 1024px), y ejercicios para practicar (hacer que el search ocupe 100% en mobile, cambiar a un menú hamburguesa, etc.).

Si quieres, puedo: ordenar más archivos, añadir ejemplos interactivos o preparar ejercicios y soluciones para practicar media queries.