# NH Jet Fun Website - Project Overview & Instructions

**Project Name:** NH Jet Fun (nhjetfun.com)  
**Status:** Live and Active  
**Last Updated:** May 24, 2026

---

## 📋 Project Summary

NHJetFun.com is a modern jet ski rental website built with:
- **Code Management:** GitHub (beandm15/nhjetfun.com)
- **Hosting/Deployment:** Netlify
- **Domain:** Namecheap (nhjetfun.com)
- **Booking System:** Booqable (via bookings.nhjetfun.com)

The site showcases two jet ski rentals with pricing, requirements, FAQ, and contact information with automatic deployment from GitHub.

---

## 🛠️ Technology Stack

### Code Repository
- **Platform:** GitHub
- **Repository:** https://github.com/beandm15/nhjetfun.com
- **Branch:** main
- **Files:**
  - `index.html` - Main website (single-page HTML)
  - `jetski-sunset.jpg` - Contact section hero image
  - `rental-agreement.html` - Rental agreement page
  - `README.md` - Documentation

### Web Hosting & Deployment
- **Platform:** Netlify (https://app.netlify.com)
- **Project Name:** nhjetfun
- **Deployment:** Continuous (automatic from GitHub)
- **Build Settings:** Static HTML (no build process)
- **Live URL:** https://nhjetfun.com

### Domain & DNS
- **Registrar:** Namecheap
- **Domain:** nhjetfun.com
- **Nameservers:** Netlify DNS

### Booking System
- **Platform:** Booqable
- **Booking URL:** https://bookings.nhjetfun.com
- **Plan:** Standard (Grow plan needed for widget)

---

## 📁 Project Structure

```
nhjetfun-site (Local folder)
│
├── index.html                 # Main website file
├── jetski-sunset.jpg         # Contact section image
├── rental-agreement.html     # Rental agreement page
└── README.md                 # Documentation

GitHub Repository (beandm15/nhjetfun.com)
│
├── index.html
├── jetski-sunset.jpg
├── rental-agreement.html
└── README.md

Netlify Deployment
└── Automatically pulls from GitHub main branch
    └── Deploys to https://nhjetfun.com
```

---

## 🚀 Workflow: Making Changes

### Step 1: Update Files Locally

Create or edit files on your computer in your `nhjetfun-site` folder:
- `index.html` - Main content, sections, styling, JavaScript
- Image files (`.jpg`, `.png`) - Hero images, product photos
- HTML pages - Rental agreement, policies, etc.

### Step 2: Push to GitHub

**Using GitHub Website (Easiest):**
1. Go to https://github.com/beandm15/nhjetfun.com
2. Click the file you want to edit
3. Click the pencil icon (✏️)
4. Make your changes
5. Scroll to bottom and click **"Commit changes"**
6. GitHub saves the file

**Using Command Line (More Efficient):**
```bash
cd ~/nhjetfun-site
git add .
git commit -m "Description of changes"
git push origin main
```

### Step 3: Netlify Auto-Deploys

✅ **Automatic!** No additional steps needed.

- Netlify monitors your GitHub repository
- When you push changes, Netlify deploys within 1-5 minutes
- Visit https://nhjetfun.com to see live changes
- Check Netlify dashboard for deployment status

---

## 📝 Recent Changes

### May 24, 2026 — Boating Certificates Section & Great Bay Removal
- **Added:** New `#certificates` section with 4 NH-recognized online certification options
- **Added:** "Get Certified" nav link between Pricing and FAQ
- **Removed:** All promotional references to Great Bay (saltwater, not permitted for jet ski rentals)
- **Updated:** FAQ "Where can I ride?" answer now notes saltwater/tidal bodies are not permitted
- **Updated:** FAQ "Do I need a boating license?" answer links to the new certificates section
- **File:** `index.backup.20260524.html` saved as prior version backup

### May 24, 2026 - Contact Section Redesign
- **Removed:** Email contact form (not functioning)
- **Removed:** Phone number field
- **Updated:** Location to "Hampstead, New Hampshire"
- **Updated:** Rental season to "May 30 through Oct 15"
- **Removed:** Legal entity reference (Veralase LLC)
- **Added:** Jet ski sunset image in contact section
- **Improved:** Email link styled as clickable mailto: bookings@nhjetfun.com
- **Improved:** Footer contrast and readability
- **Connected:** GitHub for automatic deployments

---

## 🔗 Important Links

| Purpose | URL |
|---------|-----|
| **Live Website** | https://nhjetfun.com |
| **Booking System** | https://bookings.nhjetfun.com |
| **GitHub Repository** | https://github.com/beandm15/nhjetfun.com |
| **Netlify Dashboard** | https://app.netlify.com |
| **Namecheap Domain** | https://www.namecheap.com (domain management) |
| **Booqable Bookings** | https://booqable.com |

---

## 📞 Contact Information

**Business Email:** bookings@nhjetfun.com  
**Location:** Hampstead, New Hampshire  
**Rental Season:** May 30 through Oct 15  
**GitHub Owner:** beandm15  

---

## 🔐 Access & Credentials

### GitHub
- **URL:** https://github.com/beandm15/nhjetfun.com
- **Access:** Public repository (visible to all, editable by authorized users)
- **Username:** beandm15

### Netlify
- **URL:** https://app.netlify.com
- **Project:** nhjetfun
- **Access:** David Bean (site owner)

### Namecheap
- **Domain:** nhjetfun.com
- **DNS:** Configured to Netlify nameservers

### Booqable
- **Booking Platform:** https://bookings.nhjetfun.com
- **Current Plan:** Standard

---

## 📊 Deployment Pipeline

```
Local Computer
    ↓
    (Edit files)
    ↓
GitHub Repository (main branch)
    ↓
    (Push changes)
    ↓
Netlify (watches GitHub)
    ↓
    (Automatic build & deploy)
    ↓
nhjetfun.com (Live Site)
```

---

## 🛠️ Common Tasks

### Task: Update Website Content
1. Edit `index.html` on GitHub (web editor)
2. Commit changes
3. Wait 1-5 minutes
4. Refresh https://nhjetfun.com
5. Done! ✅

### Task: Change Contact Information
1. Edit the contact section in `index.html`
2. Update email, location, or season dates
3. Commit to GitHub
4. Netlify deploys automatically

### Task: Add New Image
1. Create or edit `index.html` to reference the image:
   ```html
   <img src="/your-image.jpg" alt="Description">
   ```
2. Upload the image file to GitHub (same way as HTML)
3. Commit changes
4. Netlify deploys automatically

### Task: Check Deployment Status
1. Go to https://app.netlify.com
2. Click "nhjetfun" project
3. Click "Deploys" tab
4. See list of recent deployments with status
5. Click a deploy to see details/logs

### Task: Revert Changes
1. Go to GitHub: https://github.com/beandm15/nhjetfun.com
2. Click "Commits" to see history
3. Find the version you want to revert to
4. Click the commit
5. Click "Revert this commit"
6. Netlify redeploys with old version

---

## ⚠️ Important Notes

1. **Single-Page Site:** The entire website is one `index.html` file plus assets
2. **No Build Process:** Changes deploy directly (no build step needed)
3. **Auto-Deployment:** Every GitHub commit triggers a Netlify deploy
4. **DNS Propagation:** Domain changes take 24 hours to propagate
5. **Booking System:** Booqable integration is separate from this website
6. **Backups:** GitHub serves as automatic backup of all code

---

## 📋 Checklist for Team Members

If adding team members to the project:

- [ ] Create GitHub account
- [ ] Grant access to beandm15/nhjetfun.com repository
- [ ] Provide Netlify dashboard access
- [ ] Provide Namecheap domain access (if needed)
- [ ] Explain the GitHub → Netlify workflow
- [ ] Share this documentation
- [ ] Test by making a small change and confirming deployment

---

## 🔍 Monitoring & Maintenance

### Daily
- Visit https://nhjetfun.com to verify site is live
- Check for any broken links or images

### Weekly
- Review Netlify deployment logs for errors
- Test booking system (bookings.nhjetfun.com)
- Check website performance

### Monthly
- Review GitHub commits for changes
- Confirm all analytics are tracking
- Test all contact forms and email links
- Verify SSL certificate is valid

---

## 🚨 Troubleshooting

### Site Not Updated After Push to GitHub?
1. Check Netlify deployment status (https://app.netlify.com)
2. Look for green checkmark (deployed successfully)
3. Hard refresh browser (Ctrl+Shift+Delete)
4. Wait 5 minutes and try again
5. Check Netlify deploy log for errors

### Image Not Showing?
1. Verify filename matches in HTML exactly
2. Confirm image is uploaded to GitHub
3. Check image path starts with `/` (root)
4. Hard refresh browser cache
5. Check Netlify deploy log

### Email Link Not Working?
1. Verify HTML has `href="mailto:bookings@nhjetfun.com"`
2. Test on different browser/device
3. Check for typos in email address
4. Hard refresh and try again

### Domain Not Resolving?
1. Check Netlify DNS settings
2. Verify nameservers in Namecheap match Netlify
3. Wait 24 hours for DNS propagation
4. Contact Netlify support if issue persists

---

## 📞 Support & Help

- **GitHub Issues:** https://github.com/beandm15/nhjetfun.com/issues
- **Netlify Support:** https://support.netlify.com
- **Namecheap Support:** https://www.namecheap.com/support
- **Booqable Support:** https://www.booqable.com/support

---

## 📝 Version History

| Date | Changes | Version |
|------|---------|---------|
| May 24, 2026 | Connected GitHub to Netlify, redesigned contact section | 2.0 |
| May 24, 2026 | Added Boating Certificates section (4 options); removed Great Bay references; added Get Certified nav link; updated FAQ boating license answer | 2.1 |
| Sept 20, 2025 | Added jet ski images and pricing | 1.5 |
| Sept 13, 2025 | Initial website launch | 1.0 |

---

## 📄 Document Information

- **Created:** May 24, 2026
- **Last Updated:** May 24, 2026
- **Maintained By:** David Bean (beandm15)
- **Location:** GitHub repository documentation
- **Status:** Active & Current

---

**For questions or updates to this guide, please contact bookings@nhjetfun.com**
