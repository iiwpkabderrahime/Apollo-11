# 🚀 Apollo 11 — Mission Website

A fully responsive, multi-section tribute website dedicated to the **Apollo 11 Moon Landing** — humanity's greatest achievement in space exploration. Built with pure HTML and CSS, NO JavaScript or frameworks.

---

## 🌐 Live Preview

> Open `index.html` in any modern browser to view the project locally.

---

## 📁 Project Structure

```
Apollo11-Mission/
├── index.html       # Main HTML file
├── styles.css       # Desktop styles & animations
├── Tablet.css       # Tablet responsive styles (≤ 1200px)
├── mobile.css       # Mobile responsive styles (≤ 699px)
└── Images/          # All local images and SVG assets
    ├── Apollo11-Rocket-Background-PC.jpg
    ├── Overview-image.png
    ├── Neil-Armstrong.jpg
    ├── Buzz0Aldrin.jpg
    ├── Michael Collins.webp
    ├── Moon2.png
    ├── Transparent Moon.png
    ├── Location-svg.svg
    └── Steps-Svg.svg
```

---

## 📌 Sections

| Section | Description |
|---|---|
| **Hero** | Full-screen rocket launch background with mission date and animated scroll CTA |
| **Overview** | Mission summary, key stats — distance, duration, time on the Moon |
| **Crew** | Profile cards for Armstrong, Aldrin, and Collins with roles and traits |
| **Landing** | Touchdown moment at Tranquility Base with quote and site details |
| **Impact** | Scientific legacy, moon rock stats, and a link to NASA research data |
| **Timeline** | 4-event mission timeline from liftoff to splashdown |
| **Footer** | Apollo 11 branding, NASA link, and GitHub link |

---

## 🎨 Design System

### Color Palette

All colors are defined as CSS custom properties:

```css
:root {
  --primary:      #ffffff;    /* Main text */
  --secondarey:   #0b3d91;    /* NASA blue — buttons, accents, borders */
  --gray:         #a1a1a113;  /* Card backgrounds */
  --gray-hover:   #a1a1a13d;  /* Card hover state */
  --black:        #080808;    /* Deep black — crew section, footer */
  --black2:       #131313;    /* Page background */
  --border-color: #434652;    /* Subtle borders and dividers */
  --Light-Blue:   #7a98f1;    /* Highlights, roles, stats, links */
  --white-hd:     #e5e2e1;    /* Navbar button gradient start */
}
```

### Typography

```css
/* Headings */
font-family: "Space Grotesk", sans-serif;

/* Body */
font-family: "Inter", sans-serif;
```

Both loaded via Google Fonts `@import` in `styles.css`.

---

## 🎞️ Animations

### Keyframes

```css
@keyframes slid-in   /* Sections enter from the left */
@keyframes slid-up   /* Sections rise from below */
@keyframes flip      /* Moon image rotates on scroll */
@keyframes scrol     /* Hero scroll CTA bounces up/down */
```

### Usage Per Section

| Section | Animation | Trigger |
|---|---|---|
| Overview | `slid-in` | Scroll-driven `view()` |
| Crew | `slid-up` | Scroll-driven `view()` |
| Landing | `slid-up` | Scroll-driven `view()` |
| Impact | `slid-up` | Scroll-driven `view()` |
| Timeline | `slid-up` | Scroll-driven `view()` |
| Moon image | `flip` | Scroll-driven `view()` |
| Scroll CTA | `scrol` | Infinite alternate |

All scroll-driven animations use:
```css
animation-timeline: view();
animation-range: entry;
```

> ⚠️ Requires Chromium 115+ (Chrome, Edge). Firefox support is limited.

---

## 🧱 Layout System

### Overview Section
```css
.ovr {
  display: flex;         /* Text left, image right */
  align-items: center;
}
```

### Crew Cards
```css
/* Desktop — flex row, evenly spaced */
.images { display: flex; justify-content: space-evenly; }

/* Neil Armstrong scaled up as hero card */
.neil { transform: scale(1.16); }
.neil:hover { transform: scale(2); }

/* Tablet — Neil full width on top, Buzz & Collins below */
.images {
  display: grid;
  grid-template-areas:
    "neil neil"
    "buzz mich";
}
```

### Timeline
```css
/* Desktop */
#Timeline div { display: flex; justify-content: space-around; }

/* Tablet */
grid-template-columns: repeat(2, 1fr);

/* Mobile */
grid-template-columns: repeat(1, 1fr);
```

---

## 📱 Responsive Design

Three breakpoints, each with a dedicated CSS file:

| File | Breakpoint | Key Changes |
|---|---|---|
| `styles.css` | > 1200px (desktop) | Full flex/grid layouts, large typography |
| `Tablet.css` | ≤ 1200px | Crew grid reflows, sections stack vertically |
| `mobile.css` | ≤ 699px | Single column, nav links hidden, scaled typography |

### Notable Mobile Behaviors
- Navigation links hidden — only logo visible
- Hero padding and font size reduced
- Landing quote box loses background image, goes flat
- Impact section border and padding removed for a cleaner mobile view
- Crew cards stack vertically with Neil on top
- Timeline collapses to 1 column

---

## ✨ Special Details

**Navbar** — `backdrop-filter: blur(10px)` with semi-transparent background for a frosted glass effect over the hero image.

**Explore Button** — gradient from `--white-hd` → `--Light-Blue` → `--secondarey`, subtle `translateY` on hover.

**Neil Armstrong Card** — intentionally scaled up (`scale(1.16)`) on desktop to reflect his role as mission commander. Scales to `2x` on hover.

**Timeline Cards** — progressive border opacity using hex alpha values (`#0b3c9142` → `#0b3d91`) to create a visual intensity build toward landing day.

**Moon Image (Impact section)** — rotates using a `flip` animation tied directly to scroll position via `animation-timeline: view()`.

---

## 🛠️ Built With

- **HTML5** — Semantic elements (`<header>`, `<section>`, `<article>`, `<nav>`, `<footer>`, `<time>`)
- **CSS3** — Flexbox, Grid, custom properties, scroll-driven animations, `backdrop-filter`, `@keyframes`
- **Google Fonts** — Space Grotesk & Inter
- **No JavaScript** — Entirely static

---

## 🚀 Getting Started

1. Clone or download the repository:
   ```bash
   git clone https://github.com/iiwpkabderrahime/Apollo11-Mission.git
   ```
2. Open `index.html` in any modern browser.
3. No build step, no dependencies to install.

---

## ✍️ Author

**iiwpkabderrahime**
[GitHub](https://github.com/iiwpkabderrahime)

---

## 📄 License

Built for educational and portfolio purposes. All NASA imagery is in the public domain via [nasa.gov](https://www.nasa.gov).
