# Josh for CT - Campaign Website

A clean, fast, static HTML website for the Josh Elliott for Governor campaign.

## Quick Start

### Local Development

Just open `index.html` in your browser. No build step required.

For a local server (optional, but useful for testing):
```bash
# Using Python
python3 -m http.server 8000

# Then visit http://localhost:8000
```

### Editing with Claude Code

```bash
cd ~/Projects/joshforct-website  # or wherever you put it
claude
# Then just ask: "Update the events page to add a town hall on January 20th"
```

## Deployment to GitHub Pages

### Initial Setup

1. Create a new repo on GitHub called `joshforct-website` (or similar)

2. Push this folder to GitHub:
```bash
cd ~/Projects/joshforct-website
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/joshforct-website.git
git push -u origin main
```

3. Enable GitHub Pages:
   - Go to your repo on GitHub
   - Settings → Pages
   - Source: "Deploy from a branch"
   - Branch: `main` / `(root)`
   - Save

4. Your site will be live at `https://YOUR_USERNAME.github.io/joshforct-website/`

### Connecting Your Custom Domain (Namecheap)

1. In your GitHub repo, create a file called `CNAME` with just:
```
joshforct.com
```

2. In Namecheap, go to Domain List → Manage → Advanced DNS

3. Add these records:
   - **A Record**: Host `@`, Value `185.199.108.153`
   - **A Record**: Host `@`, Value `185.199.109.153`
   - **A Record**: Host `@`, Value `185.199.110.153`
   - **A Record**: Host `@`, Value `185.199.111.153`
   - **CNAME Record**: Host `www`, Value `YOUR_USERNAME.github.io.`

4. Wait 10-30 minutes for DNS to propagate

5. In GitHub Pages settings, enter `joshforct.com` as the custom domain and enable "Enforce HTTPS"

## Making Updates

```bash
cd ~/Projects/joshforct-website
claude
# Make your changes...
git add .
git commit -m "Description of changes"
git push
```

Site updates automatically within ~1 minute.

## File Structure

```
joshforct-website/
├── index.html          # Homepage
├── about.html          # About Josh
├── platform.html       # Policy platform
├── contact.html        # Contact form
├── events.html         # Upcoming events
├── dtc.html            # DTC information
├── css/
│   └── style.css       # All styles
├── images/             # Photos and graphics
│   └── (add your images here)
├── CNAME               # Custom domain config
└── README.md           # This file
```

## Forms

The forms currently point to `https://formspree.io/f/YOUR_FORM_ID`. To make them work:

1. Go to [formspree.io](https://formspree.io) and create a free account
2. Create a new form and get your form ID
3. Replace `YOUR_FORM_ID` in these files:
   - `index.html` (two forms: join form and email signup)
   - `contact.html`

## Images

Add images to the `images/` folder:
- `josh-portrait.jpg` - Main photo for About page
- `favicon.png` - Browser tab icon (32x32 or 64x64)

Then reference them in HTML like:
```html
<img src="images/josh-portrait.jpg" alt="Josh Elliott">
```

## Customization

### Colors

Edit the CSS variables at the top of `css/style.css`:
```css
:root {
  --primary: #063b54;      /* Main brand blue */
  --accent: #c41e3a;       /* Donate button red */
  /* ... etc */
}
```

### Fonts

Currently using Source Serif 4 (headings) and Source Sans 3 (body). Change in the `<head>` of each HTML file and in CSS variables.

## Tips

- Keep images optimized (use [squoosh.app](https://squoosh.app) to compress)
- Test on mobile before pushing (use browser dev tools)
- The site is pure HTML/CSS/JS - no build process needed
