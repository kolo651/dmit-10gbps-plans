# DMIT 10Gbps: Which Plans Get a Real 10Gbps Port, What They Cost, and the Throttle Nobody Mentions

Two questions tend to sit behind this search. Does DMIT genuinely hand you a 10Gbps port, or is that number marketing? And how much do you have to spend before a 10Gbps plan shows up in your cart?

The port is real. DMIT lists 10Gbps on plans across all three of its networks and all three of its locations, and the cheapest entry point at Los Angeles is a $12.90/month Tier 1 box. But the number comes bundled with a traffic allowance, an overage throttle, and a hardware platform tier that swings the price by several dollars a month. Reading the plan list without understanding those three things is how people end up disappointed.

## What a 10Gbps port actually means on a DMIT box

It's the port speed on the hypervisor side, shared across the instances on that host. It is not a promise that a single connection from your laptop will run at 10Gbps, and no provider can promise that, because your home line, the route in between, and the far-end server all get a vote.

What it does buy you is headroom. A 10Gbps port means a bursty workload, a big file transfer, or a hundred concurrent users don't immediately queue behind a 100Mbps ceiling. On DMIT's metered plans, the port speed is what you get while you're inside your monthly traffic allowance. That distinction matters more than the port number itself.

The other useful detail: DMIT counts traffic in both directions. Upload and download both draw from the same monthly bucket, so a plan advertising 3TB is not 3TB down plus 3TB up.

## The three networks, and where 10Gbps shows up

DMIT runs three product lines per location, and the port speed you get depends on which one you pick.

**Premium (Pro)** is the China-optimized line, built around China Telecom's CN2 GIA (AS4809), with China Unicom and China Mobile routed through premium transit as well.

**Eyeball (EB)** targets the same traffic with different plumbing: CMIN2 and, at Los Angeles, Unicom's AS9929. It usually costs the same as Premium but hands you far more monthly traffic for the money.

**Tier 1 (T1)** is plain international transit with no China optimization at all. It's the cheapest line, and, counterintuitively, it's where 10Gbps is easiest to get.

Here's the wrinkle that trips people up: **Hong Kong's Premium line tops out at 1Gbps.** If you specifically want a 10Gbps port in Hong Kong, you're looking at the Tier 1 line, not the expensive one. Los Angeles is the opposite: Premium and Eyeball both climb to 10Gbps once you pass the entry tiers.

## The catch: when 10Gbps turns into 4Mbps

This is the part that deserves more attention than it gets. DMIT doesn't cut you off when the high-speed allowance runs out. It drops you to a fixed slower speed and lets you keep using the server as long as you like.

How far it drops depends entirely on the line:

| Network line | Entry-tier overage speed | Mid-tier overage speed | Top-tier overage speed |
| --- | --- | --- | --- |
| Tier 1 (LAX / HKG / TYO) | 50–100Mbps | 100–200Mbps | 500Mbps–1Gbps |
| Premium (Pro) | 4Mbps | 8Mbps | 10Mbps |
| Eyeball (EB) | 4Mbps | 8Mbps | 10Mbps |

Read that Premium row again. A 10Gbps CN2 GIA plan that burns through its traffic allowance becomes a 4Mbps connection. That's fine for a monitoring script or an SSH session, and miserable for anything else.

Tier 1, meanwhile, throttles to 100Mbps or better on most tiers. You lose the premium routing, but you keep a genuinely usable connection after the allowance is gone. For anyone whose real requirement is "big port, predictable fallback," that trade is the whole story.

## Full plan and price comparison

DMIT restocks and retires plans constantly, so treat the tables below as the current shape of the lineup rather than a fixed catalog. Prices are USD.

### Tier 1 — the cheapest route to 10Gbps

The Tier 1 ladder is identical across Los Angeles, Hong Kong and Tokyo in both price and traffic. Core counts and RAM vary by a step or two between regions and restock batches.

