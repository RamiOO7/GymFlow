# 🏋️ GymFlow

App web para registrar tus entrenos de gimnasio: rutina por días, series con kg y repeticiones, progreso e historial. Funciona en móvil y PC, **se puede instalar como app** (PWA) y funciona sin conexión.

## Características

- **3 días de fuerza:** Empuje, Tirón y Pierna (4 series · 10-12 reps · 1 min de descanso).
- **Foto de cada ejercicio** para aclarar cómo se hace.
- **Añade tus propios ejercicios** a cualquier día.
- **Progreso:** entrenos totales, volumen total, mejor sesión y gráfica.
- **Historial** de entrenos guardado en tu dispositivo (`localStorage`).
- **Instalable y offline** gracias al `manifest` y al `service worker`.

## Estructura

```
gymflow/
├── index.html            # La app completa (HTML + CSS + JS)
├── manifest.webmanifest  # Datos de instalación (nombre, iconos, colores)
├── sw.js                 # Service worker (caché offline)
├── icons/                # Iconos 192, 512 y apple-touch
├── LICENSE               # MIT
└── README.md
```

## Probar en local

La instalación y el modo offline necesitan `http://localhost` o `https`, no vale abrir el archivo directamente.

```bash
cd gymflow
python3 -m http.server 8080
```

Abre <http://localhost:8080>.

## Publicarla (elige una)

Todas son gratis y dan HTTPS, que es obligatorio para poder instalarla.

### Opción A: Netlify Drop (la más rápida)
1. Entra en <https://app.netlify.com/drop>.
2. Arrastra la carpeta `gymflow` entera.
3. Te da un enlace `https://…netlify.app`. Puedes cambiarle el nombre en *Site settings*.

### Opción B: GitHub Pages
1. Crea un repositorio en GitHub y sube todos los archivos a la raíz.
2. Ve a **Settings → Pages**.
3. En *Source* elige **Deploy from a branch**, rama `main` y carpeta `/ (root)`.
4. En un par de minutos estará en `https://TU-USUARIO.github.io/NOMBRE-REPO/`.

### Opción C: Vercel
1. Sube el proyecto a GitHub.
2. En <https://vercel.com/new> importa el repositorio.
3. Framework: **Other**. Pulsa *Deploy*.

## Instalarla en el móvil o PC

| Dispositivo | Cómo |
|---|---|
| **iPhone / iPad** (Safari) | Botón Compartir → **Añadir a pantalla de inicio** |
| **Android** (Chrome) | Menú ⋮ → **Instalar aplicación** |
| **PC** (Chrome / Edge) | Icono de instalar en la barra de direcciones |

## Personalizar

- **Rutina:** edita el objeto `R` en `index.html` (nombre del ejercicio + clave de imagen).
- **Colores:** variables CSS al inicio de `index.html` (`--ac`, `--ac2`, `--bg`…).
- **Nueva versión:** si cambias archivos, sube el número de `C` en `sw.js` (`gymflow-v2`…) para que se actualice la caché.

## Nota sobre los datos

Todo se guarda en el navegador del dispositivo. Si borras los datos del sitio o cambias de móvil, se pierde el historial.

## Licencia

MIT © 2026 RamiOO7
