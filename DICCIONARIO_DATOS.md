# Diccionario de datos

## `songs`
| Campo | Tipo | Uso |
|---|---|---|
| `id` | INTEGER PK | ID de MediaStore / canción |
| `title` | TEXT | Título |
| `artist` | TEXT | Artista |
| `uri` | TEXT | URI local del audio |
| `duration_ms` | INTEGER | Duración en milisegundos |
| `album_id` | INTEGER | ID de álbum para carátula |
| `date_added` | INTEGER | Fecha de alta si se conoce |
| `last_seen_at` | TEXT | Última detección en biblioteca |

## `playlists`
| Campo | Tipo | Uso |
|---|---|---|
| `id` | INTEGER PK | ID interno |
| `name` | TEXT UNIQUE | Nombre de la lista |
| `created_at` | TEXT | Fecha de creación |
| `updated_at` | TEXT | Última actualización |

## `playlist_songs`
| Campo | Tipo | Uso |
|---|---|---|
| `playlist_id` | INTEGER FK | Lista a la que pertenece |
| `song_id` | INTEGER FK | Canción añadida |
| `position` | INTEGER | Orden dentro de la lista |

## `settings`
| Campo | Tipo | Uso |
|---|---|---|
| `key` | TEXT PK | Nombre de preferencia |
| `value` | TEXT | Valor guardado como texto |
