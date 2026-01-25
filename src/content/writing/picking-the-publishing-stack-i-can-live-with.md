---
title: "Picking the publishing stack I can live with"
description: "Evaluating Substack, Ghost, WordPress, and static publishing — and why I chose Cloudflare Pages with Astro."
pubDate: 2025-01-25
---

After some initial search it didn't take a long time to reduce the options to Substack, hosted Ghost, self hosted Wordpress and static file based publishing on Cloudflare Pages or GitHub pages.

Substack was attractive, it's zero maintenance and you just write and publish. In exchange of losing some of your domain authority and independence. But a future migration would be troublesome and I would sacrifice the hard built discoverability. I chose not to be locked in to a platform.

Hosted Ghost was a great option for my intended use case. I wanted to publish and keep my content for later discoverability by AI assistants and search engines. So that my work would be visible to the people to whom they matter for. But yes it costs 15 USD per month. In yearly context it's a cost that I don't want to pay.

Self hosted Wordpress sounds like the best. But only sounds like it. Because once you're on that ecosystem you will have to deal with future security vulnerabilities, attracting scanners and keeping the installation up-to-date with all the plugins working correctly. I remember from the past where a contact form plugin caused my installation to be used to send spam emails. Because I wasn't on top of every update of the plugin and Wordpress itself.

## My choice: Static file based publishing via Cloudflare pages and Astro

I chose this path because:

- It allows very fast serving of my content without any server side processing or complex caching configuration.
- I can still integrate third party contact forms and some interactive layer.
- I can set this up once and then it's for free and will keep my domain authority built over time.
- No platform locking.
- I can migrate to any of the other options with minimal friction because I own the content and how they are stored.
- Almost zero security headache. Which means I can keep up with the updates without pressure.
- It's hosted by Cloudflare's large CDN.

### What I sacrificed

- Convenience provided by Substack and hosted Ghost. I will need to use an editor like Obsidian on my phone and then commit and push the changes to publish.
- Fancy plugins these platforms offer. I don't mind that anyways.

I'm writing this down on my phone using Obsidian before setting the whole thing up. I thought I can use this as an experiment to see how this works before committing fully. And It works for me.
