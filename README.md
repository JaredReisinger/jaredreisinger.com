# jaredreisinger.com

[![Netlify Status](https://api.netlify.com/api/v1/badges/10be7eed-7c05-49a5-bb6e-d54611383388/deploy-status)](https://app.netlify.com/sites/jaredreisinger/deploys)

Content and layout for [jaredreisinger.com](https://jaredreisinger.com) website. Uses Netlify's GitHub integration to automatically deploy this Hugo-driven site _for free!_


## Notes to self...

### TODO:

- [ ] See if I can get Hugo to process images so that hi-res original source can be the only thing checked in. I _think_ I might have been using `guetzli` manually because of how slow it was to process... but a responsize image solution (which creates much smaller images) might make it fast enough to use during the build. Eleventy can do this, so I bet Hugo can, too.

- [ ] Look into new Tailwind CSS integration with Hugo. (See next item as well.)

- [ ] Finally try to understand the CSS/JS from the original template. I have a feeling it's pretty old-school and there may be easier/smaller things that could be used like [Alpine.js](https://alpinejs.dev/)


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
- ~~"two" (what a name!)~~ REMOVED!
- regular list items in "tiles" style?
- ~~contact form~~ REMOVED!
