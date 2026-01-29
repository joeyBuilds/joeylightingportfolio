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

## January 28, 2026 Updates

### iOS Chrome Favicon Fix
- **Problem:** Favicon wasn't appearing on Chrome tabs on iOS (showed generic globe icon)
- **Root cause:** iOS Chrome doesn't support SVG favicons — requires PNG format
- **Solution:** Generated properly sized PNG favicons from `AlchemyCircleRounded.png`
- **Files created:**
  - `images/favicon-32x32.png` — for tab icons
  - `images/favicon-16x16.png` — for smaller displays
  - `images/apple-touch-icon.png` — for iOS home screen (180x180)
  - `favicon.ico` in root directory — fallback
  - `apple-touch-icon.png` in root directory — fallback
- **HTML updated:** PNG favicon links placed before SVG so iOS picks them up first

### Mobile/Tablet Logo Size Increase
- Increased nav logo size for better visibility on mobile/tablet
- **Logo font-size:** 1.12rem → 1.25rem
- **Nav-logo height:** 2.34em → 2.8em
- **Nav gradient adjusted:** Extended slightly to accommodate larger logo while maintaining legibility

### Animated Project Separators
Added sleek geometric separators between tour project sections with multi-layered animation effects.

#### Final Design: Diamond Shape
Chosen to contrast with circular floating background elements:
- Outer diamond frame
- Inner diamond
- Cross lines through center
- Center dot

#### Animation Effects (7-second cycle)
1. **Line sweep:** Light pulses travel inward along lines toward center, fading out before reaching the end
2. **Diamond glow:** Center diamond pulses brighter with drop-shadow when waves arrive
3. **Ring burst:** Diamond-shaped ring expands outward from center dot with blur dissolve effect

#### Separator Placement
Separators added between:
- Lainey Wilson → Kendrick Lamar
- Kendrick Lamar → Rage Against The Machine
- Rage Against The Machine → Backstreet Boys
- Taylor Swift → Jonas Brothers

**NOT placed after:**
- Backstreet Boys (has "Operating" section divider)
- Jonas Brothers (end of projects section)

#### Responsive Design
- Lines use viewport units: 28vw on desktop/tablet, 25vw on mobile
- Max-width: 300px to prevent excessive length on ultrawide monitors

#### CSS Classes
```css
.project-separator        /* Container */
.project-separator .line  /* Animated sweep lines */
.project-separator .icon  /* Center icon container */
.project-separator .ring  /* Diamond burst effect element */
```

#### Keyframe Animations
- `lineSweep` / `lineSweepReverse` — Converging line pulse animations
- `circleGlowSep` — Diamond glow/pulse effect
- `ringBurstSep` — Expanding diamond burst with blur dissolve (starts at scale 0.3, expands to 2.2)

### Design Exploration File
- `separator-options.html` — Preview file with all separator designs explored:
  - **Shapes:** Diamond, Square Alchemy, Hexagon, Original Circle
  - **Effects:** Glow, Spin Pulse, Ripple Scale, Ring Burst
  - Useful for future design iterations

### Floating Background Elements Refinement
Reduced visual noise from the floating geometric background elements:
- **Canvas opacity:** 0.6 → 0.45
- **Node opacity range:** 0.15-0.4 → 0.1-0.3
- **Added blur:** 1px CSS filter blur for softer, more ambient appearance

---

## January 28, 2026 Session - Visual Polish & Animations

### Hero Image Shutter Reveal Animation
Dramatic reveal effect when page loads, replacing the simple fade-in:
- **10 vertical shutter blades** that slide open to reveal the hero image
- **Organic stagger timing** - blades open from center outward with non-uniform delays
- Animation sequence: center blades (6,5,7) open first, outer blades (1,10) open last
- Each blade has 1.6s animation duration with custom cubic-bezier easing
- Blade delays range from 1.65s to 2.58s for natural, non-mechanical feel

### Hero Text Timing Sync
- Text reveal now synced to start as shutter animation completes
- **First line:** 3.0s delay
- **Second line:** 3.2s delay
- **Subtitle:** 3.5s delay

### Subtle Glitch Effect on Hero Image
- Gentle RGB channel separation effect
- Runs on 8-second cycle
- Very subtle (1-2px offset) to avoid being distracting

### Favicon Overhaul
- Tested multiple source images for clarity on mobile
- **Final choice:** `twotri_Rounded.png` (triangular geometric design)
- Generated all required sizes:
  - `favicon-16x16.png`, `favicon-32x32.png`, `favicon-48x48.png`
  - `favicon-192x192.png`, `favicon-512x512.png`
  - `apple-touch-icon.png` (180x180)
  - `favicon.ico` (multi-size)

### Nav Logo Updates
- **Image:** Changed to `BetterAlchemyCircle_Rounded.png`
- **Size increased:** 5.5em desktop (was 4.3em), 3.5em mobile (was 2.8em)
- **Clickable:** Logo now scrolls to top of page when clicked
- Added `.logo-link` wrapper with smooth scroll behavior

### Contact Section - Complete Redesign

#### Position Change
- **Moved text to TOP of image** (was at bottom)
- `justify-content: flex-start` with 3rem top padding

#### Bold Text Shadow with Black Glow
Multi-layer shadow for maximum legibility over white light beams in photo:
```css
text-shadow:
    -2px -2px 0 rgba(0,0,0,0.9),
    2px -2px 0 rgba(0,0,0,0.9),
    -2px 2px 0 rgba(0,0,0,0.9),
    2px 2px 0 rgba(0,0,0,0.9),
    0 0 10px rgba(0,0,0,1),
    0 0 20px rgba(0,0,0,1),
    0 0 40px rgba(0,0,0,0.9),
    0 0 60px rgba(0,0,0,0.7),
    0 0 80px rgba(0,0,0,0.5);
```
- 4-corner outline (solid black edges)
- 5 layers of blur glow radiating outward (10px to 80px)

#### Spotlight Reveal Animation
Text reveals with cinematic spotlight effect:
- Starts blurred (10px) and invisible
- Mid-animation: bright white/blue glow burst
- Ends sharp with black glow shadow
- **Title:** 0.3s delay after section visible
- **Email:** 0.6s delay (staggered)

#### Responsive Positioning
Fine-tuned translateY values per breakpoint to avoid covering face in background image:
- **Default (large):** translateY(0)
- **1001-1100px:** translateY(-40px)
- **601-1000px:** translateY(-10px)
- **≤600px:** translateY(20px)

### Demo Files Created (can be deleted)
- `hero-reveal-demos.html` - 5 shutter reveal animation options
- `hero-effects-demos.html` - Hero image effect options v1
- `hero-effects-demos-2.html` - Hero image effect options v2
- `contact-legibility-demos.html` - Contact text shadow options
- `contact-reveal-demos.html` - Contact text reveal animation options
- `contact-text-animation-demos.html` - Contact text animation options

---

## Deployment
Hosted on Vercel. Deploy with:
```bash
cd outputs
vercel --prod
```

Live URL: https://joeylightingportfolio-black.vercel.app/
