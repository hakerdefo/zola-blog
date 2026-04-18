+++
title = "Embedding a Video and a Map"
date = "2025-04-18"
description = "A quick reference post showing how to embed a YouTube video and an OpenStreetMap map inside a Zola post."
draft = true

[taxonomies]
tags = ["meta", "howto"]
+++

This post is a sandbox for the two new shortcodes: a YouTube embed and an OpenStreetMap embed.
Both are fully responsive and respect the blog's colour theme.

<!-- more -->

## YouTube

Use the `youtube` shortcode with the video's ID (the part after `?v=` in the URL).

```
{{ "{{" }} youtube(id="NrG63A7DnGI") }}
```

{{ youtube(id="aqz-KE-bpKQ", title="Rick Astley — Never Gonna Give You Up") }}

Optional parameters:

| Parameter | What it does | Example |
|-----------|-------------|---------|
| `id` | YouTube video ID (**required**) | `id="NrG63A7DnGI"` |
| `title` | Accessibility label for the iframe | `title="My video"` |
| `start` | Start time in seconds | `start=42` |

A timestamped example:

```
{{ "{{" }} youtube(id="dQw4w9WgXcQ", start=42, title="Rick Astley — Never Gonna Give You Up") }}
```

---

## OpenStreetMap

Use the `map` shortcode with a latitude and longitude. The pin is placed at the same coordinates.

```
{{ "{{" }} map(lat=48.8584, lon=2.2945) }}
```

{{ map(lat=48.8584, lon=2.2945, caption="Eiffel Tower, Paris") }}

Optional parameters:

| Parameter | What it does | Default |
|-----------|-------------|---------|
| `lat` | Latitude (**required**) | — |
| `lon` | Longitude (**required**) | — |
| `zoom` | Zoom level for the "view larger map" link | `14` |
| `delta` | Half-width of the visible bbox in degrees | `0.01` (~1 km) |
| `caption` | Label used as the iframe's accessibility title | `"Map"` |

For a tighter close-up, shrink `delta`:

```
{{ "{{" }} map(lat=48.8584, lon=2.2945, delta=0.004, zoom=16, caption="Eiffel Tower close-up") }}
```

{{ map(lat=48.8584, lon=2.2945, delta=0.004, zoom=16, caption="Eiffel Tower close-up") }}
