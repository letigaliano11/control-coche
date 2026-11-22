# Anotaciones sobre mi coche

Aplicación web (PWA) de una sola página para llevar anotaciones sobre tu coche, incluido guardar dónde has aparcado mediante GPS. Funciona directamente desde `index.html`, sin necesidad de compilar nada.

## Archivos

- `index.html`: la aplicación completa (HTML, CSS y JavaScript).
- `manifest.json`: datos de instalación como app (nombre, iconos, atajos).
- `icon-512.png` (y demás iconos): iconos de la app y pantalla de bienvenida.

## Cómo cambiar el nombre de la app

El nombre aparece en varios sitios. Para cambiarlo del todo, edita estos puntos:

### 1. Nombre visible dentro de la app (`index.html`)

Busca la cabecera (`<header>`) y cambia el texto de la línea con `class="sub"`:

```html
<div><h1>LDL</h1><div class="sub">Anotaciones sobre mi coche</div></div>
```

- `<h1>` es el nombre corto que se ve en grande.
- `<div class="sub">` es el nombre completo que se ve debajo.

### 2. Nombre corto (`index.html`)

La sigla **LDL** (de la versión original) se repite en cuatro sitios. Si quieres cambiarla, sustitúyela en todos a la vez:

| Lugar | Qué es |
|---|---|
| `<title>LDL</title>` | Título de la pestaña del navegador |
| `<meta name="apple-mobile-web-app-title" content="LDL">` | Nombre bajo el icono en iPhone/iPad |
| `<img src="icon-512.png" alt="LDL">` | Texto alternativo de la pantalla de bienvenida |
| `<h1>LDL</h1>` | Título grande en la cabecera |

Con un buscar y reemplazar de `LDL` por tu nombre corto basta (ojo: no toques `ldl_parking`, ver el punto 4).

### 3. Nombre al instalar la app (`manifest.json`)

Cambia los campos `name` y `short_name`:

```json
{
  "name": "Anotaciones sobre mi coche",
  "short_name": "Mi coche"
}
```

- `name`: nombre completo, aparece en la pantalla de instalación.
- `short_name`: nombre que aparece bajo el icono en la pantalla de inicio (mejor que sea corto, unos 12 caracteres).

Si ya tenías la app instalada en el móvil, desinstálala y vuelve a instalarla para que se actualice el nombre.

### 4. Datos guardados (opcional, no recomendado)

La app guarda la ubicación del aparcamiento en el navegador con la clave `ldl_parking` (constante `PK` en el JavaScript). **No hace falta cambiarla** al renombrar la app. Si la cambias, se perderá cualquier ubicación guardada previamente.

## Créditos

Diseño original PSG. Diseño actualizado Leticia SF Galiano.
