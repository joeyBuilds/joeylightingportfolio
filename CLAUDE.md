# Joey Troup Portfolio Website - Enhancement Summary

## Overview
Portfolio website for Joey Troup, a concert lighting programmer. The site features dynamic visual effects, geometric branding elements, and optimized mobile experience.

---

## Visual Design Enhancements

### Parallax Scrolling (Desktop Only)
- Hero and tour images shift at different speeds while scrolling for depth effect
- Implemented via `data-parallax` attributes with configurable speed values
- **Disabled on mobile (≤900px)** to prevent jitter

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

### Preloader
- Branded loading animation with light-beam sweep
- "Joey Troup" text with pulsing glow
- 1.5 second display before fade-out

### Mobile Optimization

#### Hero Image Positioning
- **Tablet (≤900px):** `object-position: 70% center` — pans image right to center silhouette
- **Phone (≤600px):** `object-position: 75% center` — pans even more right

#### Jitter Prevention
- All image transforms disabled on mobile with `transform: none !important`
- All animations disabled on mobile with `animation: none !important`
- Parallax JavaScript returns early on mobile (≤900px)
- Ken Burns animation disabled on mobile

#### Layout Adjustments
- Dedicated tablet breakpoint (max-width: 900px)
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

### Contact Section
- "Available for tours, festivals & special events" text **removed**
- Clean layout with just title and email

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

## Deployment
Hosted on Vercel. Deploy with:
```bash
cd outputs
vercel --prod
```

Live URL: https://joeylightingportfolio-black.vercel.app/
