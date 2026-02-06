# Valentine Page 💖

A professional, romantic single-page Valentine experience with URL shortening, caching, and video support. Fully static and deployable to Cloudflare Pages.

## Enterprise Features
- ✨ **Custom URL Shortening** - Automatic shortened URLs via spoo.me API for easy sharing
- 💾 **Browser Caching** - localStorage persists setup data to avoid re-entry
- 🎬 **Video Support** - Embed custom video via &video= parameter
- 💖 **Professional UI** - Glassmorphism design with romantic pink gradients
- 🎨 **SEO Optimized** - Full OG meta tags and semantic HTML5
- 📱 **Responsive Design** - Mobile-first, works on all devices
- 🎁 **Instant Download** - Screenshot the greeting as PNG
- 🎉 **Confetti Animation** - Celebratory animations on acceptance
- 🎵 **Background Music** - Royalty-free romantic instrumental

## URL Parameters
- **name**: Required. The valentine's name.
- **date**: Optional. Important date in YYYY-MM-DD format.
- **datetype**: Optional. marriage | firstmeet | engagement
- **message**: Optional. Short custom message (max 250 chars).
- **album**: Optional. Public Google Photos shared link (https only).
- **video**: Optional. Video URL (https only).

### Example URLs
With all parameters:
https://valentine.chkoushik.com/?name=Shivani&date=2022-11-27&datetype=marriage&message=You%20are%20my%20calm

Or let the form auto-shorten - just fill the form and get a beautiful shortened URL automatically.

## Setup Form (No Parameters)
If no URL parameters provided, visitors see a smart setup form with:
- Name field (required)
- Date picker with event type selector
- Personal message text area (max 250 chars)
- Google Photos album link
- Video URL support (optional)
- Form data auto-saved to browser localStorage

After submission:
1. URL Shortening: Generates a shortened spoo.me link
2. Share Modal: Shows copy-to-clipboard + Facebook/WhatsApp sharing
3. Caching: Setup persists in localStorage for future visits

## localStorage
The page auto-saves form data under key `valentine_setup`. Users return and form pre-fills automatically.

## Technical Details

### Security
- XSS Prevention: All user inputs rendered via DOM textContent (not innerHTML)
- URL Validation: All links must be HTTPS
- Sanitized: Template literals avoid injection

### API Integration
- spoo.me URL Shortener: Bearer token auth, fallback to full URL if API fails
- No backend required - fully static
- API key embedded (production-safe)

### Design System
- Colors: Romantic pink gradient (#d4416b primary, #ff6b9d accent)
- Fonts: Playfair Display (serif romance), Montserrat (clean sans-serif)
- Effects: Glassmorphism cards, smooth animations, responsive grid
- Favicon: Heart emoji SVG (data URI, no external dependency)

## Cloudflare R2 Integration with Pages

**R2** is Cloudflare's object storage service - perfect for hosting your video!

### Setup R2 + Pages
1. **Create R2 Bucket** in Cloudflare Dashboard
   - Dashboard → R2 → Create bucket
   - Upload your video file

2. **Configure Custom Domain** (Optional but recommended)
   - R2 Bucket → Settings → Custom Domain
   - Add your domain (e.g., `s3.yourdomain.com`)
   - Point DNS to Cloudflare

3. **Get Video URL**
   - Bucket → Files → Video file → Copy URL
   - Example: `https://s3.yourdomain.com/video.mp4`

4. **Use in Valentine Page**
   - Direct URL parameter: `?video=https://s3.yourdomain.com/video.mp4`
   - Or set in setup form when page loads

### Example with R2
```
https://valentine.chkoushik.com/?name=Vidya&video=https://s3.chkoushik.com/Koushik%20%26%20Vidya%20Wedding%20Teaser%20Traditional%20.mp4
```

## Deploy to Cloudflare Pages
1. Push to GitHub (`git push origin master`)
2. Connect in Cloudflare Dashboard → Pages → Create project
3. Select GitHub repository
4. Build: Leave empty (static site)
5. Output directory: `/`
6. Domain: Auto-generated or configure custom domain

## Complete Setup Flow
1. **Code**: Hosted on GitHub (free)
2. **Video**: Hosted on Cloudflare R2 (5GB free monthly)
3. **Web App**: Deployed on Cloudflare Pages (unlimited)
4. **Domain**: Add custom domain in Cloudflare DNS
5. **URL Shortening**: spoo.me API creates shareable links

## Notes
- Music plays after user clicks YES (browser autoplay policy)
- Google Photos albums must have link sharing enabled
- **R2 videos are CORS-enabled by default** ✅
- Shortened URLs created via spoo.me are permanent and trackable
- All three services (R2, Pages, Shortener) work seamlessly together
