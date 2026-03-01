## Lab 3 – Ragdoll Dreams Landing Page

This project is the solution for **Web Engineering – Lab 3**.  
It is a responsive, single–page marketing site for the fictional cattery **“Ragdoll Dreams”**.

### Features

- **Responsive layout** for desktop, tablet and mobile (custom CSS + Tailwind utility classes).
- **Hero section** with call‑to‑action button that scrolls to the contact form.
- **“Why Ragdoll” section** with four feature cards.
- **Available kittens grid** with image cards and CTA buttons.
- **Cattery section** with photo and bullet list of commitments.
- **Contact section** with form and contact information.
- **Floating mascot** SVG cat with speech bubble.
- All visible content translated to **Russian**.

### Tech stack

- Plain **HTML5**
- **CSS3** (`style.css` + `reset.css`)
- **Tailwind CSS CDN** for some typography and layout utilities (no build step)
- A small amount of **vanilla JavaScript** for the mobile navigation and mascot animation.

### Project structure

- `index.html` – main single page of the site.
- `style.css` – main custom stylesheet, including responsive breakpoints.
- `reset.css` – CSS reset (Meyer reset) to normalise browser defaults.
- `assets/` – image files used in the hero, kittens grid and cattery section.

### How to run locally

1. Clone the repository and switch to the `lab3` branch if needed.
2. Open `index.html` directly in a modern browser  
   **or** serve the folder with any simple HTTP server, for example:

   ```bash
   # from the project root
   python -m http.server 8000
   ```

   Then open `http://localhost:8000/index.html` in the browser.

No additional build tools or dependencies are required.

### Notes for grading

- The page is fully responsive down to 320px width; key breakpoints are 1024px, 768px, 375px and 320px.
- Main section headings use Tailwind typography classes to match the provided design.
- All navigation links scroll to in‑page sections, and interactive elements have reasonable accessible labels.
