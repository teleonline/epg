[Read in English](README_en.md)

# Teleonline EPG - Guía de programación

Guía de programación de TV (**XMLTV** y **JSON**) generada automáticamente cada día a partir de fuentes EPG públicas. Es el repositorio de la guía de [Teleonline](https://teleonline.org); la lista de canales está en [teleonline/listas](https://github.com/teleonline/listas).

## URLs

Comprimidos (GitHub Pages, recomendado):

```
https://teleonline.github.io/epg/epg.xml.gz
```
```
https://teleonline.github.io/epg/epg.json.gz
```

Los mismos archivos, en bruto:

```
https://raw.githubusercontent.com/teleonline/epg/gh-pages/epg.xml.gz
```
```
https://raw.githubusercontent.com/teleonline/epg/gh-pages/epg.json.gz
```

Sin comprimir (Release `epg-latest`):

```
https://github.com/teleonline/epg/releases/download/epg-latest/epg.xml
```
```
https://github.com/teleonline/epg/releases/download/epg-latest/epg.json
```

Las URLs son permanentes: cada día se sobrescribe el contenido, pero la dirección no cambia.

## Cómo usar

En cualquier cliente IPTV ([Teleonline](https://teleonline.app), VLC, Kodi, Jellyfin, TVHeadend, IPTV Smarters, Tivimate), añade la URL del XML como fuente EPG remota. En VLC: Medio > Abrir ubicación de red > pegar la URL del XML.
