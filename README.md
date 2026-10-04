# webshare pricing: what each plan actually costs, and when a pay-per-IP alternative comes out cheaper

Search "webshare pricing" and you land on a pricing page that doesn't really have *a* price. Webshare sells four different things, each billed in a different unit: per proxy, per IP, per gigabyte, or free. That's why the numbers you see in reviews range from "$2.99/month" to "$7 per GB" without anyone being technically wrong.

So here's the breakdown, plus the part most pricing articles skip: what happens when your workload is heavy enough that per-GB residential billing stops making sense, and a per-IP model with unlimited bandwidth starts looking better.

## The 60-second version

Webshare's lineup, in plain terms:

- **Free plan** — 10 shared datacenter proxies, up to 1GB/month of traffic, no credit card, no expiry.

- **Datacenter proxies** — from **$2.99/month** for 100 shared proxies. Billed per proxy, with bandwidth included. Annual billing knocks roughly 30% off.

- **Rotating residential** — billed **per GB**, with volume tiers. Entry tiers sit around $3.50/GB in the most recent third-party price tables, dropping toward $1.40/GB at multi-terabyte volume.

- **Static residential (ISP)** — billed **per IP per month**, starting at about **$0.30/IP** at the 20-IP tier. US-only pool.

All paid tiers support HTTP and SOCKS5. The differences between them are IP type and billing unit, not features.

## Webshare's free tier is the real entry point

Ten shared datacenter proxies and 1GB of monthly traffic, no card required, no time limit. PCMag's review treats this as the headline feature of the service, and it's the same offer Webshare's own browser extension page describes.

What it's good for: kicking the tires on a scraper, testing whether your target site blocks datacenter ranges, running a small monitoring job that never gets near 1GB. What it isn't good for: anything residential, any serious volume, or anything where you need geo-targeting beyond the handful of countries the free pool covers well. PCMag noted that the non-US free locations had noticeably thinner inventory.

If a niche project fits inside 10 datacenter IPs and 1GB, your Webshare bill is genuinely $0 forever. Rare, but real.

## Datacenter pricing: the $2.99 tier and the "$0.018/IP" fine print

The 100-proxy package at $2.99/month works out to about $0.0299 per IP, including bandwidth. From there it's a straightforward volume curve: the per-IP cost falls as you buy more, and Webshare advertises discounts of roughly 30% for annual prepay. One reviewer's math put 1,000 proxies at under $27/month on an annual plan.

The number worth understanding is the **"from $0.018/IP"** figure Webshare puts on its homepage. One analysis of the company's pricing found that this is not the entry price at all, it reflects the discount available above roughly 60,000 IPs. At 100 proxies you're paying $0.0299/IP, not $0.018. Same product, different point on the curve.

Inside the datacenter product there are three variants: shared, private, and dedicated. Shared is the cheap one. Private and dedicated cost more because the IPs are yours alone, which matters if other users' traffic on a shared IP is what's getting you blocked.

## Rotating residential: this is where the bill gets unpredictable

Webshare's rotating residential pool is billed purely by bandwidth. CNET's most recent review lists the curve like this: 1GB at $3.50, 10GB at $2.75/GB, 25GB at $2.60, 50GB at $2.45, 100GB at $2.25, 250GB at $2.00, 500GB at $1.75, 1,000GB at $1.50, and 3,000GB at $1.40/GB.

Two caveats. First, other outlets have quoted Webshare's residential standard rate as $7/GB, and one older piece cited $13,500/month for a 300GB enterprise tier. Those numbers come from different dates and different plan structures, which is exactly why you should read the cart total rather than a review table. Second, third-party deal pages have advertised everything from 20% to 50% off residential at various points, so the effective per-GB price fluctuates more than the sticker tiers suggest.

The structural point stands regardless: on a per-GB plan, your cost scales with page weight that you don't control. If you're scraping JavaScript-heavy product pages, the same number of requests can cost two or three times what it costs on a lighter site, and none of that is visible until the invoice.

## Static residential (ISP): per IP, US-only

Static residential runs from around **$0.30 per IP per month** at the smallest tier (20 IPs), and those IPs stay fixed for as long as you keep paying. That makes it the right product for account management, ad verification, and anything that needs a consistent identity rather than a fresh one every request.

The constraint: the static residential pool is US-only. If your work needs residential IPs in Germany or Brazil that stay put, this product doesn't cover it. Webshare's datacenter pool spans 50+ countries and its rotating residential pool is advertised across 195 countries, so the static offering is the narrow one.

Also worth flagging before you buy anything: Webshare's terms state you're eligible for a refund only if you cancel within two days, used less than 1GB, and used fewer than 1,000 proxies. That's a narrow window, so test with the free tier first rather than buying big and hoping.

## Where the Webshare pricing model starts to strain

Three things show up repeatedly in reviews of the service:

