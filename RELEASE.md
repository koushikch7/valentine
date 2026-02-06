# Release Notes

## 2026-02-06 - Enterprise Upgrade
### Major Features Added
- **URL Shortening Integration**: Automatic spoo.me API integration with Bearer token auth
- **Browser Caching**: localStorage saves setup data (name, date, message, album, video) for persistent form state
- **Video Support**: New &video= URL parameter for embedding custom videos
  - **Cloudflare R2 Integration**: Videos hosted on Cloudflare R2 with custom domain support
  - Default video URL from R2 as fallback
  - Fully CORS-enabled CDN delivery
- **Professional UI Redesign**: 
  - Glassmorphism cards with blur effects
  - Beautiful pink romantic gradient background with radial overlays
  - Enhanced navbar with branding
  - Smooth animations (pulse, float, slideUp, fall)
  - Mobile-first responsive design
- **Advanced Share Modal**: URL copy, Facebook/WhatsApp sharing buttons
- **SEO Optimization**: 
  - Semantic meta tags (description, keywords, author)
  - Open Graph tags for social sharing
  - Favicon as heart emoji SVG
  - Theme color meta tag
- **Security Hardening**:
  - All user inputs rendered via DOM textContent (XSS prevention)
  - HTTPS validation for all URLs
  - Safe localStorage JSON serialization
  - Fallback URL shortening (uses full URL if API fails)
- **UX Improvements**:
  - Toast notifications for copy-to-clipboard
  - Improved popup styling with animations
  - Constrained "NO" button movement on hover
  - Character counter for message field
  - Helper text with link to Google Photos sharing guide

### Technical Changes
- **File Size**: ~854 lines of production-ready HTML/CSS/JS
- **Dependencies**: html2canvas (CDN), Google Fonts (CDN)
- **Color Palette**: 
  - Primary: #d4416b
  - Light: #ff6b9d
  - Dark: #a83051
  - Accent: #ffc0cb
- **Typography**: Playfair Display (serif), Montserrat (sans-serif)
- **Removed**: theme parameter (fixed gradient instead)
- **Added Parameters**: video (optional https URL)

### Stability
- Graceful API failure handling - shortening still works if spoo.me API unavailable
- localStorage errors caught silently
- CORS-safe video embedding (Cloudflare R2 fully supported)
- Cross-browser compatible
- **Cloudflare Native**: Works perfectly with Cloudflare Pages + R2 + Workers ecosystem

## Previous Version (2026-02-06 - Initial)
- Added improved setup flow with message, theme, and album fields
- Added URL validation and message length enforcement
- Added date label display and year/month/day counter
- Hardened rendering against injection by using text nodes
- Updated UI styling and typography for a more cinematic feel
- Kept story fixed (no URL overrides)
