# Santoor ABC Tab

A browser-based ABC notation viewer and tablature tool for a 27-course Persian santoor reference layout in Dastgāh-e Šur.

## Features

- ABC notation input
- Standard sheet-music rendering using ABCJS
- Three tablature groups, each drawn as a 9-line course stave:
  - BASS: B9 is the top line; B1 is the bottom line
  - MIDDLE: M9 is the top line; M1 is the bottom line
  - HIGH: H9 is the top line; H1 is the bottom line
- A4 reference selection
- Persian Šur course frequencies
- Nearest-course selection when ABC asks for a pitch not present on the instrument
- Chord support such as `[CEG]`
- Basic ABC accidentals, key signatures, octave marks, bars, rests, decorations and grace notes
- Print stylesheet
- Download the entered ABC
- No server/backend required

## Run locally

Just open `index.html` in a modern browser.

## GitHub Pages

1. Create a public repository, e.g. `santoor-abc-tab`.
2. Upload `index.html` and `styles.css`.
3. Settings → Pages.
4. Deploy from `main` / root.
5. Open the generated Pages URL.

## Layout implementation

Each wrapped music system is rendered as its own SVG, with its matching 27-course santoor tablature inserted directly underneath. This keeps each notation system and its tab together when the music wraps across the page.

The tab renderer uses ABCJS's rendered note classes (`abcjs-note`, `abcjs-lN`, etc.) to place the course labels horizontally under the corresponding music system.

ABCJS's rendered-object/class APIs are documented as useful but volatile; if ABCJS is upgraded, the tab alignment code should be retested.

## Licensing / attribution

This project uses ABCJS from the public CDN. ABCJS is MIT licensed.

This is an independent santoor interface and is not affiliated with Rick van der Sluijs or Diatotab.


## Course direction

Course numbering always follows pitch upward within each group:

- B1 = E3 koron (lowest bass course)
- B9 = F4 (highest bass course)
- M1 = E4 koron (lowest middle course)
- M9 = F5 (highest middle course)
- H1 = E5 koron (lowest high course)
- H9 = F6 (highest high course)

On the displayed tablature, the visual line order is therefore reversed within each group: 9 at the top, 1 at the bottom. This makes the tab behave like a vertical pitch layout: higher courses appear higher on the page.


## v5 layout
- Uses ABCJS `oneSvgPerLine` so every wrapped notation system is a separate SVG.
- Places the matching santoor tablature immediately below each notation system.
- Aligns course markers to the note positions within that system.
