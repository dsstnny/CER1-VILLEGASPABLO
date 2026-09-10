# CER1 — Centro Cultural Puerto Abierto

Certamen N°1 — Front End
**EIN082B Taller de Lenguaje de Programación** — Ingeniería en Informática
Estudiante: Pablo Villegas
Profesora: Pamela Gatica Caballero

Sitio web del **Centro Cultural Puerto Abierto**, una organización ficticia ubicada
en el Barrio Puerto de Valparaíso. El sitio difunde la programación de actividades
y permite inscribirse en ellas.

## Cómo ver el sitio

Abrir `index.html` directamente en el navegador. No requiere servidor ni
instalación: es un sitio estático de HTML, CSS y Bootstrap.

## Estructura del proyecto

```
CER1-VILLEGASPABLO/
├── index.html          Página principal
├── cartelera.html      Cartelera de actividades (6 actividades)
├── inscripcion.html    Formulario de inscripción
├── css/
│   ├── bootstrap.css   Framework CSS (Bootstrap 5.3.8, sin modificar)
│   └── estilos.css     Hoja de estilos propia
└── js/
    └── bootstrap.bundle.min.js   JavaScript de Bootstrap (menú colapsable)
```

## Tecnologías

| Tecnología | Uso |
|---|---|
| HTML5 | Estructura y contenido, con elementos semánticos |
| Bootstrap 5.3.8 | Framework CSS: grilla, navbar, cards, badges, formularios |
| CSS propio | Identidad visual, paleta de colores y ajustes responsivos |

Bootstrap se carga desde archivos **locales** y no desde un CDN, para que el
sitio funcione completo aunque no haya conexión a internet.

## Páginas

### 1. `index.html` — Página principal
- Identificación del centro cultural en la barra de navegación y el pie de página.
- Sección de bienvenida destacada con imagen de fondo y llamada a la acción.
- Descripción de la organización ("Quiénes somos").
- Selección de 3 actividades destacadas.
- Segunda llamada a la acción hacia la cartelera.
- Información de contacto y ubicación, con los horarios de atención en una lista.

### 2. `cartelera.html` — Cartelera de actividades
- 6 actividades presentadas con el sistema de grilla de Bootstrap.
- Cada actividad incluye imagen, nombre, categoría, fecha y descripción breve.
- Distribución responsiva: 1 columna en celular, 2 en tablet, 3 en escritorio.

### 3. `inscripcion.html` — Inscripción
Formulario con los controles apropiados para cada tipo de dato:

| Campo | Control | Obligatorio |
|---|---|---|
| Nombre completo | `input type="text"` | Sí |
| Correo electrónico | `input type="email"` | Sí |
| Teléfono | `input type="tel"` | Sí |
| Edad | `input type="number"` con `min`/`max` | Sí |
| Actividad de interés | `select` con las 6 actividades | Sí |
| Comentarios adicionales | `textarea` | No |
| Aceptación de condiciones | `input type="checkbox"` | Sí |

Los campos están agrupados en tres `fieldset` con su `legend`: datos de la
persona, actividad de interés y condiciones de participación.

La obligatoriedad se implementa con el atributo `required` de HTML, sin JavaScript.

## Paleta de colores

Definida como variables CSS en `:root` dentro de `css/estilos.css`:

| Variable | Color | Uso |
|---|---|---|
| `--azul-puerto` | `#10333f` | Barra de navegación, pie de página, títulos |
| `--azul-medio` | `#1d6076` | Enlaces y detalles |
| `--terracota` | `#b45034` | Botones y badges, con texto blanco encima |
| `--terracota-oscuro` | `#9e4426` | Estado `hover` de los botones |
| `--terracota-claro` | `#e08a6a` | Acento sobre fondos oscuros (barra de navegación) |
| `--arena` | `#f5f0e8` | Fondo general |
| `--gris-texto` | `#33393d` | Color del texto |

## Responsividad

- `<meta name="viewport">` en las tres páginas.
- Grilla de Bootstrap con clases por breakpoint (`col-md-*`, `row-cols-lg-3`).
- Menú de navegación colapsable (`navbar-expand-lg`) bajo los 992 px.
- Imágenes con `img-fluid` y `object-fit: cover` para que no se deformen.
- Media queries propias en `estilos.css` para ajustar espaciados en pantallas
  menores a 768 px y 576 px.

## Accesibilidad

- `lang="es"` en el elemento `<html>`.
- Todas las imágenes tienen atributo `alt` descriptivo.
- Cada control del formulario tiene su `<label>` asociado por `for`/`id`.
- Atributos ARIA en el menú (`aria-current`, `aria-expanded`, `aria-label`) y en
  los textos de ayuda del formulario (`aria-describedby`).
- Jerarquía de encabezados sin saltos: un solo `<h1>` por página, luego `<h2>` y `<h3>`.

## Créditos de imágenes

Fotografías de [Unsplash](https://unsplash.com), de uso libre.
