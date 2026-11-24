# 🐾 UI Kit – Sistema de Control de Rescates y Adopciones Animales

Librería de componentes de interfaz (Design System) desarrollada con **HTML5 y CSS3 puro**, sin frameworks.
Constituye la base visual del sistema de gestión de rescates y adopciones.

**Asignatura:** Desarrollo de Sistemas Informáticos
**Docente:** Jorge Zambrano
**Actividad:** #5 – Unidad 3: Estilo de un documento web y diseño adaptable

---

## 📁 Estructura del proyecto

```
ui-kit-rescates/
├── index.html   → Página de demostración de todos los componentes
├── style.css    → Librería de estilos (variables + componentes)
└── README.md    → Guía de uso
```

## ▶️ Cómo verlo

Abra `index.html` en cualquier navegador. No requiere instalación.

---

## 🎨 1. Design System (variables)

Todas las variables están en `:root` dentro de `style.css`. Para cambiar la identidad visual basta con editar estos valores.

| Variable | Valor | Uso |
|---|---|---|
| `--color-primario` | `#1f6f78` | Acciones principales, encabezado |
| `--color-secundario` | `#f2a541` | Acciones de adopción, acentos |
| `--color-exito` | `#2e7d32` | Mensajes correctos, urgencia baja |
| `--color-error` | `#c62828` | Errores, acciones peligrosas, urgencia alta |
| `--color-advertencia` | `#b26a00` | Avisos, urgencia media |

También hay variables de **tipografía** (`--fuente-base`, `--texto-sm`…), **espaciado** (`--esp-1` a `--esp-12`), **radios** (`--radio-md`…) y **sombras** (`--sombra-md`…).

Se aplica la regla general `box-sizing: border-box` a todos los elementos.

---

## 🔘 2. Botones

Clase base `.btn` + una variante.

```html
<button class="btn btn--primario">Registrar rescate</button>
<button class="btn btn--secundario">Ver adopciones</button>
<button class="btn btn--peligro">Eliminar registro</button>
<button class="btn btn--contorno">Cancelar</button>
```

| Clase | Descripción |
|---|---|
| `.btn--primario` / `--secundario` / `--peligro` / `--contorno` | Variantes de color |
| `.btn--sm` / `.btn--lg` | Tamaños |
| `.btn--bloque` | Ancho completo |
| atributo `disabled` | Botón deshabilitado |

Estados: `:hover` (se eleva y oscurece), `:focus-visible` (anillo de foco), `:active` y `:disabled`.

---

## 📝 3. Formularios

```html
<div class="form-grupo">
  <label class="form-label form-label--requerido" for="nombre">Nombre</label>
  <input class="form-control" type="text" id="nombre" placeholder="Ej.: Luna" required>
</div>

<div class="form-grupo">
  <label class="form-label" for="especie">Especie</label>
  <select class="form-control" id="especie">
    <option>Perro</option>
  </select>
</div>
```

- `.form-control` sirve para `input`, `select` y `textarea`.
- Al recibir el foco (`:focus`) cambia el borde y muestra un anillo de color.
- `.form-label--requerido` agrega un asterisco rojo con `::after`.
- Los campos inválidos se marcan en rojo con `:invalid` (solo después de escribir).
- Envuelva los grupos en `.formulario` para obtener una grilla adaptable.

---

## 🗂️ 4. Tarjetas (Cards)

```html
<article class="card">
  <img class="card__imagen" src="perro.jpg" alt="Foto de Rocky">
  <div class="card__cuerpo">
    <div class="card__titulo">
      <h3>Rocky</h3>
      <span class="badge badge--alta">Alta</span>
    </div>
    <ul class="card__datos">
      <li><strong>Especie:</strong> Perro</li>
    </ul>
  </div>
  <div class="card__pie">
    <button class="btn btn--primario btn--sm">Ver ficha</button>
  </div>
</article>
```

- Sombra (`box-shadow`) y bordes redondeados (`border-radius`).
- `:hover` la eleva; `:focus-within` la resalta al navegar con teclado.
- `.card--urgente` agrega una franja roja lateral.
- Coloque varias tarjetas dentro de `.grilla` para que se acomoden solas.

---

## 🏷️ 5. Badges (urgencia y estado)

```html
<!-- Urgencia -->
<span class="badge badge--alta">Alta</span>
<span class="badge badge--media">Media</span>
<span class="badge badge--baja">Baja</span>

<!-- Estado -->
<span class="badge badge--rescatado">Rescatado</span>
<span class="badge badge--tratamiento">En tratamiento</span>
<span class="badge badge--adopcion">En adopción</span>
<span class="badge badge--adoptado">Adoptado</span>
```

Alertas en bloque: `.alerta.alerta--exito`, `.alerta--advertencia`, `.alerta--error`.

---

## ♿ Accesibilidad y diseño adaptable

- Contraste de colores adecuado y badges con texto + punto (no depende solo del color).
- Foco visible en todos los elementos interactivos y enlace "Saltar al contenido".
- Etiquetas `<label>` asociadas a cada campo y área táctil mínima de 44 px.
- Respeta `prefers-reduced-motion`.
- Grillas con `auto-fit` + media queries a 768 px y 480 px.

---

## 🌿 Flujo de trabajo Git

- `main` → versión estable
- `develop` → integración
- `feature/ui-kit` → desarrollo de este UI Kit (fusionada en `develop`)