1. **Per-GB metering punishes high-volume, low-value requests.** There's no way to cap the risk except by watching usage.

2. **No mobile proxies.** CNET states plainly that Webshare doesn't currently offer them.

3. **Static residential is geographically limited**, so the "residential IP that doesn't rotate" product only exists for one country.

If your workload is mostly datacenter scraping at scale, none of this matters much and Webshare's per-IP curve is hard to beat. If your workload is residential and bandwidth-heavy, you're paying a rate that moves every time a target site redesigns its front end.

That second scenario is the one where a different billing model is worth a look.

## The other billing model: pay per IP, get unlimited bandwidth

**9Proxy** sells residential proxies with a structure Webshare's residential line doesn't offer: you buy a fixed number of residential IPs, and bandwidth through each IP is unlimited. The company runs two residential models side by side, and the distinction is documented on its own docs site:

| Feature | Residential by IP | Residential by GB |
| --- | --- | --- |
| Billing type | Fixed package, number of IPs | Fixed package, total GB |
| Bandwidth | Unlimited while the IP is active | Capped by the GB you bought |
| Validity | Unused IPs never expire | 180 days (unlimited on Enterprise) |
| IP lifespan | A few hours up to ~24 hours | Rotates per request or session |
| Setup | Requires the desktop app (local port forwarding) | Works from the dashboard, username/password or IP whitelist |

The practical consequence: on the IP plan, a page that weighs 4MB costs you exactly nothing extra. Scrape 100 pages through one IP or 10,000, the price doesn't move. If your scraping targets are bandwidth-hungry, that's the whole argument.

The trade-off is equally concrete. Your IP lives for hours, not forever, so it's not a static residential replacement. And the IP model needs the desktop app, which some teams (and reviewers) find less convenient than a username-and-password setup. The GB plan is the flexible one there, but it brings you back to metered bandwidth.

The pool is smaller too: 20M+ residential IPs across 90+ countries, against Webshare's advertised 80M+ rotating residential IPs. Smaller pool, different economics.

Third-party testing puts 9Proxy's success rate in a useful range. Geekflare ran 300 sequential requests through rotating residential IPs against a Cloudflare-protected e-commerce target and reported 293 passes (97.7%), 5 CAPTCHA challenges, 2 hard blocks, and a 0.63-second average response time. The same test pattern through a datacenter pool blocked 34% of requests on the first pass. One iTWire review noted streaming services were a weak spot, which matches what most residential providers say when you ask them not to promise Netflix.

## 9Proxy's full plan list, current prices

The company raised prices on its IP-based and bundle packages on June 1, 2026, the first adjustment in its history, and left GB-based pricing untouched. These are the post-adjustment numbers reported by reviewers and cross-checked against reseller listings.

### IP-based packages (unlimited bandwidth per IP)

| Package | Price per IP | Total | Notes |
| --- | --- | --- | --- |
| 100 IPs | $0.24 | $24 | Small projects, proof-of-concept |
| 500 IPs | $0.144 | $72 | Solo operators, light multi-accounting |
| 1,000 IPs + 500 bonus | $0.084 | $126 | Small teams, steady workloads |
| 2,500 IPs | $0.084 | $210 | Multiple verticals |
| 5,000 IPs | $0.072 | $360 | Agencies, SEO stacks |
| 15,000 IPs | $0.048 | $720 | Regional teams |
| 25,000 IPs | $0.035 | $863 | Resellers, heavy automation |
| 50,000 IPs | $0.029 | $1,438 | High-volume resellers |
| 100,000 IPs | $0.023 | $2,300 | Business tier |
| 200,000 IPs | $0.021 | $4,140 | Business tier |
| 500,000 IPs | $0.018 | $8,625 | Business tier |

Unused IPs don't expire on this model, which changes the economics if your usage comes in bursts rather than a steady monthly flow.

