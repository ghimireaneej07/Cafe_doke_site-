# Cafe Frontend Design Rules — Industry UI/UX Standard

> **Purpose:** A practical frontend rulebook for building a premium, modern cafe website with a dark-first visual identity, strong conversion UX, excellent mobile behavior, accessibility, and production-level frontend quality.

**Version:** 1.0  
**Last researched:** August 20, 2026

---

## 1. Core Design Philosophy

The cafe website should feel like the cafe itself:

- **Premium, warm, atmospheric**
- **Minimal but not empty**
- **Editorial rather than template-like**
- **Image-led but performance-conscious**
- **Easy to use within seconds**
- **Designed mobile-first**
- **Focused on conversion:** visit, view menu, order, reserve, call, or get directions

### The 30-second rule

A first-time visitor should quickly understand:

1. What the cafe serves
2. Where it is
3. When it is open
4. What makes it special
5. What action they should take next

Do not sacrifice these answers for visual effects.

---

# 2. Visual Direction

## Recommended aesthetic

Use a **dark editorial cafe aesthetic**:

- Deep charcoal / near-black backgrounds
- Warm off-white typography
- One restrained coffee-inspired accent
- Large food photography
- Soft shadows
- Subtle borders
- Generous whitespace
- Rounded corners used consistently
- Editorial typography
- Small uppercase labels for metadata
- Motion used for atmosphere, not decoration

### Suggested palette

```css
:root {
  --bg: #0D0C0A;
  --surface: #151310;
  --surface-2: #1C1915;
  --text: #F4F0E8;
  --muted: #A9A39A;
  --accent: #C9955B;
  --border: rgba(255,255,255,.10);
  --success: #8FAF7A;
  --danger: #C96F67;
}
```

Do not use pure `#000` everywhere. Near-black surfaces create better hierarchy.

Do not use five accent colors. One primary accent is normally enough.

---

# 3. Typography

## Use typography as a major part of the brand

Recommended pairing:

- **Display:** elegant serif
- **Body/UI:** modern sans-serif

Example:

```css
--font-display: "Cormorant Garamond", serif;
--font-body: "Inter", sans-serif;
```

Alternative display fonts:

- Playfair Display
- DM Serif Display
- Instrument Serif
- Fraunces

Alternative UI fonts:

- Inter
- Manrope
- Geist
- Plus Jakarta Sans

### Typography rules

- H1 should be visually dominant.
- Body text should remain highly readable.
- Never use thin text for important information.
- Keep paragraph widths around 45–70 characters.
- Use line-height generously.
- Use uppercase sparingly.
- Do not use more than 2–3 font families.
- Prices should be easy to scan.

### Suggested scale

```text
Hero H1:       clamp(3rem, 8vw, 7rem)
Section H2:    clamp(2rem, 4vw, 4rem)
Card title:    1.1rem–1.4rem
Body:          1rem–1.125rem
Small label:   .7rem–.8rem
```

Use `clamp()` rather than dozens of breakpoint-specific font sizes.

---

# 4. Global Layout System

Use a consistent spacing system.

Recommended base:

```text
4px
8px
12px
16px
24px
32px
48px
64px
96px
128px
```

### Container

Desktop:

```css
max-width: 1280px;
margin-inline: auto;
padding-inline: 32px;
```

Tablet:

```text
24px horizontal padding
```

Mobile:

```text
16px–20px horizontal padding
```

### Section spacing

Desktop:

```text
96px–144px vertical
```

Mobile:

```text
64px–88px vertical
```

Do not make every section identical. Use spacing to create rhythm.

---

# 5. Header / Navigation

The header should be minimal.

Recommended structure:

```text
[Logo]     Menu   About   Visit     [Reserve / Order]
```

### Rules

- Keep primary navigation to roughly 4–6 items.
- Use descriptive labels.
- Make the primary CTA visually distinct.
- Keep the logo simple.
- On desktop, avoid hiding important navigation unnecessarily.
- On mobile, use a clean menu drawer.
- Make the header sticky only when it genuinely helps.
- If sticky, reduce its height after scrolling.
- Do not cover content with the header.

### Mobile navigation

Use:

```text
☰ Menu
```

with a full-height or well-designed drawer.

