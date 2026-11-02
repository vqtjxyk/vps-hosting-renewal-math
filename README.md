# us vps hosting: what $21.99/year actually buys you, plus datacenter picks, renewal math and a plan-by-plan decision guide

A usable US VPS costs less than most people assume. RackNerd's current specials start at **$21.99 per year** — about $1.83 a month — for a KVM virtual machine with 1 GB RAM, 20 GB SSD, a dedicated IPv4, a 1Gbps port and 3 TB of monthly traffic in a US datacenter. Provisioning is automatic after payment, and the official FAQ states these promo prices renew at the same rate for as long as you keep the service.

That last part is the detail worth pausing on, because "cheap VPS" searches are full of first-year teasers that triple on renewal. Below: the full current plan table, what the renewal promise really covers, how to pick a US datacenter, which plans waste money on which workloads, and an honest list of what you don't get at this price.

> **Quick picks**
> - Personal project, small site, dev/test box: the **1 GB KVM plan at $21.99/year**. 3 TB of traffic covers nearly anything a hobby project will push. 👉 [check the 1 GB KVM plan's current price](https://my.racknerd.com/cart.php?a=add&pid=952&aff=11397)
> - Self-hosting AI tools or anything memory-hungry: start at 4 GB ($59.99/year). The reasons are in the RAM requirements section below.
> - Want to compare everything first: 👉 [browse all of RackNerd's current VPS specials](https://bit.ly/RacKnerd)

## RackNerd's current specials: the full plan table

RackNerd's specials page currently lists five KVM VPS plans, all billed yearly, all with full root access, one dedicated IPv4, a 1Gbps network port and RAID-10 SSD storage:

| Plan | vCPU / RAM | SSD | Monthly traffic | Yearly price | Order |
| --- | --- | --- | --- | --- | --- |
| 1 GB KVM VPS | 1 / 1 GB | 20 GB | 3 TB | $21.99/yr | [order the 1 GB plan](https://my.racknerd.com/cart.php?a=add&pid=952&aff=11397) |
| 2 GB KVM VPS | 2 / 2 GB | 35 GB | 5 TB | $35.99/yr | [order the 2 GB plan](https://my.racknerd.com/cart.php?a=add&pid=953&aff=11397) |
| 4 GB KVM VPS | 3 / 4 GB | 60 GB | 7 TB | $59.99/yr | [order the 4 GB plan](https://my.racknerd.com/cart.php?a=add&pid=954&aff=11397) |
| 6 GB KVM VPS | 6 / 6 GB | 100 GB | 12 TB | $89.99/yr | [order the 6 GB plan](https://my.racknerd.com/cart.php?a=add&pid=955&aff=11397) |
| 8 GB KVM VPS | 7 / 8 GB | 150 GB | 20 TB | $119.99/yr | [order the 8 GB plan](https://my.racknerd.com/cart.php?a=add&pid=956&aff=11397) |

All five are unmanaged KVM machines. At deployment you pick from CentOS, Rocky Linux, AlmaLinux, Fedora, Debian or Ubuntu, and a custom ISO can be requested through a support ticket if you need something else. Management happens in RackNerd's ctrl panel: reboot, OS reinstall, HTML5 VNC console, root password reset, plan upgrades, plus a self-managed inbound firewall.

Two things stand out in the table. The 1 GB to 2 GB jump doubles CPU, RAM, storage and traffic for $14 more per year — cheap headroom. And CPU allocation isn't linear: 1 to 3 vCPU through the 4 GB tier, then a jump to 6 vCPU at 6 GB and 7 vCPU at 8 GB, which matters for anything parallel.

Beyond the specials, RackNerd also runs a standard catalog with 512 MB plans from $26.99/year, monthly-billed KVM and Ryzen NVMe lines, and a separate Windows VPS product line with its own monthly pricing. This article focuses on the five specials because they're the current headline deals — and because the specials page is where the renewal promise lives.

## Renewal pricing: does the cheap rate survive year two?

For these specials, yes — and RackNerd commits to it in writing. The official specials FAQ says the plans are "lifetime recurring": you renew at the same rate for as long as you decide to keep the service. A $21.99/year plan costs $21.99 every year, not just the first one.

The condition is baked into that same sentence. *As long as you decide to keep the service* means renewing on time. Let a plan expire and you're back to buying at whatever current pricing applies; the locked rate belongs to active subscriptions. Put the renewal date in your calendar the day the server arrives. It's the single cheapest insurance policy in budget hosting.

Some third-party write-ups claim RackNerd promo prices double at renewal. That claim circulates mainly around limited holiday flash deals, where stock runs out and terms can differ. For the five plans currently on the specials page, the official renewal promise is the authoritative source — and it's the reason the yearly specials usually beat the monthly catalog on long-term cost. 👉 [see which specials are still in stock](https://bit.ly/RacKnerd)

## Picking a US datacenter: why the location dropdown matters more here

RackNerd runs roughly 20 datacenter locations — Los Angeles, San Jose, Seattle, Dallas, Chicago, New York, Atlanta, Tampa, Ashburn and Utah domestically, plus Toronto, Amsterdam, London and other international sites. Most budget hosts at this price offer two to four, so the location choice is genuinely yours.

Practical rules of thumb:

- **Los Angeles** if you or your visitors are in Asia or on the West Coast. Independent reviews consistently note LA holds up best at peak hours and has routing friendlier to Asian destinations than the cheaper East Coast options.
- **Dallas, Chicago, New York or Ashburn** for East/Central US audiences, or if you're calling US East-based APIs and databases.
- **Ashburn** is also the default answer for anything that benefits from dense East Coast peering.

Two network facts worth knowing before you order. RackNerd runs Noction IRP, a platform that dynamically optimizes BGP routing paths across its network — one reason its budget plans often test better on latency than the spec sheet suggests. And to settle a question that comes up in every VPS forum: this is standard international routing, not CN2-optimized China direct transit. Los Angeles is the friendliest RackNerd location for Asian routes among its US sites, but nobody should order expecting a China-optimized line.

## Which plan fits your workload: use the RAM requirements, not vibes

The most common cheap-VPS mistake is buying on price and discovering the software doesn't fit. RackNerd makes this unusually easy to avoid, because its own specials page publishes memory requirements for the one-click apps available in ctrl:

- **n8n, Coolify** — comfortable from 2 GB RAM. The $35.99/year plan handles it.
- **Ollama, AnythingLLM, LibreChat, Hermes Agent** — want at least 4 GB. You need the $59.99/year tier or above.
- **OpenClaw** — wants at least 8 GB. That's the $119.99/year plan, full stop.

So the decision rules write themselves:

1. Blog, static site, small bot, tunnel endpoint, light dev box → 1 GB at $21.99/year. If $14/year extra doesn't hurt, take 2 GB for headroom.
2. A handful of Docker services, small databases, a dashboard → 2 GB at $35.99/year.
3. Anything touching local LLMs or embedding workloads → 4 GB minimum at $59.99/year, and check the specific app's requirement before checkout.
4. Multiple AI applications or heavier builds at once → 6 or 8 GB.

One clarification since "KVM" gets thrown around loosely: these are full virtual machines with dedicated kernels and root access, so Docker, custom kernels and typical self-hosted stacks run without the restrictions container-based budget plans impose. If you'd rather skip manual setup, the ctrl panel ships one-click installers for Docker with Portainer, WordPress stacks (AdminBolt, CyberPanel, CloudPanel) and the apps listed above. 👉 [order the 4 GB plan if you're in the self-hosted AI camp](https://my.racknerd.com/cart.php?a=add&pid=954&aff=11397)

## What RackNerd doesn't give you

The limits matter as much as the prices, and most comparison articles skip them:

- **Unmanaged, full stop.** You handle OS updates, security patching and your own applications. Support covers platform-level problems — network, host node, panel — around the clock, but a server you broke yourself is yours to fix.
- **Ticket-based support only.** No live chat. Typical replies arrive within hours, slower during big promo rushes.
- **Metered traffic.** Every plan has a hard transfer allocation, 3 to 20 TB monthly depending on tier. There's no "unlimited" number to hide behind, so budget your bandwidth.
- **No block storage, object storage or load balancers.** The product line is VPS and dedicated servers. If you need attached volumes or managed cloud services, you're shopping in a different category.
- **A control panel without an API.** ctrl covers the essentials, but there's no infrastructure-as-code tooling. Fine for a handful of servers; painful at twenty.
- **No contractual SLA on the cheapest tiers.** Community-reported uptime generally sits at 99.9%+, but nothing in the contract guarantees it.

None of these disqualify the product for its actual audience — people comfortable running their own servers. If you need managed support or contractual uptime, budget VPS is the wrong category entirely.

## How the yearly math compares against monthly-billed US rivals

"us vps hosting" searches mostly surface monthly-billed providers, so here's the honest comparison using verified current pricing — the numbers do the arguing:

| Provider | Entry plan | Price & billing | What you get |
| --- | --- | --- | --- |
| RackNerd | 1 GB KVM Special | $21.99/year | 1 vCPU, 1 GB RAM, 20 GB SSD, 3 TB traffic, 1Gbps, 1 IPv4 |
| OliveVPS | Los Angeles Starter | $3.99/month (≈$47.88/yr) | 1 dedicated vCPU, 1 GB RAM, 25 GB NVMe, 1 TB traffic, 1Gbps, 99.99% SLA |
| HostFinch | US-VPS-1 | $7.99/month (≈$95.88/yr) | 1 vCPU, 2 GB RAM, 40 GB SSD, 300 Mbps port, unmetered traffic |

Reading the table fairly:

- **OliveVPS** is the strongest entry-level competitor on paper — dedicated core, NVMe storage and a contractual 99.99% SLA in a Tier III Los Angeles facility, with Windows available from its $7.99/mo Pro tier. It fits anyone who wants month-to-month flexibility or an SLA-backed machine. Over a year, though, its Starter costs about 2.2× RackNerd's 1 GB special, and its traffic allowance is 1 TB versus 3 TB.
- **HostFinch** gives you more RAM and storage per month and simpler bandwidth accounting (unmetered on a 300 Mbps port), on monthly billing with a 99.95% uptime target. Its cheapest Linux plan runs roughly $96 a year against RackNerd's $22 — a real gap for anything you plan to keep long-term. It also sells Windows VPS from $12.99/month, though the Windows Server license adds $19.99/month on top, a detail easy to miss on the pricing page.
- **RackNerd** wins on total cost of ownership and location count. The tradeoffs are yearly commitment, unmanaged-only service, and metered rather than unmetered traffic.

There's no single winner. Short experiment, want out anytime → the monthly options make sense. Anything you expect to still be running next year, the yearly RackNerd specials cost less than two months of either rival.

## FAQ

**Is the $21.99/year RackNerd deal real?**
Yes — the 1 GB KVM plan is currently listed on the official specials page with the specs in the table above. Holiday promos have dipped lower in past years, but those are limited stock and come and go.

**Do the specials renew at the same price?**
Per the official specials FAQ, yes — the plans are lifetime recurring, provided you renew on time before the service expires.

**KVM or OpenVZ?**
KVM. Full virtualization, your own kernel, Docker and custom ISOs (via ticket) all supported.

**How fast is provisioning?**
Servers deploy automatically right after payment — minutes, not hours, per the official page and third-party reviews.

**Is the network China-optimized?**
No. Standard international BGP routing with Noction IRP optimization. Los Angeles is the friendliest US location for Asian routes, but it's not a CN2 line.

**Can I get Windows?**
RackNerd sells Windows VPS as a separate monthly-billed product line. The five specials above are Linux plans.

## Before you click order

Three checks that take a minute and prevent the usual regret. First, match your software's RAM appetite against the memory list above — self-hosted AI tools need the 4 GB tier at minimum, and OpenClaw needs all 8 GB. Second, pick the datacenter for where your users are: Los Angeles for Asian or West Coast traffic, East Coast locations otherwise. Third, calendar the renewal date when the server arrives, because the lifetime pricing only holds for subscriptions that don't lapse. If all three line up, 👉 [pick your plan on RackNerd's specials page](https://bit.ly/RacKnerd) and you'll have root access before your coffee cools.
