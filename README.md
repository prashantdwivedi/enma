# Enma Dev

```
░░░░░░░ ░░░    ░░ ░░░    ░░░  ░░░░░      ░░░░░░  ░░░░░░░ ░░    ░░
▒▒      ▒▒▒▒   ▒▒ ▒▒▒▒  ▒▒▒▒ ▒▒   ▒▒     ▒▒   ▒▒ ▒▒      ▒▒    ▒▒
▒▒▒▒▒   ▒▒ ▒▒  ▒▒ ▒▒ ▒▒▒▒ ▒▒ ▒▒▒▒▒▒▒     ▒▒   ▒▒ ▒▒▒▒▒   ▒▒    ▒▒
▓▓      ▓▓  ▓▓ ▓▓ ▓▓  ▓▓  ▓▓ ▓▓   ▓▓     ▓▓   ▓▓ ▓▓       ▓▓  ▓▓
███████ ██   ████ ██      ██ ██   ██     ██████  ███████   ████
```

An enma.dev, a simple Linux tips and tricks website, shares that experience with linux exploration.

## 📚 Documentation Platforms

This repository now supports **two documentation platforms**:

### 🎨 Mintlify (Modern, AI-Native)

Beautiful, modern documentation with rich components and AI-powered features.

- **Setup Guide**: See [MINTLIFY_SETUP.md](MINTLIFY_SETUP.md)
- **Preview locally**: `mintlify dev`
- **Deploy**: Connect to Mintlify.com or use their CLI

### 📖 MkDocs (Classic, Material Theme)

Traditional static site generator with Material theme.

- **Config**: `mkdocs.yml`
- **Preview locally**: `mkdocs serve`
- **Build**: `mkdocs build`

## 🚀 Quick Start

### Option 1: Mintlify (Recommended)

```bash
# Install Mintlify CLI
npm i -g mintlify

# Preview documentation
mintlify dev

# Open http://localhost:3000
```

**Deploy to production:**

- See [DEPLOYMENT.md](DEPLOYMENT.md) for step-by-step deployment guide
- See [MINTLIFY_SETUP.md](MINTLIFY_SETUP.md) for full setup instructions

### Option 2: MkDocs

```bash
# Install dependencies
pip install mkdocs-material mkdocs-glightbox mkdocs-minify-plugin

# Preview documentation
mkdocs serve

# Build static site
mkdocs build
```

## 📖 Content Sections

- **Linux Commands** - Essential Linux commands and system administration
- **Linux Software** - Installation guides for useful Linux tools
- **Tools Customise** - Customize your development environment

## 🛠️ Technologies

- **Mintlify** - Modern documentation platform
- **MkDocs** - Static site generator (legacy support)
- **Markdown** - Content format
- **GitHub** - Version control and hosting

## 📝 Contributing

Contributions are welcome! Feel free to:

1. Fork the repository
2. Create a new branch for your changes
3. Add or update documentation
4. Submit a pull request

## 📄 License

This project is open source and available for use.

## 📚 Documentation Guides

- **[QUICKSTART.md](QUICKSTART.md)** - Quick reference and common tasks
- **[DEPLOYMENT.md](DEPLOYMENT.md)** - How to deploy your docs (no build needed!)
- **[MINTLIFY_SETUP.md](MINTLIFY_SETUP.md)** - Complete setup and customization
- **[MIGRATION_SUMMARY.md](MIGRATION_SUMMARY.md)** - Detailed migration changelog

## 🔗 Links

- **Website**: [enma.dev](https://enma.dev)
- **Repository**: [github.com/prashantdwivedi/enma](https://github.com/prashantdwivedi/enma)
- **Mintlify Docs**: [mintlify.com/docs](https://mintlify.com/docs)
