# Santoor ABC Tab v8

A browser-only ABC notation viewer with aligned Persian santoor tablature.

## Course mapping

The exact 27-course layout supplied for this project is used. Course numbers increase with pitch within each register:

- Bass: B1 E3 koron through B9 F4
- Middle: M1 E4 koron through M9 F5
- High: H1 E5 koron through H9 F6

ABC notes are interpreted using their **written octave and accidentals**, converted to 12-TET frequency at the selected A4 reference, and mapped to the nearest santoor course by cents. The visual position of the tab follows the written pitch; a low ABC note cannot be treated as the same pitch as a higher occurrence of the same letter.

## Display

Each wrapped notation system is rendered as one block. Its three tablature lines sit directly underneath the notation:

HIGH
MIDDLE
BASS

The number is the course number to strike. There are no dot markers and the generated area has no horizontal scrollbar.

## Credits

Uses ABCJS 6.6.4 from jsDelivr. The application is an independent santoor tablature interface inspired by the general idea of ABC-to-tab tools.
