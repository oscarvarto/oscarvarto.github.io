# Work and Good Customs

Multilingual Hugo blog using the [hugo-book](https://github.com/alex-shpak/hugo-book) theme. Deployed to GitHub Pages at `work-and-good-customs.oscarvarto.mx`.

## Setup

```sh
git clone <repo-url>
cd oscarvarto.github.io
git submodule update --init --recursive
```

## Adding Content

### Markdown posts

Create a file in `content/posts/` with the naming convention `<slug>.<lang>.md` (e.g., `my-post.en.md`, `my-post.es.md`).

```toml
+++
title = 'Post Title'
date = 2026-02-15T00:00:00-06:00
draft = false
tags = ['tag1', 'tag2']
categories = ['category']
+++

Your Markdown content here.
```

### Raw HTML posts

For self-contained HTML articles (with their own CSS/JS), use `.html` content files with `layout = 'raw'`:

```toml
+++
title = 'Article Title'
date = 2026-02-15T00:00:00-06:00
draft = false
layout = 'raw'
tags = ['tag1']
categories = ['category']

[params]
  rawJS = ['https://cdn.tailwindcss.com']
  rawFonts = ['https://fonts.googleapis.com/css2?family=Inter:wght@400;700&display=swap']
  rawCSS = ['https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css']
  rawBaseTarget = '_blank'
  bodyClass = 'bg-gray-50'
+++

<style>
/* your custom CSS */
</style>

<!-- your HTML content -->

<script>
// your scripts
</script>
```

The `raw` layout renders a standalone page (no theme wrapper), injecting the specified CDN resources into `<head>`.

## Local Preview

```sh
hugo server
```

## Publishing

Push to `main`. GitHub Actions builds and deploys automatically.
