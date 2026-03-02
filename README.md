# Ragdoll Dreams 🐱

Jekyll landing page for the Ragdoll Dreams cat breeder, managed with Decap CMS and deployed to GitHub Pages.

---

## Tech Stack

| Layer | Tool |
|---|---|
| Static Site Generator | [Jekyll](https://jekyllrb.com/) |
| CMS | [Decap CMS](https://decapcms.org/) |
| Hosting | [GitHub Pages](https://pages.github.com/) |
| CSS | Custom framework (Lab 3) + Tailwind CDN |
| CI/CD | GitHub Actions |

---

## Project Structure

```
ragdoll-dreams/
├── _data/
│   ├── settings.yml        ← All site content (hero, sections, contact, footer)
│   └── navigation.yml      ← Nav menu items
├── _kittens/               ← One .md file per kitten
│   ├── seal-point.md
│   ├── blue-point.md
│   ├── lilac-point.md
│   └── flame-point.md
├── _layouts/
│   └── default.html        ← Base HTML template
├── _includes/
│   ├── nav.html
│   ├── footer.html
│   ├── mascot.html
│   └── scripts.html
├── assets/
│   ├── css/
│   │   ├── style.css       ← Lab 3 CSS framework
│   │   └── reset.css
│   └── images/             ← Upload your images here
├── admin/
│   ├── index.html          ← Decap CMS entry point
│   └── config.yml          ← CMS field definitions
├── .github/workflows/
│   └── deploy.yml          ← Auto-deploy on push to main
├── index.html              ← Main page template
├── _config.yml
└── Gemfile
```

---

## Setup Instructions

### 1. Create the GitHub Repository

```bash
git init
git add .
git commit -m "feat: initial Jekyll + Decap CMS setup"
git remote add origin https://github.com/YOUR_USERNAME/ragdoll-dreams.git
git push -u origin main
```

### 2. Configure Decap CMS

Open `admin/config.yml` and update line 2:

```yaml
backend:
  name: github
  repo: YOUR_USERNAME/ragdoll-dreams   # ← Your actual repo
  branch: main
```

Commit and push this change.

### 3. Enable GitHub Pages

1. Go to your repo → **Settings** → **Pages**
2. Under **Source**, select **GitHub Actions**
3. The first deploy will run automatically on your next push

### 4. Enable Decap CMS OAuth (GitHub backend)

Decap CMS needs OAuth to write back to your repo. The easiest free option:

**Option A — Netlify Identity (recommended even for GitHub Pages):**
1. Create a free [Netlify](https://netlify.com) account
2. Create a new site → **Import existing project** → connect your GitHub repo
3. Under **Site settings → Identity**, enable Identity
4. Under **Identity → Services**, enable **Git Gateway**
5. Add this to `admin/config.yml`:
   ```yaml
   backend:
     name: git-gateway
     branch: main
   ```

**Option B — GitHub OAuth app (self-hosted):**
Follow the [Decap CMS GitHub backend guide](https://decapcms.org/docs/github-backend/).

### 5. Add Your Images

Place your images in `assets/images/`:

```
assets/images/
├── hero.webp
├── seal.jpg
├── blue.webp
├── lilac.jpg
├── flame.jpg
└── catery.jpg
```

Then upload them via the CMS or directly via Git.

### 6. Access the CMS

Once deployed, visit:

```
https://YOUR_USERNAME.github.io/ragdoll-dreams/admin/
```

Log in with your GitHub account. You can now edit:
- ✅ Hero heading, subtitle, CTA text
- ✅ All section text (about, cattery, contact)
- ✅ Contact details (email, phone, location)
- ✅ Footer content
- ✅ Mascot message
- ✅ Navigation links
- ✅ All kitten cards (name, date, description, photo, status)
- ✅ Add / remove kittens

---

## Local Development

```bash
# Install Ruby dependencies
bundle install

# Run local dev server
bundle exec jekyll serve --livereload

# Visit http://localhost:4000
```

---

## Git Workflow (for a good commit history)

```bash
# Feature: add a new kitten
git checkout -b feat/add-flame-point-kitten
# ... make changes ...
git add _kittens/flame-point.md assets/images/flame.jpg
git commit -m "feat(kittens): add flame point kitten listing"
git push origin feat/add-flame-point-kitten
# Open a Pull Request → merge to main → auto-deploys

# Fix: update contact info
git checkout -b fix/update-phone-number
git add _data/settings.yml
git commit -m "fix(contact): update phone number"
git push origin fix/update-phone-number
```

Suggested commit prefixes: `feat:`, `fix:`, `content:`, `style:`, `chore:`

---

## What's CMS-Editable

Everything in `_data/settings.yml` and `_kittens/*.md` is editable through the Decap CMS UI without touching code:

| Content | File | CMS Section |
|---|---|---|
| Hero text & image | `_data/settings.yml` | Главный экран |
| About breed cards | `_data/settings.yml` | О рэгдоллах |
| Kittens intro text | `_data/settings.yml` | Котята |
| Cattery description | `_data/settings.yml` | Питомник |
| Contact details | `_data/settings.yml` | Контакты |
| Footer text | `_data/settings.yml` | Футер |
| Mascot message | `_data/settings.yml` | Маскот |
| Navigation links | `_data/navigation.yml` | Навигация |
| Each kitten card | `_kittens/*.md` | 🐱 Котята |
