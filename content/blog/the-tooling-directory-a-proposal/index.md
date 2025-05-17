---
title: The `.tooling/` directory, a proposal
description: Towards a more-organized root directory
date: 2020-08-25T13:16:00-07:00

# tileImage: https://unsplash.com/photos/Kw_zQBAChws
# tileAttrib: Ashim D’Silva

banner:
  image: tile.jpg
---

Take a peek in the root directory of a modern JavaScript project and you'll likely see more than a few config files used entirely for tooling for the project. One of mine has the following:

```
.babelrc
.commitlintrc.yaml
.editorconfig
.eslintrc.yaml
.gitignore
.prettierignore
.prettierrc.yaml
.releaserc.yaml
.snyk
.stylelintignore
.stylelintrc.yaml
.travis.yml
jest.config.js
styleguide.config.js
```

That's 14 of the 26 root files or directories committed to the project—_more than half!_ This is the first thing a person sees when they visit the project on GitHub or if they `npm install` it. This "noise" adds to the [cognitive load](https://en.wikipedia.org/wiki/Cognitive_load) for newcomers to the project. It even adds to the load for me, the author, in that I have wade through "50% noise" any time I look for something in the root directory.

Looking back, it's easy to see how this came about organically. First, with `git`, the `.gitignore` file was (and is) used to automatically exclude some files from being considered part of the repository. A `.gitignore` file can exist in any directory, but most commonly appears in a project root. After that, with the introduction of `npm` came `.npmignore` serving a similar purpose but excluding files when publishing an npm package. Then CI/CD pipelines add their configs, then ESLint, then other tools. With every new tool that needs some kind of config, the root directory is an obvious choice, and there's a _lot_ of precedence.

This root directory overload has such an impact that many projects put their source tree—their _raison d'etre!_—into a `src/` or `lib/` sub-directory. This is a tacit acknowledgement that there is simply too much "noise" in the root directory.

I think we can do better. Just as "all of the actual source code" ends up in `src/`, and "all of the installed dependency packages" end up in `node_modules/`, we can push for "all of the tooling configuration" to end up in `.tooling/`. This alone would change my example project:

{{<side-by-side>}}

{{%side-by-side-item%}}
##### from:
```
.git/
__mocks__/
build-tool/
docs/
example/
src/
.babelrc                 *
.commitlintrc.yml        *
.editorconfig            *
.eslintrc.yaml           *
.gitignore
.prettierignore          *
.prettierrc.yaml         *
.releaserc.yaml          *
.snyk                    *
.stylelintignore         *
.stylelintrc.yaml        *
.travis.yml              *
CHANGELOG.md
CODE_OF_CONDUCT.md
CONTRIBUTING.md
LICENSE
README.md
jest.config.js           *
package-lock.json
package.json
styleguide.config.js     *
```
{{%/side-by-side-item%}}

{{%side-by-side-item%}}
##### to:
```
.git/
.tooling/      <===== (with the 13 starred files)
__mocks__/     *
build-tool/    *
docs/
example/
src/
.gitignore
CHANGELOG.md
CODE_OF_CONDUCT.md
CONTRIBUTING.md
LICENSE
README.md
package-lock.json
package.json
```
{{%/side-by-side-item%}}

{{%side-by-side-item%}}
##### or even:
```
.git/
.tooling/      <===== (with 2 additional items)
docs/
example/
src/
.gitignore
CHANGELOG.md
CODE_OF_CONDUCT.md
CONTRIBUTING.md
LICENSE
README.md
package-lock.json
package.json
```
{{%/side-by-side-item%}}

{{</side-by-side>}}

{{<side-by-side>}}

{{%side-by-side-item%}}
What a difference this makes! Not only does it de-clutter the root directory, but it helps corral the odd standouts, like `jest.config.js` and `styleguide.config.js`, that don't start with a leading period and therefore don't sort alongside the other period-prefixed tooling config files.  The third "or even" example also moves two non-config tooling-related directories, for an even cleaner root.

#### Why call it `.tooling/`, and not `.config/`?

It's important and useful to not conflate "files needed for tools used by the project" with "configuration files for the project itself". The project config files may well be packaged with or deploy with the project, but the tooling configuration files almost certainly won't. Further, it makes it much more apparent where to look when, for example, one needs to adjust the ESLint settings: the tooling needs to change, and the necessary file is in `.tooling/`. For the more philosophical among you, naming the directory `.tooling/` is a matter of "name it for its _purpose_ (semantics), not for what it _is_ (syntax)".  It is less important that the files within are config files, and more important that the files within are for tooling. This also has the advantage that it becomes reasonable to put _non_-config tooling-related files here, such as in the "or even" case of the above example, or Storybook's `preview.js`, or project-local tooling scripts, and so on.
{{%/side-by-side-item%}}

{{<side-by-side-item>}}
{{<figure src="organized.jpg" width="300" attr="Photo by Edgar Chaparro" attrlink="https://unsplash.com/photos/r6mBXuHnxBk">}}
{{</side-by-side-item>}}

{{</side-by-side>}}

With its constituent files now hidden away, the leading period in the name `.tooling/` may not be strictly necessary. It serves a similar purpose to the leading period on the individual file names, however, subtly indicating that it's "not exactly" a part of the project, and in many presentations shifting the directory up and away from core project directories like `docs/` or `src/`.

#### What would have to happen?

Tools would need to add `.tooling/` as an additional place to look for their configuration. There is a chicken-and-egg issue here... until `.tooling/` becomes an expectation, supporting it seems extra work with little benefit. A project with 6 config files in the root, and only 2 in `.tooling/` is likely to forego using `.tooling/` entirely.

The good news is that many tools _already_ support variations in configuration file names—to support JSON, YAML, and/or TOML syntax—and location, so addding one more location shouldn't be a horrendous lift.  Yes, it does add some small additional complexity to their configuration-loading process, but not really _that_ much.

#### What can you do?

If you'd find something like a `.tooling/` directory useful, reach out to the folks responsible for your tools and ask! You could also use this as an excuse to contribute to some of those tools that you take advantage of every day.

This is an open request to cloud services to support looking for their config files in a `.tooling/` directory.  For example, `.tooling/.travis.yml` instead of only `.travis.yml`.  To the extent that these services don't have their own source code exposed as open source, only public demand can cause them to add support.
