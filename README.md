# App DJ

PWA de mezcla con dos decks, mixer de 3 bandas y crossfader. Funciona en el navegador del celular y se instala como app.

## Publicar en GitHub Pages

1. Crea un repositorio nuevo (por ejemplo `app-dj`) y sube todo el contenido de esta carpeta a la raíz.
2. Ve a **Settings → Pages**, en *Source* elige la rama `main` y la carpeta `/ (root)`. Guarda.
3. En uno o dos minutos queda publicada en `https://TU-USUARIO.github.io/app-dj/`.
4. Ábrela en el celular:
   - Android (Chrome): menú ⋮ → *Instalar app*.
   - iPhone (Safari): botón compartir → *Agregar a pantalla de inicio*.

## Probar en el computador

```bash
python3 -m http.server 8000
```
y abre `http://localhost:8000`. El service worker necesita `localhost` o HTTPS.

## Controles

- **Cargar**: elige un MP3, WAV o M4A del teléfono. El BPM se calcula solo.
- **Play / Cue**: Cue en pausa marca el punto; Cue sonando vuelve a ese punto y pausa.
- **Hot cues 1 a 4**: toca uno vacío para marcarlo, toca uno marcado para saltar. Mantén presionado para borrarlo.
- **Sync**: iguala el tempo con el otro deck.
- **Pitch**: arrastra el fader; `±8` cambia el rango (8, 16, 50 %).
- **Jog**: con la pista sonando empuja o frena; en pausa busca.
- **Forma de onda**: arrástrala para moverte. La barra delgada de abajo salta a cualquier punto.
- Doble toque en cualquier fader o perilla lo devuelve a su posición inicial.

## Notas

- En iPhone, si el interruptor de silencio está activado puede que no suene.
- Si cambias íconos o el manifest, sube el número de versión en `sw.js` (`appdj-v1` → `appdj-v2`).
