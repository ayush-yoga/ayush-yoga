# CLAUDE.md — Ayush Yoga & Ayurveda

## Project Overview

Static single-page website for an Ayurveda and Ashtanga Yoga instructor based in Austin, TX. The site serves as a marketing and information hub for yoga classes, Ayurveda counseling, and wellness workshops.

## Tech Stack

- **HTML5** with embedded CSS and vanilla JavaScript (no frameworks)
- **Google Fonts**: Cormorant Garamond (serif, headings) and Jost (sans-serif, body)
- **No build system** — no npm, no bundler, no package.json
- **No testing framework**
- **No CI/CD pipeline**

## File Structure

```
index.html    — Entire website (HTML + embedded CSS + embedded JS, ~1,273 lines)
CLAUDE.md     — This file
```

The site is fully self-contained in `index.html`. There are no other source files, assets, or dependencies beyond the Google Fonts CDN link.

## Development Workflow

1. Open `index.html` directly in a browser — no install or build steps required
2. Edit `index.html` and refresh the browser to see changes
3. Test responsive layout by resizing the browser or using DevTools device mode (breakpoint: 768px)

## CSS Conventions

### Custom Properties (`:root`)

Color palette variables used throughout:
- `--cream`, `--beige` — background tones
- `--terra`, `--terra-deep` — primary accent (brown/terra cotta)
- `--sage`, `--sage-light` — secondary accent (green)
- `--dark`, `--muted`, `--white` — text and neutral colors

### Naming

- **Kebab-case** class names: `.service-card`, `.schedule-tab-content`
- **BEM-inspired** structure: `.about-box`, `.about-box-inner`, `.about-quote`
- **State classes**: `.active`, `.open`
- **Section IDs**: lowercase (`#hero`, `#about`, `#services`, `#schedule`, `#testimonials`, `#contact`)

### Layout

- `.container` — max-width 960px centered wrapper
- CSS Grid for multi-column layouts (`.about-grid`, `.services-grid`, `.testimonials-grid`)
- Flexbox for alignment within components
- Single responsive breakpoint: `@media (max-width: 768px)`

### Reusable Classes

- `.btn`, `.btn-primary`, `.btn-outline` — button styles
- `.section-label`, `.section-title`, `.divider` — section header pattern
- `.level-all`, `.level-beg`, `.level-int`, `.level-adv`, `.level-pvt` — schedule level badges

## JavaScript Conventions

- **Vanilla JS only** — no libraries or frameworks
- **camelCase** function names: `showTab()`, `handleSubmit()`
- **Inline `onclick` handlers** in HTML for navigation and tab switching
- **DOM manipulation** via `document.getElementById()`, `document.querySelector()`, `.classList.toggle()/.add()/.remove()`
- **`<script>` block** at the bottom of the file (~lines 1244–1273)

### Key Interactions

| Feature | Implementation |
|---|---|
| Mobile menu | Hamburger button toggles `.open` class on `#navLinks` |
| Schedule tabs | `showTab(tabId)` toggles `.active` on tab buttons and content |
| Contact form | `handleSubmit(e)` prevents default, shows `#form-success`, resets form after 5s timeout |
| Footer year | `document.getElementById('year').textContent = new Date().getFullYear()` |

## Page Sections (in order)

1. **Navigation** — fixed sticky navbar with responsive hamburger menu
2. **Hero** — welcome section with CTA buttons
3. **About** — instructor bio, credentials, philosophy quote
4. **Services** — four service cards (Ashtanga Yoga, Ayurveda Counseling, Mind-Body Wellness, 3-Day Intensive)
5. **Schedule** — tabbed view (Online Classes / Consultations) with pricing
6. **Testimonials** — three review cards with star ratings
7. **Contact** — contact info, payment methods (Zelle/Venmo), contact form
8. **Footer** — copyright with dynamic year

## Guidelines for AI Assistants

- All changes go in `index.html` — do not split into separate CSS/JS files unless explicitly asked
- Preserve the existing color palette via CSS custom properties; do not hardcode color values
- Maintain kebab-case for CSS classes and camelCase for JS functions
- Keep responsive behavior intact — test changes against the 768px breakpoint
- The site has no build step; changes take effect immediately on browser refresh
- There are no tests to run — verify changes by reviewing the HTML structure and inspecting in a browser
