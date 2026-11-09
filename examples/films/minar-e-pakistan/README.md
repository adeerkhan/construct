# Minar-e-Pakistan — a 9:16 film

The tower in Lahore's Greater Iqbal Park, raised on its five-pointed star platform, assembling
across a 32-second cue: the star base, the ten-petal flower base, the fluted shaft, then the dome.

| file | what it is |
| --- | --- |
| `scene.json` | the construct: the star platform, the flower base, the tower shaft and the dome, with their evidence |
| `minar-e-pakistan.wav` | the cue, the same theme used for the Construct film series (32 s, 44.1 kHz stereo) |
| `minar-audio.json` | the cue measured by `construct audio` at 30 fps |

## Regenerate it

```sh
python3 construct_hologram/cli.py audio examples/films/minar-e-pakistan/minar-e-pakistan.wav \
    --out examples/films/minar-e-pakistan/minar-audio.json --fps 30

python3 construct_hologram/cli.py video examples/films/minar-e-pakistan/scene.json \
    --out renders/minar-e-pakistan-9x16.mp4 --format tiktok --assembly 30 --seconds 32 \
    --audio examples/films/minar-e-pakistan/minar-audio.json \
    --sound examples/films/minar-e-pakistan/minar-e-pakistan.wav \
    --title "Minar-e-Pakistan" \
    --facts minaret.total.height,minaret.tower.height,minaret.base.height,minaret.petals.height \
    --credit @adeerkhan
```

`--credit @adeerkhan` prints the handle in the slate, under the data reference.

## What is evidence, what is designed

- **Verified** (Wikipedia): the tower stands in Greater Iqbal Park, built 1960–1968 to
  commemorate the Lahore Resolution of 23 March 1940; designed by Nasreddin Murat-Khan; the base
  rises 8 m, the tower 62 m on it (about 70 m total); the ten unfolding petals of the flower-like
  base are 9 m high; the star-shaped platform is about 97.5 m across; the small dome on top is steel
  with a pinnacle.
- **Inferred**: the star outline, the petal arrangement, the fluting, the dome and the plaza. The
  crescent pools, the marble inscriptions and the park planting are not modelled.