The drawer should include:

- Menu
- About
- Gallery
- Location
- Hours
- Order/Reserve CTA
- Social links

Keyboard and screen-reader behavior must work correctly.

---

# 6. Hero Section — Most Important Section

The hero should communicate the cafe's personality immediately.

## Recommended Hero Pattern A — Cinematic Image

```text
┌───────────────────────────────────────┐
│ NAVIGATION                            │
│                                       │
│      [FULL-BLEED CAFE IMAGE]          │
│                                       │
│        SPECIALTY COFFEE               │
│        MADE SLOW.                     │
│        SERVED WARM.                   │
│                                       │
│        [ VIEW MENU ] [ VISIT US ]     │
│                                       │
│                         Scroll ↓      │
└───────────────────────────────────────┘
```

Use a high-quality cafe interior, coffee preparation, pastry, or signature dish.

## Recommended Hero Pattern B — Editorial Split

```text
┌──────────────────────┬────────────────┐
│                      │                │
│  GOOD COFFEE.        │   Large food   │
│  BETTER COMPANY.     │   photograph   │
│                      │                │
│  Short description   │                │
│  [VIEW MENU]         │                │
└──────────────────────┴────────────────┘
```

This is excellent for premium cafes that want a more sophisticated look.

## Recommended Hero Pattern C — Dark Video

Use subtle video of:

- Espresso extraction
- Latte art
- Barista preparation
- Steam
- Cafe ambience
- Pastry preparation

Rules:

- Keep video short and compressed.
- Add a dark overlay.
- Never allow video to overpower text.
- Respect reduced-motion preferences.
- Provide a poster image.
- Do not block the page while video loads.

### Hero rule

**One hero = one primary message + one primary CTA + one secondary CTA.**

Do not place 6 buttons in the hero.

---

# 7. Hero Copy Formula

Use:

```text
[SMALL EYEBROW]
SPECIALTY COFFEE • FRESH BAKES

[HEADLINE]
Coffee worth slowing down for.

[SUPPORTING TEXT]
Small-batch coffee, house-made pastries,
and a space made for lingering.

[PRIMARY CTA]
View Menu

[SECONDARY CTA]
Find Us
```

Avoid generic copy such as:

> Welcome to our amazing cafe where we provide the best coffee experience.

Make it specific and brand-driven.

---

# 8. Signature / Featured Items

Immediately after the hero, introduce the products.

Recommended:

```text
OUR SIGNATURES

[Large Card] [Large Card] [Large Card]

Coffee
Pastries
Signature Drinks
```

Each card should contain:

- Strong image
- Item name
- One-line description
- Price
- Optional dietary indicator
- Optional "Popular" badge

### Card rule

Do not overload cards with:

- Huge shadows
- 10 badges
- Long descriptions
- Excessive animations
- Tiny text

---

# 9. Menu UX

The menu is one of the highest-priority parts of the site.

## Never make a PDF the only menu

Build the menu as real HTML content.

Recommended structure:

```text
MENU

[Coffee] [Tea] [Breakfast] [Pastries] [Desserts]

ESPRESSO
Americano                 ₹___
Cappuccino                ₹___
Flat White                ₹___

SIGNATURE
House Latte               ₹___
Mocha                     ₹___
Cold Brew                 ₹___
```

### Menu requirements

Every item should have:

- Name
- Price
- Short description where useful
- Dietary/allergen information where relevant
- Optional image for signature products

### Filtering

If the menu is large:

```text
All | Coffee | Food | Desserts | Drinks
```

Avoid complicated filter systems.

### Mobile menu

Use sticky category tabs or horizontal scrolling categories.

Do not force users to open a PDF.

---

# 10. About / Brand Story

Do not create a giant wall of text.

Use an editorial composition:

```text
[Image]        [SHORT EYEBROW]

               We believe coffee
               should slow you down.

               2–4 short paragraphs

               [OUR STORY →]
```

Tell users:

- Why the cafe exists
- What makes it different
- Coffee philosophy
- Food philosophy
- Local identity

Keep it human.

---

# 11. Atmosphere / Gallery

Cafe websites benefit heavily from photography.

Recommended layout:

