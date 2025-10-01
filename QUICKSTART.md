# 🚀 Mintlify Quick Start Guide

## 📦 Install Mintlify CLI

```bash
npm i -g mintlify
```

## 🔥 Run Locally

```bash
cd /Users/prashant/Developer/enma
mintlify dev
```

Open: http://localhost:3000

## 🌐 Deploy to Mintlify Cloud

### Step 1: Sign Up

Go to [mintlify.com](https://mintlify.com) and create an account

### Step 2: Connect Repository

1. Click "New Documentation"
2. Connect your GitHub account
3. Select the `enma` repository
4. Mintlify auto-detects `mint.json`

### Step 3: Deploy

- Push to GitHub → Auto-deploys
- Your docs go live instantly!

### Step 4: Custom Domain (Optional)

1. Mintlify Dashboard → Settings → Custom Domain
2. Add `enma.dev`
3. Update DNS records as shown
4. Wait for SSL certificate (5-10 mins)

## 🎨 Customization Cheat Sheet

### Colors

Edit `mint.json`:

```json
"colors": {
  "primary": "#14b8a6",    // Main color
  "light": "#5eead4",      // Light variant
  "dark": "#0d9488"        // Dark variant
}
```

### Add a New Page

1. Create markdown file: `docs/your-page.md`
2. Add frontmatter:
   ```yaml
   ---
   title: Your Page Title
   description: Page description
   icon: icon-name
   ---
   ```
3. Add to navigation in `mint.json`:
   ```json
   "navigation": [
     {
       "group": "Group Name",
       "pages": ["docs/your-page"]
     }
   ]
   ```

### Components

#### Cards

```markdown
<Card title="Title" icon="star" href="/link">
  Description
</Card>
```

#### Callouts

```markdown
<Tip>This is a tip</Tip>
<Warning>This is a warning</Warning>
<Info>This is info</Info>
<Note>This is a note</Note>
```

#### Tabs

```markdown
<Tabs>
  <Tab title="Option 1">
    Content 1
  </Tab>
  <Tab title="Option 2">
    Content 2
  </Tab>
</Tabs>
```

#### Code Groups

````markdown
<CodeGroup>
  ```bash Ubuntu
  apt install package
````

```bash macOS
brew install package
```

</CodeGroup>
```

## 📊 Analytics Setup

1. Get Google Analytics 4 Measurement ID
2. Edit `mint.json`:
   ```json
   "analytics": {
     "ga4": {
       "measurementId": "G-XXXXXXXXXX"
     }
   }
   ```

## 🔍 Icon Reference

Common icons for `icon` field in frontmatter:

| Category      | Icons                                             |
| ------------- | ------------------------------------------------- |
| General       | `book`, `file`, `folder`, `home`, `star`          |
| Tech          | `code`, `terminal`, `database`, `server`, `cloud` |
| Actions       | `download`, `upload`, `save`, `edit`, `delete`    |
| UI            | `palette`, `wrench`, `cog`, `shield`, `lock`      |
| Communication | `comments`, `message`, `envelope`, `bell`         |
| Media         | `image`, `video`, `music`, `camera`               |

Full list: [Font Awesome Icons](https://fontawesome.com/icons)

## 🐛 Troubleshooting

### Images not showing?

- Use `/docs/assets/image.png` format
- Check file exists in correct location

### Page not in navigation?

- Add to `navigation` in `mint.json`
- Remove `.md` extension from path
- Format: `"docs/folder/filename"`

### Hot reload not working?

```bash
# Kill process and restart
mintlify dev --clear-cache
```

### JSON validation error?

```bash
# Test if mint.json is valid
node -e "JSON.parse(require('fs').readFileSync('mint.json'))"
```

## 📝 File Structure

```
mint.json              ← Main config
docs/
  ├── index.md        ← Homepage
  ├── assets/         ← Images
  └── [folders]/      ← Content
```

## 🔗 Useful Links

- 📖 [Full Setup Guide](MINTLIFY_SETUP.md)
- 📋 [Migration Summary](MIGRATION_SUMMARY.md)
- 🌐 [Mintlify Docs](https://mintlify.com/docs)
- 💬 [Community Discord](https://discord.gg/mintlify)
- 📦 [GitHub Repo](https://github.com/prashantdwivedi/enma)

## ⚡ Common Commands

```bash
# Install CLI
npm i -g mintlify

# Run locally
mintlify dev

# Clear cache
mintlify dev --clear-cache

# Update CLI
npm update -g mintlify

# Check version
mintlify --version
```

## 🎯 Next Steps

1. ✅ Run `mintlify dev` to preview
2. ✅ Deploy to Mintlify Cloud
3. ✅ Set up custom domain
4. ✅ Add Google Analytics
5. ✅ Customize colors/theme
6. ✅ Add more content

## 💡 Pro Tips

- Use `<Tip>` components for helpful hints
- Add `icon` to pages for better navigation
- Group related pages in `navigation`
- Keep descriptions under 160 characters for SEO
- Test on mobile with `mintlify dev` → view on phone
- Use code groups for multi-platform commands

---

**Need help?** Check [MINTLIFY_SETUP.md](MINTLIFY_SETUP.md) for detailed instructions!
