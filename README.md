# Calculadora SOH — Baterías de Vehículos

## Archivos
- `index.html` — La aplicación web (sube a GitHub Pages)
- `manifest.json` — Permite instalarla como app en el teléfono
- `Codigo.gs` — Backend en Google Apps Script (guarda datos en Sheets)

---

## Paso 1 — Configurar Google Apps Script (cuenta institucional)

1. Ve a [script.google.com](https://script.google.com) con tu cuenta **mop.gob.sv**
2. **Nuevo proyecto** → nómbralo `Calculadora SOH API`
3. Borra el contenido de `Codigo.gs` y pega el contenido del archivo `Codigo.gs`
4. Guarda con **Ctrl+S**
5. Clic en **"Implementar"** → **"Nueva implementación"**
   - Tipo: **Aplicación web**
   - Ejecutar como: **Yo**
   - Quién tiene acceso: **Cualquier persona**
6. Clic en **"Implementar"** → acepta permisos → **copia la URL** que termina en `/exec`

---

## Paso 2 — Pegar la URL de la API en index.html

Abre `index.html` y busca esta línea (cerca del inicio del bloque `<script>`):

```javascript
var GAS_API_URL = 'PEGA_AQUI_TU_URL_DE_APPS_SCRIPT';
```

Reemplaza `PEGA_AQUI_TU_URL_DE_APPS_SCRIPT` con la URL copiada en el paso anterior.

Ejemplo:
```javascript
var GAS_API_URL = 'https://script.google.com/macros/s/AKfycb.../exec';
```

---

## Paso 3 — Subir a GitHub Pages

1. Crea cuenta en [github.com](https://github.com) si no tienes
2. Crea un **repositorio nuevo** → nómbralo `calculadora-soh` → **público** → clic en "Create repository"
3. Sube los 3 archivos: `index.html`, `manifest.json` *(puedes arrastrarlos o usar "Add file → Upload files")*
4. Ve a **Settings** → **Pages** (menú izquierdo)
5. En "Source" selecciona **"Deploy from a branch"** → Branch: **main** → carpeta: **/ (root)** → **Save**
6. Espera 1-2 minutos → GitHub te dará una URL tipo:
   `https://TU_USUARIO.github.io/calculadora-soh/`

Esa URL funciona en cualquier dispositivo, sin restricciones institucionales.

---

## Paso 4 — Instalar como app en el teléfono (opcional)

### Android (Chrome):
1. Abre la URL en Chrome
2. Toca el menú (⋮) → **"Añadir a pantalla de inicio"**
3. La app aparece como ícono en tu pantalla, sin barra del navegador

### iPhone (Safari):
1. Abre la URL en Safari
2. Toca el botón de compartir (⬆) → **"Añadir a pantalla de inicio"**

---

## Notas
- Los datos siempre se guardan en Google Sheets en tu cuenta institucional
- Si necesitas cambiar la URL de la API (por ejemplo al re-publicar el script), solo edita la línea `GAS_API_URL` en `index.html` y sube el archivo actualizado a GitHub
