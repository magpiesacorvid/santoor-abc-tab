# Persian Santoor ABC → Tab

A zero-dependency browser tool that converts common ABC music notation into tab labels for a
27-course Persian santoor tuned for Dastgāh-e Šur.

## Your tab labels

- Bass side: `B1`–`B9`
- Middle side: `M1`–`M9`
- High side: `H1`–`H9`

The full standard layout includes all 27 courses. 

## Tuning

The tool uses the Hz table supplied for this santoor:

| Tab | Note | Hz |
|---|---|---:|
| B1 | E3 koron | 160.122 |
| B2 | F3 | 174.614 |
| B3 | G3 | 195.998 |
| B4 | A3 koron | 213.737 |
| B5 | Bb3 | 233.082 |
| B6 | C4 | 261.626 |
| B7 | D4 koron | 285.305 |
| B8 | Eb4 | 311.127 |
| B9 | F4 | 349.228 |
| M1 | E4 koron | 320.244 |
| M2 | F4 | 349.228 |
| M3 | G4 | 391.995 |
| M4 | A4 koron | 427.474 |
| M5 | Bb4 | 466.164 |
| M6 | C5 | 523.251 |
| M7 | D5 | 587.330 |
| M8 | Eb5 | 622.254 |
| M9 | F5 | 698.456 |
| H1 | E5 koron | 640.487 |
| H2 | F5 | 698.456 |
| H3 | G5 | 783.991 |
| H4 | Ab5 | 830.609 |
| H5 | Bb5 | 932.328 |
| H6 | C6 | 1046.502 |
| H7 | D6 | 1174.659 |
| H8 | Eb6 | 1244.508 |
| H9 | F6 | 1396.913 |

A4 reference is 440 Hz.

## How the conversion works

ABC pitches are interpreted as 12-tone-equal-temperament input. The tool converts each ABC pitch
to Hz and chooses whichever santoor course has the smallest absolute pitch distance in cents.

This means a note that does not exist on the santoor is automatically moved to the closest available
course. For example, A4 (440 Hz) maps to M4 (A4 koron, 427.474 Hz), because that is closer than B♭4.

When two courses have the same pitch (for example B9 and M2 are both F4), the lower physical group
wins: B before M before H.

## ABC support

The converter handles:

- `C D E F G A B`
- lowercase octave notes: `c d e f g a b`
- sharps: `^C`
- flats: `_E`
- naturals: `=F`
- repeated accidentals such as `^^C` / `__D`
- octave marks: `c`, `C,`, `c'`, etc.
- note lengths: `C2`, `C/2`, `C3/2`
- bars and most other non-note ABC text
- simple chords: `[CEG]`
- ties: `C~D`

Duration is retained after the tab label, e.g. `M6{2}` or `M6{1/2}`.

## Run locally

Open `index.html` in a browser.

## Run on GitHub Pages

1. Create a GitHub repository.
2. Upload `index.html`.
3. Go to **Settings → Pages**.
4. Select **Deploy from a branch**.
5. Select the branch containing `index.html` and `/ (root)`.
6. Save.

No server, Python, Node, npm, or external dependencies are required.

## Important limitation

ABC is a broad format. This is intentionally a lightweight parser for ordinary melodic ABC rather
than a full ABC renderer. It does not attempt to interpret every ABC feature such as complex
grace-note syntax, tuplets, broken-rhythm operators, voices, or inline fields semantically.
Those characters are generally preserved in the output.

The pitch mapping itself is independent of ABC's key signature: explicit ABC accidentals and the
written pitch are converted directly to the nearest santoor course.
