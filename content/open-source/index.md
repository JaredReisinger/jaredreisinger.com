---
title: Open Source
description: Contributing to the community at large
weight: 50
# date: 2019-07-10T17:55:29-07:00
---

> If I have developed greater software, it is by standing on the shoulders of giants.
>
> {{<cite before="not quite" person="Isaac Newton (or Bernard of Chartres)" href="https://en.wikipedia.org/wiki/Standing_on_the_shoulders_of_giants" >}}

With so much in software and technology dependent on the open sharing of information and past effort, I would be remiss not to do so myself. Much of my work is owned by the companies for which I've worked, but some of it---and much of my personal effort---is open source.

In particular, I'm proud of:

- [**@jaredreisinger/react-crossword**](https://github.com/JaredReisinger/react-crossword) ([npm](https://www.npmjs.com/package/@jaredreisinger/react-crossword)): A flexible, responsive, and easy-to-use crossword component for React apps. After some dissatisfaction with the existing crossword component libraries (all apparently forked from the same original source), I decided to create my own, and it quickly shot to the top of the [npm search results for "react crossword"](https://www.npmjs.com/search?q=react%20crossword).

- [**puppycam.turehounds.com**](https://github.com/JaredReisinger/puppycam.turehounds.com): A site that hosts a 24/7 live-stream of the puppies we’ve whelped (only live for a couple of months every two or three years!) with news and other details about the puppies as they grow. The site is designed to auto-deploy and auto-refresh any time changes are made to the source.

- [**order-fetcher**](https://github.com/JaredReisinger/order-fetcher) ([npm](https://www.npmjs.com/package/order-fetcher)): An easy-to-use command-line for extracting order/item data from a WooCommerce site. As the technical point-of-contact for both the Seattle Kennel Club and Evergreen Basenji Club, I use order-fetcher to generate detailed order information for other club members.

- [**specialty-slurper**](https://github.com/JaredReisinger/specialty-slurper): Fills a niche need for the annual [Basenji Club of America](https://basenji.org) Yearbook, which includes the winners of all Basenji [specialties](https://www.akc.org/sports/conformation/resources/conformation-explanation/) for the year. There's more hard-coded logic in this tool than I'd prefer, but it saves _hours_ of time for the Yearbook editor every year.

- [**xyzzybot**](https://github.com/JaredReisinger/xyzzybot) (with [fizmo-json](https://github.com/JaredReisinger/fizmo-json)): Still a work-in-progress, xyzzybot brings the glory of Infocom-style text adventures (Zork, anyone?) to Slack. I particularly like the way that xyzzybot attempts to automatically distinguish game commands (`give flower to troll`) from out-of-band chatter in the channel (`hey, why don't we try giving the flower to the troll?`), with the goal of completely disappearing as the broker between the game and the players.

- [**Automatic mapping layout**](https://observablehq.com/d/58f420d9218ed67d): An Observable HQ notebook that explores using D3's "force layout" tools to create text-adventure-style game maps from minimal easy-to-write input.

- [**Commentator**](http://jaredreisinger.github.io/Commentator/): Although way out-of-date (it's for Visual Studio 2012 and 2013!), Commentator shows the type of user interaction I'm really proud of: when it's doing its job, things _just work_ and you hardly even notice it's there.

I've also contributed odds-and-ends to several open-source projects:

- [reactjs/react-docgen](https://github.com/reactjs/react-docgen/pull/454)
- Compromise: [fix build on non-Macs](https://github.com/spencermountain/compromise/pull/650), [automated build pipeline](https://github.com/spencermountain/compromise/pull/679), and [regexp-style matching](https://github.com/spencermountain/compromise/pull/715)
- [pg_hashids](https://github.com/iCyberon/pg_hashids/pull/20): fixed a bug in low-level C code that calls the PostgresQL API; the bug had been present for years, since the creation of the library
- [ipedrazas/drone-helm](https://github.com/ipedrazas/drone-helm/pull/87)
- [helm/charts](https://github.com/helm/charts/pull/9390)
- Discourse: [pagination](https://github.com/discourse/discourse/pull/4866), [developing via Docker](https://github.com/discourse/discourse/pull/4450), [email whitelisting/blacklisting with GitHub auth](https://github.com/discourse/discourse/pull/4457), and [benchmarking when running in Docker](https://github.com/discourse/discourse/pull/4454)

And, of course, you can always look at [all of my public repositories on GitHub](https://github.com/JaredReisinger?tab=repositories).
