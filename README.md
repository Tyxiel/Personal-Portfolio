# tyxiel-personal-portfolio

> 🌐 Personal portfolio showcasing projects and skills. Built for the [freeCodeCamp Responsive Web Design Certification](https://www.freecodecamp.org/certification/tyxiel/responsive-web-design).

[🇧🇷 Português](#-visão-geral-pt) | [🇺🇸 English](#-overview-en)

---

## 📋 Table of Contents

- [Visão Geral (PT)](#-visão-geral-pt)
- [Overview (EN)](#-overview-en)
- [Tech Stack](#-tech-stack)
- [Prerequisites](#-prerequisites)
- [Getting Started](#-getting-started)
- [Architecture](#-architecture)
- [Deployment](#-deployment)
- [Troubleshooting](#-troubleshooting)
- [Contributing](#-contributing)
- [License](#-license)

---

## 🇧🇷 Visão Geral (PT)

Este é um portfólio pessoal estático desenvolvido para apresentar projetos e habilidades técnicas. O site é totalmente responsivo, acessível e otimizado para performance, sem dependências de build ou frameworks complexos.

### Principais Funcionalidades

- ✅ Design responsivo (mobile-first)
- ✅ Navegação com menu dropdown animado
- ✅ Ícones dinâmicos com BoxIcons (hover effects)
- ✅ Seções: Welcome, Projects, Contact
- ✅ Acessibilidade: ARIA labels, semântica HTML5
- ✅ Performance: CSS variables, preload de assets, scroll suave
- ✅ Deploy automático via GitHub Pages

---

## 🇺🇸 Overview (EN)

This is a static personal portfolio built to showcase projects and technical skills. The site is fully responsive, accessible, and performance-optimized, with no build dependencies or complex frameworks.

### Key Features

- ✅ Responsive design (mobile-first)
- ✅ Animated dropdown navigation
- ✅ Dynamic BoxIcons with hover effects
- ✅ Sections: Welcome, Projects, Contact
- ✅ Accessibility: ARIA labels, semantic HTML5
- ✅ Performance: CSS variables, asset preloading, smooth scrolling
- ✅ Auto-deploy via GitHub Pages

---

## 🛠 Tech Stack

| Category | Technology | Version/Purpose |
|----------|-----------|-----------------|
| **Markup** | HTML5 | Semantic structure, ARIA attributes |
| **Styling** | CSS3 | CSS Variables, Grid, Flexbox, Media Queries |
| **Interactivity** | Vanilla JavaScript | DOM manipulation, event listeners (embedded) |
| **Icons** | BoxIcons | CDN via `unpkg.com` |
| **Hosting** | GitHub Pages | Static site deployment |
| **License** | GNU AGPL v3 | Copyleft license for network software |

### Why This Stack?

- **Zero build step**: Edit `.html`/`.css` and refresh — no compilation needed.
- **Maximum compatibility**: Works in all modern browsers without transpilation.
- **Lightweight**: ~15KB CSS + ~3KB JS embedded = fast load times.
- **Educational**: Built to meet freeCodeCamp certification requirements.

---

## 📦 Prerequisites

| Tool | Version | Purpose | Install Command |
|------|---------|---------|----------------|
| **Web Browser** | Chrome 90+, Firefox 88+, Safari 14+ | Render and test the site | [Download](https://www.google.com/chrome/) |
| **Text Editor** | Any (VS Code recommended) | Edit source files | [VS Code](https://code.visualstudio.com/) |
| **Git** | 2.30+ (optional) | Clone repo and manage versions | `sudo apt install git` / `brew install git` |
| **Node.js** | Not required | — | — |

> 💡 **No package manager, bundler, or runtime needed.** This is a pure static site.

---

## 🚀 Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/tyxiel/tyxiel-personal-portfolio.git
cd tyxiel-personal-portfolio
```

### 2. Open Locally

**Option A: Direct file open (quick test)**
```bash
# macOS
open index.html

# Linux
xdg-open index.html

# Windows
start index.html
```

**Option B: Local server (recommended for accurate testing)**
```bash
# Python 3
python3 -m http.server 8000

# Then open: http://localhost:8000

# Or with Node.js (if installed)
npx serve .
```

### 3. Verify Functionality

Check these interactive elements:

| Element | Expected Behavior |
|---------|------------------|
| ☰ Dropdown menu (top-left) | Expands on click/hover, rotates icon 90° |
| 🔗 Navigation links | Smooth scroll to section, active state highlighting |
| 🖱️ Icon hover effects | BoxIcons switch from regular to solid variant |
| 📱 Responsive layout | Grid collapses to single column on mobile (<768px) |
| ♿ Keyboard navigation | Tab through links, focus indicators visible |

### 4. Customize (Optional)

**Update contact links** in `index.html`:
```html
<!-- Find and replace placeholder values -->
<a href="mailto:your.email@example.com">  <!-- Your email -->
<a href="https://linkedin.com/in/tyxiel">  <!-- Your LinkedIn -->
```

**Change color scheme** in `styles.css`:
```css
:root {
  --color-pink: #e6beae; /* Primary accent */
  --color-darker: #343a40; /* Dark background */
  /* Add or modify variables as needed */
}
```

**Add a new project** in the `#projects` section:
```html
<a href="YOUR_PROJECT_URL" target="_blank" rel="noopener noreferrer">
  <img src="YOUR_IMAGE_URL" alt="Descriptive alt text" />
  <p class="project-tile" aria-hidden="true">Project Name</p>
</a>
```

---

## 🏗 Architecture

### Directory Structure

```
tyxiel-personal-portfolio/
├── index.html          # Main entry point + embedded JavaScript
├── styles.css          # All styles (CSS variables, responsive rules)
├── README.md           # This documentation
└── LICENSE             # GNU AGPL v3 license text
```

### File Responsibilities

#### `index.html`
- **Structure**: Semantic HTML5 with ARIA labels for accessibility
- **Navigation**: Fixed dropdown menu with JavaScript toggle
- **Content Sections**:
  - `#welcome-section`: Hero with profile link and title
  - `#projects`: Grid of project cards with external links
  - `#contact`: Contact methods with icon buttons
- **Embedded JavaScript** (`<script>` in `<head>`):
  ```js
  // Dropdown toggle with click-outside-close
  // Icon hover effects (BoxIcons regular ↔ solid)
  // Event delegation for nav links
  ```

#### `styles.css`
- **Design System**: CSS custom properties (`--color-*`) for theming
- **Layout**: CSS Grid for projects, Flexbox for navigation/contact
- **Responsive Breakpoints**:
  ```css
  /* Mobile-first base styles */
  /* Tablet: @media (min-width: 768px) */
  /* Desktop: @media (min-width: 1024px) */
  ```
- **Accessibility**:
  - `prefers-reduced-motion` support
  - Focus indicators, sufficient color contrast
  - `aria-hidden` for decorative text

### Request Flow (Static Site)

```
User opens index.html
       ↓
Browser parses HTML → loads styles.css → executes embedded JS
       ↓
DOM fully rendered → event listeners attached
       ↓
User interacts → JS updates classes/styles → visual feedback
```

### CSS Architecture Highlights

```css
/* 1. CSS Variables for maintainability */
:root {
  --color-lightest: #f8f9fa;
  --color-darkest: #212529;
  /* ... 8 total variables */
}

/* 2. Mobile-first responsive grid */
#projects main {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
}

/* 3. Hover effects with transforms */
#projects main > a:hover {
  transform: translateY(-9px) translateX(-15px);
  box-shadow: 15px 9px var(--color-darkest);
}

/* 4. Reduced motion preference */
@media (prefers-reduced-motion: reduce) {
  * { transition: none !important; }
}
```

---

## 🔐 Environment Variables

**None required.** This is a fully static site with no backend, API calls, or server-side rendering.

> ⚠️ **Note**: The email link `mailto:your.email@example.com` is a placeholder. Update it directly in `index.html` before deployment.

---

## ⚙️ Available Scripts

| Command | Description | Use Case |
|---------|-------------|----------|
| `python3 -m http.server 8000` | Start local dev server | Test responsive behavior, avoid CORS issues |
| `npx serve .` | Alternative local server (Node) | Quick preview with clean URLs |
| `open index.html` | Open file directly in browser | Fastest local testing (limited features) |
| `git add . && git commit -m "msg"` | Stage and commit changes | Version control workflow |
| `git push origin main` | Deploy to GitHub Pages | Trigger auto-deploy (if configured) |

### GitHub Pages Deployment Workflow

```bash
# 1. Ensure you're on the main branch
git checkout main

# 2. Commit your changes
git add .
git commit -m "feat: update contact email"

# 3. Push to trigger deployment
git push origin main

# 4. Wait ~1-2 minutes, then visit:
# https://tyxiel.github.io/tyxiel-personal-portfolio/
```

> 🔄 **Auto-deploy**: GitHub Pages rebuilds automatically on push to `main`. No manual steps needed.

---

## 🧪 Testing

### Manual Testing Checklist

```markdown
- [ ] Site loads without console errors
- [ ] Dropdown menu toggles on click AND hover
- [ ] All project links open in new tab (target="_blank")
- [ ] Contact icons have visible hover states
- [ ] Layout adapts to mobile (≤768px), tablet, desktop
- [ ] Keyboard navigation works (Tab/Shift+Tab)
- [ ] Color contrast meets WCAG AA (text on background)
- [ ] `prefers-reduced-motion` disables animations
```

### Accessibility Audit (Optional)

```bash
# Install Lighthouse CLI
npm install -g @lhci/cli

# Run audit
lhci autorun --collect.url=http://localhost:8000
```

Or use Chrome DevTools → Lighthouse tab → Generate report.

### Cross-Browser Testing

Test in:
- Chrome/Edge (Chromium)
- Firefox
- Safari (macOS/iOS)
- Mobile Chrome/Safari (via device emulator or physical device)

---

## 🌍 Deployment

### GitHub Pages (Recommended)

**Automatic Setup** (if repo name is `username.github.io`):
1. Go to repo **Settings** → **Pages**
2. Set **Source** to `Deploy from branch`
3. Select branch: `main`, folder: `/ (root)`
4. Save → Wait for deployment URL

**Manual Configuration** (`_config.yml` not required for static sites):
```yaml
# Optional: _config.yml for Jekyll compatibility (not used here)
theme: null
```

### Alternative: Netlify (Drag & Drop)

```bash
# 1. Build (no build step needed)
# 2. Drag the entire folder to Netlify Drop
# 3. Site is live instantly
```

### Alternative: Vercel

```bash
# Install Vercel CLI
npm i -g vercel

# Deploy
vercel --prod
```

### Custom Domain (Optional)

1. Add `CNAME` file to repo root:
   ```
   yourdomain.com
   ```
2. Configure DNS with your registrar:
   ```
   Type: CNAME
   Name: www
   Value: username.github.io
   ```

---

## 🔧 Troubleshooting

### ❌ Dropdown menu not working

**Cause**: JavaScript not executing due to file open via `file://` protocol.

**Solution**:
```bash
# Use a local server instead of direct file open
python3 -m http.server 8000
# Then visit http://localhost:8000
```

### ❌ Icons not loading

**Cause**: BoxIcons CDN blocked or network issue.

**Solution**:
1. Check network tab for failed requests to `unpkg.com`
2. Verify internet connection
3. Fallback: Download BoxIcons locally and update the `<link>` tag

### ❌ Layout broken on mobile

**Cause**: Browser cache serving old CSS.

**Solution**:
```bash
# Hard refresh
Ctrl+F5 (Windows) / Cmd+Shift+R (macOS)

# Or clear cache in DevTools → Application → Clear storage
```

### ❌ GitHub Pages showing 404

**Cause**: Deployment not triggered or branch misconfigured.

**Solution**:
1. Go to **Settings** → **Pages** in GitHub repo
2. Confirm branch is `main` and folder is `/ (root)`
3. Check **Actions** tab for deployment status
4. Wait up to 2 minutes for propagation

### ❌ Email link not opening mail client

**Cause**: Placeholder email not replaced.

**Solution**:
```html
<!-- In index.html, update: -->
<a href="mailto:your.email@example.com">
<!-- To: -->
<a href="mailto:real@email.com">
```

---

## 🤝 Contributing

Contributions are welcome! This project follows the [GNU AGPL v3](LICENSE) license.

### How to Contribute

1. Fork the repository
2. Create a feature branch: `git checkout -b feat/amazing-feature`
3. Commit changes: `git commit -m 'feat: add amazing feature'`
4. Push to branch: `git push origin feat/amazing-feature`
5. Open a Pull Request

### Contribution Guidelines

- ✅ Keep changes focused and atomic
- ✅ Test responsiveness manually before submitting
- ✅ Update documentation if adding new features
- ✅ Follow existing code style (no semicolons in JS, CSS variables for colors)
- ✅ Use descriptive commit messages ([Conventional Commits](https://www.conventionalcommits.org/) encouraged)

### Reporting Issues

Use the [GitHub Issues](https://github.com/tyxiel/tyxiel-personal-portfolio/issues) tab with:
- Clear title and description
- Steps to reproduce
- Expected vs actual behavior
- Browser/device information
- Screenshots if visual issue

---

## 📜 License

Distributed under the **GNU Affero General Public License v3.0**. See [`LICENSE`](LICENSE) for full text.

### What This Means

| You Can | You Must |
|---------|----------|
| ✅ Use commercially | 🔓 Disclose source code if modified |
| ✅ Modify and distribute | 🔗 Provide source to network users |
| ✅ Patent use | 📝 Include license and copyright |
| ✅ Private use | 🔄 Share improvements under same license |

> ℹ️ **AGPL Specific**: If you host a modified version on a server, you must make the source code available to users who interact with it over a network.

### Quick Start with License Compliance

```bash
# When forking/modifying:
# 1. Keep LICENSE file intact
# 2. Add your copyright to modified files:
<!-- Copyright (C) 2024 Your Name -->

# 3. If deploying modified version publicly:
#    - Provide a "Source" link to your fork
#    - Or include source code download option
```

---

## 🙏 Acknowledgments

- [freeCodeCamp](https://www.freecodecamp.org/) — For the curriculum and certification
- [BoxIcons](https://boxicons.com/) — For the beautiful, free icon set
- [GitHub Pages](https://pages.github.com/) — For hassle-free static hosting
- [MDN Web Docs](https://developer.mozilla.org/) — For reliable web documentation

---

> 💡 **Pro Tip**: Bookmark this README. When in doubt, re-read the "Getting Started" or "Troubleshooting" sections. When contributing, always test on mobile first.

*Built with ❤️ by [Tyxiel](https://github.com/tyxiel)*
