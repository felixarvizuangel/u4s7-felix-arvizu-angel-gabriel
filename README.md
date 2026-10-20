# U4S7 — Félix Arvizu Ángel Gabriel

**Grupo:** DSM 4-1 · **Matrícula:** 25311014

## Demo en vivo (producción)
https://u4s7-felix-arvizu-angel-gabriel.onrender.com

## Semana 7 — Pulido funcional y UX

### Lo nuevo
- **Paginación:** el listado de servicios muestra 5 por página, con «← Anterior», «Siguiente →» y «Página X de Y».
- **Búsqueda por título:** buscador con `?q=...` que no distingue mayúsculas, con opción «Quitar búsqueda».
- **Estado vacío:** muestra un mensaje distinto si todavía no hay servicios o si la búsqueda no encontró nada.
- **Búsqueda + paginación juntas:** al cambiar de página no se pierde lo que se buscó.
- **Responsivo:** en celular la tabla se desliza de lado sin romper la página.
- **Accesibilidad:** `aria-label` en el buscador y en la barra de paginación.

### Archivos modificados
- `core/views.py` — vista `servicios` con `Paginator` y filtro `titulo__icontains`
- `core/templates/core/servicios.html` — buscador, estado vacío y controles de página

### Hallazgos de la UI review
1. Los enlaces «Editar» y «Eliminar» eran muy pequeños para tocarlos en celular (menos de 44px de alto); se les agregó relleno (`py-2`).
2. El texto gris del estado vacío y de «Página X de Y» (`text-slate-500`) se veía claro; se oscureció a `text-slate-600`.
3. Con la tecla Tab no siempre se notaba el foco en los enlaces; se agregó `focus:outline` visible.
4. A ~375px la tabla ya no rompe la página gracias a `overflow-x-auto`.