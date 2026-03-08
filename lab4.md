# Lab 4 — Static Site Generator & Git CMS

**Site:** https://ragdolldreams.netlify.app
**CMS:** https://ragdolldreams.netlify.app/admin/
**Branch:** `lab4`

---

## Overview

This lab migrates the Ragdoll Dreams landing page (built in Labs 2–3) to a **Jekyll** static site generator and integrates **Decap CMS** as a Git-based content management system. All site content is editable through a Russian-language CMS admin panel without touching any code.

---

## Requirements Checklist

| Requirement | Status | Details |
|---|---|---|
| Static Site Generator | ✅ | Jekyll |
| Git-based CMS | ✅ | Decap CMS (GitHub backend) |
| Lab 3 CSS integrated | ✅ | `assets/css/style.css` + `reset.css` |
| Maximum CMS-editable content | ✅ | Every section is a separate editable collection |
| Deployed live | ✅ | Netlify — `ragdolldreams.netlify.app` |
| Decent git history | ✅ | 20+ semantic commits |

---

## Tech Stack

| Layer | Tool |
|---|---|
| Static Site Generator | [Jekyll](https://jekyllrb.com/) |
| CMS | [Decap CMS](https://decapcms.org/) with GitHub backend |
| Hosting | [Netlify](https://netlify.com) |
| CSS | Custom framework (Lab 3) + Tailwind CDN |
| Auth | GitHub OAuth via Netlify |

---

## Project Structure

```
tum-web-lab2/
├── _colors/                    ← Color category entries (used in kitten dropdown)
│   ├── seal-point.md
│   ├── blue-point.md
│   ├── lilac-point.md
│   ├── flame-point.md
│   ├── chocolate-point.md
│   └── cream-point.md
├── _data/                      ← Per-section content files (all CMS-editable)
│   ├── site_identity.yml       ← Site title & description
│   ├── navigation.yml          ← Nav menu items
│   ├── hero.yml                ← Hero heading, subtitle, CTA, image
│   ├── mobile_section.yml      ← Mobile bar text & image
│   ├── about_section.yml       ← About breed heading & feature cards
│   ├── kittens_section.yml     ← Kittens section text & UI labels
│   ├── cattery_section.yml     ← Cattery description, image, commitments
│   ├── contact_section.yml     ← Contact form labels, info, email/phone
│   ├── footer_section.yml      ← Footer headings, tagline, note
│   └── mascot_section.yml      ← Mascot speech bubble text
├── _kittens/                   ← One .md file per kitten listing
│   ├── seal-point.md
│   ├── blue-point.md
│   ├── lilac-point.md
│   └── flame-point.md
├── _layouts/
│   └── default.html            ← Base HTML template
├── _includes/
│   ├── nav.html
│   ├── footer.html
│   ├── mascot.html
│   └── scripts.html
├── assets/
│   ├── css/
│   │   ├── style.css           ← Lab 3 CSS framework
│   │   └── reset.css
│   └── images/
├── admin/
│   ├── index.html              ← Decap CMS entry point (Russian locale)
│   └── config.yml              ← CMS collections & field definitions
├── index.html                  ← Main page template
├── _config.yml
└── Gemfile
```

---

## What Is CMS-Editable

Every visible string and image on the site can be changed through the admin panel. Each section is its own independent collection:

| CMS Collection | File | Editable content |
|---|---|---|
| 🌐 Название сайта | `_data/site_identity.yml` | Title, meta description |
| 🔗 Навигация | `_data/navigation.yml` | Menu items (label + URL) |
| 🏠 Главный экран | `_data/hero.yml` | Heading, subtitle, CTA button, background image |
| 📱 Мобильная секция | `_data/mobile_section.yml` | Text, button label, thumbnail image |
| 🐱 О рэгдоллах | `_data/about_section.yml` | Section heading, all 4 feature cards |
| 🐾 Секция «Котята» | `_data/kittens_section.yml` | Heading, intro text, card UI labels |
| 🏡 Питомник | `_data/cattery_section.yml` | Heading, description, photo, commitments list |
| ✉️ Контакты | `_data/contact_section.yml` | All form labels, placeholders, email/phone/address |
| 🔻 Футер | `_data/footer_section.yml` | Column headings, tagline, copyright note |
| 🐈 Маскот | `_data/mascot_section.yml` | Mascot speech bubble text |
| 🐱 Котята | `_kittens/*.md` | Per-kitten: name, gender, color, date, photo, status |
| 🎨 Окрасы котят | `_colors/*.md` | Color category labels (used in kitten dropdown) |

---

## CMS Authentication Setup

The CMS uses the **GitHub backend** with OAuth routed through Netlify:

1. Register a GitHub OAuth App:
   - Homepage URL: `https://ragdolldreams.netlify.app`
   - Callback URL: `https://api.netlify.com/auth/done`
2. In Netlify → **Project configuration → Access & security → OAuth**:
   - Add GitHub provider with the Client ID and Client Secret

Users log in at `/admin/` via **"Login with GitHub"** — no separate passwords required.

---

## Local Development

```bash
# Install Ruby dependencies
bundle install

# Start local server with live reload
bundle exec jekyll serve --livereload

# Visit http://localhost:4000
```

> Note: the CMS admin requires the live Netlify URL for OAuth. Local preview is for site content only.

---

## Git History Summary

The branch follows conventional commits with a clear progression:

```
style:    integrate Lab 3 CSS framework
feat:     add default HTML layout + includes
feat:     add main page template wired to data files
feat:     add Decap CMS admin entry point + config
content:  add kitten listings (seal, blue, lilac, flame point)
feat:     add main Jekyll page template and Gemfile
fix:      align navigation data structure with CMS schema
feat:     make site title and description CMS-editable
feat:     make contact form labels CMS-editable
feat:     make footer headings CMS-editable
feat:     make kitten card UI strings CMS-editable
feat:     make mobile section image CMS-editable
refactor: split CMS settings into separate per-section collections
feat:     add kitten color categories and redesign kitten card
feat:     set CMS locale to Russian
docs:     add lab 4 report as lab4.md
```
