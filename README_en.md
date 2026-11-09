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

The EPG IDs are the original ones from the sources. To match them with your own channel list, match by name.

## How it works

1. The sources in `epg/sources.txt` are downloaded.
2. Programmes are filtered by time window (`epg/settings.txt`).
3. Channels in `epg/exclusions.txt` are excluded and a country is assigned (`epg/countries.txt`).
4. `epg.xml`, `epg.json` and their `.gz` versions are generated.
5. The guide is always published. If the number of channels drops by more than 15 % compared to the previous one, the workflow leaves a visible warning in its summary, but it does not block publication.

The generated files are **not stored in `main`**: the `.gz` files are published every day to the `gh-pages` branch in a single commit that replaces the previous one (the history does not grow), and the uncompressed files go to the `epg-latest` Release.

## Configuration (`epg/` folder)

| File | What it does |
|---|---|
| `sources.txt` | EPG source URLs, one per line. The `# --- España ---` header sets the default country for the sources below it |
| `settings.txt` | Days of past and future programming |
| `exclusions.txt` | Channel ID patterns to exclude |
| `countries.txt` | Country exceptions: `channel id = country` |

## Automatic generation

The workflow `.github/workflows/update-epg-guide.yml` runs every day at 04:00 UTC and can also be run manually from the *Actions* tab. To run it locally: `php scripts/build-epg-guide.php`.
