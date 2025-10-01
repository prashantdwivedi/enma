# 🚀 Mintlify Deployment Guide

## MkDocs vs Mintlify Deployment

### ❌ Old Way (MkDocs)

With MkDocs, you had to manually build and deploy:

```bash
# Build the static site
mkdocs build

# This creates a 'site/' directory with HTML files
# Then manually upload to hosting (GitHub Pages, Netlify, etc.)
```

### ✅ New Way (Mintlify)

**No build step needed!** Mintlify automatically builds and deploys from your GitHub repository.

---

## 🎯 Mintlify Deployment Options

## Option 1: Mintlify Cloud (Recommended) 🌟

### Step 1: Sign Up

1. Go to [mintlify.com](https://mintlify.com)
2. Click "Sign Up" (or "Get Started")
3. Sign in with your GitHub account

### Step 2: Connect Repository

1. In your Mintlify dashboard, click **"New Documentation"**
2. Select **"Connect GitHub Repository"**
3. Authorize Mintlify to access your repositories
4. Select the `enma` repository from the list

### Step 3: Configure (Auto-detected!)

Mintlify will automatically:

- ✅ Detect your `mint.json` configuration
- ✅ Find your documentation files in `docs/`
- ✅ Set up the build pipeline

### Step 4: Deploy! 🚀

Click **"Deploy"** and that's it!

Your documentation will be live at:

```
https://your-project.mintlify.app
```

### Step 5: Auto-Deploy on Every Push

From now on, every time you push to GitHub:

```bash
# Make changes to your docs
git add .
git commit -m "Update documentation"
git push

# Mintlify automatically:
# 1. Detects the push
# 2. Builds your docs
# 3. Deploys the updates
# 4. Your site is live in ~30 seconds!
```

**No manual build needed!** ✨

---

## Option 2: Custom Domain Setup

### Connect Your Domain (enma.dev)

1. **In Mintlify Dashboard**

   - Go to Settings → **Custom Domain**
   - Enter: `enma.dev`
   - Click "Add Domain"

2. **Get DNS Records**

   Mintlify will show you DNS records like:

   ```
   Type: CNAME
   Name: @
   Value: cname.mintlify.com
   ```

3. **Update Your DNS Provider**

   Go to your domain registrar (where you bought enma.dev) and add the DNS records

4. **Wait for DNS Propagation**

   - Usually takes 5-30 minutes
   - SSL certificate auto-generated
   - Your docs will be live at `https://enma.dev`

---

## Option 3: Preview Branches

Mintlify automatically creates preview deployments for pull requests:

```bash
# Create a new branch
git checkout -b feature/new-guide

# Make changes and push
git push origin feature/new-guide

# Create a pull request on GitHub

# Mintlify automatically creates a preview URL like:
# https://preview-123.mintlify.app
```

You can test changes before merging! 🎯

---

## 📝 Deployment Workflow Comparison

### MkDocs Workflow (Old)

```bash
1. Edit docs                    # Local editing
2. mkdocs build                 # Manual build ⚠️
3. git add site/                # Commit build files
4. git commit -m "Update"
5. git push
6. Wait for hosting to update   # GitHub Pages/Netlify
7. Check if it worked           # Manual verification
```

### Mintlify Workflow (New)

```bash
1. Edit docs                    # Local editing
2. git commit -m "Update"
3. git push
4. ✨ Done! Auto-deployed in 30s
```

**That's it!** No build step, no manual deployment! 🎉

---

## 🔧 Local Development

### Preview Changes Locally

Before pushing to GitHub, preview your changes:

```bash
# Install Mintlify CLI (one time)
npm install -g mintlify

# Start local dev server
mintlify dev

# Open http://localhost:3000
# Hot reload enabled - changes show instantly!
```

### Validate Before Pushing

```bash
# Check if mint.json is valid
node -e "JSON.parse(require('fs').readFileSync('mint.json'))"

# Run GitHub Actions validation locally (optional)
# Requires act: https://github.com/nektos/act
act -j validate
```

---

## 📊 Monitoring Your Deployment

### Mintlify Dashboard

After deployment, monitor:

- 📈 **Analytics** - Page views, visitors
- 🔍 **Search Queries** - What users search for
- 📱 **Device Stats** - Mobile vs desktop
- 🌍 **Geography** - Where your visitors are from
- ⏱️ **Build Status** - Deployment history

### Build Notifications

Set up notifications:

1. Dashboard → Settings → **Notifications**
2. Enable:
   - ✅ Slack notifications
   - ✅ Email alerts
   - ✅ Discord webhooks
   - ✅ GitHub status checks

---

## 🔄 Continuous Deployment

### Automatic Workflow

```
┌─────────────┐
│  You Edit   │
│  Markdown   │
└──────┬──────┘
       │
       ▼
┌─────────────┐
│ git commit  │
│  git push   │
└──────┬──────┘
       │
       ▼
┌─────────────────┐
│ GitHub Receives │
│     Push        │
└──────┬──────────┘
       │
       ▼
┌─────────────────┐
│ Mintlify Webhook│
│    Triggered    │
└──────┬──────────┘
       │
       ▼
┌─────────────────┐
│  Auto Build     │
│  (~10-20s)      │
└──────┬──────────┘
       │
       ▼
┌─────────────────┐
│  Auto Deploy    │
│   (~5-10s)      │
└──────┬──────────┘
       │
       ▼
┌─────────────────┐
│ ✅ Live Site!   │
│ No Manual Work  │
└─────────────────┘
```

### Deployment Speed

Typical deployment times:

- Small changes (1-2 files): **~15-30 seconds**
- Medium updates (5-10 files): **~30-60 seconds**
- Large changes (20+ files): **~1-2 minutes**

**Much faster than MkDocs + GitHub Pages!** ⚡

---

## 🎨 Environment Variables (Optional)

### Add Secrets/Config

1. Mintlify Dashboard → Settings → **Environment Variables**
2. Add variables like:

   - `GA_MEASUREMENT_ID` - Google Analytics
   - `API_KEY` - For API docs
   - `ENVIRONMENT` - production/staging

3. Use in your docs:
   ```markdown
   Analytics ID: ${GA_MEASUREMENT_ID}
   ```

---

## 🐛 Troubleshooting Deployment

### Build Failed?

**Check the build logs:**

1. Mintlify Dashboard → **Deployments**
2. Click on the failed deployment
3. View error logs

**Common issues:**

❌ **Invalid JSON in mint.json**

```bash
# Validate locally
node -e "JSON.parse(require('fs').readFileSync('mint.json'))"
```

❌ **Missing page files**

```bash
# Check if all pages in mint.json exist
# Pages listed in navigation must exist in docs/
```

❌ **Image paths incorrect**

```bash
# Use /docs/assets/image.png format
# NOT /assets/image.png
```

### Deployment Stuck?

1. Check GitHub → Actions tab for any failures
2. Check Mintlify status page
3. Contact Mintlify support (very responsive!)

---

## 📚 Rollback Changes

### Revert to Previous Version

If you need to undo a deployment:

```bash
# Option 1: Git revert
git revert HEAD
git push

# Option 2: Mintlify Dashboard
# Dashboard → Deployments → Select version → "Rollback"
```

Mintlify keeps history of all deployments! 🕒

---

## ✅ Post-Deployment Checklist

After your first deployment:

- [ ] ✅ Site loads at Mintlify URL
- [ ] ✅ All pages accessible
- [ ] ✅ Images display correctly
- [ ] ✅ Search works
- [ ] ✅ Navigation functions properly
- [ ] ✅ Mobile view looks good
- [ ] ✅ Dark/light mode toggles
- [ ] ✅ Custom domain configured (if needed)
- [ ] ✅ Analytics enabled
- [ ] ✅ Notifications set up

---

## 🎯 Summary

### Key Differences

| Task           | MkDocs                  | Mintlify                      |
| -------------- | ----------------------- | ----------------------------- |
| Build          | Manual (`mkdocs build`) | **Automatic** ✨              |
| Deploy         | Manual upload           | **Automatic on push** ✨      |
| Hosting        | Self-managed            | **Mintlify Cloud** ✨         |
| SSL            | Manual setup            | **Auto-generated** ✨         |
| CDN            | Configure yourself      | **Built-in global CDN** ✨    |
| Preview PRs    | Not available           | **Automatic preview URLs** ✨ |
| Time to deploy | 5-15 minutes            | **30 seconds** ✨             |

### The Mintlify Advantage

**Before (MkDocs):**

- Build locally
- Commit build files
- Push to hosting
- Wait for deployment
- Hope nothing breaks 😅

**Now (Mintlify):**

- Edit docs
- Push to GitHub
- ✨ Done! 🎉

---

## 🚀 Ready to Deploy?

### Quick Deploy

```bash
# Make sure you're on the right branch
git checkout mintlify

# Commit any remaining changes
git add .
git commit -m "Ready for Mintlify deployment"

# Push to GitHub
git push origin mintlify

# Now go to mintlify.com and connect your repo!
```

### Need Help?

- 📖 [Mintlify Documentation](https://mintlify.com/docs)
- 💬 [Mintlify Discord Community](https://discord.gg/mintlify)
- 📧 Support: support@mintlify.com

---

**Your documentation is ready to go live!** 🌟

No more manual builds. No more hosting headaches. Just push and deploy! 🚀