```text
┌──────────────┬─────────┐
│              │         │
│    IMAGE     │ IMAGE   │
│              │         │
├───────┬──────┴─────────┤
│ IMAGE │     IMAGE      │
└───────┴────────────────┘
```

Use varied image sizes rather than a boring uniform grid.

### Image priorities

Show:

1. Signature coffee
2. Best food
3. Interior
4. People / atmosphere
5. Barista craft
6. Exterior / storefront

Avoid stock images whenever possible.

---

# 12. Social Proof

Use authentic proof.

Possible section:

```text
LOVED LOCALLY

★★★★★

"Beautiful space, excellent coffee..."

— Customer Name

[Google Rating] [Instagram] [Reviews]
```

Keep testimonials short.

If using review platforms, don't fabricate ratings.

---

# 13. Location / Visit Section

This section should answer:

- Where?
- When?
- How to get there?
- Can I park?
- Can I reserve?
- Can I order?

Recommended layout:

```text
COME BY

[MAP]

123 Example Street
Chennai, India

MON–FRI   7:00 AM – 10:00 PM
SAT–SUN   8:00 AM – 11:00 PM

[GET DIRECTIONS]
[CALL]
```

On mobile, make phone, directions, and ordering actions easy to tap.

---

# 14. CTA Strategy

Do not use the same CTA everywhere.

Use context-aware CTAs:

```text
Hero       → View Menu
Menu       → Order Now
Story      → Our Story
Location   → Get Directions
Footer     → Contact Us
```

### Primary CTA

Use the accent color.

### Secondary CTA

Use transparent/outlined treatment.

### CTA rule

Every major section should have either:

- a clear action, or
- a deliberate reason not to have one.

Avoid CTA spam.

---

# 15. Dark Theme Rules

Dark mode is not:

```text
black background + white text
```

Build depth.

Recommended layers:

```text
Page background
    ↓
Section surface
    ↓
Card surface
    ↓
Hover surface
```

Example:

```text
#0D0C0A
#151310
#1C1915
#242019
```

### Contrast

Use strong contrast for:

- Headings
- Prices
- CTAs
- Navigation
- Important information

Use muted contrast only for:

- Supporting descriptions
- Metadata
- Secondary information

Do not use gray text that becomes difficult to read.

---

# 16. Borders and Shadows

Prefer subtle borders over giant shadows.

Good:

```css
border: 1px solid rgba(255,255,255,.08);
```

Use shadows sparingly.

Avoid:

```css
box-shadow: 0 20px 80px rgba(0,0,0,.8);
```

on every card.

Premium design usually comes from spacing, typography, imagery, and hierarchy—not excessive effects.

---

# 17. Border Radius

Choose a system and stay consistent.

Example:

```text
Buttons: 999px
Cards: 20px
Images: 16–24px
Inputs: 12px
```

Do not mix 4px, 7px, 13px, 18px, 27px, and 31px randomly.

---

# 18. Micro-Interactions

Use animation to communicate state.

Good:

- Button hover
- Image scale on hover
- Navigation underline
- Menu category transitions
- Scroll reveal
- Modal transitions
- Cart feedback
- Loading states

Avoid:

- Constant floating objects
- Excessive parallax
- Spinning logos
- Text flying everywhere
- Long page-load animations
- Animations on every element

### Timing

Typical UI transitions:

```css
transition: 180ms–300ms ease;
```

Larger page transitions:

```text
300ms–600ms
```

Motion should feel calm and intentional.

---

# 19. Scroll Animations

Recommended:

```text
fade-up
fade-in
subtle scale
image reveal
clip-path reveal
```

Use staggered animations for small groups.

Example:

```text
Card 1 → 0ms
Card 2 → 80ms
Card 3 → 160ms
```

Never make users wait for content to become usable.

Respect:

```css
@media (prefers-reduced-motion: reduce) {
  /* disable non-essential motion */
}
```

---

# 20. Images

Images are central to cafe design, but they can destroy performance.

### Rules

- Use WebP/AVIF where appropriate.
- Provide responsive image sizes.
- Use `srcset`.
- Compress aggressively without visibly damaging quality.
- Set explicit width/height or aspect ratio.
- Lazy-load below-the-fold images.
- Do not lazy-load the primary hero image if it is the LCP element.
- Always use meaningful `alt` text for informative images.
- Use empty alt text for purely decorative images.

