# Cola Bomb

A crate holds 25 cola bottles. Some of them were shaken until they are ready to go
off. Pull the good ones, leave the bombs, and beat the clock.

**Play it: https://ctbot000.github.io/cola-bomb/**

No build step, no dependencies — one self-contained `index.html`.

## How it plays

- Every crate hides a number of shaken bottles. Pull the required number of good
  ones before the fizz meter runs out.
- Pull a shaken bottle and it blows: you lose one of your three bottles and the
  crate starts over at the same difficulty.
- **Shake test** (2 per crate) listens to the bottle under the cursor without
  opening it. A hissing bottle gets flagged and locked so you cannot pull it by
  accident; a quiet one is safe.
- Clearing a crate pays a bonus plus whatever time is left on the meter. Each
  crate after that packs one more bomb and asks for one more pull, up to 12 bombs
  in 25 bottles — at which point every single safe bottle has to come out.

Consecutive safe pulls build a streak multiplier up to ×5. Your best score is
kept in the browser.

### Keyboard

| Key | Action |
| --- | --- |
| `←` `↑` `↓` `→` | move between bottles |
| `Enter` / `Space` | pull the bottle |
| `S` | shake test |

## Running it locally

Open `index.html` in a browser, or serve the folder:

```bash
python3 -m http.server 4173
```

Then visit http://localhost:4173.
