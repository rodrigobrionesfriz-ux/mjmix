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

La app se usa con el teléfono en horizontal. En tablet funciona en ambas posiciones.

**Deck**
- **Cargar** (junto a cada forma de onda): muestra solo los formatos que tu teléfono puede reproducir (MP3, M4A, WAV y, según el equipo, AAC, FLAC u OGG). El BPM se calcula solo.
- **Play / Cue**: Cue en pausa marca el punto; Cue sonando vuelve a ese punto y pausa. Doble toque en Cue lleva el tema al inicio.
- **Pitch y Sync**: fader en el borde exterior; `±8` cambia el rango (8, 16, 50 %).
- **Jog**: con la pista sonando empuja o frena; en pausa busca.
- **Loops**: `↻` activa un loop del largo indicado (por defecto 4 beats) y lo vuelve a tocar para salir. `½` y `×2` cambian el largo. `In` y `Out` arman un loop manual.

**Biblioteca**
- El botón **Biblioteca** (a la derecha de las formas de onda) abre tu lista de temas.
- **Agregar carpeta** suma todos los temas compatibles de una carpeta; **Agregar temas** permite elegir archivos sueltos. En algunos teléfonos el selector de carpetas no está disponible y solo aparece Agregar temas.
- Los temas quedan guardados dentro de la app, así que siguen ahí al volver a abrirla. ✕ quita un tema de la biblioteca (el archivo original no se borra) y Vaciar los quita todos.
- Los botones **A** y **B** de cada fila cargan el tema en ese deck. El botón se pinta cuando el tema está cargado ahí. El BPM se guarda la primera vez que lo cargas.
- Si el deck está sonando, la app pregunta antes de cargar. Lo mismo pasa con el botón Cargar.

**Modos de pads**
- **Hot cue**: 8 puntos por deck. Toca para marcar o saltar; mantén presionado para borrar.
- **Pad FX**: se activan mientras mantienes el pad. Roll de ½ a 1/16 de beat (al soltar la pista sigue donde habría ido), Eco, Filtro HP, Filtro LP y Freno.
- **Salto**: fila de arriba retrocede 1, 4, 8 o 16 beats; fila de abajo avanza. Si hay loop activo, el loop se mueve con el salto.
- **Sampler**: 8 sonidos incluidos, compartidos entre ambos decks.

**Mixer**
- Gain, Agudos, Medios, Graves y Filtro por canal (Filtro a la izquierda corta agudos, a la derecha corta graves).
- **Beat FX**: elige efecto con ◀ ▶ (Eco, Reverb, Flanger, Phaser), ajusta el tiempo con − +, elige canal A, Master o B, y actívalo con On. Nivel controla la intensidad.
- **Sampler**: volumen de los sonidos del sampler.
- Doble toque en cualquier fader o perilla lo devuelve a su posición inicial.

## Notas

- En iPhone, si el interruptor de silencio está activado puede que no suene.
- Si cambias íconos o el manifest, sube el número de versión en `sw.js` (`appdj-v1` → `appdj-v2`).
