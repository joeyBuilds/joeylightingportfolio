# Joey Troup Portfolio Website - Enhancement Summary

## Overview
Portfolio website for Joey Troup, a concert lighting programmer. The site features dynamic visual effects, geometric branding elements, and optimized mobile experience.

---

## Visual Design Enhancements

### Parallax Scrolling (Desktop Only)
- Hero and tour images shift at different speeds while scrolling for depth effect
- Implemented via `data-parallax` attributes with configurable speed values
- **Disabled on tablet/mobile (≤1100px)** to prevent jitter

### Text Animations
- Hero title reveals with slide-up word animation
- Glow effect on hover for hero title
- Staggered reveal timing for About section paragraphs

### Ken Burns Motion (Desktop Only)
- Tour images slowly pan/zoom while in view
- Hover override for immediate scale effect
- **Disabled on mobile** with `animation: none !important`

### Section Transitions
- Smoother reveal animations triggered at 10% visibility threshold
- 50px bottom margin for earlier triggering on scroll

---

## Floating Geometric Network

### Custom Logo Shapes
The floating nodes are recreations of Joey's actual logo featuring:
- Double concentric outer rings
- Inner circle
- Diamond/rotated square connecting cardinal points
- 4 small circles at top, bottom, left, right positions
- Diagonal X cross pattern
- Triangular connectors pointing toward center
- Center dot

### Configuration
- 12 large shapes (10-18px) instead of many small particles
- Very slow drift (0.08 speed) for ambient fixture feel
- Slow rotation (0.003 speed)
- Subtle opacity (0.15-0.4)
- Layered behind content (z-index: 0)

### Interactivity
- Mouse hover creates connections to nearby nodes
- **Touch support for mobile devices** (touchstart, touchmove, touchend)
- Small indicator dot appears at cursor/touch position
- Connection opacity: 0.35 for mouse, 0.12 for node-to-node

---

## Functionality

### Nav Bar Logo
- AlchemyCircleRounded.png image displayed before "Joey Troup" text in nav
- Slow 20s infinite clockwise spin animation (`logoSpin` keyframe)
- Desktop: circle 4.3em, name 1.37rem
- Mobile (≤1100px): circle 2.34em, name 1.12rem
- Nav background gradient strengthened for legibility: solid black fading to transparent, prevents content from showing through behind logo

### Preloader
- Branded loading animation with light-beam sweep
- Beam widened to `min(400px, 60vw)` for desktop visibility (was 200px)
- "Joey Troup" text with pulsing glow
- 1.5 second display before fade-out

### Mobile Optimization

#### Hero Image Positioning
- **Tablet (≤1100px):** `object-position: 65% center` — pans image right to center silhouette
- **Phone (≤600px):** `object-position: 65% center` — pans even more right

#### Jitter Prevention
- All image transforms disabled on mobile with `transform: none !important`
- All animations disabled on mobile with `animation: none !important`
- Parallax JavaScript returns early on mobile (≤1100px)
- Ken Burns animation disabled on mobile

#### Layout Adjustments
- Dedicated tablet breakpoint (max-width: 1100px) — raised from 900px for better mid-size viewport support
- Dedicated phone breakpoint (max-width: 600px)
- Constrained image heights (45-60vh tablet, 35-50vh phone)
- Lazy loading on all below-fold images
- Adjusted padding, font sizes, and spacing for mobile

### Scroll Reveal Timing
- Threshold lowered from 30% to 10%
- Root margin adjusted to trigger 50px before element enters viewport

---

## Content

### About Section
```
I started behind a drum kit and ended up behind a lighting console. Turns out both are about the same thing — timing, feel, and reading the room.

A decade of experience has taught me that great lighting isn't about the rig. It's about accentuating the artist's vision, and pulling the audience into their story.
```

### Scroll Hint
- "Scroll" text replaced with SVG downward-pointing geometric arrow
- Gentle bobbing animation (`scrollBob` keyframe, 2s loop)

### Contact Section
- "Available for tours, festivals & special events" text **removed**
- Clean layout with just title and email

### Footer
- Copyright updated to "© 2026 Joey Troup | Equivalent Exchange LLC"

---

## File Structure
- `index.html` - Main production file with all enhancements
- `index-enhanced.html` - Copy of enhanced version
- `index-original-backup.html` - Backup of original before modifications
- `images/` - Tour photos, Ghost grid images, profile photos
- `CLAUDE.md` - This documentation file

---

## Tours Featured

### Programming
- Lainey Wilson: Whirlwind Tour
- Kendrick Lamar: Grand National Tour
- Rage Against The Machine: Public Service Announcement Tour
- Backstreet Boys: DNA World Tour

### Operating
- Taylor Swift: The Eras Tour
- Jonas Brothers: Happiness Begins Tour

---

## Brand Elements
- **Font:** Space Grotesk
- **Color scheme:** Dynamic gradient backgrounds that shift per section
- **Logo:** Sacred geometry style with concentric circles, triangles, and interconnected elements

---

## January 2026 Updates

### Tour Entry Spacing (Tablet/Mobile)
- Added margin-bottom between `.tour-feature` sections for clearer visual separation
- **Tablet (≤1100px):** 8rem spacing between tour entries
- **Mobile (≤600px):** 6rem spacing between tour entries

### Hamburger Navigation Menu
- Added hamburger button for tablet/mobile viewports (≤1100px)
- Compact dropdown menu (not full-screen overlay)
- Positioned top-right, appears below nav bar
- Features:
  - Three-line icon animates to X when open
  - Blurred background with subtle border
  - Closes on link tap, outside click, or Escape key
- Files: Hamburger button in `<nav>`, mobile menu as separate `<div class="mobile-menu">`

### Favicon
- Created custom SVG favicon based on simplified alchemy circle design
- Design: Two concentric circles with upward-pointing triangle
- Location: `images/favicon.svg`
- Also set as apple-touch-icon

### Additional Files Created
- `favicon-options.html` - Preview page showing 8 favicon design options at multiple sizes (can be deleted)

---

## Deployment
Hosted on Vercel. Deploy with:
```bash
cd outputs
vercel --prod
```

Live URL: https://joeylightingportfolio-black.vercel.app/
