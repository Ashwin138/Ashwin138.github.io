# Kamaucha.me Redirector

A simple GitHub Pages redirector that redirects users from `kamaucha.me/name` to `kamauchanepali.com/tip/name`.

## Features

- Redirects any path from kamaucha.me to kamauchanepali.com/tip
- Works with GitHub Pages (static hosting)
- Fast and lightweight HTML/JavaScript solution
- Beautiful loading animation

## How it Works

1. User visits: `kamaucha.me/example`
2. JavaScript detects the path and redirects to: `kamauchanepali.com/tip/example`

The redirect preserves the entire path, so:
- `kamaucha.me/john` → `kamauchanepali.com/tip/john`
- `kamaucha.me/mary/test` → `kamauchanepali.com/tip/mary/test`

## Setup with GitHub Pages

### Step 1: Create/Use Your GitHub Repository

Your repository: `ashwin138.github.io`

### Step 2: Push Files to GitHub

```bash
git init
git add .
git commit -m "Initial commit - Kamaucha redirector"
git branch -M main
git remote add origin https://github.com/ashwin138/ashwin138.github.io.git
git push -u origin main
```

### Step 3: Enable GitHub Pages

1. Go to your repository on GitHub: `https://github.com/ashwin138/ashwin138.github.io`
2. Click on **Settings**
3. Scroll to **Pages** section
4. Under **Source**, select **main** branch
5. Click **Save**

### Step 4: Configure Custom Domain

1. In the same **Pages** section, under **Custom domain**
2. Enter: `kamaucha.me`
3. Click **Save**

### Step 5: DNS Configuration

Go to your domain registrar (where you bought kamaucha.me) and add these DNS records:

**A Records** (point to GitHub Pages):
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

**CNAME Record** (for www subdomain):
```
Type: CNAME
Name: www
Value: ashwin138.github.io
```

### Step 6: Wait for DNS Propagation

DNS changes can take 1-48 hours to propagate. You can check status at: https://www.whatsmydns.net/

### Step 7: Enable HTTPS (Optional but Recommended)

Once DNS is configured:
1. Go back to GitHub Pages settings
2. Check **Enforce HTTPS**

## Testing Locally

Just open `index.html` in your browser to test the redirect logic.

## Files

- `index.html` - Main page with redirect logic
- `404.html` - Handles all routes via GitHub Pages 404 feature
- `CNAME` - Custom domain configuration for GitHub Pages

## Troubleshooting

If redirects aren't working:
1. Check that `404.html` exists (GitHub Pages uses this for routing)
2. Verify DNS settings are correct
3. Clear browser cache
4. Wait for DNS propagation (up to 48 hours)