| Plan | CPU / RAM | SSD | Monthly traffic | Port | Overage speed | Price | Order |
| --- | --- | --- | --- | --- | --- | --- | --- |
| T1.WEE | 1 core / 1GB | 20GB | 1TB | 4Gbps | 50–100Mbps | $36.90/yr | [ See the T1.WEE annual plan](https://www.dmit.io/aff.php?aff=12046) |
| T1.TINY | 1 core / 1–2GB | 20GB | 2TB | 4Gbps | 100–200Mbps | $6.90/mo · $76.90/yr | [ Check T1.TINY pricing](https://www.dmit.io/aff.php?aff=12046) |
| T1.STARTER | 1–2 cores / 2GB | 40GB | 4TB | 10Gbps | 100–200Mbps | $12.90/mo · $154.80/yr | [ Order T1.STARTER with a 10Gbps port](https://www.dmit.io/aff.php?aff=12046) |
| T1.MINI | 2 cores / 2–4GB | 60GB | 8TB | 10Gbps | 100–200Mbps | $21.90/mo · $262.80/yr | [ See T1.MINI specs and stock](https://www.dmit.io/aff.php?aff=12046) |
| T1.MICRO | 4 cores / 4GB | 80GB | 16TB | 10Gbps | 200Mbps | $32.90/mo · $394.80/yr | [ Check T1.MICRO availability](https://www.dmit.io/aff.php?aff=12046) |
| T1.MEDIUM | 4 cores / 8GB | 160GB | 32TB | 10Gbps | 200Mbps | $49.90/mo · $598.80/yr | [ Order T1.MEDIUM](https://www.dmit.io/aff.php?aff=12046) |
| T1.LARGE | 8 cores / 16GB | 320GB | 64TB | 10Gbps | 500Mbps | $99.90/mo · $1,198.80/yr | [ See T1.LARGE pricing](https://www.dmit.io/aff.php?aff=12046) |
| T1.GIANT | 8 cores / 24GB | 640GB | 128TB | 10Gbps | 1Gbps | $199.90/mo · $2,398.80/yr | [ Compare T1.GIANT and top-tier plans](https://www.dmit.io/aff.php?aff=12046) |

The step from T1.TINY to T1.STARTER is the interesting one: six dollars more per month buys a 10Gbps port and double the traffic. T1.WEE is the odd one out at 4Gbps, which is why it exists mainly as a cheap annual entry box.

### Los Angeles Premium (CN2 GIA)

Premium is the line you buy when mainland China latency is the priority. On the AS3 platform (AMD EPYC 7003), pricing runs:

| Plan | CPU / RAM | SSD | Traffic | Port | Overage | Price | Order |
| --- | --- | --- | --- | --- | --- | --- | --- |
| LAX.Pro.TINY | 1 core / 2GB | 20GB | 1TB | 1Gbps | 4Mbps | $10.90/mo | [ Start with LAX.Pro.TINY](https://www.dmit.io/aff.php?aff=12046) |
| LAX.Pro.Pocket | 2 cores / 2GB | 40GB | 1.5TB | 4Gbps | 4Mbps | $16.90/mo | [ Check LAX.Pro.Pocket](https://www.dmit.io/aff.php?aff=12046) |
| LAX.Pro.STARTER | 2 cores / 2GB | 80GB | 3TB | 10Gbps | 4Mbps | $34.90/mo | [ Order the 10Gbps LAX.Pro.STARTER](https://www.dmit.io/aff.php?aff=12046) |
| LAX.Pro.MINI | 4 cores / 4GB | 80GB | 5TB | 10Gbps | 8Mbps | $62.90/mo | [ See LAX.Pro.MINI](https://www.dmit.io/aff.php?aff=12046) |
| LAX.Pro.MICRO | 4 cores / 4GB | 160GB | 7TB | 10Gbps | 8Mbps | $87.90/mo | [ Compare LAX.Pro.MICRO](https://www.dmit.io/aff.php?aff=12046) |
| LAX.Pro.MEDIUM | 6 cores / 8GB | 160GB | 14TB | 10Gbps | 10Mbps | $199.90/mo | [ Check LAX.Pro.MEDIUM](https://www.dmit.io/aff.php?aff=12046) |

Notice that the first two rungs aren't 10Gbps at all. Only STARTER and above get there.

Newer hardware pushes the numbers up. On the AN5 platform (AMD EPYC 9005), the same Premium line lists higher across the board: $14.90, $21.90 and $43.90 for the three small tiers, then $79.90 for MINI, $110.90 for MICRO, $289.90 for MEDIUM, $499.90 for LARGE and $1,009.90 for GIANT. Higher tiers also pick up extra IPv4 addresses. The AN4 platform sits between the two.

If you want the newest silicon, 👉 [open the Los Angeles AN5 Premium cart to check current stock](https://www.dmit.io/cart.php?region=los-angeles&generation=an5&network=premium&aff=12046) — the same page lets you flip between platforms, networks and regions before you commit.

One thing worth knowing about AS3: DMIT's own platform notes describe it as still being optimized, and warn that disk performance and SLA can sit below mature platforms. If the workload is production-critical, either pay up for AN4/AN5 or test first.

### Los Angeles Eyeball (CMIN2)

Same price points as Premium, considerably more traffic. If most of your users are on China Unicom or China Mobile, this is usually the better buy.

| Plan | CPU / RAM | SSD | Traffic | Port | Overage | Price | Order |
| --- | --- | --- | --- | --- | --- | --- | --- |
| LAX.EB.TINY | 1 core / 2GB | 20GB | 1.5TB | 2Gbps | 4Mbps | $10.90/mo | [ See LAX.EB.TINY](https://www.dmit.io/aff.php?aff=12046) |
| LAX.EB.Pocket | 2 cores / 2GB | 40GB | 3TB | 4Gbps | 4Mbps | $16.90/mo | [ Check LAX.EB.Pocket](https://www.dmit.io/aff.php?aff=12046) |
| LAX.EB.STARTER | 2 cores / 2GB | 80GB | 5TB | 10Gbps | 4Mbps | $34.90/mo | [ Order the 10Gbps LAX.EB.STARTER](https://www.dmit.io/aff.php?aff=12046) |
| LAX.EB.MINI | 4 cores / 4GB | 80GB | 10TB | 10Gbps | 8Mbps | $62.90/mo | [ See LAX.EB.MINI](https://www.dmit.io/aff.php?aff=12046) |
| LAX.EB.MICRO | 4 cores / 4GB | 160GB | 14TB | 10Gbps | 8Mbps | $87.90/mo | [ Compare LAX.EB.MICRO](https://www.dmit.io/aff.php?aff=12046) |
| LAX.EB.MEDIUM | 6 cores / 8GB | 160GB | 30TB | 10Gbps | 10Mbps | $199.90/mo | [ Check LAX.EB.MEDIUM](https://www.dmit.io/aff.php?aff=12046) |

Put STARTER side by side with the Pro version: same $34.90, same 10Gbps port, but 5TB of traffic instead of 3TB. You're trading CN2 GIA return routing for CMIN2. Whether that's a downgrade depends entirely on which Chinese carrier your users are on.

### Hong Kong Premium — the 1Gbps ceiling

Worth stating plainly, because it's a common source of confusion: Hong Kong Premium is a 1Gbps line. TINY runs $39.90/month with 500GB, STARTER $79.90/month with 1TB, and the higher tiers climb into the hundreds for 1.5–2.5TB. You are paying for sub-50ms latency to mainland China and Hong Kong's position as a regional hub, not for port speed.

If 10Gbps at Hong Kong is the actual requirement, the Tier 1 line delivers it from $12.90/month with 4TB of traffic — and drops to 100Mbps after that instead of 4Mbps.

## How to pick without overthinking it

Deleting everything else, the decision comes down to three questions.

**Who are your users?** China Telecom heavy audience, take Premium. Mostly Unicom and Mobile, take Eyeball and pocket the extra traffic. Serving Europe, Southeast Asia or the Americas, Tier 1 is fine and much cheaper. Education network traffic, Tier 1 again.

**Do you need a 10Gbps port, or do you need a big traffic allowance?** These get confused constantly. A 10Gbps port matters for concurrency and burst. A big allowance matters for sustained volume. Tier 1 gives you both at a low price, which is why it's the default answer for download boxes, backup targets and international API services. 👉 [Browse the full Tier 1 lineup at all three locations](https://www.dmit.io/aff.php?aff=12046) if that's the shape of your workload.

**What happens at the end of the month?** If running out of traffic means a real outage, the 4Mbps fallback on Premium and Eyeball is a problem, not a feature. Tier 1's 100Mbps–1Gbps fallback is the more forgiving model.

## Discounts, billing cycles and the stock problem

DMIT doesn't keep a permanent public coupon sitting on its homepage. Discounts arrive as recurring promo codes during campaigns, and they're usually tied to a specific line and a specific billing term. At checkout there's a Validate Code box; paste a code there and the panel will tell you whether it applies to what you've selected, which is more reliable than any coupon list, including dated ones.

What you can count on without a code is annual billing. Most Tier 1 tiers work out to roughly ten months' worth of charges over twelve, so T1.STARTER lands at $154.80 for the year versus $12.90 a month.

Stock is the real constraint. Popular plans sell out regularly, and some series get retired outright — Tokyo's Eyeball line and Hong Kong's Eyeball line have both been taken off the menu at different points. If a plan you want is out of stock, the waiting list and the restock announcements are worth watching rather than settling for the wrong network.

Payment is straightforward for most buyers: PayPal, Alipay and major credit cards are all accepted.

## Questions that come up after purchase

**Why isn't my speed test showing 10Gbps?** Because the port isn't the bottleneck. Single-thread throughput depends on the route, the congestion on the far end and your own connection. Test multi-threaded, and test at different times of day.

**My traffic disappeared faster than expected.** Bidirectional counting. A 3TB allowance covers upload and download combined.

**The IP got blocked.** Los Angeles Pro and Eyeball plans can request an IP replacement through the control panel when the address becomes unreachable. Tier 1 plans handle this differently and generally require a paid change.

**Can I run Windows?** DMIT offers KVM virtualization with AMD EPYC processors and SSD storage; whether Windows is viable on a given plan depends on RAM, so check the plan's specifications before assuming.

## The short answer

DMIT's 10Gbps claim holds up. It's just not the headline. The plans that carry it, the throttled speed you inherit when traffic runs out, and the platform tier you're buying on are what actually determine whether the server suits you.

For most people who arrive here looking for a 10Gbps DMIT box, the answer is Tier 1 at $12.90/month: real 10Gbps port, 4TB of traffic, and a 100Mbps cushion afterwards instead of a 4Mbps crawl. If China routing quality is the actual requirement, spend the money on Premium or Eyeball and accept that the fallback speed is slow. Either way, 👉 [check live availability and current pricing before you order](https://www.dmit.io/aff.php?aff=12046) — the lineup moves faster than any plan list.
