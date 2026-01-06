# Solixar Digital Website

Company website for Solixar Digital LLC, hosting app landing pages, privacy policies, terms of service, and support information.

## Structure

```
solixardigital-website/
├── index.html                    # Company landing page
├── styles.css                    # Shared styles
├── apps/
│   └── prospectors-helper/
│       ├── index.html            # App landing page
│       ├── privacy.html          # Privacy Policy
│       ├── terms.html            # Terms of Service
│       └── support.html          # Support page
└── README.md
```

## URLs (after deployment)

- **Company:** https://solixardigital.com
- **App:** https://solixardigital.com/apps/prospectors-helper/
- **Privacy:** https://solixardigital.com/apps/prospectors-helper/privacy.html
- **Terms:** https://solixardigital.com/apps/prospectors-helper/terms.html
- **Support:** https://solixardigital.com/apps/prospectors-helper/support.html

## Deployment Instructions

### Step 1: Create GitHub Repository

```bash
cd /Users/eric/Projects/solixardigital-website
git init
git add .
git commit -m "Initial website with Prospector's Helper pages"
```

Then create a new repository on GitHub:
1. Go to https://github.com/new
2. Name it `solixardigital-website` (or `solixardigital.com`)
3. Keep it public (required for free GitHub Pages)
4. Don't initialize with README (you already have one)

```bash
git remote add origin https://github.com/YOUR_USERNAME/solixardigital-website.git
git branch -M main
git push -u origin main
```

### Step 2: Enable GitHub Pages

1. Go to your repository on GitHub
2. Click **Settings** → **Pages** (in left sidebar)
3. Under "Source", select **Deploy from a branch**
4. Select **main** branch and **/ (root)** folder
5. Click **Save**

Your site will be live at `https://YOUR_USERNAME.github.io/solixardigital-website/` within a few minutes.

### Step 3: Configure Custom Domain

#### In GitHub:
1. Go to **Settings** → **Pages**
2. Under "Custom domain", enter `solixardigital.com`
3. Click **Save**
4. Check "Enforce HTTPS" (after DNS propagates)

#### At Your Domain Registrar:

Add these DNS records:

**Option A: Apex domain (solixardigital.com)**

Add these A records pointing to GitHub's IP addresses:
```
Type: A
Name: @
Value: 185.199.108.153

Type: A
Name: @
Value: 185.199.109.153

Type: A
Name: @
Value: 185.199.110.153

Type: A
Name: @
Value: 185.199.111.153
```

**Option B: Also add www subdomain (recommended)**
```
Type: CNAME
Name: www
Value: YOUR_USERNAME.github.io
```

### Step 4: Wait for DNS Propagation

DNS changes can take up to 48 hours to propagate, but usually complete within a few hours. You can check status at https://dnschecker.org

### Step 5: Verify HTTPS

Once DNS propagates:
1. Go back to **Settings** → **Pages**
2. Check "Enforce HTTPS"

## Adding Future Apps

To add another app, create a new folder under `apps/`:

```
apps/
├── prospectors-helper/
└── new-app-name/
    ├── index.html
    ├── privacy.html
    ├── terms.html
    └── support.html
```

Copy the Prospector's Helper files as templates and update the content.

## For Apple App Store

Use these URLs in App Store Connect:

- **Privacy Policy URL:** `https://solixardigital.com/apps/prospectors-helper/privacy.html`
- **Terms of Service URL:** `https://solixardigital.com/apps/prospectors-helper/terms.html`
- **Support URL:** `https://solixardigital.com/apps/prospectors-helper/support.html`
- **Marketing URL:** `https://solixardigital.com/apps/prospectors-helper/`

## Updating Content

1. Edit the HTML files locally
2. Commit and push to GitHub:
   ```bash
   git add .
   git commit -m "Update privacy policy"
   git push
   ```
3. Changes will be live within minutes

## Local Development

To preview locally, you can use any simple HTTP server:

```bash
# Python 3
cd /Users/eric/Projects/solixardigital-website
python3 -m http.server 8000
# Then open http://localhost:8000

# Or use Node.js
npx serve
```
