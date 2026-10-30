# Profullstack CSS: agent usage contract

This file is the short, stable interface guide for coding agents working in a project that uses `@profullstack/css`.

## First moves

1. Read the nearby page and preserve its existing framework and conventions.
2. Import `@profullstack/css` once from the app's global stylesheet.
3. Build the page with semantic HTML and native controls first.
4. Use only the layout classes, component classes, data attributes, and tokens listed in `css/manifest.json`.
5. Keep behavior in the app. This package styles markup; it does not ship JavaScript.

## Markup contract

- Use `main`, `nav`, `header`, `footer`, `section`, `article`, `form`, `label`, `button`, `a`, `table`, `details`, and other native elements according to their meaning.
- Use `<button>` for an action and `<a href>` for navigation. Never create clickable `div` elements.
- Give every form control a visible `<label>`. Connect hints and errors with `aria-describedby`; mark invalid fields with `aria-invalid="true"`.
- Keep a logical heading order. A page has one clear `h1`; section headings follow it.
- Put accessible status text in the document. Color and icons alone do not communicate state.
- Do not invent framework class names. If a pattern is missing, compose native elements and existing tokens, then document the addition in the project.

## Supported layout vocabulary

`container`, `prose`, `stack`, `cluster`, `grid`, `split`, and `section` are the complete layout primitives. Use `data-space="sm|lg"` on `.stack` and `data-columns="2|3|4"` on `.grid` when needed. Layouts adapt to narrow screens without breakpoint classes.

## Supported component vocabulary

- `.card` for a bordered surface.
- `.button` for a link styled as a button; native `<button>` is already styled.
- `data-variant="secondary|ghost|danger"` for button variants.
- `.alert` with `role="status"` or `role="alert"` when appropriate; use `data-tone="success|warning|danger"` for status tone.
- `.badge` for a short label; use `data-tone="success|warning|danger"` when tone adds meaning.
- Native controls, tables, details/summary, progress, meter, and dialog elements receive baseline styling.

## Tokens and themes

Use `--pf-*` custom properties from `css/tokens.css` for colors, spacing, type, borders, and radii. Do not hard-code a second palette. The default follows the operating system theme. Set `data-theme="light"` or `data-theme="dark"` on `<html>` to choose explicitly.

## Accessibility and behavior

Keep keyboard focus visible. Preserve native keyboard behavior. Respect `prefers-reduced-motion`. Do not imply that CSS opens dialogs, validates forms, submits data, or makes a navigation menu interactive; implement those behaviors with native HTML or application code.

## Machine-readable reference

For exact spellings and snippets, read `css/manifest.json`. For the complete human guide, read `docs/agent-guide.md` and `README.md`.
