# LucentLink

A clean, customizable, and responsive Linktree-style landing page built using HTML, Tailwind CSS, and Font Awesome. Easily manage your profile, social links, messaging guidelines, About section, and link cards directly from Markdown front matter.

## Live Preview

[LucentLink](https://cx48.github.io/LucentLink-Hugo") can be deployed for free using Vercel or GitHub Pages

![LucentLink Screenshot](https://raw.githubusercontent.com/cx48/LucentLink-Hugo/refs/heads/main/static/images/screenshot.png)

## Features

- **Profile Section**: Display a profile image, name, description, and social icons.
- **Messaging Etiquette**: Optional section to share guidelines on how to contact you.
- **About Section**: Optional section to highlight professional background, current focus, and personal interests.
- **Link Cards**: Styled link cards with icons, titles, and descriptions.
- **Tailwind CSS**: Uses Tailwind utility classes for styling.
- **Font Awesome**: Include any Font Awesome icon for links and social icons.
- **Modular Partials**: All HTML markup is in Hugo partials for easy customization.

## Getting Started

### Prerequisites

- [Hugo (Extended)](https://gohugo.io/getting-started/installation/)
- Git (To track changes)

### Quick Setup

1. Create a new Hugo site (if you haven’t already)

```
hugo new site my-site
cd my-site
```

2. Clone this repo into your Hugo site’s themes folder

```
git clone https://github.com/cx48/LucentLink-Hugo.git themes/LucentLink-Hugo
```

3. Enable the theme in your new site’s `config.toml`. If `config.toml` doesn't exists, then edit `hugo.toml` by adding the following code.

```
baseURL = "https://yourdomain.com/"
languageCode = "en-us"
title = "LucentLink"
theme = "LucentLink-Hugo"
minVersion = "0.115.0"

[params]
  description     = "A clean, customizable, and responsive Linktree-style landing page built using HTML, Tailwind CSS, and Font Awesome."
  googleAnalytics = ""    # your GA ID, if any

[outputs]
  home = ["HTML"]
```

4. Copy or edit `content/_index.md`—that’s the only file you ever need to touch.

5. Run the dev server

```
hugo server -D
```

## Configuration

All content is driven by front matter in `content/_index.md`:

```yaml
title: "LucentLink"
profileImage: "images/img.jpg"
name: "Your Name"
description: "Your tagline or role"
socials:
  - url: "https://twitter.com/you"
    icon: "fab fa-twitter"
# ...
messaging:
  title: "Messaging Etiquette"
  items:
    - icon: "fas fa-check-circle"
      color: "text-green-400"
      text: "Your guideline here."
# ...
about:
  title: "About Me"
  sections:
    - heading: "Professional Background"
      content: "Your background text."
# ...
links:
  - href: "https://github.com/you"
    icon: "fab fa-github"
    title: "GitHub"
    description: "Explore my projects"
# ...
```

- **Add/Remove Sections**: Simply remove or comment out `messaging:` or `about:` blocks to toggle those sections.
- **Add Links**: Append to the `links:` array.
- **Add Socials**: Append to the `socials:` array.

## Partials

- `layouts/partials/profile.html`
- `layouts/partials/messaging.html`
- `layouts/partials/about.html`
- `layouts/partials/link-card.html`

You can override any partial by copying it into your project’s `layouts/partials/` folder and editing.

## Development

Run Hugo’s development server:

```bash
hugo server -D
```

Navigate to [http://localhost:1313](http://localhost:1313) to preview changes live.

## Deployment

### Vercel

1. Push your repo to GitHub.
2. Sign in to [Vercel](https://vercel.com/) and import the project.
3. Set the **Framework Preset** to **Hugo**.
4. Use the build command:
   ```bash
   hugo --gc --minify
   ```
5. Output directory: `public`
6. Deploy and visit your Vercel URL.

### GitHub Pages

1. In `config.toml`, set:
   ```toml
   baseURL = "https://<username>.github.io/<repo>/"
   publishDir = "public"
   ```
2. Build the site:
   ```bash
   hugo --gc --minify
   ```
3. Push the `public/` folder to the `gh-pages` branch:
   ```bash
   git subtree push --prefix public origin gh-pages
   ```

## Customization

- **CSS**: Update Tailwind config or your custom CSS in `assets/css` or `static/css`.
- **Icons**: Change any Font Awesome icon class in front matter.
- **Templates**: Edit partials or create new ones in `layouts/partials/`.

## Contributing

1. Fork this repo.
2. Create a feature branch: `git checkout -b feature/my-change`
3. Commit your changes: `git commit -m "feat: add new ..."
4. Push to branch: `git push origin feature/my-change`
5. Open a Pull Request.

## License

This project is licensed under the MIT License - see the LICENSE file for details.
