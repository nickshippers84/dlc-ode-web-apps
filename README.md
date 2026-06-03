# ODE Embeddable Course Apps

Self-contained interactive activities for online learning courses. Each folder is one embeddable app.

## Structure

```
ODE apps/
├── README.md
├── _shared/
│   └── brand.css          ← shared brand colors, fonts, and base styles
├── ODE-Driving-Abilities/
│   └── index.html
└── [future-app-name]/
    └── index.html
```

## Brand Identity

All apps share `_shared/brand.css`. Link it from every app:

```html
<link rel="stylesheet" href="../_shared/brand.css" />
```

### Colors

| Role | Hex | Usage |
|------|-----|-------|
| Construction Orange | `#F87431` | Primary actions, hover accents |
| Deep Blue | `#1B3A8C` | Headline accents, SIPDE letters, completion text |
| Warm Cream | `#F5E6D3` | Empty slots, hover backgrounds, completion panels |
| Blue-Green | `#2C5F8D` | Success states, filled slots |
| Very Dark | `#0D1B2A` | Body text |
| Slate Gray | `#64748B` | Instructions, labels, muted text |
| Near-White | `#F8F9FA` | Page background |

CSS variables are prefixed with `--ode-` (e.g. `var(--ode-orange)`, `var(--ode-font-headline)`).

### Typography

| Element | Font |
|---------|------|
| Headlines (`h1`, `.ode-headline`) | **Montserrat** |
| Sub-headlines, labels, body | **Inter** |

### Shared utility classes

- `.ode-app` — centered layout shell
- `.ode-card` — white panel with border and shadow
- `.ode-headline` / `.ode-label` / `.ode-instructions` — typed text styles
- `.ode-btn`, `.ode-btn-primary`, `.ode-btn-secondary` — button styles
- `.ode-message`, `.ode-message--success`, `.ode-message--error` — feedback text
- `.ode-completion` — success banner

## Embedding

Each app is an `index.html` that links to the shared brand stylesheet. Embed in your LMS or course page with an iframe:

```html
<iframe
  src="path/to/ODE-Driving-Abilities/index.html"
  title="SIPDE Driving Abilities Activity"
  width="100%"
  height="640"
  frameborder="0"
  style="border: none; max-width: 720px;"
></iframe>
```

When hosting, keep the `_shared` folder alongside app folders so relative paths resolve correctly.

## Apps

| Folder | Activity |
|--------|----------|
| `ODE-Driving-Abilities` | Match the five SIPDE safe driving abilities |

## Creating a new app

1. Create a folder (e.g. `ODE-My-Activity/`)
2. Add `index.html` with `<link rel="stylesheet" href="../_shared/brand.css" />`
3. Use `.ode-app` as the root wrapper and brand CSS variables for any custom styles
