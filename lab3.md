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

- The page is fully responsive down to 320px width; key breakpoints are 1024px, 768px, 375px and 320px.
- Main section headings use Tailwind typography classes to match the provided design.
- All navigation links scroll to in‑page sections, and interactive elements have reasonable accessible labels.
### Demo
<img width="1901" height="1052" alt="image" src="https://github.com/user-attachments/assets/800f51ca-8cff-4986-b61c-68c58120190a" />
<img width="1903" height="1049" alt="image" src="https://github.com/user-attachments/assets/8af992f2-e021-456a-8ac2-3cf238adcbfa" />
<img width="1901" height="1046" alt="image" src="https://github.com/user-attachments/assets/bc9ddc94-faa6-4d31-a08f-9af0d01a5042" />
<img width="1882" height="1040" alt="image" src="https://github.com/user-attachments/assets/7b28cca3-23a4-4a18-ae06-a0fbc7d0dba4" />


