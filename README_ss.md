# Sweet Escape 🌸

A soft, editorial wellness landing page with four modular sections.  
Built with vanilla HTML · CSS · JS — no build step, no dependencies.

## Project structure

```
sweet-escape/
├── index.html       ← everything lives here (single-file)
├── images/          ← add your card + hero images here (optional)
└── README.md
```

## How to customize

Open `index.html` and scroll to the **`CONTENT CONFIGURATION`** block near the bottom.  
All content lives in three plain JavaScript objects — no HTML editing required.

| Object | What it controls |
|---|---|
| `JOURNAL_PROMPTS` | The five (or more) reflection questions |
| `ESCAPE_CARDS`    | Title, emoji, prompt text, and background color/image per card |
| `CLOSING`         | Reflection section headline, columns, and closing tagline |

Hero copy is set via `data-*` attributes on `<section id="hero">` in the HTML.

### Swapping in real images

**Card images** — set `bgColor` to a CSS `url()` value:
```js
bgColor: "url('images/paradise.jpg') center/cover no-repeat",
```

**Hero background** — add to `#hero` in CSS:
```css
#hero {
  background-image: url('images/hero-bg.jpg');
  background-size: cover;
  background-position: center top;
}
```

## Deploy to GitHub Pages

1. Push this folder to a GitHub repository.
2. Go to **Settings → Pages → Source → main branch / root**.
3. Your site will live at `https://your-username.github.io/sweet-escape/`.

## Adding sections

Each section follows the same pattern:

1. Add a `<section id="my-section">` in the HTML with placeholder `id`s.
2. Add a config object in the `CONTENT CONFIGURATION` block.
3. Add a `renderMySection()` function in the render engine area.
4. Style it in the `<style>` block using the existing design tokens.

## Design tokens (CSS variables)

| Token | Value | Used for |
|---|---|---|
| `--rose` | `#e8a0b0` | Accents, bullets, CTA |
| `--gold` | `#c9a84c` | Borders, rules |
| `--cream` | `#fdf8f0` | Section backgrounds |
| `--text-dark` | `#4a2a35` | Headlines |
| `--text-mid` | `#7a5060` | Body copy |
| `--font-display` | Playfair Display | Headings |
| `--font-body` | Cormorant Garamond | Body, prompts |
| `--font-ui` | Lato | Labels, buttons |
