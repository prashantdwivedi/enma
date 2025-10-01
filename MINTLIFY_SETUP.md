# Mintlify Documentation Setup Guide

Your MkDocs documentation has been successfully converted to Mintlify! 🎉

## What's Changed

1. **Created `mint.json`** - The main Mintlify configuration file
2. **Updated all markdown files** - Added proper frontmatter with titles, descriptions, and icons
3. **Fixed image paths** - Updated all image paths to work with Mintlify's structure
4. **Enhanced homepage** - Added interactive cards and better organization

## Quick Start

### Option 1: Deploy to Mintlify Cloud (Recommended)

1. **Sign up for Mintlify** at [mintlify.com](https://mintlify.com)

2. **Connect your GitHub repository**

   - Go to your Mintlify dashboard
   - Click "New Documentation"
   - Connect your GitHub account
   - Select this repository
   - Mintlify will automatically detect the `mint.json` file

3. **Deploy**

   - Mintlify will automatically build and deploy your docs
   - Your docs will be live at `your-project.mintlify.app`

4. **Custom Domain** (Optional)
   - In your Mintlify dashboard, go to Settings → Custom Domain
   - Add your domain `enma.dev`
   - Follow the DNS configuration instructions

### Option 2: Local Development

1. **Install Mintlify CLI**

   ```bash
   npm i -g mintlify
   ```

2. **Preview your docs locally**

   ```bash
   mintlify dev
   ```

   Your docs will be available at `http://localhost:3000`

3. **Make changes**
   - Edit markdown files in the `docs/` folder
   - Edit `mint.json` to update navigation or theme
   - Changes will hot-reload automatically

## Project Structure

```
enma/
├── mint.json              # Mintlify configuration
├── docs/                  # Documentation content
│   ├── index.md          # Homepage
│   ├── assets/           # Images and assets
│   ├── linux-commands/   # Linux commands guides
│   ├── linux-software/   # Software installation guides
│   └── tools-customise/  # Tools customization guides
└── MINTLIFY_SETUP.md     # This guide
```

## Configuration Overview

### `mint.json` Key Features

- **Teal color scheme** - Matching your original MkDocs theme
- **Tabbed navigation** - Three main sections (Linux Commands, Linux Software, Tools Customise)
- **GitHub integration** - Links to your repository
- **Search enabled** - Full-text search across all documentation
- **Responsive design** - Works great on mobile and desktop

### Customization Options

Edit `mint.json` to customize:

- **Colors** - Change `colors.primary`, `colors.light`, `colors.dark`
- **Logo** - Update `logo.dark` and `logo.light` paths
- **Navigation** - Modify the `navigation` array
- **Tabs** - Add or remove tabs in the `tabs` array
- **Footer** - Update `footerSocials` links

## Key Differences from MkDocs

| Feature       | MkDocs          | Mintlify               |
| ------------- | --------------- | ---------------------- |
| Config File   | `mkdocs.yml`    | `mint.json`            |
| Local Preview | `mkdocs serve`  | `mintlify dev`         |
| Build Command | `mkdocs build`  | Automatic on deploy    |
| Hosting       | Self-hosted     | Cloud-hosted           |
| Themes        | Material/Custom | Built-in modern theme  |
| Components    | Limited         | Rich component library |

## Advanced Features

### Using Mintlify Components

You can now use Mintlify's rich component library:

#### Cards

```markdown
<Card title="Title" icon="icon-name" href="/path">
  Description
</Card>
```

#### Card Groups

```markdown
<CardGroup cols={2}>
  <Card title="Card 1" icon="code">Content</Card>
  <Card title="Card 2" icon="book">Content</Card>
</CardGroup>
```

#### Callouts

```markdown
<Note>This is a note</Note>
<Warning>This is a warning</Warning>
<Tip>This is a tip</Tip>
<Info>This is info</Info>
```

#### Tabs

```markdown
<Tabs>
  <Tab title="Tab 1">
    Content for tab 1
  </Tab>
  <Tab title="Tab 2">
    Content for tab 2
  </Tab>
</Tabs>
```

#### Accordions

```markdown
<Accordion title="Click to expand">
  Hidden content here
</Accordion>
```

### SEO Optimization

Each page has frontmatter with:

- `title` - Used for page title and SEO
- `description` - Used for meta description
- `icon` - Font Awesome icon name

Example:

```yaml
---
title: Page Title
description: Page description for SEO
icon: terminal
---
```

## Analytics Setup

To add Google Analytics:

1. Get your GA4 measurement ID
2. Update `mint.json`:
   ```json
   "analytics": {
     "ga4": {
       "measurementId": "G-XXXXXXXXXX"
     }
   }
   ```

## GitHub Integration

### Auto-deploy on Push

Mintlify automatically deploys when you push to your GitHub repository:

1. Make changes to your docs
2. Commit and push to GitHub
3. Mintlify automatically rebuilds and deploys

### Preview Deployments

- Every pull request gets a preview URL
- Test changes before merging to main

## Troubleshooting

### Images not showing?

- Make sure image paths start with `/docs/assets/`
- Check that images exist in `docs/assets/` folder

### Page not in navigation?

- Add the page path to `navigation` in `mint.json`
- Format: `"docs/folder/filename"` (without `.md`)

### Local preview not working?

```bash
# Reinstall Mintlify CLI
npm uninstall -g mintlify
npm install -g mintlify

# Clear cache and restart
mintlify dev --clear-cache
```

## Support and Resources

- **Mintlify Documentation**: https://mintlify.com/docs
- **Community Discord**: Join Mintlify Discord for help
- **GitHub Issues**: Report issues in this repository

## Next Steps

1. **Deploy to Mintlify** - Follow Option 1 above
2. **Set up custom domain** - Point enma.dev to Mintlify
3. **Add analytics** - Set up Google Analytics
4. **Customize theme** - Adjust colors and branding in `mint.json`
5. **Add more content** - Create new guides and tutorials

## Keeping Both Systems (Optional)

If you want to keep both MkDocs and Mintlify:

- MkDocs files remain unchanged
- `mint.json` and updated markdown files work with Mintlify
- You can continue to build MkDocs with `mkdocs build`
- Choose which platform to use for production

---

**Questions?** Open an issue on GitHub or refer to [Mintlify's documentation](https://mintlify.com/docs).
