# saga-research.github.io

Landing site for **Saga Research** — systems for adaptive grounded autonomy.

**[saga-research.github.io](https://saga-research.github.io/)**

<img src="qr.png" alt="QR code linking to https://saga-research.github.io/" width="220">

Scan to open the site.

## Contents

| Path | Purpose |
| --- | --- |
| `index.html` | The whole site: hero, recent work, contact |
| `styles.css` | All styling — aurora backdrop, grid, marquee |
| `favicon.svg` | Tab mark; `favicon-32.png` and `apple-touch-icon.png` are generated from it |
| `favicon-anon.svg` | Tab mark for the `anon` style — no glyph, just the aurora in a rounded tile |
| `logos/` | "Featured on" marks, flattened to sit on the dark field |
| `qr.png` | The QR code above |

## Switches

Two attributes in `index.html` change what the page shows. No build step, no JS
framework — edit the attribute, reload.

### `data-style` on `<html>`

How loudly the site names itself.

```html
<html lang="en" data-style="default">
```

| Value | Wordmark | Favicon | Tab title | Aurora |
| --- | --- | --- | --- | --- |
| `default` | "Saga Research" top-left | `favicon.svg` | saga research | full strength |
| `anon` | hidden | `favicon-anon.svg` | Systems for Adaptive Grounded Autonomy | `opacity: 0.42` |

The wordmark and aurora hang off `[data-style="anon"]` rules in `styles.css`.
Title, favicon, and meta description live in `<head>`, so a small inline script
there swaps them instead — it also drops the PNG icons in `anon`, since those
still carry the named mark.

Note that `anon` only removes the *branding*. The page still credits Stanford
SAIL and links to named GitHub / arXiv / X accounts.

### `data-featured` on `.hero-featured`

What sits in the "Featured on" slot.

```html
<div class="hero-featured" data-featured="single">
```

| Value | Shows |
| --- | --- |
| `single` | One credit — the YC mark next to "YC Paper Club" |
| `marquee` | The scrolling strip of all six logos |

Both versions stay in the markup; the inactive one is hidden in CSS. To change
the single credit, edit the `.featured-single` paragraph. To change the
marquee, edit **both** copies of the `<ul class="logos">` — it's duplicated so
the loop is seamless.

## Local preview

No build step — it's static.

```sh
python3 -m http.server 8080
# then open http://127.0.0.1:8080/
```

## Contact

saga.research.ai@gmail.com