### Recommended image ratios

```text
Hero:        16:9 / 21:9
Product:     4:5 / 1:1
Gallery:     mixed
Portrait:    4:5
Interior:    3:2
```

---

# 21. Responsive Design

Design mobile first.

Breakpoints should be based on layout needs, not device names.

Typical starting points:

```text
Mobile: 0–639px
Tablet: 640–1023px
Desktop: 1024px+
Large: 1280px+
```

These are starting points, not laws.

### Mobile priorities

On mobile:

1. Logo
2. Menu
3. Primary CTA
4. Hero message
5. Menu access
6. Location/hours
7. Social proof

Never make mobile feel like a squeezed desktop page.

---

# 22. Touch UX

Buttons should be comfortable to tap.

Target approximately:

```text
44px × 44px minimum interactive area
```

Give neighboring buttons enough spacing to prevent accidental taps.

Do not make tiny icon-only buttons for critical actions.

---

# 23. Accessibility

Accessibility is part of professional frontend quality.

### Required

- Semantic HTML
- Correct heading hierarchy
- Keyboard navigation
- Visible focus states
- Meaningful labels
- Good color contrast
- Accessible forms
- Alt text
- Reduced-motion support
- Proper modal behavior
- Accessible navigation

### Semantic structure

Prefer:

```html
<header>
<nav>
<main>
<section>
<article>
<footer>
```

over a page made entirely from `<div>` elements.

### Forms

Every form control needs a meaningful label.

Do not rely only on placeholder text.

---

# 24. Navigation Accessibility

Navigation must work with:

- Mouse
- Keyboard
- Touch
- Screen readers

Menus should have clear states:

```text
default
hover
focus
active
current
disabled
```

Never remove the browser focus indicator without replacing it with a better visible focus state.

---

# 25. Performance Budget

A beautiful cafe site that loads slowly is a bad cafe site.

Target:

```text
LCP: ≤ 2.5s
INP: ≤ 200ms
CLS: ≤ 0.1
```

These are Google's recommended good Core Web Vitals thresholds.

### Avoid

- Huge background videos
- 10+ unoptimized images
- Giant JavaScript bundles
- Multiple unnecessary font files
- Autoplay-heavy media
- Excessive third-party scripts

### Performance priority

```text
HTML
 ↓
Critical CSS
 ↓
Hero image
 ↓
Main content
 ↓
Interactions
 ↓
Below-fold media
```

---

# 26. Loading States

Never show a blank page while data loads.

Use:

- Skeleton cards
- Image placeholders
- Button loading states
- Menu loading states

Avoid giant spinners for simple actions.

Example:

```text
[ View Menu ]
```

becomes:

```text
[ Loading... ]
```

only when necessary.

---

# 27. Error States

Design errors intentionally.

Bad:

```text
Error
```

Better:

```text
We couldn't load the menu.

Please try again.

[TRY AGAIN]
```

For ordering:

```text
Something went wrong with your order.

Your cart is still saved.

[TRY AGAIN]
```

---

# 28. Menu Item Card Rules

Recommended card anatomy:

```text
┌───────────────────────────┐
│                           │
│        FOOD IMAGE         │
│                           │
├───────────────────────────┤
│ Cappuccino          ₹180  │
│ Double espresso, silky    │
│ milk foam.                │
│                           │
│ ● Vegetarian              │
└───────────────────────────┘
```

Hierarchy:

```text
Image
 ↓
Name + Price
 ↓
Description
 ↓
Dietary metadata
 ↓
Action
```

---

# 29. Reservation / Ordering UX

If the cafe supports ordering:

Keep the flow short.

```text
Select item
 ↓
Customize
 ↓
Add to cart
 ↓
Review
 ↓
Checkout
```

Do not force account creation before adding items.

If reservation is supported:

```text
Date
Time
Guests
Contact
Confirm
```

Make availability obvious.

---

# 30. Floating Mobile CTA

For a cafe with ordering/reservation:

```text
┌──────────────────────────────┐
│  View Menu     Order Now     │
└──────────────────────────────┘
```

