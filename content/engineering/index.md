---
title: Engineering
description: Where the rubber meets the road
weight: 20
# date: 2019-07-10T17:55:14-07:00
---

When it comes right down to it, software needs to work. It needs to be resilient, robust, and reliable. It needs to be dependable. In many cases, this means taking humans---fickle creatures that we are---out of the equation as much as possible.

Much of my work over the last several years has been centered around automating processes to make them more reliable, less flaky, and in many cases, significantly faster. Among other things, I helped a company take a two-week _(at best!)_ deployment cycle and turn it into a fully automated continuous integration/continuous delivery pipeline with only about a 1-hour delay between submission and deployment. This is even easier now with the myriad tools and software-as-a-service offerings that are available.

A good example of the kind of "best processes" I aim for can be found in:

- [**order-fetcher**](https://github.com/JaredReisinger/order-fetcher): An easy-to-use command-line for extracting order/item data from a WooCommerce site. I use Greenkeeper to keep an eye on dependencies---and in many cases it handles updates entirely hands-free---and any commits are automatically built via Travis CI. Further, the `sematic-release` tool ensures that the version number is bumped and a new package published to npm based entirely on the kind of change in the commit.
