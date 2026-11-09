# Teleonline EPG - Guía de programación

Guía de programación de TV (**XMLTV** y **JSON**) generada automáticamente cada día a partir de fuentes EPG públicas. Es el repositorio de la guía de [Teleonline](https://teleonline.org); la lista de canales está en [teleonline/listas](https://github.com/teleonline/listas).

## URLs

Comprimidos (GitHub Pages, recomendado):

```
https://teleonline.github.io/epg/epg.xml.gz
https://teleonline.github.io/epg/epg.json.gz
```

Los mismos archivos, en bruto:

```
https://raw.githubusercontent.com/teleonline/epg/gh-pages/epg.xml.gz
https://raw.githubusercontent.com/teleonline/epg/gh-pages/epg.json.gz
```

Sin comprimir (Release `epg-latest`):

```
https://github.com/teleonline/epg/releases/download/epg-latest/epg.xml
https://github.com/teleonline/epg/releases/download/epg-latest/epg.json
```

Las URLs son permanentes: cada día se sobrescribe el contenido, pero la dirección no cambia.

## Cómo usar

En cualquier cliente IPTV ([Teleonline](https://teleonline.app), VLC, Kodi, Jellyfin, TVHeadend, IPTV Smarters, Tivimate), añade la URL del XML como fuente EPG remota. En VLC: Medio > Abrir ubicación de red > pegar la URL del XML.

Los IDs del EPG son los originales de las fuentes. Para cruzarlos con tu propia lista de canales, empareja por nombre.

## Cómo funciona

1. Se descargan las fuentes de `epg/sources.txt`.
2. Se filtran los programas por ventana temporal (`epg/settings.txt`).
3. Se excluyen los canales de `epg/exclusions.txt` y se asigna país (`epg/countries.txt`).
4. Se generan `epg.xml`, `epg.json` y sus `.gz`.
5. La guía se publica siempre. Si el número de canales baja más de un 15 % respecto a la anterior, el workflow deja un aviso visible en su resumen, pero no bloquea la publicación.

Los archivos generados **no se guardan en `main`**: los `.gz` se publican cada día en la rama `gh-pages` con un único commit que sustituye al anterior (el historial no crece) y los sin comprimir en el Release `epg-latest`.

## Configuración (carpeta `epg/`)

| Archivo | Qué hace |
|---|---|
| `sources.txt` | URLs de las fuentes EPG, una por línea. La cabecera `# --- España ---` fija el país por defecto de las que van debajo |
| `settings.txt` | Días de programación pasada y futura |
| `exclusions.txt` | Patrones de IDs a excluir |
| `countries.txt` | Excepciones de país: `id del canal = país` |

## Generación automática

El workflow `.github/workflows/update-epg-guide.yml` se ejecuta cada día a las 04:00 UTC y también a mano desde la pestaña *Actions*. Para ejecutarlo en local: `php scripts/build-epg-guide.php`.
