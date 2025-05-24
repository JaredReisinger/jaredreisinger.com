# jaredreisinger.com

[![Netlify Status](https://api.netlify.com/api/v1/badges/10be7eed-7c05-49a5-bb6e-d54611383388/deploy-status)](https://app.netlify.com/sites/jaredreisinger/deploys)

Content and layout for [jaredreisinger.com](https://jaredreisinger.com) website. Uses Netlify's GitHub integration to automatically deploy this Hugo-driven site _for free!_

This site uses:

- [Hugo](https://gohugo.io) for processing content into static HTML
- [Node.js/npm](https://nodejs.org) to manage TailwindCSS and other development tooling
- [TailwindCSS](https://tailwindcss.com/) utility CSS for styling
- [Alpine.js](https://alpinejs.dev/) for very limited interactivity (the mobile navigation menu)

## Local development

Assuming that [`hugo`](https://gohugo.io) and [Node.js/`npm`](https://nodejs.org) is installed, and `npm install` has been run to pull down Node packages, `hugo server` will launch a development server that watches for changes.

## Concepts

> [!NOTE]
>
> Image handling needs to be revisited. The original template used Javascript to manage images, which prevented newer responsive-imaging structure from being used. (Likely because the pre-Hugo implementation already did this, and the conversion didn't make use of Hugo's asset pipelines.) As of [May 2025](https://github.com/JaredReisinger/jaredreisinger.com/pull/2), that Javascript is gone.

Images are (were!!) minimized via `guetzli`, and WebP variants created with `cwebp`:~~

```shell
some-page/ $ guetzli --verbose original.jpg tile.jpg
some-page/ $ cwebp -preset photo -v -mt original.jpg -o tile.webp
```

---

## History

Layout and SCSS/JS originally from [Forty](https://themes.gohugo.io/forty/) (and also [on github](https://github.com/MarcusVirg/forty)), but substantially revamped to minimize and streamline, and customize.

The templates for Forty were strangely redundant; I've endeavored to streamline this so that (for instance) both list and single pages can take advantage of the home page banner styles, tiles, etc. As of [May 2025](https://github.com/JaredReisinger/jaredreisinger.com/pull/2), this has been overhauled to use TailwindCSS and very minimal Alpine.js, removing a ton of custom CSS, JS, and vendored FontAwesome webfonts. In total, this change is a net reduction of around 28,000 lines of code.
