---
title: "Why I chose not to implement an AI agent even when it was tempting"
description: "A Shopify app case study on dead stock detection, inventory decisions, and why AI agents don’t belong in the decision layer of business-critical systems."
pubDate: 2025-01-26
---

Recently I worked on a Shopify app. The specs were great. On the surface it looked like I can finally develop an AI agent that will actually make decisions in a business cycle.

The app is about detecting dead stocks or products with declining sales.

## Why dead stocks can bleed e-commerce businesses silently?

Warehouse spaces are limited and is one of the main expenses of e-commerce businesses. As the business owner you need to make sure you're using this scarce resource efficiently and inside boundary of the business risks.

Let's say a product has 40 percent margin. Everyday it sits in the warehouse it's a ticking clock which reduces the margin because by sitting there it costs money to the business. That's one aspect.

The second aspect is the locked capital into inventory that's not cycling. You want to recycle the capital often to make sure you activate another margin opportunity on it over and over again.

It's similar to holding a losing position on your investment portfolio. Yes you might break even one day if you just hold it long enough. But then you're not allowed to use that capital elsewhere.

## Merchants need a stop loss on losing positions (dead stock) just like in trading and investing

Yes it's clear. I frankly find the metaphor clever. So that's the reason I made it a header.

## What was the app doing?

The app is configurable to run inventory analysis weekly or daily and then send a report.

- Products that had no sales in the last X days.
- Products that had declining sales.

After the detection the app takes different actions.

- Run a private campaign for the product and draft the emails and prepare the coupon codes as well as making the customer list that will get the deal on their inboxes.
- Put the product in a sales collection for catalog based discounts. This is the most straightforward but can be damaging for some brands whose buyers are sensitive to discounts.
- Sending an email to the supplier with a return request of the merchant have the power to do so contractually.
- Add product as a gift product next to other items.
- Create bundle products with other matching products based on the bought-together patterns.

I initially detected declining sales and forecasting based on linear regression. But yes this was an overcomplication. I then decided to do it based on velocity of the sales in the last 90 days Vs 30 days and made a threshold of 60 percent lower sales velocity. These as soft declines. Yet they can be **meaningful**.

## "Can be meaningful" part was the trigger that made me think I can make an AI agent to judge it.

I was excited finally I was gonna implement a proper AI agent into e-commerce. Only to realize later that this was also very much deterministic.

First of all my threshold might just be normal fluctuations of sales velocity and that can be variable based on the store and the nature of the product. İt could also be the case the product was in promotion 2 months ago. İt can also be the case it was Black Friday 1 month ago. İt could be that the products is a winter coat while now it's April aka seasonality. I could have let the AI decide based on all these facts if the read decline is normal or something that would cause the stock to be flagged as dead or dying stock.

You must have noticed it. These are all deterministic factors that can be coded. Leaving it to the fuzzy AI reasoning would actually be doing the same work by prompting and extra tooling for the AI agent. Which obviously is not a great design and a forceful implementation.

## Where's the line? When can AI decide safely or not?

The measure for me are two simple factors working together.

- Responsibility 
- Visibility

In our case AI implementation passed this test. Because the app was taking bounded actions with visible impact. And it was reducing the human need for managing and aspect of the inventory.

And by design the app was going to either be trusted to act autonomously or present the action as suggestion on the report sent to the merchant.

With good monitoring the visibility was there and the responsibility was taken by the person who approved autonomous action.

**But** when I removed the decision of selecting the products to be actioned upon from the AI. What I noticed was sad. The only remaining applicability of the AI agents was the email drafting part. Then all the fancy AI agents working together coolness disappeared.

I could have chosen to go ahead and build the AI agent anyways but I don't like pretending to be doing something useful when I'm actually making bad systems design. This app needs to live without the AI agents (except the email drafting part ).

I don’t see a good application of AI agents in the decision layer here, because the decision surface is already well-defined and the risk belongs to the business, not the system.

İf you're trying to make similar decisions and want to have a chat. Feel free to send me an email [berkan.duzgun@aizetech.nl](mailto:berkan.duzgun@aizetech.nk) Would be happy to think along.