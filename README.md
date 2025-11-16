# Boxi Xia - Personal Website

This repository contains the source code for my personal website, built with [Hugo](https://gohugo.io/) and the [PaperMod](https://github.com/adityatelange/hugo-PaperMod) theme.

🔗 **Live Site:** https://boxixia.github.io/

## About

A personal website showcasing my research, projects, and blog posts in machine learning and robotics.

## Tech Stack

- **Static Site Generator:** Hugo v0.152.2
- **Theme:** PaperMod
- **Deployment:** GitHub Pages via GitHub Actions
- **Features:** Search, archive, tags, dark/light mode, RSS feed

## Local Development

### Prerequisites
- Hugo Extended v0.152.2 or higher ([installation guide](https://gohugo.io/installation/))

### Running Locally

```bash
# Clone the repository with submodules
git clone --recurse-submodules https://github.com/boxiXia/boxiXia.github.io.git
cd boxiXia.github.io

# Start the development server
hugo server -D

# View at http://localhost:1313/
```

### Project Structure

```
.
├── .github/workflows/  # GitHub Actions deployment workflow
├── content/           # Markdown content files
│   ├── posts/        # Blog posts
│   ├── about.md      # About page
│   ├── archives.md   # Archive page
│   └── search.md     # Search page
├── themes/PaperMod/  # PaperMod theme (git submodule)
├── hugo.toml         # Hugo configuration
└── README.md         # This file
```

## Adding Content

### Create a New Post

```bash
hugo new posts/my-new-post.md
```

Then edit the file in `content/posts/my-new-post.md`.

### Publish a Post

Remove `draft: true` from the front matter or set it to `false`.

## Deployment

The site automatically deploys to GitHub Pages when changes are pushed to the `master` branch via GitHub Actions.

## Configuration

Main configuration is in `hugo.toml`. Key sections:
- Site metadata and URLs
- PaperMod theme settings
- Social media links
- Navigation menu
- Search and archive features

## License

Content is © Boxi Xia. Feel free to reference the Hugo setup and configuration.

## Contact

- GitHub: [@boxiXia](https://github.com/boxiXia)
- Google Scholar: [Profile](https://scholar.google.com/citations?user=TjA61pwAAAAJ&hl=en)
