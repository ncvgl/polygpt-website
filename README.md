# PolyGPT Website

Single-page landing site for PolyGPT desktop app.

## Structure

- `index.html` - Main landing page (single file, no build required)
- `assets/logo.png` - PolyGPT logo

## Local Development

Simply open `index.html` in your browser:

```bash
open index.html
```

Or use a local server:

```bash
# Python
python3 -m http.server 8000

# Node
npx serve
```

Then visit `http://localhost:8000`

## Deployment

### Option 1: Vercel (Recommended)

1. Push this directory to a GitHub repo
2. Go to [vercel.com](https://vercel.com)
3. Click "Import Project" and select your repo
4. Deploy (auto-detects static site, zero config needed)
5. Add custom domain `polygpt.app` in project settings

### Option 2: Cloudflare Pages

1. Push to GitHub
2. Go to [pages.cloudflare.com](https://pages.cloudflare.com)
3. Connect repo and deploy
4. Add custom domain in settings

### Option 3: GitHub Pages

1. Push to a repo (e.g., `polygpt-website`)
2. Go to repo Settings → Pages
3. Select branch to deploy
4. Visit at `username.github.io/polygpt-website`
5. Configure custom domain if needed

## Updating Download Links

Download links point to GitHub Releases using the `/latest/` URL pattern:

```
https://github.com/ncvgl/polygpt/releases/latest/download/PolyGPT-mac.dmg
https://github.com/ncvgl/polygpt/releases/latest/download/PolyGPT-Setup.exe
https://github.com/ncvgl/polygpt/releases/latest/download/PolyGPT.AppImage
```

These auto-redirect to the newest release. No manual updates needed!

## Adding Demo Video

Replace the video placeholder section in `index.html` (around line 135) with:

```html
<div class="gradient-border max-w-4xl mx-auto mb-16">
    <video controls class="w-full rounded-lg">
        <source src="assets/demo.mp4" type="video/mp4">
        Your browser doesn't support video.
    </video>
</div>
```

Or embed YouTube/Vimeo:

```html
<div class="gradient-border max-w-4xl mx-auto mb-16">
    <iframe
        class="w-full aspect-video rounded-lg"
        src="https://www.youtube.com/embed/YOUR_VIDEO_ID"
        allowfullscreen>
    </iframe>
</div>
```

## Analytics

Add your analytics code in the `<head>` section where it says:

```html
<!-- Analytics Placeholder -->
<!-- Add your analytics code here (Google Analytics, Plausible, etc.) -->
```

### Google Analytics

```html
<script async src="https://www.googletagmanager.com/gtag/js?id=G-XXXXXXXXXX"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'G-XXXXXXXXXX');
</script>
```

### Plausible (privacy-friendly)

```html
<script defer data-domain="polygpt.app" src="https://plausible.io/js/script.js"></script>
```

## Customization

All colors are defined in Tailwind config at the top of `index.html`:

```javascript
colors: {
    'poly-cyan': '#00D4FF',
    'poly-blue': '#4D7CFF',
    'poly-purple': '#B24DFF',
}
```

Adjust as needed to match your branding.

## License

MIT
