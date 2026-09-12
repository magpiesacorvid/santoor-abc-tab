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

## Important implementation note

The standard instrument definition contains all 27 courses.

The tab renderer uses ABCJS's rendered note classes (`abcjs-note`, `abcjs-lN`, etc.) to place the course labels horizontally under the corresponding music system.

ABCJS's rendered-object/class APIs are documented as useful but volatile; if ABCJS is upgraded, the tab alignment code should be retested.

## Licensing / attribution

This project uses ABCJS from the public CDN. ABCJS is MIT licensed.

This is an independent santoor interface and is not affiliated with Rick van der Sluijs or Diatotab.
