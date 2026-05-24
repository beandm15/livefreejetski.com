# NH Jet Fun - Quick Workflow Guide

**How to Make Updates to nhjetfun.com**

---

## 🔄 The Workflow (3 Steps)

### Step 1️⃣: Edit Your Files
Edit locally on your computer, OR edit directly on GitHub

### Step 2️⃣: Push to GitHub
Commit your changes to the repository

### Step 3️⃣: Netlify Deploys
Automatic! Your site updates within 1-5 minutes

---

## 📝 How to Update Content

### Method A: Edit on GitHub (Easiest - No Downloads)

**Perfect for:** Small text changes, quick fixes

1. Go to https://github.com/beandm15/nhjetfun.com
2. Click on the file you want to edit (e.g., `index.html`)
3. Click the **pencil icon** (✏️) in the top right
4. Make your changes
5. Scroll down and click **"Commit changes"**
6. Done! ✅ Netlify deploys automatically (1-5 minutes)

---

### Method B: Edit Locally (Better for Big Changes)

**Perfect for:** Multiple changes, new images, major redesigns

**Setup (first time only):**
```bash
# Download the code
git clone https://github.com/beandm15/nhjetfun.com
cd nhjetfun.com
```

**Making changes:**
```bash
# Edit your files in your text editor

# Check what changed
git status

# Prepare your changes
git add .

# Describe what you changed
git commit -m "Updated contact section with new hours"

# Push to GitHub
git push origin main
```

Done! ✅ Netlify deploys automatically (1-5 minutes)

---

## 🖼️ How to Add/Update Images

### Via GitHub Website:
1. Go to https://github.com/beandm15/nhjetfun.com
2. Click **"Add file"** → **"Upload files"**
3. Drag and drop your image
4. Click **"Commit changes"**
5. Update `index.html` to reference the new image

### Via Command Line:
1. Copy your image to the project folder
2. Run:
```bash
git add your-image.jpg
git commit -m "Added new image"
git push origin main
```

**Remember:** Update `index.html` to use the new image
```html
<img src="/your-image.jpg" alt="Description">
```

---

## ✅ Verify Your Changes

1. **Wait 1-5 minutes** after pushing to GitHub
2. Visit **https://nhjetfun.com**
3. **Hard refresh** (Ctrl+Shift+Delete on Windows, Cmd+Shift+Delete on Mac)
4. Check that your changes appear
5. Done! ✅

---

## 🔍 Check Deployment Status

1. Go to **https://app.netlify.com**
2. Click your **nhjetfun** project
3. Look at the **Deploys** section
4. See the status:
   - 🟢 **Published** = Success!
   - 🟡 **Building** = In progress, wait a few seconds
   - 🔴 **Failed** = Check the deploy log

---

## ⚡ Quick Reference

| Task | Steps | Time |
|------|-------|------|
| **Update text/HTML** | Edit on GitHub → Commit → Done | 5 min |
| **Add image** | Upload to GitHub → Update HTML → Done | 10 min |
| **Fix typo** | Edit on GitHub → Commit → Done | 5 min |
| **Major redesign** | Edit locally → Push → Done | 15 min |
| **Revert changes** | GitHub history → Revert commit → Done | 5 min |

---

## 📋 Files You'll Edit

| File | What's In It | When You Edit |
|------|-------------|--------------|
| `index.html` | Entire website (text, layout, styles) | Every content update |
| `jetski-sunset.jpg` | Contact section image | When changing photos |
| `rental-agreement.html` | Rental agreement page | When updating terms |
| `README.md` | GitHub documentation | Rarely needed |

---

## 🚨 Common Issues & Fixes

### "My changes didn't appear"
- [ ] Check Netlify dashboard - deployment may be in progress
- [ ] Hard refresh your browser (Ctrl+Shift+Delete)
- [ ] Wait 5 more minutes
- [ ] Check Netlify deploy log for errors

### "Image won't show"
- [ ] Verify filename is correct in `index.html`
- [ ] Check image path starts with `/` (slash)
- [ ] Verify image file is uploaded to GitHub
- [ ] Hard refresh browser
- [ ] Check file extension (.jpg, .png, etc.)

### "Accidentally broke something"
- [ ] Don't panic! GitHub has version history
- [ ] Go to GitHub repository
- [ ] Click "Commits" to see history
- [ ] Find the version before your changes
- [ ] Click "Revert this commit"
- [ ] Your old version redeploys

---

## 🔐 Remember

✅ **Do:**
- Edit files on GitHub or locally
- Commit with clear messages
- Wait 1-5 minutes after pushing
- Hard refresh browser to see changes
- Check Netlify dashboard if unsure

❌ **Don't:**
- Edit live without testing first
- Upload very large files (over 10MB)
- Delete files unless you mean to
- Forget to commit your changes

---

## 📞 Need Help?

- **GitHub:** https://github.com/beandm15/nhjetfun.com
- **Netlify Status:** https://app.netlify.com
- **Website:** https://nhjetfun.com
- **Email:** bookings@nhjetfun.com

---

## 🎯 Summary

```
Your Computer
    ↓
    Edit files
    ↓
GitHub (git push)
    ↓
Netlify (watches)
    ↓
Auto-deploy
    ↓
nhjetfun.com (Updated!)
```

**That's it!** 🚀

Every time you push to GitHub, Netlify automatically builds and deploys your changes to the live website.
