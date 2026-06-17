# Sweet Escape ✈

A boarding pass to wonder. Awareness as destination, dessert as the
feeling of arrival. Built with vanilla HTML · CSS · JS — no build
step, no dependencies.

## The concept

Every section borrows real travel-document language and applies it
to something dreamy and edible:

| Section | Travel metaphor | What it does |
|---|---|---|
| **Hero** | Literal boarding pass — gate, seat, perforated tear-line | Sets the destination: Sweet Escape |
| **Journal** | In-flight declaration card | Five reflection prompts, framed as "what are you carrying with you" |
| **Ports of Call** | Passport stamps at three layovers | Paradise, Starry, Turtle — each a stamped mini-destination |
| **Arrivals** | Arrivals board, dark "nighttime terminal" palette | Closing reflection — you've landed, now what |

## Project structure

```
sweet-escape/
├── index.html       ← everything lives here (single-file)
├── images/           ← optional: real photography to layer in later
└── README.md
```

## How to customize

Open `index.html` and scroll to the **`CONTENT CONFIGURATION`**
block near the bottom. Three plain JS objects control all copy:

| Object | Controls |
|---|---|
| `DECLARATION_ITEMS` | The five journal/reflection prompts |
| `PORTS` | Name, stamp emoji, port code, and prompt per card |
| `ARRIVALS` | Closing board rows + final tagline |

Hero copy lives in `data-*` attributes on `<section id="hero">` —
gate, seat, departure time, destination name, and the CTA text are
all editable there without touching layout markup.

### Swapping in real images later

Right now the stamps and ticket are pure CSS/type. If you want to
layer in real photography (e.g. an actual sky behind the ticket, or
a textured paper background):

```css
#hero {
  background-image: url('images/sky-backdrop.jpg');
  background-size: cover;
  background-position: center top;
}
```

```css
.port-stamp {
  background-image: url('images/paradise-texture.jpg');
  background-size: cover;
}
```

## Deploy to GitHub Pages

1. Push this folder to a GitHub repository.
2. **Settings → Pages → Source → main branch / root.**
3. Live at `https://your-username.github.io/sweet-escape/`.

## Design tokens

| Token | Value | Reads as |
|---|---|---|
| `--paper` | `#fcf6ee` | Boarding-pass cream stock |
| `--coral` | `#e8746b` | Wax-seal / "boarding now" stamp |
| `--teal` | `#2b6e63` | Airline ticket ink / pistachio |
| `--gold` | `#c98f3a` | Foil stamp / perforation line |
| `--ink` | `#3a2e2a` | Espresso print ink |
| `--tan` | `#f2d8c2` | Croissant fill |
| `--font-display` | Fraunces | Headlines, destination names |
| `--font-script` | Cormorant Garamond | Body copy, prompts |
| `--font-data` | Space Mono | Ticket data — gate, seat, codes |

The mono/serif pairing is doing the conceptual work: elegant escape,
printed like infrastructure.

## Adding a new section

1. Add a `<section id="...">` with placeholder element `id`s.
2. Add a config object in the `CONTENT CONFIGURATION` block.
3. Add a `render*()` IIFE in the render engine area.
4. Style it using the existing tokens — keep the perforation/stamp
   language going so new sections still feel like part of the same
   itinerary.

## Possible next stops

- Audio: a soft ambient loop that starts on "boarding" (use the
  `boarding-cta` click as the trigger).
- Card interactions: click a port-of-call stamp to flip and reveal a
  longer prompt or a text input.
- Mobile nav: a sticky mini boarding-pass header that scrolls with
  the page once you're past the hero.
- Entrance animation: the ticket could slide in like it's being
  printed, or the perforation could "tear" on scroll.
