# Study with me

Open study notes, written while learning and shared as they go.

Each unit has three parts: **notes** with live interactive diagrams you can play with, a **quiz** to test recall, and **flashcards** for drilling. Everything runs in the browser — no accounts, no tracking, no server.

**Live site:** https://Hasti-zanganeh.github.io

---

## What's here

| Subject | Units |
| --- | --- |
| Spiking neural networks | Day 2 — The CUBA LIF equations |

More gets added as I study. Other subjects will appear here over time.

---

## Using it

Just open the link. A few things worth knowing:

- **Quiz scores and your theme choice are saved in your own browser.** They never leave your device and I can't see them. Clearing your browser data resets them.
- **The diagrams are interactive.** Drag the sliders. Most of the ideas are much easier to see than to read.
- **Flashcards** flip on click, and arrow keys move between them.
- It works on phones.

---

## How it's built

One self-contained `index.html` file. No framework, no build step, no dependencies. Fonts come from Google Fonts; everything else is inline.

That's deliberate — it means the site will still work in ten years, and anyone can read the whole thing by viewing source.

The diagrams are hand-written SVG driven by small JavaScript simulations. When you drag a slider on the membrane-potential widget, it's genuinely integrating the differential equation, not replaying a canned animation.

---

## Adding a new unit

All content lives in the `SITE` object near the top of the `<script>` block in `index.html`. Nothing else needs to change.

```js
{
  id: "day3",
  n: "Day 3",
  title: "Surrogate gradients",
  blurb: "One short line describing the unit.",
  notes: [ /* blocks — see below */ ],
  quiz:  [ /* questions */ ],
  cards: [ /* flashcards */ ]
}
```

### Note blocks

| Type | Use |
| --- | --- |
| `{t:"h", v:"Heading"}` | Section heading |
| `{t:"p", v:"Text…"}` | Paragraph (inline HTML allowed) |
| `{t:"eq", v:"a = b\n<em>gloss</em>"}` | Equation with an optional italic gloss |
| `{t:"note", v:"<p>…</p>"}` | Callout box; add `class:"warn"` for the red variant |
| `{t:"tbl", v:[[header…],[row…]]}` | Table — first array is the header row |
| `{t:"widget", v:"lif"}` | Embeds an interactive diagram by name |

### Quiz questions

```js
{
  q: "The question text",
  o: ["option A", "option B", "option C"],
  a: 1,                    // index of the correct option
  h: "An optional hint",
  e: "Why the answer is right — shown after they answer"
}
```

### Flashcards

```js
{ f: "Front — the prompt", b: "Back — the answer (HTML allowed)" }
```

Wrap a formula on the back in `<span class='k'>…</span>` to render it in monospace.

### New widgets

Add an entry to the `WIDGETS` object with an `html` string and an `init()` function, then reference it from a note block by its key.

---

## Adding a new subject

Append to `SITE.subjects`:

```js
{
  id: "shortname",
  title: "Subject title",
  blurb: "One or two lines on what it covers.",
  units: [ /* units */ ]
}
```

---

## Updating the live site

Edit `index.html` in this repo (the pencil icon on GitHub works fine), commit, and the site refreshes within a minute.

---

## Notes and corrections

If you spot an error, please open an issue — I'd rather know.

These are study notes, not a textbook. They're written to help me understand things, and shared in case they help someone else. Check anything important against the primary sources.

---

## License

Content is [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) — use it, adapt it, just credit it.
Code is MIT.

---

Built by YOUR NAME.
