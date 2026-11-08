# Vavoo M3U8 Scraper

Scrapes live TV channels from Vavoo / Geil mirrors and writes an **M3U** playlist.

## Portugal + public EPG

Default run builds `output/playlist-portugal.m3u` with:

- `group-title="Portugal"`
- `tvg-id` from the API when available (e.g. `24Kitchen.pt`)
- `url-tvg` pointing to a public XMLTV guide:

```text
https://xmltv.live/epg/pt.xml
```

## Usage

```bash
node scrape.js
```

Resolve real HLS URLs (recommended for players; links expire → re-run later):

```bash
node scrape.js --resolve
```

Optional:

```bash
node scrape.js --base https://vavoo.to
node scrape.js --out output/my.m3u
```

## Install in an IPTV app

1. Run the script
2. Open `output/playlist-portugal.m3u` (or host it and paste the URL)
3. EPG URL (if the app asks separately): `https://xmltv.live/epg/pt.xml`

**Note:** Resolved stream URLs are short-lived. Refresh the playlist periodically if playback stops working.
