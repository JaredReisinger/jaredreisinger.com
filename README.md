# jaredreisinger.com

[![Netlify Status](https://api.netlify.com/api/v1/badges/10be7eed-7c05-49a5-bb6e-d54611383388/deploy-status)](https://app.netlify.com/sites/jaredreisinger/deploys)

Content and layout for [jaredreisinger.com](https://jaredreisinger.com) website. Uses Netlify's GitHub integration to automatically deploy this Hugo-driven site _for free!_


## Notes to self...

### Local development

Assuming that [`hugo`](https://gohugo.io) is installed, `hugo server` will launch a development server tht watches for changes.

### Images

Images are minimized via `guetzli`, and WebP variants created with `cwebp`:

```shell
some-page/ $ guetzli --verbose original.jpg tile.jpg
some-page/ $ cwebp -preset photo -v -mt original.jpg -o tile.webp
```

_(Actually, we pre-process with hugo, so maybe we don't need to?)_

---

## History

Layout and SCSS/JS originally from [Forty](https://themes.gohugo.io/forty/) (and also [on github](https://github.com/MarcusVirg/forty)), but substantially revamped to minimize and streamline, and customize.

The templates for Forty were strangely duplicative; I've endeavored to streamline this so that (for instance) both list and single pages can take advantage of the home page banner styles, tiles, etc. Now, any page can opt in to any/all of the following:

- tiles
- "two" (what a name!)
- regular list items in "tiles" style?
- contact form
