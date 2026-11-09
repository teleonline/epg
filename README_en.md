[Leer en español](README.md)

# Teleonline EPG - Program Guide

TV program guide (**XMLTV** and **JSON**) generated automatically every day from public EPG sources. This is the repository for the [Teleonline](https://teleonline.org) guide; the channel list lives in [teleonline/listas](https://github.com/teleonline/listas).

## URLs

Compressed (GitHub Pages, recommended):

```
https://teleonline.github.io/epg/epg.xml.gz
https://teleonline.github.io/epg/epg.json.gz
```

The same files, raw:

```
https://raw.githubusercontent.com/teleonline/epg/gh-pages/epg.xml.gz
https://raw.githubusercontent.com/teleonline/epg/gh-pages/epg.json.gz
```

Uncompressed (Release `epg-latest`):

```
https://github.com/teleonline/epg/releases/download/epg-latest/epg.xml
https://github.com/teleonline/epg/releases/download/epg-latest/epg.json
```

The URLs are permanent: the content is overwritten every day, but the address does not change.

## How to use

In any IPTV client ([Teleonline](https://teleonline.app), VLC, Kodi, Jellyfin, TVHeadend, IPTV Smarters, Tivimate), add the XML URL as a remote EPG source. In VLC: Media > Open Network Stream > paste the XML URL.
