# Palette Picker

A small, dependency-free web page that generates harmonious colour combinations.
Pick how many colours you need (2 to 6) and get 20 combinations, each with its hex codes, ready to copy.

**Live site:** https://simgraworldwide.github.io/palette_picker/

## Features

- Choose 2, 3, 4, 5 or 6 colours per combination
- 20 combinations per run, each based on a named colour harmony
- Click a swatch to copy its hex code, or use **Copy all** for the whole combination
- **New combinations** button, or press <kbd>Space</kbd>
- Remembers your last colour count
- Light and dark mode, works on phone and desktop

## How the colours are generated

Colours are built in the [OKLCH](https://oklch.com) colour space rather than HSL, so equal steps in lightness look equal to the eye. Each combination starts from a base hue and applies one of these harmony rules:

| Harmony | Idea |
| --- | --- |
| Analogous | Neighbouring hues, 18–32° apart |
| Monochromatic | One hue, spread across light to dark |
| Complementary | Base hue plus its opposite (180°) |
| Split complementary | Base hue plus the two hues beside its opposite (150°, 210°) |
| Triadic | Three hues evenly spaced (120°) |
| Tetradic | Two complementary pairs (0°, 60°, 180°, 240°) |
| Neutrals + accent | Tinted neutrals with one saturated accent |
| Muted earth | Low-chroma warm hues with one contrasting note |
| Pastel | High lightness, low chroma |

Lightness is spread evenly across each combination, chroma is reduced near black and white, and any colour outside the sRGB gamut is pulled back in before it is converted to hex. Base hues for the 20 combinations step around the colour wheel by the golden angle (137.5°), so a run covers a wide range of hues.

## Run locally

No build step and no dependencies apart from Google Fonts. Clone the repo and open `index.html` in a browser:

```bash
git clone https://github.com/simgraworldwide/palette_picker.git
cd palette_picker
open index.html   # or double-click the file
```

## Deployment

The site is served with GitHub Pages from the `main` branch (root folder). Any push to `main` updates the live site.
