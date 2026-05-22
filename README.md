# Sigma Cutz — Premium Barbershop Website

A modern, responsive website for **Sigma Cutz**, a premium barbershop in Barrie, Ontario. Built with semantic HTML, CSS custom properties, and vanilla JavaScript for optimal performance.

## Overview

**Sigma Cutz** is Barrie's premier barbershop, offering modern fades, classic cuts, beard sculpts, hot-towel shaves, and specialized services. The website showcases the shop's expertise, services, and makes it easy for customers to book appointments.

### Design Philosophy
- **Dark theme** with luxury gold accents — premium, professional aesthetic
- **Typography-first** — serif display faces (Cinzel, Cormorant Garamond) for brand presence
- **Responsive & accessible** — works seamlessly on mobile, tablet, and desktop
- **Performance-focused** — minimal dependencies, vanilla JS, optimized assets

## Project Structure

```
Sigma-Cutz/
├── index.html              # Main website (Sigma Cutz barbershop)
├── sigma-styles.css        # Barbershop styling
├── styles.css              # (Unused — from template bundle)
├── assets/
│   ├── sigma-logo.webp     # Brand logo
│   └── yyz-logo.png        # (Template artifact)
└── README.md               # This file
```

## Key Sections

### 1. **Utility Strip** (Top Banner)
- Real-time open status with animated indicator
- Quick access to address and phone
- Google Maps and booking links

### 2. **Header** (Sticky Navigation)
- Logo with brand name and tagline ("Slay & Shine")
- Navigation links (Services, About, Reviews, Contact)
- Call-to-action button (Book on Google)
- Mobile hamburger menu with drawer navigation

### 3. **Hero Section**
- Headline: "Sharp cuts. **Sharper** presence."
- Shop tagline and value proposition
- Call-to-action buttons (Book on Google, Call)
- Featured info card with:
  - Logo display
  - Address and phone
  - Live status indicator
  - Shop hours

### 4. **Marquee Divider**
- Animated text carousel highlighting key services
- Gold background with uppercase serif type
- Runs continuously on loop

### 5. **Services Section**
Eight service cards with pricing:
- Signature Cut ($38)
- Skin Fade ($42)
- Beard Sculpt ($25)
- Hot Towel Shave ($45)
- Cut + Beard Combo ($60)
- Kids Cut / Under 12 ($28)
- Senior Cut / 65+ ($30)
- Line-Up & Edge ($18)

Each card includes:
- Service description
- Duration estimate
- Specialty indicator
- Price (CAD)

### 6. **About Section**
- Core message and shop philosophy
- Four value pillars:
  - On-time service (avg. 8 min wait)
  - Master barbers (10+ years experience)
  - Sanitized stations (sterilized between clients)
  - 4.9-star service (187+ Google reviews)

### 7. **Reviews Section**
- Google rating badge (4.9 stars, 187 reviews)
- Repeat client metric (97% last 12 months)
- Three featured testimonials with client avatars

### 8. **Contact / Booking Section**
- Shop hours table (Mon–Sun with live today marker)
- Three contact methods:
  - Phone: (705) 241-0504
  - Address: 418 Blake St, Barrie, ON L4M 1L3
  - Google Business listing link
- Embedded Google Map
- Booking CTA with two options:
  - Call for immediate confirmation
  - Book via Google Business Profile

### 9. **Footer**
- Brand summary and values
- Four-column navigation (Services, Shop, Contact)
- Instagram social link (@sigma_cutz_barrie)
- Copyright and legal links

### 10. **Mobile CTA** (Sticky Bottom)
- Quick-access call button
- Quick-access booking button
- Only visible on mobile/tablet

## Design System

### Color Palette
```css
--bg: #0A0A0A              /* Deep black background */
--bg-2: #131313            /* Elevated surfaces */
--bg-3: #1C1C1C            /* Tertiary background */
--ink: #F4EFE5             /* Off-white text */
--ink-2: #C8C0B0           /* Secondary text */
--gold: #C9A961            /* Primary accent */
--gold-2: #E0C58A          /* Bright accent */
--gold-deep: #9C7F3E       /* Dark accent */
--gold-soft: #F2DDB0       /* Soft accent */
--green: #4A9D5A           /* Status: open */
--red: #C44545             /* Status: error/alert */
```

