# Tarbela Dam — a 9:16 film

The earth-filled dam on the Indus: a 2,743 m embankment 143 m high, with its spillways, five outlet
tunnels, a 4,888 MW powerhouse and the reservoir upstream, assembling across a 32-second cue.

| file | what it is |
| --- | --- |
| `scene.json` | the construct: the embankment, crest, spillway, powerhouse, generators, tunnels and reservoir |
| `tarbela-dam.wav` | the cue, the same theme used for the Construct film series (32 s, 44.1 kHz stereo) |
| `tarbela-audio.json` | the cue measured by `construct audio` at 30 fps |

## Regenerate it

```sh
python3 construct_hologram/cli.py audio examples/films/tarbela-dam/tarbela-dam.wav \
    --out examples/films/tarbela-dam/tarbela-audio.json --fps 30

python3 construct_hologram/cli.py video examples/films/tarbela-dam/scene.json \
    --out renders/tarbela-dam-9x16.mp4 --format tiktok --assembly 30 --seconds 32 \
    --audio examples/films/tarbela-dam/tarbela-audio.json \
    --sound examples/films/tarbela-dam/tarbela-dam.wav \
    --title "Tarbela Dam" --facts dam.height,dam.length,reservoir.area,power.capacity \
    --credit @adeerkhan
```

## What is evidence, what is designed

- **Verified** (Wikipedia): an earth-filled dam on the Indus, the largest in the world; 143 m above
  the riverbed; the main wall 2,743 m of earth and rock fill; a service spillway of 18,406 m³/s and
  an auxiliary spillway of 24,070 m³/s; five outlet tunnels, four carrying 17 generators totalling
  4,888 MW; the reservoir 80.5 km long and 250 km²; completed 1976.
- **Drawn at about 1:6.7** so the whole dam fits one construct (the scene's geometry is scaled;
  the facts are real). The valley, the reservoir's extent and the structures are a reconstruction;
  the spillway gates and tunnel interiors are not modelled.
