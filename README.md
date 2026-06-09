# Elite Physio Care — Website

**A premium physiotherapy website for Dr. Vaishnavi Ashokkumar Kadam, BPT**  
Home physiotherapy & online consultations · Pune, Maharashtra

---

## Overview

Elite Physio Care is a single-file, production-ready HTML website designed as a premium healthcare brand. The visual identity draws from editorial luxury wellness — large typography, deep teal tones, alternating section backgrounds, and intentional motion. It is built to feel custom-designed, not templated.

---

## Live File

| File | Description |
|------|-------------|
| `elite-physio-care.html` | Full website — self-contained, no dependencies except CDN fonts + GSAP |

Open the HTML file directly in any browser to preview. No build step required.

---

## Design System

### Typography
| Role | Font |
|------|------|
| Display / Headings | Cabinet Grotesk (800, 900) |
| Body | Switzer / Inter (300–500) |
| UI Labels | Inter (500–600) |

### Color Palette
| Name | Hex | Usage |
|------|-----|-------|
| Deep Medical Teal | `#0f5048` | Primary brand, hero CTA, footer |
| Teal Light | `#1aaa95` | Accents, floats, highlights |
| Teal Dark | `#0a2e2b` | Dark section backgrounds |
| Teal Accent | `#2ecab3` | Stats, counters, eyebrow labels |
| Sage Green | `#96b89a` | Soft UI accents |
| Off-White | `#FAFAF8` | Main page background |
| Stone | `#f5f3ef` | Alternating section backgrounds |
| Ink | `#1a1610` | Primary text |
| Muted | `#6b6560` | Secondary text, descriptions |

### Section Backgrounds (alternating)
```
Hero        → #FAFAF8 (off-white)
About       → #0a2e2b (deep teal dark)
Services    → #FAFAF8
Conditions  → #f5f3ef (stone)
Trust       → #FAFAF8
Journey     → #0a2e2b
Testimonials→ #f5f3ef
Booking     → #FAFAF8
Footer      → #1a1610
```

---

## Sections

### 1. Navigation
- Fixed top bar, transparent on load
- Frosted glass (`backdrop-filter: blur`) on scroll
- Mobile: hides nav links, keeps CTA
- Smooth scroll to all anchor sections

### 2. Hero
- Full-viewport editorial layout
- Animated headline: *"Recovery Shouldn't Require a Journey."*
- Floating trust chips: BPT Qualified · 50+ Patients · Home Visits
- Doctor avatar card with metric floats (50+ patients, 2 yrs experience)
- Staggered entrance animations (200ms → 900ms delay sequence)
- Subtle GSAP parallax on background radial shapes

### 3. About — The Story
- Dark teal background, editorial narrative layout
- 2-column: brand story left, credentials timeline right
- Animated stat counters: 50+, 2, 8, 100% (trigger on scroll)
- Timeline: BPT → Pune University → Dhole Patil College → Elite Physio Care

### 4. Services & Pricing
- Three full-width immersive panels (not cards)
- Each panel: large content column + visual pattern column
- Pricing displayed prominently

| Service | Price |
|---------|-------|
| Online Consultation | ₹399 / session |
| Home Visit | ₹599 / visit |
| Monthly Recovery Program | ₹6,099 / 12 sessions ⭐ Recommended |

### 5. Conditions Treated
- 4-column responsive grid
- Hover: lift + top teal border reveal animation
- 8 conditions: Back Pain, Neck Pain, Knee Pain, Arthritis, Frozen Shoulder, Sports Injuries, Slip Disc, Stroke Rehabilitation

### 6. Why Patients Stay
- Replaces generic "Why Choose Us"
- Split layout: narrative + patient quote left, feature list right
- 6 features with hover slide-in effect

### 7. Patient Journey
- Dark section, 6-step horizontal timeline
- Scroll-triggered progress line animation
- Steps activate sequentially on viewport entry

### 8. Testimonials
- Editorial mixed layout (no plain card grid)
- 3 real-feeling patient stories
- Large dark main quote + secondary white + teal highlight