👉 [Grab the smallest IP package and test the bandwidth model yourself](https://bit.ly/9-Proxy)

### GB-based packages

| Package | Price per GB | Total | Validity |
| --- | --- | --- | --- |
| 5 GB | $3.00 | $15 | 180 days |
| 50 GB + 5 GB bonus | $2.10 | $105 | 180 days |
| 100 GB | $1.50 | $150 | 180 days |
| 200 GB | $1.00 | $200 | 180 days |
| 1,000 GB | $0.80 | $800 | 180 days |
| 2,000 GB | $0.75 | $1,500 | 180 days |
| 3,000 GB | $0.72 | $2,160 | Unlimited |
| 6,000 GB | $0.70 | $4,200 | Unlimited |
| 10,000 GB | $0.68 | $6,800 | Unlimited |

At the top of this table, $0.68/GB versus Webshare's $1.40/GB at 3,000GB is roughly half the rate. At the bottom, 5GB for $15 versus Webshare's $3.50/GB entry tier is a worse deal. Which one wins depends entirely on where your volume lands.

👉 [Check the current per-GB tiers before they move again](https://bit.ly/9-Proxy)

### Bundle packages (IPs + GB in one purchase)

| Bundle | Contents | Price | Traffic validity |
| --- | --- | --- | --- |
| Starter | 100 IPs + 5 GB | $30 | 180 days |
| Popular | 1,500 IPs + 50 GB | $180 | 180 days |
| Pro | 5,000 IPs + 500 GB | $720 | 180 days |

Bundles make sense when part of your workload needs a stable IP for a session and part just needs traffic. The 180-day validity means you're not forced to burn it inside a month.

👉 [Compare the bundle packages against buying IPs and GB separately](https://bit.ly/9-Proxy)

A couple of other things worth knowing before you sign up. 9Proxy runs a referral program that pays up to 15% commission and advertises **5% off for users who join through a referral link**, so it's worth checking whether the sign-up link you arrive through carries that discount. Free trials exist but are limited and issued at the support team's discretion, so ask before you buy if you want to validate the success rate on your specific targets.

## Webshare vs 9Proxy, by billing model

|  | Webshare | 9Proxy |
| --- | --- | --- |
| Free tier | 10 datacenter proxies, 1GB/month, no card | No permanent free tier; limited trials on request |
| Datacenter proxies | Yes, from $2.99/mo for 100 IPs | Not in the documented lineup (residential only) |
| Residential, per GB | Yes, entry tiers around $3.50/GB, down to ~$1.40/GB | Yes, $3.00/GB down to $0.68/GB at 10,000GB |
| Residential, per IP | Static residential, from ~$0.30/IP/mo | IP-based, unlimited bandwidth, from $0.24/IP |
| Static, fixed IPs | Yes (ISP product), US only | IPs last hours, not permanent |
| Pool size | 80M+ rotating residential, 400K+ datacenter | 20M+ residential, 90+ countries |
| Protocols | HTTP, SOCKS5 | HTTP(S), SOCKS5 |
| Setup | Dashboard, no app needed | Dashboard for GB plans; desktop app for IP plans |

Two of these rows decide most purchases. Webshare wins outright on datacenter pricing and on having a free tier that actually lasts. 9Proxy wins on residential cost-per-request when bandwidth is the constraint, and on the fact that unused IPs don't expire.

## Which one fits your job

**Stick with Webshare if:** you're scraping targets that don't block datacenter IPs, you want to start for $0, or you need a permanent pool of fixed US residential IPs for account work. Its datacenter curve at 100 IPs for $2.99 is the cheapest entry point in this comparison by a wide margin.

**Look at 9Proxy if:** your residential usage is bandwidth-heavy or spiky, you're tired of watching a GB counter, or you want the option of buying IPs once and using them over months rather than inside a billing cycle. The per-IP model also removes the "page got heavier, bill got bigger" problem entirely.

**Use both if:** you want cheap datacenter IPs for the easy 80% of your targets and residential for the hardened remainder. Nothing about these two services is mutually exclusive, and the pricing structures point in different directions on purpose.

## FAQ

**Does Webshare have a free plan?**

Yes. 10 shared datacenter proxies and up to 1GB/month, no credit card, no time limit.

**Is Webshare's "from $0.018/IP" the price for 100 proxies?**

No. That figure reflects volume pricing above roughly 60,000 IPs. The 100-proxy tier is about $0.0299/IP, or $2.99/month.

**Does Webshare charge monthly or annually?**

Both. Annual prepay discounts run around 30%, and residential bandwidth is typically purchased as a one-time balance rather than a subscription.

**Does 9Proxy have datacenter proxies?**

Not according to its own product documentation, which describes two residential models only. If you need datacenter IPs, Webshare is the relevant option here.

**How long does a 9Proxy IP last?**

On IP-based plans, somewhere between a few hours and about 24 hours. On GB-based plans the IP rotates per request or per session, depending on the mode.

**Can I get a refund from Webshare?**

Its terms limit refunds to cancellations within two days where you used under 1GB and fewer than 1,000 proxies. Test on the free tier first.

**Does 9Proxy have a discount code?**

Its referral program advertises 5% off for referred users, and the platform has run short promotional windows with larger discounts on specific packages in the past. Check the price in the cart rather than relying on coupon sites.

---

The honest summary: Webshare's pricing is excellent for datacenter work and free testing, and it's the reason its name gets searched so often. On residential, the per-GB model asks you to forecast bandwidth you can't control. If that's the part of the bill that keeps surprising you, buying IPs with unlimited bandwidth instead is a straightforward fix, and the 100-IP tier at $24 is cheap enough to test against your own targets.

👉 [Start with 9Proxy and see what the per-IP model does to your bill](https://bit.ly/9-Proxy)
