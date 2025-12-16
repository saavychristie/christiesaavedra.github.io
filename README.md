# Christie Saavedra Portfolio Website

Your professional portfolio website for christiesaavedra.com

## Files Included

```
portfolio-site/
├── index.html              # Main portfolio page
├── dashboard.html          # Interactive healthcare dashboard demo
├── samples/
│   ├── quick-start-guide.html
│   ├── change-email.html
│   └── kb-article.html
├── assets/
│   ├── Resume_Christie_Saavedra.pdf    # Add your resume here
│   └── Portfolio_Christie_Saavedra.pdf  # Add your portfolio here
└── README.md
```

## Before You Deploy

1. **Add your PDF files** to the `assets/` folder:
   - `Resume_Christie_Saavedra.pdf`
   - `Portfolio_Christie_Saavedra.pdf`

2. **Update your LinkedIn URL** in index.html if needed (search for "linkedin.com/in/christiesaavedra")

---

## OPTION 1: Porkbun Static Hosting (Easiest)

Porkbun offers free static hosting with your domain!

### Steps:

1. **Log into Porkbun** at https://porkbun.com

2. **Go to Domain Management** → Click on **christiesaavedra.com**

3. **Click "Static Hosting"** (free with domain)

4. **Upload your files:**
   - Upload all files from this folder
   - Make sure `index.html` is at the root level
   - Upload the `samples/` and `assets/` folders with their contents

5. **Enable hosting** - Your site will be live at christiesaavedra.com!

### SSL Certificate:
Porkbun provides free SSL. Make sure HTTPS is enabled in your hosting settings.

---

## OPTION 2: GitHub Pages (Free, More Control)

### Steps:

1. **Create a GitHub account** at https://github.com (if you don't have one)

2. **Create a new repository:**
   - Name it: `christiesaavedra.github.io` (or any name)
   - Make it Public
   - Don't initialize with README

3. **Upload files:**
   - Click "uploading an existing file"
   - Drag all files from this folder
   - Commit the changes

4. **Enable GitHub Pages:**
   - Go to Settings → Pages
   - Source: Deploy from a branch
   - Branch: main, / (root)
   - Save

5. **Connect your domain (in Porkbun):**
   - Go to Porkbun → Domain Management → christiesaavedra.com
   - DNS Records → Add these records:

   ```
   Type: A
   Host: (leave blank or @)
   Answer: 185.199.108.153

   Type: A
   Host: (leave blank or @)
   Answer: 185.199.109.153

   Type: A
   Host: (leave blank or @)
   Answer: 185.199.110.153

   Type: A
   Host: (leave blank or @)
   Answer: 185.199.111.153

   Type: CNAME
   Host: www
   Answer: christiesaavedra.github.io
   ```

6. **Add custom domain in GitHub:**
   - Go to your repo Settings → Pages
   - Custom domain: christiesaavedra.com
   - Check "Enforce HTTPS"

7. **Wait 10-30 minutes** for DNS propagation

---

## OPTION 3: Netlify (Free, Easy Deployment)

### Steps:

1. **Go to** https://netlify.com and sign up (free)

2. **Drag and drop** this entire folder onto the Netlify dashboard

3. **Your site is live!** (with a random netlify.app URL)

4. **Add custom domain:**
   - Site settings → Domain management → Add custom domain
   - Enter: christiesaavedra.com
   - Follow their DNS instructions for Porkbun

---

## Testing Your Site

Before going live, you can test locally:

1. **On Mac/Linux:** Open Terminal, navigate to this folder, run:
   ```
   python -m http.server 8000
   ```
   Then open http://localhost:8000

2. **On Windows:** Same command in Command Prompt, or just double-click `index.html`

---

## Updating Your Site

To make changes after deployment:

- **Porkbun/Netlify:** Re-upload the changed files
- **GitHub Pages:** Edit files directly on GitHub or push changes via Git

---

## Need Help?

- **Porkbun Support:** https://porkbun.com/support
- **GitHub Pages Docs:** https://docs.github.com/en/pages
- **Netlify Docs:** https://docs.netlify.com

---

## Portfolio Link for Job Applications

Once live, share this link:

**https://christiesaavedra.com**

Or link directly to specific sections:
- Dashboard: https://christiesaavedra.com/dashboard.html
- Quick-Start Guide: https://christiesaavedra.com/samples/quick-start-guide.html
- Change Email: https://christiesaavedra.com/samples/change-email.html
- KB Article: https://christiesaavedra.com/samples/kb-article.html
