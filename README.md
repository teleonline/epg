[Read in English](README_en.md)

# Teleonline EPG - Guía de programación

La guía de programación de TV de [Teleonline](https://teleonline.org), gratuita y actualizada cada día. Añádela a tu reproductor y verás qué están emitiendo los canales ahora mismo y qué viene después.

La lista de canales está en [teleonline/listas](https://github.com/teleonline/listas).

## Para tu reproductor (XML)

Es el archivo que necesita tu reproductor para mostrar la programación: [Teleonline](https://teleonline.app), VLC, Kodi, Jellyfin, TVHeadend, IPTV Smarters, Tivimate...

Copia esta dirección y pégala donde tu aplicación pida la **guía**, **EPG** o **XMLTV**:

```
https://teleonline.github.io/epg/epg.xml.gz
```

Si tu reproductor no acepta archivos `.gz`, usa esta versión sin comprimir:

```
https://github.com/teleonline/epg/releases/download/epg-latest/epg.xml
```

## Para programadores y aplicaciones (JSON)

Es la misma guía en un formato más cómodo para quien crea webs o aplicaciones. Si solo quieres ver la programación en tu reproductor, **no lo necesitas**.

```
https://teleonline.github.io/epg/epg.json.gz
```

Sin comprimir:

```
https://github.com/teleonline/epg/releases/download/epg-latest/epg.json
```

Las direcciones no cambian nunca: lo que se actualiza cada día es el contenido.
