# Asset Creation Guide 🎨

This document describes the visual assets needed for Infin.Love that are currently missing or need to be created.

## Priority Assets

### 1. Open Graph Image (`og-image.jpg`)

**Status**: ⚠️ **Missing** - Currently referenced in meta tags but doesn't exist

**Purpose**: Social media share preview image for Facebook, LinkedIn, Slack, etc.

**Specifications**:
- **Dimensions**: 1200 x 630 pixels (exact)
- **Format**: JPG
- **File size**: < 200 KB (optimized for web)
- **Color space**: sRGB
- **Location**: Root directory (`/og-image.jpg`)

**Design Requirements**:
- **Background**: Purple/pink gradient matching site aesthetic
  - Colors: #F06292 → #BA68C8 → #7C4DFF
  - Style: 135deg gradient (same as site)
- **Primary Text**: "∞ Infin.Love"
  - Font: Georgia or similar serif
  - Color: White or #FFD700 (sacred gold)
  - Size: Large, readable even when small
- **Secondary Text**: "Sacred Reciprocity & Infinite Love" (optional)
- **Visual Elements**:
  - Heart imagery (💜, 💝, 💖) scattered or floating
  - Infinity symbol (∞) prominent
  - Ethereal, sacred, loving aesthetic
- **Safe Zones**: Keep important content 150px from edges (may be cropped on some platforms)

**Test Platforms**:
- Facebook Share Debugger
- Twitter Card Validator
- LinkedIn Post Inspector

---

### 2. Logo (`logo.png`)

**Status**: ⚠️ **Missing** - Referenced in structured data but doesn't exist

**Purpose**: Brand identity, favicon alternatives, app icon

**Specifications**:
- **Dimensions**: 512 x 512 pixels (square)
- **Format**: PNG with transparency
- **File size**: < 50 KB
- **Color space**: sRGB
- **Location**: Root directory (`/logo.png`)

**Design Requirements**:
- **Primary Element**: Infinity symbol (∞)
- **Secondary Element**: Purple heart (💜) or heart shape
- **Style**:
  - Clean, simple design
  - Recognizable at small sizes (16x16, 32x32)
  - Works on both light and dark backgrounds
- **Colors**:
  - Primary: #E91E63 (love pink)
  - Secondary: #9C27B0 (soft purple)
  - Accent: #FFD700 (sacred gold)
- **Transparency**: Use for background
- **Versions to consider**:
  - Full color (512x512)
  - Favicon sizes (16x16, 32x32, 180x180)
  - Apple touch icon (180x180)

---

## Optional/Future Assets

### 3. PWA Icons (for manifest.json)

**Status**: 📝 **Future Enhancement**

When ready to enhance PWA experience:

**Sizes Needed**:
- 192x192 (Android home screen)
- 512x512 (Android splash screen)
- 180x180 (Apple touch icon)
- 144x144 (Windows tile)
- 96x96, 72x72, 48x48 (various Android densities)

**Specifications**:
- Format: PNG with transparency
- Based on logo design
- Maskable icon version (for Android adaptive icons)
- Safe zone: Keep important content in center 80%

---

### 4. Favicon Variations

**Status**: ✅ **Partially Complete** - SVG emoji favicon exists

Current: SVG emoji (💜) as data URI

**Additional formats to consider**:
- `favicon.ico` (multi-size: 16x16, 32x32, 48x48)
- `favicon-16x16.png`
- `favicon-32x32.png`
- `apple-touch-icon.png` (180x180)

---

### 5. Screenshot (for PWA manifest)

**Status**: 📝 **Future Enhancement**

**Purpose**: Shown in browser install prompts for PWA

**Specifications**:
- Dimensions: 1280 x 720 pixels minimum
- Format: PNG or JPG
- Shows hero section of the site
- Clean, representative of the experience

---

## Design Tools & Resources

### Recommended Tools:
- **Figma** (free, collaborative)
- **Canva** (easy templates)
- **Adobe Photoshop/Illustrator** (professional)
- **GIMP** (free, open-source)
- **Inkscape** (free, vector graphics)

### Color Palette Reference:
```css
--love-pink: #E91E63
--heart-rose: #F06292
--sacred-gold: #FFD700
--soft-purple: #9C27B0
--deep-violet: #4A148C
--pure-white: #ffffff
--soft-black: #1a1a2e
```

### Font Reference:
- Primary: Georgia, Palatino (serif)
- Fallback: system serif fonts

### Inspiration:
- Visit https://infin.love for live aesthetic
- Sacred geometry, mandala patterns
- Gradient backgrounds with transparency
- Soft, ethereal, loving energy

---

## How to Contribute Assets

1. **Review Specifications**: Ensure you understand the requirements above
2. **Create Asset**: Use preferred design tool
3. **Optimize**:
   - Compress images (use TinyPNG, ImageOptim, etc.)
   - Keep file sizes small
   - Test at various sizes
4. **Submit**:
   - Open PR with asset file(s)
   - Include preview/mockup in PR description
   - Mention testing done

5. **Feedback**: Be open to design iteration

---

## Validation Checklist

Before submitting, verify:

### For og-image.jpg:
- [ ] Exactly 1200 x 630 pixels
- [ ] File size < 200 KB
- [ ] Text readable when small
- [ ] Tested on Facebook Share Debugger
- [ ] Safe zones respected
- [ ] Matches site aesthetic

### For logo.png:
- [ ] Exactly 512 x 512 pixels (or larger, square)
- [ ] Transparent background
- [ ] Recognizable at 16x16
- [ ] Works on light and dark backgrounds
- [ ] File size < 50 KB
- [ ] Uses brand colors

---

## Questions?

Need help with asset creation?

- Open an issue with `design` label
- Email: tristan.stoltz@gmail.com
- Check CONTRIBUTING.md for contribution process

Thank you for helping make Infin.Love more beautiful! 💜✨
