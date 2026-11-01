# Faisal Masjid — a 9:16 film

The national mosque of Pakistan in Islamabad, assembling across a 32-second cue: the site
platform, the tent-shaped prayer hall, the courtyard porticoes, then the four 90 m minarets.

| file | what it is |
| --- | --- |
| `scene.json` | the construct: the prayer hall as four curved shell faces, the portal, the courtyard and porticoes, four minarets, and their evidence |
| `faisal-masjid.wav` | the cue, synthesised for this film (drone, ney-like line, plucked arpeggios, soft frame drum; 32 s, 44.1 kHz stereo) |
| `faisal-audio.json` | the cue measured by `construct audio` at 30 fps |

## Regenerate it

```sh
python3 construct_hologram/cli.py audio examples/films/faisal-masjid/faisal-masjid.wav \
    --out examples/films/faisal-masjid/faisal-audio.json --fps 30

python3 construct_hologram/cli.py video examples/films/faisal-masjid/scene.json \
    --out renders/faisal-masjid-9x16.mp4 --format tiktok --assembly 30 --seconds 32 \
    --audio examples/films/faisal-masjid/faisal-audio.json \
    --sound examples/films/faisal-masjid/faisal-masjid.wav \
    --title "Faisal Masjid" \
    --facts minaret.height,hall.height,hall.capacity,site.area
```

`--format tiktok` is 1080 × 1920 at 30 fps with the steady camera. The scene's
`presentation.framing.portrait` block (`yaw` 20, `pitch` 8, `fit` 0.55) frames the hall and the
four minarets; the title slate sets the title, the sources as a data reference, and the place
labels and facts below the construct.

## What is evidence, what is designed

- **Verified** (Wikipedia unless noted): the mosque is the national mosque of Pakistan, designed
  by Vedat Dalokay, built 1976–1986, first prayer 18 June 1988; an eight-sided tent-shaped
  concrete shell with no dome; four minarets 90 m tall (the tallest in South Asia) with their
  galleries almost 60 m up (Twentieth Century Society); the hall holds 10,000 and the mosque
  300,000; the structure covers 130,000 m²; the hall is 40 m tall (Alluring World) and rests on
  four concrete girders; the entrance is from the east, before a courtyard with porticoes.
- **Inferred**: the shell's four straight-faced sails (the real surface is folded and curved), the
  sizes of the courtyard and its bays, the portal, the stair and the site platform, and the exact
  positions of the minarets at the hall's corners. The construct is an *approximate
  reconstruction*, and its page says so.
- **Designed**: the staging, the cue and the framing. No photograph or artwork is embedded.
