# 🏆 Polla Mundial FIFA 2026 — Brothers (Versión 2)

Versión completamente reescrita, mucho más simple y robusta. Verificada con pruebas automáticas antes de entregarla.

## Qué cambió respecto a la versión anterior

- **Un solo archivo `app.js`** con todo el código — antes había 4 archivos separados con imports que se rompían fácilmente.
- **Firebase vía REST directo** (`fetch`) en lugar del SDK con listeners — esto eliminó el bug de timing que causaba que algunos participantes no aparecieran en el ranking.
- **Todas las keys de Firebase usan el prefijo `p`** (ej. `p1`, `p2`) para que Firebase nunca las convierta automáticamente en arrays (esto fue la causa raíz del bug con "Ali").
- **Probado antes de entregar**: la lógica de puntuación fue verificada con un script de pruebas que confirma 14 puntos para Ali con los datos del Excel.

## Instrucciones de despliegue

### 1. Sube TODO a un repositorio nuevo en GitHub

Para evitar cualquier confusión con repos anteriores:

1. Ve a `github.com/new`
2. Nombre: `polla-2026` (o el que prefieras, simple y sin guiones raros)
3. Público → Create repository
4. **Importante**: arrastra estas 3 cosas exactamente:
   - El archivo `index.html`
   - El archivo `app.js`
   - La carpeta `css` (completa)
   - La carpeta `pages` (completa)
5. Commit changes

### 2. Verifica la estructura

Después de subir, tu repo debe verse exactamente así en la raíz:
```
app.js
index.html
css/
  └── style.css
pages/
  ├── admin.html
  ├── eliminatorias.html
  ├── grupos.html
  ├── ranking.html
  └── todos.html
```

Si ves los archivos sueltos sin las carpetas `css/` y `pages/`, algo salió mal en la subida — bórralos y vuelve a intentar arrastrando las carpetas completas, no archivo por archivo.

### 3. Activa GitHub Pages

Settings → Pages → Source: Deploy from a branch → Branch: `main` / `/(root)` → Save

### 4. Carga los datos iniciales

1. Abre tu sitio → selecciona cualquier nombre → Entrar
2. Ve a 🔧 Admin → PIN `2026`
3. Pestaña "🌱 Datos Iniciales" → clic en "Cargar datos del Excel"
4. Ve a 🏆 Ranking — Ali debe aparecer con 14 pts, Vlasho con 14 pts, Osmar con 12 pts

### 5. Comparte el link

```
https://TU_USUARIO.github.io/polla-2026/
```

## Las credenciales de Firebase ya están configuradas

El archivo `app.js` ya tiene tus credenciales de Firebase (`polla-mundial-2026-4f9b1`) cargadas — no necesitas tocar nada ahí, a menos que quieras usar un proyecto Firebase diferente.

## Si algo no funciona

Abre la consola del navegador (F12) en la página que falla y revisa si hay errores en rojo. Como ahora todo vive en un solo `app.js`, si algo se rompe es mucho más fácil encontrarlo — solo hay un archivo de lógica que revisar.
