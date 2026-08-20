# Cómo publicar Botiquín como app instalable

Estos archivos ya están listos para ser una PWA (Progressive Web App): se puede instalar en el celular como un ícono y funciona offline. Solo falta subirlos a algún lugar con HTTPS — no funciona abriendo el `index.html` como archivo local (los navegadores bloquean la instalación y el guardado offline sin un servidor real).

## Opción más rápida: Netlify Drop (gratis, sin cuenta, 2 minutos)

1. Entrá a **https://app.netlify.com/drop**
2. Arrastrá la carpeta completa (con `index.html`, `manifest.json`, `service-worker.js` y los íconos) a la página.
3. Netlify te da al instante una URL tipo `https://algo-random.netlify.app`.
4. Abrí esa URL desde el celular (Chrome en Android o Safari en iPhone).
5. **Android/Chrome:** va a aparecer un cartel de "Agregar a pantalla de inicio" (o tocá el menú ⋮ → "Instalar app").
   **iPhone/Safari:** tocá el botón de compartir (□↑) → "Agregar a pantalla de inicio".
6. Listo — queda como un ícono más, abre en pantalla completa, y funciona sin conexión después de la primera carga.

Si más adelante querés cambiar algo, volvés a arrastrar la carpeta actualizada a la misma URL de Netlify (o generás una nueva).

## Alternativas igual de válidas
- **GitHub Pages**: si ya tenés o querés una cuenta de GitHub, subís los archivos a un repositorio y activás Pages en la configuración. URL gratis y estable, buena si vas a seguir iterando con control de versiones.
- **Vercel**: similar a Netlify, también con arrastrar y soltar o conectado a GitHub.

## Importante sobre los datos
Los datos ahora se guardan con `localStorage`, en el navegador del dispositivo donde se use. Eso significa:
- Cada dispositivo tiene sus propios datos (no se sincroniza automáticamente entre el celular de mamá y el de papá, por ejemplo).
- Si borrás los datos del navegador/app o desinstalás, se pierde el historial.
- No hay backend ni cuenta: nadie más que ese dispositivo tiene acceso a los datos.

Si en algún momento querés que la familia comparta un mismo registro entre varios dispositivos, eso ya requiere una base de datos real (backend), que es un paso más grande — avisame si llegás a ese punto.
