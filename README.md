# Poetry Blog

A personal poetry collection hosted on GitHub Pages using Hugo. This site showcases poems exploring life, nature, and reflection.

**Live Site**: https://poems.akhil.me

## About the Project

This is a beautifully minimal, fast-loading poetry blog built with Hugo and deployed directly to GitHub Pages with automated CI/CD.

## License

This work is licensed under **Creative Commons Attribution-NonCommercial-NoDerivatives 4.0 International (CC BY-NC-ND 4.0)**.

### What You Can Do:
- ✅ Read and share the poems with attribution
- ✅ Link to individual poems
- ✅ Print or download for personal, non-commercial use

### What You Cannot Do:
- ❌ Modify or create derivative works
- ❌ Use commercially
- ❌ Remove attribution

For details, see [LICENSE.md](LICENSE.md)

## Adding New Poems

To add a new poem to the collection:

### 1. Create a New Markdown File

Create a new `.md` file in the `content/poems/` directory. For example:

```bash
content/poems/my-new-poem.md
```

### 2. Use YAML Frontmatter

Include metadata at the top of the file:

```yaml
---
title: "My Poem Title"
date: 2026-02-12T10:30:00Z
draft: false
description: "A brief description of the poem"
---

## My Poem

Your poem content here...
```

**Frontmatter Fields:**
- `title`: The title of your poem
- `date`: Publication date in ISO format (YYYY-MM-DDTHH:MM:SSZ)
- `draft`: Set to `false` to publish, `true` to hide
- `description`: A brief summary (shows in listings)

### 3. Write Your Poem

Below the frontmatter separator (`---`), write your poem using Markdown formatting.

### Example Poem:

```markdown
---
title: "The Evening Sky"
date: 2026-02-15T18:00:00Z
draft: false
description: "Reflections on the beauty of dusk"
---

## The Evening Sky

Colors fade to deeper hues,
The sun descends beyond the view,
While stars awaken, soft and blue,
The day surrenders to the night.
```

## Local Development

### Prerequisites

- [Hugo Extended](https://gohugo.io/installation/) (version 0.88.0 or later)

### Setup

1. Clone the repository:
```bash
git clone https://github.com/akhilrex/poems.git
cd poems
```

2. Initialize git submodules for the theme:
```bash
git submodule update --init --recursive
```

3. Run the Hugo development server:
```bash
hugo server
```

4. Visit http://localhost:1313 in your browser to see the site.

### Building

To build the static site:

```bash
hugo --minify
```

This generates optimized HTML, CSS, and JavaScript in the `public/` directory.

## Deployment

The site automatically deploys to GitHub Pages when you push to the `main` branch.

### GitHub Pages Configuration

1. Go to your repository settings → Pages
2. Set the source to "Deploy from a branch"
3. Select `gh-pages` as the branch and `/ (root)` as the folder
4. The GitHub Actions workflow handles everything else

### How the Deployment Works

The `.github/workflows/hugo-deploy.yml` workflow:
1. Triggers on every push to the `main` branch
2. Checks out your code including theme submodules
3. Builds the Hugo site
4. Deploys the `public/` directory to the `gh-pages` branch
5. GitHub Pages serves the site at `https://poems.akhil.me`

## Project Structure

```
poems/
├── .github/
│   └── workflows/
│       └── hugo-deploy.yml          # GitHub Actions deployment
├── archetypes/
│   └── default.md                   # Content template
├── content/
│   └── poems/
│       ├── sample-poem.md           # Example poem
│       └── [your-poems].md          # Your poem files
├── layouts/                         # Custom layouts (optional)
├── static/                          # Static assets (CSS, images, etc.)
├── config.toml                      # Hugo configuration
├── LICENSE.md                       # License information
└── README.md                        # This file
```

## Site Configuration

The site is configured in `config.toml`:

- **Base URL**: https://poems.akhil.me
- **Theme**: ed
- **Language**: English (en-us)
- **Menu**: Home and Poems sections

To customize:
- Edit `config.toml` to change the title, description, or other settings
- Modify `archetypes/default.md` to change the template for new content

## Theme

This site uses the [Ed](https://github.com/sergeyklay/gohugo-theme-ed) theme, a beautifully minimal, distraction-free theme inspired by classical book design.

**Theme Features:**
- Minimal, distraction-free design
- Perfect for typography and poetry
- Mobile responsive
- Beautiful print styles
- Clean, classically-inspired aesthetics

## Troubleshooting

### Content Not Showing
- Check that `draft: false` is set in the frontmatter
- Verify the file is in `content/poems/` directory
- Make sure the YAML frontmatter is correctly formatted

### Build Failed
- Ensure you're using Hugo Extended version
- Check that the theme is properly initialized: `git submodule update --init --recursive`
- Review the workflow logs in GitHub Actions

### Custom Domain Setup
To use a custom domain (like `poems.akhil.me`):
1. Add a `CNAME` file to the `static/` directory with your domain name
2. Configure your domain's DNS settings to point to GitHub Pages
3. See [GitHub Pages Custom Domain Guide](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site)

## Contributing

This is a personal poetry blog. While the poems are shared for enjoyment, remember they're protected under the CC BY-NC-ND 4.0 license.

## Questions or Issues?

For technical issues with the site, create an issue in the [GitHub repository](https://github.com/akhilrex/poems/issues).

---

**Happy writing! 📝** Share your words with the world.