### Typography
- **Display**: `Cinzel` (serif) — headlines, navigation, premium copy
- **Serif**: `Cormorant Garamond` (serif) — taglines, italics, editorial
- **Body**: `Inter` (sans-serif) — body text, descriptions
- **Mono**: `JetBrains Mono` (monospace) — labels, specs, time

All fonts loaded via Google Fonts with preconnect optimization.

### Responsive Breakpoints
- **Desktop**: 980px and up
- **Tablet**: 720px to 979px
- **Mobile**: Under 720px

Mobile optimizations:
- Single-column layouts
- Larger touch targets
- Simplified navigation (drawer instead of horizontal)
- Sticky bottom CTA for booking

## Features

### Interactivity
- **Mobile drawer navigation** — smooth open/close with overlay
- **Service card hover states** — subtle border and background shift
- **Navigation link underlines** — animated on hover
- **Dynamic hours** — JavaScript updates "today" marker based on current day
- **Smooth scrolling** — HTML `scroll-behavior: smooth`

### Accessibility
- Semantic HTML structure
- ARIA labels and roles throughout
- Skip-to-content link
- Proper heading hierarchy
- High contrast text
- Keyboard-navigable UI

### SEO & Metadata
- Comprehensive Open Graph tags (social sharing)
- Twitter Card metadata
- Local business structured data (schema.org)
- Hair salon service offers with pricing
- Aggregate rating (4.9★, 187 reviews)
- Geo markup (Barrie, Ontario)
- Geographic service area (Barrie, Innisfil, Oro-Medonte, Springwater)
- Canonical URL

### Performance
- Minimal dependencies (vanilla HTML/CSS/JS)
- WebP logo for reduced file size
- Preconnect for Google Fonts
- CSS custom properties for theme flexibility
- Lazy-loading on iframes (Google Maps)

## JavaScript

### Mobile Menu
```javascript
// Toggle drawer on button click
menuBtn.addEventListener('click', openDrawer);
drawerClose.addEventListener('click', closeDrawer);

// Close drawer when navigating
drawer.querySelectorAll('a').forEach(a => 
  a.addEventListener('click', closeDrawer)
);
```

### FAQ Accordion
```javascript
// Toggle accordion items (no-op if no FAQ on page)
document.querySelectorAll('.faq__q').forEach(q => {
  q.addEventListener('click', () => {
    const item = q.parentElement;
    const open = item.classList.toggle('open');
    q.setAttribute('aria-expanded', open);
  });
});
```

### Dynamic Hours
```javascript
// Update "today" marker in hours table based on current day
const today = new Date().getDay();
// Rows map: Mon, Tue, Wed, Thu, Fri, Sat, Sun (indices 0–6)
```

## Getting Started

### View Locally
1. Open `index.html` in a modern browser
2. All assets load from relative paths (no build step required)

### Customization

**Colors**: Edit CSS custom properties in `sigma-styles.css` `:root` block
```css
--gold: #C9A961;            /* Primary accent */
--gold-2: #E0C58A;          /* Bright accent */
```

**Content**: Edit text, pricing, hours in `index.html`

**Logo**: Replace `assets/sigma-logo.webp` with your logo

**Maps**: Update the embedded Google Maps iframe URL in Contact section

## Browser Support

- ✅ Chrome/Edge 90+
- ✅ Firefox 88+
- ✅ Safari 14+
- ✅ Mobile browsers (iOS Safari, Chrome Mobile)

## Future Enhancements

- Online booking integration (Calendly, Acuity Scheduling, etc.)
- Photo gallery (bento grid layout prepared)
- Barber profiles/staff page
- Blog/Insights section
- Client testimonial carousel (instead of static 3)
- Multi-language support
- Appointment confirmations via SMS/email
- Promotional banners (seasonal services)
- Instagram feed integration

## Credits

**Design System**: Premium barbershop branding with luxury dark theme  
**Typography**: Google Fonts (Cinzel, Cormorant Garamond, Inter, JetBrains Mono)  
**Icons**: Inline SVG (Feather-style line icons)  
**Location**: 418 Blake St, Barrie, ON L4M 1L3  
**Contact**: (705) 241-0504  
**Website**: sigmacutz.ca  
**Instagram**: @sigma_cutz_barrie

---

Built with semantic HTML, CSS custom properties, and vanilla JavaScript.  
**Tagline**: Slay & Shine ✨
