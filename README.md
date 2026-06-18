# 🏡 Tablero Casa López Acosta

Tablero tipo Notion (Kanban) para las actividades de la casa. Estilo SuperLeads.
Un solo archivo, sin login, sin instalar nada.

**Página publicada:** https://ricardolopezreyero.github.io/notion_casa/

## Columnas
`Reserva` → `Por hacer` → `Haciendo` → `En espera de revisión` → `Completada`

Las tarjetas se arrastran entre columnas.

## Qué puede hacer
- **➕ Nueva tarea** — escribe cualquier cosa (ej. "arreglar la llave de la puerta"), elige responsable y cae en *Por hacer*.
- **⭐ Tarea común** — catálogo con todas las responsabilidades del hogar; un clic la agrega.
- **🔁 Recurrentes** — diaria, semanal (por día) o mensual (por fecha). Cada vez que toca, se crea **una tarea nueva** en *Por hacer* automáticamente.
- **⬇︎ / ⬆︎** — exportar / importar respaldo en JSON.

## Sincronización entre dispositivos (Firebase)
El tablero funciona en **modo local** de inmediato (se guarda en cada computadora).
Para que Ricardo y Ana vean **lo mismo en tiempo real**, hay que pegar la config de un
proyecto Firebase gratis en `index.html` (bloque `FIREBASE_CONFIG`). Pasos en la conversación.

---
Hecho con cariño · estilo SuperLeads.
