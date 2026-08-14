# Analizador de transferencias Almacén → Piso de Venta

App offline (un solo HTML) empaquetada como APK Android con Capacitor,
compilada en la nube con GitHub Actions (no hace falta PC).

## Cómo subirlo a GitHub (desde el celular)

1. Entra a github.com, crea un repositorio nuevo, vacío (sin README), por
   ejemplo `analizador-transferencias`.
2. Sube TODOS los archivos y carpetas de este paquete manteniendo la misma
   estructura de carpetas (`www/`, `resources/`, `.github/workflows/`,
   `package.json`, `capacitor.config.json`). Desde la web de GitHub puedes
   arrastrar/seleccionar varios archivos a la vez con "Add file → Upload
   files", pero ojo: hay que subir las carpetas respetando las rutas (si el
   navegador del celular no te deja arrastrar carpetas completas, puedes
   subir con la app de GitHub, o crear cada carpeta manualmente con
   "Add file → Create new file" escribiendo la ruta completa, ej:
   `www/index.html`).

## Cómo compilar el APK

1. En el repositorio, ve a la pestaña **Actions**.
2. Verás el workflow "Compilar APK". Si no arrancó solo, entra y toca
   **"Run workflow"** (botón verde) → Run workflow.
3. Espera unos minutos (verás una bolita amarilla girando, luego un check
   verde ✅).
4. Toca la ejecución terminada → abajo, en **"Artifacts"**, vas a ver
   `analizador-transferencias-apk`. Descárgalo (es un .zip con el .apk
   adentro).
5. Descomprime y ya tienes `app-debug.apk` — instálalo en tu Android
   (puede que tengas que permitir "orígenes desconocidos" la primera vez).

## Notas

- El ícono que usa la app está en `resources/icon.png` (el clipboard con el
  engranaje que me mandaste). Si en algún momento quieres cambiarlo, solo
  reemplaza ese archivo (ideal 1024×1024) y vuelve a correr el workflow.
- El APK sale SIN firmar (debug) — sirve perfecto para instalar en tu
  teléfono y probarlo, pero si algún día quieres subirlo a la Play Store
  vas a necesitar firmarlo con una key propia (dímelo si llegas a esa
  parte y lo vemos).
- La app es 100% offline: no pide internet ni permisos raros, solo
  almacenamiento para poder leer los Excel que elijas y guardar el
  archivo que exporta.