A fixed bottom CTA can be useful on mobile.

Do not cover:

- Cookie controls
- Important content
- Form buttons
- Browser UI

---

# 31. Footer

A premium footer can be simple.

```text
OUTER / CAFE

Good coffee. Slow moments.

NAVIGATION
Menu
About
Gallery
Visit

CONTACT
Phone
Email
Address

SOCIAL
Instagram
Facebook

© 2026 Cafe Name
```

Include:

- Address
- Opening hours
- Phone
- Email
- Social links
- Privacy / terms if applicable

---

# 32. SEO-Friendly Frontend

Use real HTML text.

Important:

```text
H1
H2
H3
```

Structure content logically.

Include:

- Cafe name
- Location
- Cuisine/product categories
- Opening hours
- Contact information
- Menu content

Use descriptive page titles.

Example:

```text
Cafe Name — Specialty Coffee & Fresh Bakes in Chennai
```

Avoid stuffing keywords unnaturally.

---

# 33. Local Discovery

For a physical cafe, location information is not optional.

Make these highly discoverable:

```text
Address
Opening hours
Phone
Directions
Menu
Parking information
Reservation/order link
```

Use structured data where appropriate, especially `LocalBusiness` / relevant food establishment schema.

---

# 34. Component Architecture

Build reusable components.

Recommended:

```text
components/
├── Header
├── MobileMenu
├── Hero
├── SectionHeading
├── ProductCard
├── MenuTabs
├── MenuItem
├── StorySection
├── Gallery
├── Testimonial
├── Location
├── Hours
├── CTA
├── Footer
└── Button
```

Do not duplicate the same button/card markup across the entire project.

---

# 35. Design Tokens

Centralize values.

Example:

```css
:root {
  --color-bg: #0D0C0A;
  --color-surface: #151310;
  --color-text: #F4F0E8;
  --color-muted: #A9A39A;
  --color-accent: #C9955B;

  --radius-sm: 8px;
  --radius-md: 16px;
  --radius-lg: 24px;
  --radius-pill: 999px;

  --space-1: 4px;
  --space-2: 8px;
  --space-3: 12px;
  --space-4: 16px;
  --space-5: 24px;
  --space-6: 32px;
  --space-7: 48px;
  --space-8: 64px;
  --space-9: 96px;
}
```

This makes the entire site easier to maintain.

---

# 36. Component States

Every interactive component should have states.

### Button

```text
Default
Hover
Focus
Active
Loading
Disabled
```

### Input

```text
Default
Focus
Filled
Error
Disabled
```

### Menu item

```text
Default
Hover
Selected
Unavailable
```

Design all states before calling the component finished.

---

# 37. Do Not Overdesign

Avoid the common "AI-generated website" look:

- Excessive gradients
- Random glowing blobs
- Too many glass cards
- Huge rounded rectangles everywhere
- Neon accents
- Excessive animations
- Generic dashboard components
- Repetitive cards
- Fake statistics
- Stock photos with no brand connection

A cafe should feel **physical and sensory**, not like a SaaS dashboard.

---

# 38. Premium Design Formula

A strong cafe site can follow:

```text
40% Photography
20% Typography
15% Whitespace
10% Color
10% Motion
5% UI decoration
```

The exact percentages are not literal measurements; they represent priority.

---

# 39. Recommended Homepage Structure

Use this as the default information architecture:

```text
1. Header
2. Hero
3. Signature / Featured Items
4. Short Brand Story
5. Menu Preview
6. Atmosphere / Gallery
7. Testimonials / Social Proof
8. Visit Us
9. Final CTA
10. Footer
```

If the cafe is highly food-focused:

```text
Hero
 ↓
Signature Food
 ↓
Menu
 ↓
Story
 ↓
Gallery
 ↓
Reviews
 ↓
Location
```

If it is highly experience-focused:

```text
Hero
 ↓
Atmosphere
 ↓
Story
 ↓
Signature Coffee
 ↓
Gallery
 ↓
Menu
 ↓
Visit
```

---

# 40. Visual Rhythm

Do not use the same layout repeatedly.

Alternate:

```text
Full-width
 ↓
Two-column
 ↓
Grid
 ↓
Editorial split
 ↓
Full-width image
 ↓
Cards
```

