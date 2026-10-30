# Build with Profullstack CSS

This framework treats HTML as the shared interface between the browser, the person reading the code, and the agent generating it. The markup carries meaning and behavior. CSS gives that markup a coherent, responsive visual system.

## The generation loop

1. Describe the page structure with landmarks and native elements.
2. Choose a documented layout primitive (`.container`, `.stack`, `.cluster`, `.grid`, `.split`, or `.section`).
3. Add a documented component (`.card`, `.button`, `.alert`, `.badge`) only where it adds a clear visual role.
4. Reuse `--pf-*` tokens for any page-specific styling.
5. Keep interaction logic in HTML or application code, then verify it with keyboard and assistive technology.

## Why the contract is small

Agents often generate class names that look plausible but do not exist. A bounded vocabulary makes generated markup more predictable: `css/manifest.json` enumerates every supported class and variant. Unknown patterns should be composed from native HTML and existing tokens instead of guessed framework APIs.

## Install

```sh
npm install @profullstack/css
```

```css
@import "@profullstack/css";
```

The package is plain CSS. Import it in the app's global stylesheet, before app-specific rules. No JavaScript setup or runtime dependency is required.

## Page skeleton

```html
<header class="container cluster">
  <a href="/" aria-label="Acme home">Acme</a>
  <nav aria-label="Main navigation">
    <ul class="cluster" role="list">
      <li><a href="/docs">Docs</a></li>
      <li><a href="/pricing">Pricing</a></li>
    </ul>
  </nav>
</header>

<main class="container stack section">
  <header class="stack" data-space="sm">
    <p class="eyebrow">Workspace</p>
    <h1>Good morning, Alex.</h1>
    <p class="muted">A clear sentence explaining this page.</p>
  </header>

  <section class="grid" data-columns="3" aria-label="Workspace summary">
    <article class="card stack" data-space="sm">
      <h2>Projects</h2>
      <p>12 active projects</p>
    </article>
  </section>
</main>
```

## Forms

```html
<form class="stack">
  <div>
    <label for="email">Work email</label>
    <input id="email" name="email" type="email" autocomplete="email"
      aria-describedby="email-hint" required>
    <small id="email-hint">We'll send your invite here.</small>
  </div>
  <button type="submit">Send invite</button>
</form>
```

Provide error text and connect it to its field. Do not use placeholder text as the only label.

## Theme control

The browser preference is the default. An app with a theme setting can write `data-theme="light"` or `data-theme="dark"` onto the root `<html>` element. The application owns persistence and the control; the stylesheet only provides the colors.

## Reference files

- `css/manifest.json`: stable machine-readable classes, variants, tokens, and rules.
- `docs/tokens.json`: token groups for tooling and design handoff.
- `css/tokens.css`: actual CSS custom property values and theme overrides.
- `examples/`: complete HTML pages using the package.
