# Pakistan Monument — a 9:16 film

The national monument on Islamabad's Shakarparian Hills: four large petals for the four cultures
and three smaller petals for the territories, converging over a star-shaped platform, assembling
across a 32-second cue.

| file | what it is |
| --- | --- |
| `scene.json` | the construct: the seven petals, the star platform, Freedom Plaza and the museum |
| `pakistan-monument.wav` | the cue, the same theme used for the Construct film series (32 s, 44.1 kHz stereo) |
| `monument-audio.json` | the cue measured by `construct audio` at 30 fps |

## Regenerate it

```sh
python3 construct_hologram/cli.py audio examples/films/pakistan-monument/pakistan-monument.wav \
    --out examples/films/pakistan-monument/monument-audio.json --fps 30

python3 construct_hologram/cli.py video examples/films/pakistan-monument/scene.json \
    --out renders/pakistan-monument-9x16.mp4 --format tiktok --assembly 30 --seconds 32 \
    --audio examples/films/pakistan-monument/monument-audio.json \
    --sound examples/films/pakistan-monument/pakistan-monument.wav \
    --title "Pakistan Monument" --facts monument.height,monument.area,petals.large,petals.small \
    --credit @adeerkhan
```

## What is evidence, what is designed

- **Verified** (Wikipedia): a national monument and heritage museum on the Shakarparian Hills,
  designed by Arif Masoud, selected 10 July 2003, foundation 25 May 2004, completed 2006,
  inaugurated 23 March 2007; 18 m high; 2.8 hectares (28,000 m²); four large petals for the Punjabi,
  Baloch, Sindhi and Pakhtun cultures and three smaller petals for the minorities, Azad Kashmir and
  Gilgit-Baltistan; granite petals, a black granite star and a stainless steel crescent.
- **Inferred**: the petal curves and thickness, the star platform, the plaza and the museum block.
  The inner murals and the crescent are not modelled.
