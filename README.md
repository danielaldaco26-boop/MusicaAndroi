# 🔥Musica🔥 — Documentos y base de datos

Este paquete se basa en el archivo Kotlin `ai_studio_code (4).kt` proporcionado.

## Qué contiene el proyecto fuente
- Reproductor Android con Jetpack Compose y Media3.
- Lee archivos de música locales mediante `MediaStore`.
- Búsqueda por título o artista.
- Controles de reproducción, anterior/siguiente, aleatorio y repetición.
- Carátulas de álbum desde el almacenamiento multimedia.
- Listas de reproducción guardadas actualmente en `SharedPreferences` como JSON.

## Base de datos incluida
`musica.db` es una base de datos SQLite inicial con tablas para:
- `songs`: metadatos de canciones locales.
- `playlists`: listas de reproducción.
- `playlist_songs`: relación ordenada entre listas y canciones.
- `settings`: preferencias locales del reproductor.

La base de datos se entrega vacía porque las canciones reales se descubren en el teléfono con `MediaStore`. El esquema está preparado para guardar metadatos y listas si posteriormente se integra SQLite/Room en la aplicación.

## Importante
La aplicación Kotlin suministrada todavía no utiliza esta base SQLite. En el código actual, las listas se guardan en `SharedPreferences` (`music_playlists`) y las canciones se consultan desde `MediaStore`. Para que `musica.db` se use dentro de la APK, hay que integrar Room/SQLite y migrar la lógica de listas.

## Esquema
- `songs.id`: identificador local de la canción.
- `songs.uri`: URI de contenido en el dispositivo; puede cambiar si el archivo se mueve o elimina.
- `playlists.id`: identificador interno de la lista.
- `playlist_songs`: canciones y posición dentro de cada lista.
