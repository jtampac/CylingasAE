# Cylingas — Corporate Website

**Premium Industrial Corporate site for Cylingas Company L.L.C.**
EPC · Fabrication · Storage Tanks · Pressure Vessels — *Engineering Industrial Excellence Since 1974.*

A production-ready, multi-page static website (HTML5 / CSS3 / vanilla JS). No build step or dependencies required — open `index.html` or deploy the folder to any static host (Netlify, Vercel, S3/CloudFront, Nginx, Apache).

---

## 1. Sitemap

```
Home (index.html)
├── About Us (about.html) ............ Company info · Vision/Mission · Legacy timeline · MD message · Shareholders
├── Services (services.html) ......... 10 capabilities in executive format + delivery model
│   ├── EPC Projects (epc-projects.html)
│   ├── Shop Fabrication (shop-fabrication.html)
│   ├── Engineering & Design (engineering-design.html)
│   └── Operations & Maintenance (operations-maintenance.html)
├── Projects (projects.html) ......... Filterable portfolio (7 categories) + statistics
├── Facilities & Equipment (facilities.html)
├── Certifications & QHSE (certifications.html)
├── Careers (careers.html)
└── Contact Us (contact.html)
```

The brief's "Projects Portfolio" and "EPC Projects" pages are both delivered: `projects.html` is the filterable master portfolio; `epc-projects.html` is the EPC capability deep-dive.

## 2. UX Strategy

- **Audience:** procurement leads, project directors and engineers at operators (ADNOC, ENOC), international EPC contractors (Técnicas Reunidas, Tecnimont, NMDC), and government clients. They scan for **credibility signals** first — certifications, scale, named projects.
- **Primary journey:** Home → Services/Capability → Projects → Contact (Request a Proposal). Every page ends with a conversion CTA band.
- **Trust-first information hierarchy:** stamps & standards surfaced in the top bar on *every* page; animated statistics establish scale immediately; real client logos and named projects provide proof.
- **Low cognitive load:** one accent colour (gold) reserved for actions and key figures; technical mono labels orient the reader; generous negative space conveys an executive, unhurried confidence.
- **Accessibility:** semantic landmarks (`header`/`main`/`footer`/`nav`), skip-friendly focus states, `aria-current` on active nav, `prefers-reduced-motion` disables all animation, AA-contrast text on dark surfaces.

## 3. Visual Design System

| Token group | Decision |
|---|---|
| **Direction** | Premium Industrial Corporate — refined, restrained, "billion-dirham asset" gravitas. No SaaS gloss, no rounded toy cards, no bright colour. |
| **Surfaces** | Layered dark navy → ink → steel gradients; decorative blueprint grid (masked) for engineering texture. |
| **Corners** | 2px radius (effectively square) — industrial, not consumer. |
| **Motion** | Subtle only: staggered scroll reveals, counter animations, image zoom + gold underline on hover. Fully disabled under reduced-motion. |
| **Signature details** | Gold corner-brackets on framed media, mono "eyebrow" kickers with rule, square gold list markers, hairline dividers. |

### 4. Colour Palette
```
Ink / base        #070B11      Navy            #0B1521 / #0F1E30 / #142A42
Steel             #1C2C3F      Silver (text)   #9AA9BC / #C2CDDA
Paper (light)     #F4F6F9      White           #FBFCFE
Gold accent       #C2A05A  →  #D9BD7E (hover)  ·  used sparingly for actions & figures
Hairlines         rgba(176,196,222, .12–.20)
```

### 5. Typography System
- **Display / headings —** *Archivo* (700–900): confident geometric grotesque, industrial authority.
- **Body —** *IBM Plex Sans* (300–600): engineering pedigree, highly legible.
- **Technical labels / eyebrows / data —** *IBM Plex Mono*: codes, stats and kickers read like a spec sheet.
- Fluid `clamp()` type scale; tight tracking on display, wide tracking on mono labels.

### 6. Wireframe / Layout Notes
- **Header:** sticky glass nav over a mono utility top-bar (certifications + phone numbers). Collapses to full-screen mobile menu < 900px.
- **Home:** cinematic full-bleed hero (image + gradient + blueprint grid) → 4-up animated stat bar → company split → why-us features → 4 core segments → 6 featured projects → industries → client logos → CTA band.
- **Interior pages:** shorter image hero with breadcrumb → content sections alternating navy/steel/ink surfaces → CTA band.
- **Projects:** stat bar → category filter chips → responsive 3-up card grid (image, category tag, client/location/scope/sector).
- **Contact:** two-column — enquiry form (client-side demo) + offices (Dubai / Abu Dhabi / Fujairah).

### 7–8. Homepage & Page Structures
Implemented in code — see the corresponding `.html` files. All pages share the generated header/footer for consistency.

### 9. Production Code
- `assets/css/styles.css` — full design system & components
- `assets/js/main.js` — nav, scroll reveal (IntersectionObserver), animated counters, project filtering, demo form
- `build.py` — static generator (regenerate all pages: `python3 build.py`)

---

## Notes for going live
1. **Imagery** currently references the existing Cylingas media library for an authentic preview. Before launch, replace with optimised, licensed assets (WebP/AVIF, `srcset`) hosted on your CDN.
2. **Project metadata** (client / location / scope / sector) is drawn from public project names and should be **verified and finalised by Cylingas** before publication.
3. **Contact form** is a front-end demo; wire `#enquiry-form` to your mail service or backend endpoint.
4. Add real certificate scans on the QHSE page and live vacancies on Careers as needed.
