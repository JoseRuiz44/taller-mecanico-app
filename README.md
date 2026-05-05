# 🔧 Taller Mecánico PRO

App de gestión completa para taller mecánico como **PWA instalable en Android**.

🌐 **Demo en vivo:** [https://joseruiz44.github.io/taller-mecanico-app/](https://joseruiz44.github.io/taller-mecanico-app/)

---

## 📱 Instalar como App en Android

1. Abre Chrome en tu móvil y navega a la URL de la app.
2. Pulsa el menú de Chrome (⋮) → **"Añadir a pantalla de inicio"**.
3. Confirma la instalación — la app aparecerá como icono en tu escritorio.
4. ¡Funciona sin internet gracias al Service Worker!

---

## ✨ Funcionalidades

| Sección | Descripción |
|---|---|
| 🏠 Dashboard | Resumen con contadores y alertas de revisiones próximas |
| 👤 Clientes | Alta, edición y eliminación de clientes |
| 🧰 Productos | Gestión de aceites, filtros y arandelas |
| 🚗 Vehículos | Vehículos con productos asignados por tipo |
| 🧾 Revisiones | Control de revisiones con próximo km y alertas |

### Características técnicas
- 💾 Datos guardados en `localStorage` (no necesita servidor)
- 📤 Exportar todo a `taller_backup.json`
- 📥 Importar backup JSON (compatible con backups existentes)
- 📴 Funciona offline (Service Worker)
- 📱 Responsive y optimizado para móvil Android
- 🚫 Sin `alert()`/`confirm()` — modales y toasts propios
- 🔒 Sin dependencias externas

---

## 🗂️ Estructura de archivos

```
taller-mecanico-app/
├── index.html       # App completa (HTML + CSS + JS)
├── manifest.json    # Manifiesto PWA
├── sw.js            # Service Worker (offline)
├── README.md        # Este archivo
└── .github/
    └── workflows/
        └── pages.yml  # Deploy automático a GitHub Pages
```

---

## 📦 Formato del backup JSON

```json
{
  "clientes": [{ "nombre": "JOSEMI", "tel": "555555", "dir": "-" }],
  "productos": [{ "tipo": "Aceites", "nombre": "ACEITE 0W-30", "marca": "TOTAL", "ref": "-" }],
  "vehiculos": [{ "mat": "4068 GJG", "cliente": "SONIA", "marca": "FORD", "modelo": "FIESTA",
    "motor": "-", "aceite": "5W-30", "litros": "-", "fa": "A1247", "fai": "L343D",
    "fc": "FCS704", "fh": "-", "ar": "-" }],
  "revisiones": []
}
```

Al importar, los registros sin `id` reciben uno generado automáticamente.

---

## 🚀 Deploy en GitHub Pages

El workflow `.github/workflows/pages.yml` publica automáticamente al hacer push a `main`.

Activa GitHub Pages en: **Settings → Pages → Source: GitHub Actions**.