### 9. Booking
- Minimal 4-field form: Name, Phone, Condition, Consultation Type
- Form submission opens WhatsApp with pre-filled message
- Two direct CTAs: WhatsApp + Call
- Sticky floating WhatsApp button + phone button on all pages

### 10. Footer
- 4-column: Brand · Services · Conditions · Contact
- Schema.org structured data (MedicalBusiness + Physician)

---

## Animation System

| Element | Animation | Trigger |
|---------|-----------|---------|
| Hero elements | Staggered fade + translateY | Page load |
| Background shapes | Subtle parallax | GSAP ScrollTrigger |
| All sections | Fade + translateY / translateX | IntersectionObserver |
| Stat counters | Count up (eased) | IntersectionObserver |
| Journey timeline | Progress line grows | IntersectionObserver |
| Condition cards | Lift + border reveal | CSS hover |
| Trust features | Slide right | CSS hover |
| All CTAs | Scale 0.97–1.0 | CSS hover/active |

**Animation principles followed:**
- Hardware-accelerated transforms only (`translate`, `opacity`, `scale`)
- No excessive parallax, no bouncing, no spinning
- 60 FPS maintained
- `prefers-reduced-motion` can be added — all transitions use CSS

---

## SEO

Built-in meta tags and Schema markup:

```
Title:    Elite Physio Care — Dr. Vaishnavi Kadam | Home Physiotherapy Pune
Keywords: physiotherapist Pune, home physiotherapy Pune, physiotherapy at home,
          online physiotherapy consultation, Elite Physio Care, Dr Vaishnavi Kadam
Schema:   MedicalBusiness + Physician (JSON-LD)
```

---

## Customisation Checklist

Before going live, update the following:

- [ ] Replace all `XXXXXXXXXX` with Dr. Vaishnavi's actual phone number
- [ ] Replace the doctor avatar (`VK` initials circle) with a real photograph
- [ ] Update the WhatsApp link: `https://wa.me/91[ACTUAL_NUMBER]`
- [ ] Update Schema markup URL to actual domain
- [ ] Add Google Analytics / Meta Pixel if needed
- [ ] Update `<link rel="canonical">` with production URL
- [ ] Add favicon

---

## Migrating to Next.js 15

The file is structured to make Next.js migration straightforward:

```
src/
├── app/
│   ├── layout.tsx          ← move <head> fonts + schema here
│   └── page.tsx            ← main page component
├── components/
│   ├── Nav.tsx
│   ├── Hero.tsx
│   ├── About.tsx
│   ├── Services.tsx
│   ├── Conditions.tsx
│   ├── Trust.tsx
│   ├── Journey.tsx
│   ├── Testimonials.tsx
│   ├── Booking.tsx
│   └── Footer.tsx
└── styles/
    └── globals.css         ← paste :root variables + base styles
```

**Recommended packages:**
```bash
npm install framer-motion gsap @gsap/react
```

Replace `IntersectionObserver` reveals with `framer-motion`'s `whileInView` for cleaner React code.

---

## Tech Stack (current)

| Layer | Technology |
|-------|-----------|
| Markup | Semantic HTML5 |
| Styling | Custom CSS (CSS variables, Grid, Flexbox) |
| Fonts | Google Fonts CDN (Cabinet Grotesk, Switzer, Inter) |
| Animation | GSAP 3.12 + ScrollTrigger (CDN), native IntersectionObserver |
| Forms | WhatsApp deep-link (no backend required) |
| SEO | JSON-LD Schema.org MedicalBusiness |

---

## Browser Support

Chrome 90+, Firefox 90+, Safari 14+, Edge 90+  
Mobile: iOS Safari 14+, Chrome Android 90+

---

## Credits

**Design & Development:** AI-assisted, custom-built  
**Brand:** Elite Physio Care  
**Practitioner:** Dr. Vaishnavi Ashokkumar Kadam, BPT — Dhole Patil College of Physiotherapy, Pune University  
**Location:** Pune, Maharashtra, India
