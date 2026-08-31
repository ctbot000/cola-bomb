# Cola Bomb

Minesweeper in a crate of cola. Some bottles were shaken until they are ready to
go off. Every bottle you pull is stamped with **how many shaken bottles touch
it** — read the numbers, cap the bombs, and get every safe bottle out before the
fizz meter empties.

**Play it: https://ctbot000.github.io/cola-bomb/**

No build step, no dependencies — one self-contained `index.html`.

## Rules

- **The first pull is always safe.** Bombs are placed after it, never under or
  beside it, so every crate opens with a run of empty slots to reason from.
- **Every crate can be cleared by reasoning alone.** Boards are generated, then
  replayed by a solver that only makes deductions a person can make; a board is
  accepted only if that reasoning reaches every safe bottle. Guessing is never
  required. (On rare crates no such board turns up in the budget — the game says
  so in the ticker rather than letting you find out the hard way.)
- Pull a shaken bottle and it blows: one of your three bottles is spent and a
  fresh crate of the same size is packed.
- **Flag** a bottle you have proved is shaken — right-click, long-press, `F`, or
  the flag-mode button — and it is locked against accidental pulls.
- **Chord**: clicking a number whose bombs are all flagged clears its remaining
  neighbours at once. Flag wrongly and it refuses rather than killing you.
- **Shake test** (one per crate) listens to the bottle under the cursor: a
  hissing one is flagged for you, a quiet one is pulled. A safety valve, not a
  substitute for reading the crate.

Clearing pays a bonus plus whatever time is left. Your best score is kept in the
browser.

### Crates

| Crate | Board | Shaken | Fizz meter |
| --- | --- | --- | --- |
| 1–2 | 5×5 | 4, 5 | 80s, 78s |
| 3–4 | 6×6 | 7, 9 | 100s, 95s |
| 5–6 | 7×7 | 11, 13 | 121s, 116s |
| 7–8 | 8×8 | 15, 18 | 148s, 140s |
| 9+ | 8×8 | up to 20 | ~136s |

### Keyboard

| Key | Action |
| --- | --- |
| `←` `↑` `↓` `→` | move between bottles |
| `Enter` / `Space` | pull, or chord an already-open number |
| `F` | flag |
| `S` | shake test |

## Running it locally

Open `index.html` in a browser, or serve the folder:

```bash
python3 -m http.server 4173
```

Then visit http://localhost:4173.
