# mrgify-clean

A GitHub Actions bot/utility that automatically downloads and cleans the latest playlist.m3u every hour from an upstream source.

## Features

- Pulls m3u content from [`abusaeeidx/Mrgify-BDIX-IPTV`](https://github.com/abusaeeidx/Mrgify-BDIX-IPTV)
- Removes duplicate streams (by URL)
- Removes irrelevant lines (#EXTVLCOPT, #EXTHTTP, comments, blank lines, etc.)
- Keeps only valid #EXTINF + URL pairs

## Usage

No manual upload required!  
The bot fetches `playlist.m3u` from:

```
https://raw.githubusercontent.com/abusaeeidx/Mrgify-BDIX-IPTV/refs/heads/main/playlist.m3u
```

Hourly automation:
- Downloads remote playlist
- Cleans and saves it as `playlist.m3u`
- Commits if changed

## Manual Clean

You can also run manually:

```bash
python clean_m3u.py https://raw.githubusercontent.com/abusaeeidx/Mrgify-BDIX-IPTV/refs/heads/main/playlist.m3u
```

or on a local file:

```bash
python clean_m3u.py playlist.m3u
```

---
*Auto-clean, always up-to-date!*
