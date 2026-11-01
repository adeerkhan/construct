# Khyber Pass — a 9:16 film

The Khyber Pass assembling across a 32-second cue, framed for a tall screen (1080 × 1920).
Jamrud, Ali Masjid, Landi Kotal and Torkham are marked along the road that carries the pass.

| file | what it is |
| --- | --- |
| `scene.json` | the construct: NASA SRTM 30 m elevation, the OpenStreetMap road from Jamrud to Torkham, four places, and their evidence |
| `khyber-pass.wav` | the cue, synthesised for this film (drone, plucked line, frame drum, wind; 32 s, 44.1 kHz stereo) |
| `khyber-audio.json` | the cue measured by `construct audio` at 30 fps: loudness, brightness, attacks and sections |

## Regenerate it

```sh
python3 construct_hologram/cli.py audio examples/films/khyber-pass/khyber-pass.wav \
    --out examples/films/khyber-pass/khyber-audio.json --fps 30

python3 construct_hologram/cli.py video examples/films/khyber-pass/scene.json \
    --out khyber-pass-9x16.mp4 --format tiktok --assembly 30 --seconds 32 \
    --audio examples/films/khyber-pass/khyber-audio.json \
    --sound examples/films/khyber-pass/khyber-pass.wav --labels
```

`--format tiktok` is 1080 × 1920 at 30 fps with the steady camera. The scene's
`presentation.framing.portrait` block (`yaw` 0, `pitch` 40, `fit` 0.95) looks up the pass from
Jamrud to Torkham; the terrain is turned a quarter turn in the scene so its length runs up the
frame instead of across it.

## What is evidence, what is designed

- **Elevation** is NASA SRTM 30 m (SRTMGL1), sampled at 0.004° (about 370 m) over
  71.014–71.458 E, 33.954–34.168 N, and served by the OpenTopography API. The relief is drawn at
  1:2 560 with heights exaggerated 1.35× (stated on the page).
- **The road** is the OpenStreetMap geometry from Jamrud to Torkham (ODbL), routed by OSRM and
  draped on the terrain. It measures 38.3 km.
- **The places** and their facts are from Wikipedia (Khyber Pass, Ali Masjid, Landi Kotal,
  Torkham, Jamrud Fort): the pass proper is 40 km from Jamrud to Landi Kotal, the summit is
  1,072 m at Landi Kotal, the narrowest point is 967 m at Ali Masjid, and the Khyber Pass Railway
  opened in 1925.
- **Designed, not evidence**: the choice of area, contours, ridgelines, the quarter turn, the
  framing and the cue. No photograph or artwork is embedded.

The quarter turn is presentation only: the model is the same terrain in its same coordinates,
turned so a tall frame can hold it. North is therefore not up in the film; the scene records
this in `authoring.next`.