Example:

```text
[ HERO ]

[ 3 FEATURE CARDS ]

[ IMAGE | STORY ]

[ MENU GRID ]

[ LARGE IMAGE ]

[ TESTIMONIAL ]

[ MAP | HOURS ]

[ FINAL CTA ]
```

This creates visual rhythm.

---

# 41. Desktop vs Mobile

### Desktop

Use:

- Large typography
- Asymmetric layouts
- Multi-column grids
- Hover interactions
- Large photography
- Editorial whitespace

### Mobile

Use:

- Single-column flow
- Large touch targets
- Horizontal category scrolling
- Sticky contextual CTA where useful
- Shorter text
- Faster visual scanning

Do not simply shrink desktop layouts.

---

# 42. Quality Checklist Before Launch

## Visual

- [ ] Typography is consistent
- [ ] Color palette is restrained
- [ ] Spacing follows a system
- [ ] Images are high quality
- [ ] Cards use consistent radius
- [ ] Buttons have consistent styling
- [ ] Dark theme has sufficient contrast
- [ ] No unnecessary visual effects

## UX

- [ ] Menu is immediately discoverable
- [ ] Address is easy to find
- [ ] Opening hours are visible
- [ ] Primary CTA is obvious
- [ ] Mobile navigation is easy
- [ ] No dead-end pages
- [ ] Error states are designed
- [ ] Loading states are designed

## Accessibility

- [ ] Semantic HTML
- [ ] Keyboard navigation
- [ ] Visible focus states
- [ ] Meaningful labels
- [ ] Accessible navigation
- [ ] Alt text
- [ ] Good contrast
- [ ] Reduced-motion support

## Performance

- [ ] Hero image optimized
- [ ] Below-fold images lazy-loaded
- [ ] Responsive images implemented
- [ ] Fonts optimized
- [ ] No unnecessary third-party scripts
- [ ] LCP target ≤ 2.5s
- [ ] INP target ≤ 200ms
- [ ] CLS target ≤ 0.1

## Mobile

- [ ] Tested at 320px+
- [ ] Tested around 375px
- [ ] Tested around 768px
- [ ] Tested at desktop widths
- [ ] No horizontal overflow
- [ ] Buttons are easy to tap
- [ ] Text remains readable
- [ ] Sticky elements don't cover content

---

# 43. Golden Rules

1. **Design for the customer, not the designer.**
2. **Make the menu impossible to miss.**
3. **Make location and opening hours easy to find.**
4. **Use photography to sell the experience.**
5. **Use typography to establish personality.**
6. **Keep the dark theme layered, not flat black.**
7. **Use one strong accent color.**
8. **Animation should support interaction.**
9. **Mobile is a first-class experience.**
10. **Never let aesthetics destroy performance.**
11. **Use real menu text instead of a PDF-only experience.**
12. **Every interactive element needs clear states.**
13. **Accessibility is part of premium design.**
14. **Consistency beats novelty.**
15. **If an effect does not improve understanding, remove it.**

---

# 44. Research Basis

These rules were informed by current web-performance, accessibility, navigation, and cafe/restaurant UX guidance.

Key references:

- Google web.dev — Web Performance and Core Web Vitals
- W3C Web Accessibility Initiative — Menu Structure and Styling
- Nielsen Norman Group — Menu Design Checklist
- Contemporary 2026 cafe website UX/design research covering hero sections, menu UX, local information, photography, and conversion patterns

Useful references:

- https://web.dev/performance/
- https://web.dev/articles/vitals
- https://www.w3.org/WAI/tutorials/menus/
- https://www.w3.org/WAI/tutorials/menus/structure/
- https://www.w3.org/WAI/tutorials/menus/styling/
- https://media.nngroup.com/media/articles/attachments/PDF_Menu-Design-Checklist.pdf

---

# Final Implementation Principle

**Build the site so that it feels expensive, but behaves effortlessly.**

The visual layer should make visitors want to enter the cafe.

The UX layer should make it effortless to decide what to order, when to visit, and where to go.

The engineering layer should make the experience fast, responsive, accessible, and maintainable.

**Premium = strong hierarchy + great photography + typography + restraint + speed + usability.**
