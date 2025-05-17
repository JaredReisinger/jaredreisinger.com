---
title: Engineering
description: Where the rubber meets the road
weight: 20
# date: 2019–07–10T17:55:14–07:00
banner:
  image: tile.jpg
  class: style2
---

When it comes right down to it, software needs to work. It needs to be resilient, robust, and reliable. It needs to be dependable. In many cases, this means taking humans—fickle creatures that we are—out of the equation as much as possible.

Much of my work over the last several years has been centered around automating processes to make them more reliable, less flaky, and in many cases, significantly faster. Among other things, I helped a company take a two-week _(at best!)_ deployment cycle and turn it into a fully automated continuous integration/continuous delivery pipeline with only about a 1-hour delay between submission and deployment. This is even easier now with the myriad tools and software-as-a-service offerings that are available.

Good examples of the kind of “best processes” I aim for can be found in:

- [**@jaredreisinger/react-crossword**](https://github.com/JaredReisinger/react-crossword) ([npm](https://www.npmjs.com/package/@jaredreisinger/react-crossword)): A flexible, responsive, and easy-to-use crossword component for React apps. I used first Greenkeeper, and then Snyk to keep an eye on dependencies—in many cases it handles updates entirely hands-free—and any commits are automatically built via Travis CI. Further, the `semantic-release` tool ensures that the version number is bumped and a new package published to npm based entirely on the kind of change in the commit.

- [**puppycam.turehounds.com**](https://github.com/JaredReisinger/puppycam.turehounds.com): A site that periodically hosts a 24/7 live-stream (only live for a couple of months every two or three years!) of the puppies we’re raising with news and other details about the puppies as they grow. The site is designed to auto-deploy and auto-refresh any time changes are made to the source.

- [**order-fetcher**](https://github.com/JaredReisinger/order-fetcher): An easy-to-use command-line for extracting order/item data from a WooCommerce site. I used first Greenkeeper, and then Snyk to keep an eye on dependencies—in many cases it handles updates entirely hands-free—and any commits are automatically built via Travis CI. Further, the `semantic-release` tool ensures that the version number is bumped and a new package published to npm based entirely on the kind of change in the commit.

- [**semantic-release-image**](https://github.com/JaredReisinger/semantic-release-image): The `semantic-release` toolset, packaged as a standalone Docker image and updated weekly. This project uses GitHub Actions to automatically build and deploy the most recent versions of the tool and plugins, and helps any project—but especially non-Node.js ones—use `semantic-release` to manange releases.

- [**drone-plugin-helper**](https://github.com/JaredReisinger/drone-plugin-helper): A go-lang library to make it significantly easier to write and maintain Drone plugins that are based on wrapping an existing command-line tool. The case-study for using this library showed that it _drastically_ reduced the amount of hand-written code for creating a plugin; over _**85%**_ of the code for the case study was simply defining the structs that represent the sub-commands and options (i.e.“data”, vs. “code”), with only 354 total lines of code vs. about 665 lines in the existing plugin for the same underlying command-line tool. (And my case study covers more sub-commands and options than the existing one, as well.)
