---
name: frontend-design
description: >
  Build distinctive, production-grade frontend websites and UI components with
  high design quality. Optimized for business/local service sites and landing pages.
  Mobile-first always. Use when asked to create, style, or improve any web page,
  landing page, component, or web application. Triggers: "make it look better",
  "redesign", "beautify", "modern UI", "responsive", "mobile friendly", or any
  request for HTML/CSS/JS, React, Next.js, Tailwind output.
  DO NOT use for backend-only tasks, API design, or database work.
---

# Frontend Design Skill (Mobile-First Edition)

Build memorable, production-grade frontends. Every output must look like a
human designer built it — not an AI. Optimized for business sites and landing
pages deployed on Vercel, Netlify, or Cloudflare.

---

## Before You Write One Line of Code

Answer these internally. Do NOT skip:

- **What is this?** (local business, landing page, portfolio, app?)
- **Who sees it?** (local customers on phones, or desktop professionals?)
- **What mood?** Pick ONE: minimal / bold / luxury / editorial / warm / brutalist
- **What does the user do first?** (call, book, buy, read — one action only)
- **What's the primary device?** Assume mobile unless told otherwise.

If the user hasn't specified — make a decisive choice. Never default to generic.

---

## Step 1: Mobile-First Is Non-Negotiable

Every layout starts at 320px and scales UP. Never design desktop-first and
shrink down. That approach produces broken mobile experiences.

### Breakpoint System (always use these):
```css
/* Mobile base: 320px — write all base styles here */
/* Small: 480px  */ @media (min-width: 480px) { }
/* Tablet: 768px */ @media (min-width: 768px) { }
/* Desktop: 1024px */ @media (min-width: 1024px) { }
/* Wide: 1280px */ @media (min-width: 1280px) { }
```

### Mobile Rules — enforce every time:
- Minimum tap target: 44x44px (buttons, links, icons)
- Font size: never below 16px for body text on mobile
- Line height: 1.5–1.7 for body, 1.1–1.3 for headings
- Padding: minimum 16px horizontal on mobile (never let content touch screen edge)
- No horizontal scroll — ever
- Test mentally at 320px, 375px, 414px before declaring done
- Hero sections: full viewport height on mobile, text must be readable without zoom
- Navigation: hamburger or bottom nav on mobile — never a cramped horizontal menu
- Images: always width: 100%, height: auto — never fixed pixel heights on mobile
- Forms: inputs minimum 48px height, full width on mobile
- Avoid hover-only interactions — mobile has no hover

---

## Step 2: Pick Your Stack (Mixed Projects)

Since the stack varies per project, choose based on these rules:

| Situation | Use This |
|---|---|
| Simple business site, no dynamic data | Plain HTML/CSS/JS (single file) |
| Landing page with form or API call | HTML/CSS/JS + fetch() |
| Multi-page site, reusable components | Next.js (App Router) |
| Quick prototype to show client | Single HTML file always |
| Needs Supabase/auth/database | Next.js + Supabase client |

**Default: single HTML file** unless there's a clear reason not to.
Single files are easier to demo, deploy instantly on Netlify drag-and-drop,
and impress clients faster.

---

## Step 3: Design Direction

### Typography — never use generic fonts:
- BANNED: Inter, Roboto, Arial, system-ui as display font
- For luxury/beauty/editorial: Cormorant Garamond, Playfair Display, DM Serif Display
- For bold/modern: Space Grotesk, Syne, Outfit
- For clean business: Plus Jakarta Sans, DM Sans, Nunito
- Always load from Google Fonts with `display=swap`
- Always pair: one display font (headings) + one clean font (body)

### Color — be decisive:
- BANNED: purple-to-blue gradients, generic SaaS blue (#3B82F6), flat gray everything
- Define ALL colors as CSS custom properties at :root
- Always include: --color-bg, --color-text, --color-accent, --color-surface
- High contrast is better than pretty pastels
- For dark themes: background never pure #000000 — use #0A0A0A or #111111

### Layout:
- Break the grid at least once per page
- Use asymmetry, overlap, or unexpected whitespace
- Avoid cookie-cutter equal-height card grids
- On mobile: single column always, generous vertical spacing

---

## Step 4: Code Standards

```css
/* Always start your CSS with this reset */
*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
html { font-size: 16px; scroll-behavior: smooth; }
body { -webkit-font-smoothing: antialiased; }
img, video { max-width: 100%; height: auto; display: block; }
```

**Every project must have:**
- [ ] Semantic HTML (header, main, section, nav, footer — not just divs)
- [ ] CSS custom properties for all theme values
- [ ] Mobile-first responsive (320px base)
- [ ] Tap targets ≥ 44px
- [ ] Smooth transitions on interactive elements (200–300ms ease)
- [ ] Focus states visible (outline or custom style — never `outline: none` without replacement)
- [ ] Alt text on all images
- [ ] One scroll-reveal or entrance animation (IntersectionObserver, not heavy libraries)
- [ ] Sticky or accessible navigation
- [ ] Fast: no unused CSS, no render-blocking scripts, images lazy-loaded

---

## Step 5: Business Site Specific Rules

For local business / salon / service sites (your most common project type):

**Must-have sections and mobile behavior:**
1. **Navbar** — sticky, logo left, hamburger right on mobile
2. **Hero** — full viewport, huge headline, ONE CTA button, readable on 320px
3. **Services** — single column on mobile, 2-col on tablet, 3-col on desktop
4. **About** — stacked on mobile (image first, text below)
5. **Contact** — phone number as `<a href="tel:...">` — clickable on mobile
6. **Map** — iframe, 100% width, min 250px height on mobile
7. **Footer** — minimal, social links, copyright

**CTA buttons on mobile:**
- Full width on mobile (width: 100%)
- Never small or centered with wide margins
- Phone CTA should use `href="tel:+995XXXXXXXXX"`

---

## Step 6: Deployment Checklist (Vercel / Netlify / Cloudflare)

Before handing off any file:
- [ ] No hardcoded API keys anywhere in frontend code
- [ ] Environment variables used for all secrets (see CLAUDE.md for setup)
- [ ] Images optimized or using external URLs (Unsplash, CDN)
- [ ] No console.log() left in production code
- [ ] Meta tags present: title, description, og:image
- [ ] Favicon referenced
- [ ] 404 page exists for multi-page sites

---

## Output Format

- Single HTML file for demos and client previews
- Next.js component structure for real projects
- Always include a comment block at top:
```html
<!-- 
  Project: [name]
  Stack: [what you used]
  Design direction: [one word mood]
  Mobile-first: YES
-->
```
- Never explain the code unless asked
- Never apologize for design choices — commit to them

---

## What Makes Good Output Here

You're building for business owners in Georgia (Tbilisi) who will judge the
site on a phone screen first. The demo must be impressive enough in 5 seconds
on mobile for them to say "I want this." Prioritize visual impact, fast loading,
and a clear booking/contact action above everything else.
