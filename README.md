# 🏡 Tablero Casa López Acosta

Un tablero tipo **Notion / Kanban** para organizar todas las actividades de la casa: tareas, responsables, proveedores, prioridades, costos y recurrencias. Hecho en **un solo archivo**, sin instalar nada, con **sincronización en tiempo real** entre todos los dispositivos de la familia.

🔗 **App en vivo:** https://ricardolopezreyero.github.io/notion_casa/

---

## ✨ Qué hace

### Tablero
- **5 columnas** en orden de flujo: `Reserva → Por hacer → Haciendo → En espera de revisión → Completada`.
- **Arrastra y suelta** las tarjetas entre columnas (con animación suave).
- **Prioriza** dentro de una columna con las flechas **▲ / ▼** (más arriba = más prioridad).
- **Clic en toda la tarjeta** para abrir su detalle y editarla.
- Las tareas **nuevas caen en _Reserva_** y aparecen hasta arriba, emergiendo con un efecto de creación.
- **Borrar** desde la tarjeta (✕) o desde el modal: la tarjeta se comprime y desaparece mientras las demás suben a su lugar.

### Cada tarea puede tener
- **Título**, **responsable**, **columna** y **nota**.
- **Prioridad** con color: 🟢 Baja · 🟠 Media · 🔴 Alta (por defecto Baja). El color se ve también en la **franja inferior** de la tarjeta.
- **Categoría** (lista fija de las áreas del hogar).
- **Proveedor** que la resuelve (con botones de WhatsApp y llamada).
- **Costo estimado**.

### ⭐ Tareas comunes
- Catálogo precargado con las responsabilidades del hogar, **agrupadas por categoría y responsable**.
- Un clic la agrega a _Reserva_.
- Muestra primero **Top 3 más usadas** y **Últimas 5 usadas**.
- **Editable y persistente**: con el botón _✏️ Editar_ puedes **renombrar, borrar y agregar** tareas comunes para dejar el catálogo con lo que de verdad usan.

### 🔁 Recurrentes
- Crea tareas que se generan solas en _Por hacer_:
  - **Cada cierto tiempo** (cada N días o N semanas) — ideal para jardín, alberca, etc.
  - **Días de la semana** (lun, mié…).
  - **Día del mes**.
- **Editables y movibles**: cambia el intervalo o mueve la "próxima vez" cuando cambie la temporada (p. ej. el jardín de cada 3 a cada 4 semanas en invierno).

### 📇 Proveedores
- Catálogo con **nombre, celular, servicio/categoría** y **prioridad** (1ª / 2ª / 3ª opción).
- Cada proveedor arma su **botón de WhatsApp** y de **llamada** automáticamente (números de México de 10 dígitos).
- Se suben, editan y bajan. Desde el selector de proveedor de una tarea puedes **agregar uno nuevo** al vuelo.

### Otros detalles
- **👥 Filtro por responsable**: ve solo las tareas de una persona.
- **Completada**: se ven las **10 más recientes** y un botón _Cargar más_ (de 50 en 50).
- **Enter** guarda la tarea (en la nota, Ctrl/⌘ + Enter).
- **Sin login**: abres el link y ya está.

---

## 🔄 Sincronización entre dispositivos

El tablero usa **Firebase Realtime Database** (proyecto `notion-casa`). Todos los dispositivos con el link ven **lo mismo en tiempo real**: si alguien mueve una tarjeta, a los demás se les actualiza sola. Además guarda una copia local (funciona aunque parpadee el internet).

El indicador de la barra muestra **🟢 Sincronizado** o **Local**.

> ⚠️ **Reglas de Firebase:** están en modo de prueba con fecha de caducidad. Para que no deje de guardar, en *Realtime Database → Reglas* deja:
> ```json
> { "rules": { ".read": true, ".write": true } }
> ```

---

## 🚀 Cómo está montado

- **Un solo archivo**: [`index.html`](index.html) — HTML + CSS + JS, **sin build ni dependencias** (solo el SDK de Firebase por CDN y la fuente Plus Jakarta Sans).
- **Estilo SuperLeads**: tipografía *Plus Jakarta Sans*, paleta navy `#001240` + verde `#56EF9F`, bordes finos y animaciones suaves.
- **Persistencia**: `localStorage` (copia local instantánea) + Firebase (nube compartida).

### Correr en local
```bash
# desde la carpeta del proyecto
python3 -m http.server 4599
# y abre http://localhost:4599
```
O simplemente abre `index.html` en el navegador (modo local).

### Publicar (GitHub Pages)
Ya está publicado desde la rama `main` (carpeta raíz). Cada `git push` actualiza la app en
`https://ricardolopezreyero.github.io/notion_casa/` en ~1 minuto.

---

## 📁 Estructura

```
notion_casa/
├── index.html   ← toda la app (tablero, modales, lógica, estilos)
├── README.md    ← este archivo
└── .nojekyll    ← para que GitHub Pages sirva todo tal cual
```

---

Hecho con cariño para la casa López Acosta. 🏡
