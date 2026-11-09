[Leer en español](README.md)

# Teleonline EPG - Program Guide

The [Teleonline](https://teleonline.org) TV program guide, free and updated every day. Add it to your player and you will see what the channels are showing right now and what comes next.

The channel list is in [teleonline/listas](https://github.com/teleonline/listas).

## For your player (XML)

This is the file your player needs to show the schedule: [Teleonline](https://teleonline.app), VLC, Kodi, Jellyfin, TVHeadend, IPTV Smarters, Tivimate...

Copy this address and paste it where your app asks for the **guide**, **EPG** or **XMLTV**:

```
https://teleonline.github.io/epg/epg.xml.gz
```

If your player does not accept `.gz` files, use this uncompressed version:

```
https://github.com/teleonline/epg/releases/download/epg-latest/epg.xml
```

## For developers and apps (JSON)

It is the same guide in a format that is easier to use if you build websites or apps. If you only want to see the schedule in your player, **you do not need it**.

```
https://teleonline.github.io/epg/epg.json.gz
```

Uncompressed:

```
https://github.com/teleonline/epg/releases/download/epg-latest/epg.json
```

The addresses never change: what is updated every day is the content.
