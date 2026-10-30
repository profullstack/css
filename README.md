# @profullstack/css

**A calmer CSS contract for people and agents.**

Source: https://github.com/profullstack/css  
Live docs: https://profullstack.github.io/css/

Build accessible, responsive interfaces from semantic HTML. Get useful defaults for type, forms, tables, buttons, cards, and color themes without shipping a JavaScript runtime or learning a sprawling class vocabulary.

> Small vocabulary. Native HTML. Interfaces that stay readable after the first draft.

## Install

The source package is ready for its first public npm release. Until it is published, install directly from a local checkout:

```sh
npm install /path/to/profullstack-css
```

After publication, use the registry install:

```sh
npm install @profullstack/css
```

```css
@import "@profullstack/css";
```

Or use the stylesheet directly from a CDN after publication:

```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@profullstack/css/css/profullstack.css">
```

## What you get

- Semantic elements with considered defaults, plus seven predictable layout primitives.
- Light and dark palettes that follow `prefers-color-scheme`, with explicit theme overrides.
- Useful styles for forms, buttons, tables, disclosures, dialogs, status messages, and cards.
- Visible keyboard focus and reduced-motion support.
- CSS custom properties for product-level branding.
- A machine-readable manifest and an `AGENTS.md` generation contract.
- No JavaScript, build step, or runtime dependencies.

## Quick start

```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@profullstack/css/css/profullstack.css">

<main class="container stack section">
  <header class="stack" data-space="sm">
    <p class="eyebrow">Project overview</p>
    <h1>Make the next step obvious.</h1>
    <p class="muted">A short, useful description belongs here.</p>
  </header>

  <section class="grid" data-columns="2" aria-label="Project status">
    <article class="card stack" data-space="sm">
      <h2>Build quality</h2>
      <p>All checks are passing.</p>
      <span class="badge" data-tone="success">Healthy</span>
    </article>
    <article class="card stack" data-space="sm">
      <h2>Next review</h2>
      <p>Thursday at 10:30 AM.</p>
      <a class="button" href="/reviews">Open review</a>
    </article>
  </section>
</main>
```

## Agent-ready by design

The framework publishes a finite vocabulary instead of asking code generators to guess. Read `AGENTS.md` for the short contract and `css/manifest.json` for exact class names, data attributes, snippets, theme rules, and accessibility guidance. When a pattern is missing, compose native elements and existing tokens; keep behavior in your app.

## Customize

Override tokens after importing the framework:

```css
:root {
  --pf-color-primary: #4a42c4;
  --pf-color-primary-hover: #3932a5;
  --pf-radius-md: 1rem;
  --pf-content-width: 78rem;
}
```

To select a theme explicitly, set an attribute on the root element:

```html
<html lang="en" data-theme="dark">
```

Available theme values: `light`, `dark`. Without an attribute, the user's system preference wins.

## Documentation

- `docs/agent-guide.md` — complete generation and usage guide.
- `css/manifest.json` — machine-readable framework contract.
- `docs/tokens.json` — token values and theme pairs for tooling.
- `examples/` — complete sample pages.
- `docs/index.html` — rendered documentation.

## Scope

This is a CSS foundation, not a component runtime. It styles native `<dialog>` and form controls but does not open dialogs, validate inputs, submit forms, or implement menus. Use semantic HTML and add application behavior where it belongs.

## License

MIT. Independent implementation; not affiliated with Pico CSS.
