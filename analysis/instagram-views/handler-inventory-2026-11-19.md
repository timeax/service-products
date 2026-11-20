# Instagram Views handler inventory

2026-11-19 · Fresh source analysis and approved first routing revision

## Scope and source

Instagram → Views → Instagram Views (`instagram-views-views`, roadmap status `not_started`) covers one-time views on Instagram media. The starting point is the project-root 5,717-row export. All 65 mapped root IDs resolve. An independent scan of Instagram categories, names and descriptions for views, plays, viewers and watch time found 25 additional same-family candidates. The resulting inventory has 90 rows across the provider categories Instagram Views (55), Instagram Reel (18) and Instagram IGTV (17). The last verified TygerBooster lab had 70 of these rows: the 65 mapped rows and 780, 781, 783, 786 and 790. Current lab membership and health require a fresh site check before deployment. [Registry](../../handler%20services.json) · [Roadmap](../../catalog.json) · [Mapping](../../catalog-handler-service-ids.json) · [TygerBooster lab](https://tygerbooster.com/labs/226)

All 90 rows are enabled and unlocked in the export, with no state reason. Each has JAP configuration `dgp_handler_id: 1`, order type `Default` and last seen time 2026-11-18 08:02:54 UTC. All have zero markup and no rate adjustment. The export is a bare array with no site or provider-account identity. The root row ID is the reference used in bindings. The external JAP ID identifies the provider service. The shared handler configuration covers the entire set, and the source supplies no evidence about independent failure rates or whether an accepted order actually fulfills.

## What the rows say they target

The name establishes the provider's wording for each row. Accepted link formats still need testing. The nine groups below are mutually exclusive. Emergency is an attribute within the relevant target groups.

| Target evidence | Count | Mapped | Proposed disposition |
| --- | ---: | ---: | --- |
| All Videos | 12 | 12 | Start here for **Video Views**. Separate general delivery, listed speeds and Emergency. Confirm accepted Reel and legacy links before cross-target use. |
| Reel explicitly stated | 17 | 0 | **Reel Views** with General, selected speed tiers and an Emergency option. Five already belong to the last verified lab. |
| IGTV explicitly stated | 15 | 15 | Hold **Legacy IGTV Views** until accepted links are verified. A generic pool and tighter speed pools are visible in the names. |
| Photo explicitly stated | 1 | 1 | **Photo Views** candidate with a single photo-only route. |
| All Posts | 2 | 0 | **Post Views** pool if both rows cover the same photo and video post scope. |
| Named multiple targets | 5 | 0 | Three rows list Reel + IGTV + Posts, one says Reel + IGTV + Normal, one says Reel + IGTV. Verify the exact scopes before using them. |
| All / All Links | 8 | 7 | Confirm accepted link types before using them for a generic or alternate route. |
| Target unspecified in name | 29 | 29 | Distinct start, delivery and capability evidence. Confirm target before adding any to a video, Reel or photo pool. |
| Ambiguous private-video wording | 1 | 1 | Hold 761 until `PRVT` and the supported URLs are clarified. |

The 25 omitted root IDs are 716, 725, 744, 754, 757, 762, 766, 780, 781, 782, 783, 784, 785, 786, 787, 788, 789, 790, 791, 793, 795, 796, 799, 800 and 801. The per-row inventory below marks their mapping and last verified lab membership.

### Related records outside this one-time media scope

- Views combined with other metrics (721, 723, 745, 776, 802) change the delivered outcome. Photo views plus Impressions (`723`) remains a separate bundle.
- Story-related rows (52, 1049–1080, 1103) use Story targets or Story bundles. 1103 describes an automatic Story outcome even though its payload says `Default`.
- Profile views or Highlights (1167–1169) have a distinct target. Engagement packages with views (55, 95, 121–126) include additional outcomes.
- Subscription rows (1273, 1290–1317) are excluded. The Instagram Live category had likes and comments, with no viewer handler in the scan.

## Delivery, quantity and capability trade-offs

- **Start window and delivery rate are separate.** Source names give examples ranging from instant to 0–6 hours of start time. For rate, they use hourly, per-minute and daily figures, plus vague descriptions such as Fast and Super Speed. Preserve the units and avoid inferring a sustained daily rate from an hourly one. Row 763 lists instant *speed* and a 0–1 hour *start*. Row 756 spells its start claim “Insatnt.”
- **Emergency is a provider label.** Nine rows use it: 709, 712, 728, 736, 740, 758, 760, 783 and 788. They have different targets, starts, speeds and capabilities. The name does not explain what priority means. Row 758 also says “AUTO ON / OFF,” which needs clarification.
- **Structured quantity wins.** Of 88 names with a numeric quantity ceiling, 87 differ from the payload. The matching row is 727. Rows 748 and 758 have no numeric name ceiling. Eighty records have a payload maximum of 2,147,483,647. Minima are 100 on 87 rows, 50 on 729, and 1,000 on 778 and 790. If a product elects to offer a narrower range for a verified route, that becomes a deliberate Builder rule based on the intersection of payload ranges.
- **Structured capabilities win.** Cancellation is enabled on 87 rows. Drip feed is enabled on 78. No row advertises structured refill or contract support. Twelve rows have drip feed disabled, including 727, 731, 786 and 788 despite their droplet symbols. Row 730 has neither cancellation nor drip feed. The appendix records every capability profile.

## Routing candidates before product design

Choose a primary and ordered alternates against each option's advertised target, quantity range, delivery and enabled features. Keep **General delivery** speed-flexible. Keep explicitly speed-specific options in narrower pools. A fallback can support extra capabilities, while its allowed quantity range must cover the entire advertised option. Two distinct JAP external IDs are alternate rows within one integration. Site order acceptance, fulfillment history and failover behavior remain unverified.

The rate column below compares candidates with the local Builder default `lte_primary` at 5%. This accepts a candidate from 95% to 100% of the primary's rate. Live policy and retry behavior need checking. Rate gaps remain visible in the candidate list so a technical match is not overlooked. No policy changes are proposed here.

| Proposed route or comparison | Candidate IDs in primary → alternate order | Evidence | Local rate check |
| --- | --- | --- | --- |
| General Reel Views | **780 → 781** | Both explicitly Reel, list 0–1 hour, cover 100–2,147,483,647 and support cancel and drip feed. Listed speeds are 5M/day and 500K/day. Use a speed-flexible option. Both belong to the previous lab catalog. | Pass, 0.0063 → 0.0063 |
| Reel, 500K/day | **725 → 781** | Both explicitly Reel with 0–1 hour starts, matching speed, bounds and capabilities. 725 needs lab membership. Also consider 781 as a low-rate primary where a permitted same-tier alternate can be supplied. | Fails lower bound, 0.24 → 0.0063 |
| Video, up to one-hour start and 500K/day | **715 → 714** | Full quantity and capability match. Start descriptions are 1 hour and 0–1 hour. Target wording is generic on both. Confirm same video URL scope. | Pass, 0.2088 → 0.2063 |
| Video, 0–1 hour and 5M/day | **748 → 747**. Also compare **718**. | 748 says All Videos. 747 and 718 have generic target wording. Start, speed, bounds and capabilities match. Confirm equivalent URLs. | 747 passes at 1.225 from 1.23. 718 at 0.2338 fails the lower bound. |
| Video, instant start and 5M/day | **752 → 751** | Same start, speed, full payload range and capabilities. 751 explicitly says All Videos. Confirm 752's URL scope. 731 also lists instant start and 5M/day, with drip feed disabled and a much lower rate. | Pass, 1.30 → 1.26 |
| General explicitly labeled Video, up to one-hour start | **727 → 732** | Both say All Videos and support cancellation. 732 covers the full 100–100M range of 727 and adds drip feed. Their rates of delivery differ, so this route is speed-flexible. Starting with 727 limits the advertised option to its payload range and omits drip feed on this route. Review whether that trade-off is useful. | Pass, 0.25 → 0.25 |
| General All Posts | **757 → 754** | Both say All Posts. Same quantity range, cancellation support and differing start and speed descriptions. A route can offer a start within one hour with speed flexibility and no drip-feed promise. Confirm equivalent post links. Both need lab membership. | Pass, 1.3433 → 1.33 |
| Reel + IGTV + Posts, 0–1 hour and 100K/day | **716 → 784 → 762** | The three names differ only in formatting. Bounds and capabilities match. They appear under three different provider categories and all need lab membership. The order shown is descending provider rate for review. Exact legacy-link support needs confirmation. | Each cheaper alternate fails the lower bound against the higher primary. Rates 0.2188, 0.10 and 0.0063. |
| IGTV, 0–1 hour and 5M/day | **770 → 768** | Both explicitly say IGTV, with matching start, speed, quantity and capabilities. Confirm accepted legacy links. | Fails lower bound, 0.2313 → 0.125 |
| IGTV, 0–1 hour and 1M/day | **771 → 769** | Matching target, start, speed, quantity and capabilities. 777 also lists the same target and delivery, with drip feed disabled. | Fails lower bound, 0.2338 → 0.2063 |
| General legacy IGTV | **771 → 770** | Explicit IGTV target, same start window, bounds and capabilities. Different speeds fit only an option without a specific speed promise. Hold pending legacy links. | Pass, 0.2338 → 0.2313 |

**Options that still need coverage.** Photo-only row 722 is a single route. Emergency Reel 783 and 788 differ in delivery rate and capability. Emergency Video 728 and 760 differ in delivery rate and price. A request for 100M Reel views/day selects a narrow claim supported by 790, with a minimum order of 1,000. Review how valuable isolated speed tiers are before exposing them. For general delivery also consider the 50-minimum handler 729, the faster-start Reel 800 and Reel 793's advertised up-to-2M/day. Selection requires target confirmation and an explicit decision about whether they are options or alternates. Rates in the appendix are raw catalog costs.

## Proposed Builder shape

Start with target-driven tags for Video, Reels and Photos. Use single-choice delivery options for a general pool and selected evidenced delivery tiers. Split Emergency by supported target where offered. All Posts, explicitly mixed targets and legacy IGTV are potential later tags after acceptance checks. Keep private-video wording unbound for now. Give each selectable tag a target-appropriate default, and give an applicable option its own primary and fallback list so its chosen route has backups.

`Default` uses `link` and `quantity` in the JAP request. Use the registered `text/default` for Link, `number/default` for Quantity and `select/default` for delivery choices. Display the effective payload bounds and use single-choice options. Gate the `toggle/default` Drip feed on the effective handler and preserve its description. Runs and Interval (minutes) appear together when selected, using `number/default`. Both are conditional JAP request inputs. The installed DGP Spec supports node-level and global fallbacks. [Builder capabilities](../../.ai/service-builder-capabilities.json) · [JAP input guide](../../.ai/JAP-SERVICE-TYPES.md)

## Saved first revision

The approved JSON gives the root, Video Post Views tag and new General Video option the `727 → 732` chain. It gives the Reel Views tag and new General Reel option the `780 → 781` chain. These are five node-level references to two ordered routes. Video General exposes 100–100,000,000 and hides drip feed because the primary lacks that capability. Reel General exposes 100–2,147,483,647 and supports drip feed. The nine original delivery options retain their IDs, primary IDs and listed delivery wording. This revision uses 11 distinct primaries and 12 distinct referenced handlers including alternates. [Revised ProductDefinition](../../products/instagram-views.json)

| Retained single-handler choice | Handler IDs |
| --- | --- |
| Video speed-specific delivery | 706, 751, 739 |
| Reel speed-specific delivery | 781, 780, 790, 786 |
| Priority tag default and video option | 728 |
| Priority Reel option | 783 |
| Photo Post Views | 722 |

The conditional routes in the analysis remain pending link or lab verification. The saved JSON passed the installed DGP Spec schema and DGP Validation 1.2.1 using the 70-row lab baseline reconstructed from the current export, the field registry snapshot, and the local strict 5% fallback-rate policy. Ordering preview checks resolved all five defaults and eleven options, including both new general routes, their payload bounds and drip-feed visibility. DGP Core resolved all five configured fallback lists. Live Builder import, live failover and fulfillment remain unverified.

## Complete handler inventory

All rows below use `Default` and are enabled and unlocked in the source snapshot. C means structured cancellation, D means structured drip feed, and an empty capability is shown as —. Raw name, category and limits are retained for comparison. “Lab” records the last verified membership.

| Root ID | External ID | Map / Lab | Source category | Target wording | Payload min–max | Raw rate | Capabilities | Exact provider name |
| ---: | --- | --- | --- | --- | --- | ---: | --- | --- |
| 704 | jap:5994 | Mapped / Yes | Instagram Views | Unspecified | 100–2,147,483,647 | 0.0015 | C / D | Instagram Views [Max: 10M] [Start Time: 0-1 Hour] [Speed: 200K/D] |
| 705 | jap:513 | Mapped / Yes | Instagram Views | Unspecified | 100–2,147,483,647 | 0.0063 | C / D | Instagram Views [Max: 10M] [Start Time: 0-1 Hour] [Speed: 500K/Day] |
| 706 | jap:6454 | Mapped / Yes | Instagram Views | All Videos | 100–2,147,483,647 | 0.0062 | C / D | Instagram Views [All Videos] [Max: 100M] [Start Time: 0 - 1 Hours] [Speed: 20M/Day] ⚡💧⛔ |
| 707 | jap:442 | Mapped / Yes | Instagram Views | Unspecified | 100–2,147,483,647 | 0.01 | C / D | Instagram Views [Max: 5M] [Start Time: 1 - 4 Hours] [Speed: 5M/Day] ⚡💧 |
| 708 | jap:5643 | Mapped / Yes | Instagram Views | All Videos | 100–2,147,483,647 | 0.07 | C / D | Instagram Views [ALL VIDEOS] [Max: 10M]  [Start Time: 0-1 Hour] [Speed: 1M/Day] 💧 |
| 709 | jap:767 | Mapped / Yes | Instagram Views | Unspecified | 100–2,147,483,647 | 0.0812 | C / D | Instagram EMERGENCY Views [Max: 500K] [Start Time: 0 - 1 Hr] [Speed: 50K/D] 💧 |
| 710 | jap:6519 | Mapped / Yes | Instagram Views | Unspecified | 100–2,147,483,647 | 0.10 | C / D | Instagram Views [Max: 10M] [Start Time: 0 - 1 Hour] [Speed: 100K/Day] 💧 |
| 711 | jap:492 | Mapped / Yes | Instagram Views | Unspecified | 100–2,147,483,647 | 0.125 | C / D | Instagram Views [Max: 1M] [Start Time: 0-1 Hr] [Speed: 1M/D] 💧 |
| 712 | jap:6491 | Mapped / Yes | Instagram Views | All / All Links | 100–2,147,483,647 | 0.20 | C / D | Instagram Views [EMERGENCY / WORKING] [ALL LINKS] [Max: 1M] [Start Time: 0 - 3 Hrs] [Speed: 500K/D] 💧 |
| 713 | jap:167 | Mapped / Yes | Instagram Views | Unspecified | 100–217,545,811 | 0.0032 | D | Instagram Views [Max: 9M] [Start Time: 0-1 Hour] [Speed: 100K/Day] |
| 714 | jap:166 | Mapped / Yes | Instagram Views | Unspecified | 100–2,147,483,647 | 0.2063 | C / D | Instagram Views [Max: 999K] [Start Time: 0-1 Hour] [Speed: 500K/Day] 💧 |
| 715 | jap:260 | Mapped / Yes | Instagram Views | Unspecified | 100–2,147,483,647 | 0.2088 | C / D | Instagram Views [Max: 5M] [Start Time: 1 Hour] [Speed: 500K/Day] |
| 716 | jap:6470 | Omitted / No | Instagram Views | Named multiple | 100–2,147,483,647 | 0.2188 | C / D | Instagram Views [REEL + IGTV + POSTS] [Max: 9M] [Start Time: 0-1 Hour] [Speed: 100K/Day] |
| 717 | jap:6469 | Mapped / Yes | Instagram Views | All / All Links | 100–2,147,483,647 | 0.2313 | C / D | Instagram Views [ALL LINKS] [Max: 10M] [Start Time: 0-1 Hour] [Speed: 500K/Day] |
| 718 | jap:3818 | Mapped / Yes | Instagram Views | Unspecified | 100–2,147,483,647 | 0.2338 | C / D | Instagram Views [Max: 10M] [Start Time: 0-1 Hour] [Speed: 5M/Day] |
| 719 | jap:7518 | Mapped / Yes | Instagram Views | Unspecified | 100–2,147,483,647 | 0.2562 | C / D | Instagram Views [Max: 100K] [Start Time: INSTANT] [Speed: 3k/Min] |
| 720 | jap:6373 | Mapped / Yes | Instagram Views | All Videos | 100–2,147,483,647 | 0.1176 | C / D | Instagram Views [All Videos] [Max: 100M] [Start Time: 0 - 1 Hours] [Speed: 10M/Day] ⚡💧 |
| 722 | jap:5998 | Mapped / Yes | Instagram Views | Photo | 100–1,000,000 | 0.01 | C / D | Instagram Photo Views [Max: 10M] [Start Time: 0-1 Hour] [Speed: 500K/Day] ⛔ |
| 724 | jap:3427 | Mapped / Yes | Instagram Views | Unspecified | 100–217,545,811 | 0.0013 | D | Instagram Views [Max: 10M] [Start Time: 0-1 Hour] [Speed: 5M/Day] 💧 |
| 725 | jap:765 | Omitted / No | Instagram Views | Reel | 100–2,147,483,647 | 0.24 | C / D | Instagram Reel Views [Max: 10M] [Start Time: 0-1 Hour] [Speed: 500K/Day] 💧 |
| 726 | jap:635 | Mapped / Yes | Instagram Views | All / All Links | 100–2,147,483,647 | 0.2438 | C / D | Instagram Views [ALL] [Max: 1M] [Start Time: 0 - 1 Hour] [Speed: 100K/Day] 💧 |
| 727 | jap:633 | Mapped / Yes | Instagram Views | All Videos | 100–100,000,000 | 0.25 | C | Instagram Views [All Videos] [Max: 100M] [Start Time: 1 Hour] [Speed: 200K/Day] 💧 |
| 728 | jap:2 | Mapped / Yes | Instagram Views | All Videos | 100–2,147,483,647 | 0.2556 | C / D | Instagram EMERGENCY Views [All Videos] [Max: 100M] [Start Time: 0 - 1 Hour] [Speed: 400K/Day] 💧 |
| 729 | jap:640 | Mapped / Yes | Instagram Views | Unspecified | 50–100,000,000 | 0.0017 | C | Instagram Views [500K] [1Hour - 500K/Day] 💧 |
| 730 | jap:339 | Mapped / Yes | Instagram Views | Unspecified | 100–217,545,811 | 0.0009 | — | Instagram Views [Max: 60K] [Start Time: 0-1 Hour] [Speed: 60K/Day] 💧 |
| 731 | jap:1633 | Mapped / Yes | Instagram Views | Unspecified | 100–2,147,483,647 | 0.0012 | C | Instagram Views  [5M] [INSTANT - 5M/Day] 💧 |
| 732 | jap:6563 | Mapped / Yes | Instagram Views | All Videos | 100–2,147,483,647 | 0.25 | C / D | Instagram Views [All Videos] [Max: 1M] [Start Time: 0 - 1 Hour] [Speed: 100K/Day] 💧 |
| 733 | jap:790 | Mapped / Yes | Instagram Views | Unspecified | 100–100,000,000 | 0.002 | C | Instagram Views  [Max: 1M] [Start Time: 0-1 Hour] [Speed: 1M/Day] 💧 |
| 734 | jap:4349 | Mapped / Yes | Instagram Views | Unspecified | 100–2,147,483,647 | 0.25 | C / D | Instagram Views [Max: 2M] [Start Time: 0-1 Hour] [Speed: 5M/Day] 💧 |
| 735 | jap:557 | Mapped / Yes | Instagram Views | All / All Links | 100–2,147,483,647 | 0.20 | C / D | Instagram Views [ALL LINKS] [Max: 10M] [Start Time: 0-1 Hr] [Speed: 1M/Day] 💧 |
| 736 | jap:5996 | Mapped / Yes | Instagram Views | All / All Links | 100–2,147,483,647 | 0.2188 | C / D | Instagram Views [ALL / EMERGENCY] [Max: 10M] [Start Time: 0-1 Hour] [Speed: 500K/Day] |
| 737 | jap:933 | Mapped / Yes | Instagram Views | All Videos | 100–2,147,483,647 | 0.298 | C / D | Instagram Views [All Videos] [Max: 1M] [Start Time: 0-1 Hour] [Speed: 10K/Hour] 💧 |
| 738 | jap:2180 | Mapped / Yes | Instagram Views | Unspecified | 100–2,147,483,647 | 0.3072 | C / D | Instagram Views [Max: 1M] [Start Time: 1 Hour] [Speed: 1M/Day]  ⚡💧 |
| 739 | jap:3008 | Mapped / Yes | Instagram Views | All Videos | 100–2,147,483,647 | 0.625 | C / D | Instagram Views [All Videos] [Max: 100M] [Start Time: 0-1 Hour] [Speed: 5M/Hour] |
| 740 | jap:632 | Mapped / Yes | Instagram Views | Unspecified | 100–2,147,483,647 | 0.625 | C / D | Instagram Views [EMERGENCY] [Max: 1M] [Start Time: Instant] [Speed: 50K/Day] 💧 |
| 741 | jap:556 | Mapped / Yes | Instagram Views | All / All Links | 100–2,147,483,647 | 1.00 | C / D | Instagram Views [ALL LINKs] [Max: 100K] [Start Time: 0 - 1 Hour] [Speed: 50K/Hour] ⚡💧 |
| 742 | jap:5992 | Mapped / Yes | Instagram Views | Unspecified | 100–2,147,483,647 | 1.025 | C / D | Instagram Views [Max: 100M] [Start Time: 0-1 Hour] [Speed: INSTANT] 💧 |
| 743 | jap:1645 | Mapped / Yes | Instagram Views | Unspecified | 100–2,147,483,647 | 1.0875 | C / D | Instagram Views [10M] [Start Time: Instant] [Speed: 10M/Day] |
| 744 | jap:4162 | Omitted / No | Instagram Views | Named multiple | 100–2,147,483,647 | 1.197 | C / D | Instagram Views [WORKS ON REEL AND IGTV] [Max: 10M] [Start Time: 0-1 Hour] [Speed: SLOW] |
| 746 | jap:6514 | Mapped / Yes | Instagram Views | Unspecified | 100–2,147,483,647 | 1.2125 | C / D | Instagram Views [Max: 100M] [Start Time: 1 Hour] [Speed: 10M/Day]  ⚡💧 |
| 747 | jap:441 | Mapped / Yes | Instagram Views | Unspecified | 100–2,147,483,647 | 1.225 | C / D | Instagram Views [Max: 5M] [Start Time: 0-1 Hour] [Speed: 5M/Day] 💧 |
| 748 | jap:6472 | Mapped / Yes | Instagram Views | All Videos | 100–2,147,483,647 | 1.23 | C / D | Instagram Views [All Videos] [Start Time: 0 - 1 Hour] [Speed: 5M/Day] |
| 749 | jap:2261 | Mapped / Yes | Instagram Views | Unspecified | 100–2,147,483,647 | 1.25 | C / D | Instagram Views [Max: 10M] [Start Time:0 - 1 Hours] [Speed: Up to 2M / Day] ⚡💧 |
| 750 | jap:6498 | Mapped / Yes | Instagram Views | Unspecified | 100–2,147,483,647 | 1.25 | C | Instagram Views [Max: 1M] [Start Time: 1 Hour] [Speed: 5M/Day]  ⚡💧 |
| 751 | jap:6549 | Mapped / Yes | Instagram Views | All Videos | 100–2,147,483,647 | 1.26 | C / D | Instagram Views [All Videos] [Max: 5M] [Start Time: Instant] [Speed: 5M/Day] |
| 752 | jap:6516 | Mapped / Yes | Instagram Views | Unspecified | 100–2,147,483,647 | 1.30 | C / D | Instagram Views [Max: 2M] [Start Time: Instant] [Speed: 5M/Day]  ⚡💧 |
| 753 | jap:6496 | Mapped / Yes | Instagram Views | Unspecified | 100–2,147,483,647 | 1.31 | C / D | Instagram Views [Max: 1M] [Start Time: 15 Minutes] [Speed: 5M/Day]  ⚡💧 |
| 754 | jap:6365 | Omitted / No | Instagram Views | All Posts | 100–2,147,483,647 | 1.33 | C / D | Instagram Views [All Posts] [Max: 10M] [Start Time: 0-1 Hour] [Speed:1M/Day] 💧 |
| 755 | jap:8190 | Mapped / Yes | Instagram Views | All / All Links | 100–2,147,483,647 | 1.3332 | C | Instagram Views [All Links] [Max: 5M] [Start Time: 0 - 1 Hour] [Speed: 100K/Day] |
| 756 | jap:519 | Mapped / Yes | Instagram Views | Unspecified | 100–2,147,483,647 | 1.3335 | C / D | Instagram Views [Max: 1M] [Start Time: Insatnt] [Speed: 1M/Day] 💧 |
| 757 | jap:7793 | Omitted / No | Instagram Views | All Posts | 100–2,147,483,647 | 1.3433 | C | Instagram Views [All Posts] [Max: 10M] [Start Time: 0-5 Minutes] [Speed:100K/Hour] 💧 |
| 758 | jap:6457 | Mapped / Yes | Instagram Views | All Videos | 100–2,147,483,647 | 1.35 | C / D | Instagram Views [EMERGENCY - ALL TYPE OF VIDEOS - AUTO ON / OFF] |
| 759 | jap:6561 | Mapped / Yes | Instagram Views | Unspecified | 100–2,147,483,647 | 1.375 | C / D | Instagram Views [Max: 5M] [Start Time: 0-1 Hour] [Speed: INSTANT] ⛔ |
| 760 | jap:636 | Mapped / Yes | Instagram Views | All Videos | 100–2,147,483,647 | 1.50 | C / D | Instagram Views [ALL VIDEOS / EMERGENCY] [Max: 10M] [Start Time: 0-1 Hour] [Speed: 500K/Day] |
| 761 | jap:9584 | Mapped / Yes | Instagram Views | Private wording | 100–2,147,483,647 | 1.50 | C / D | Instagram Views [ALL VIDEOS / PRVT] [Max: 10M] [Start Time: 0-1 Hour] [Speed: 500K/Day] |
| 762 | jap:960 | Omitted / No | Instagram IGTV | Named multiple | 100–2,147,483,647 | 0.0063 | C / D | Instagram Views [REEL + IGTV + POSTS] [Max: 9M] [Start Time: 0-1 Hour] [Speed: 100K/Day] |
| 763 | jap:4239 | Mapped / Yes | Instagram IGTV | IGTV | 100–2,147,483,647 | 0.0063 | C / D | IGTV Views [Max: 10M] [Start Time: 0-1 Hour] [Speed: INSTANT] ⛔💧 |
| 764 | jap:8573 | Mapped / Yes | Instagram IGTV | IGTV | 100–2,147,483,647 | 0.01 | C / D | IGTV Views [Max: 5M] [Start Time: 0-6 Hour] [Speed: 1M/Day] |
| 765 | jap:1866 | Mapped / Yes | Instagram IGTV | IGTV | 100–2,147,483,647 | 0.03 | C / D | Instagram Views [IGTV] [Max: 100K] [Start Time: 0 - 1 Hour] [Speed: 50K/Hour] ⚡💧 |
| 766 | jap:6456 | Omitted / No | Instagram IGTV | Named multiple | 100–2,147,483,647 | 0.07 | C / D | Instagram Views [REEL + IGTV + NORMAL] [Max: 500K] [Start Time: 0-1 Hour] [Speed: 100K/Day] |
| 767 | jap:6692 | Mapped / Yes | Instagram IGTV | IGTV | 100–2,147,483,647 | 0.10 | C / D | IGTV Views [WORKING] [Max: 100M] [Start Time: 0-1 Hr] [Speed: 10M/D] 💧 |
| 768 | jap:6460 | Mapped / Yes | Instagram IGTV | IGTV | 100–2,147,483,647 | 0.125 | C / D | Instagram IGTV Views [Max: 5M] [Start Time: 0-1 Hour] [Speed: 5M/Day] 💧 |
| 769 | jap:5991 | Mapped / Yes | Instagram IGTV | IGTV | 100–2,147,483,647 | 0.2063 | C / D | IGTV Views [Max: 10M] [Start Time: 0-1 Hour] [Speed: 1M/Day] |
| 770 | jap:847 | Mapped / Yes | Instagram IGTV | IGTV | 100–2,147,483,647 | 0.2313 | C / D | IGTV Views [Max: 10M] [Start Time: 0 - 1 Hour] [Speed: 5M/D] 💧 |
| 771 | jap:637 | Mapped / Yes | Instagram IGTV | IGTV | 100–2,147,483,647 | 0.2338 | C / D | Instagram IGTV Views [Max: 1M] [Start Time: 0-1 Hour] [Speed: 1M/Day] 💧 |
| 772 | jap:6313 | Mapped / Yes | Instagram IGTV | IGTV | 100–2,147,483,647 | 0.25 | C / D | IGTV Views [Max: 10M] [Start Time: 0-1 Hour] [Speed: 500K/Day] |
| 773 | jap:7854 | Mapped / Yes | Instagram IGTV | IGTV | 100–100,000,000 | 0.01 | C / D | Instagram IGTV Views [Max: 10M] [Start Time:0 - 1 Hours] [Speed: Up to 2M / Day] ⚡💧 |
| 774 | jap:6478 | Mapped / Yes | Instagram IGTV | IGTV | 100–2,147,483,647 | 0.2556 | C / D | IGTV Views [Max: 1M] [Start Time: 1 Hour] [Speed: 1M/Day]  ⚡💧 |
| 775 | jap:3523 | Mapped / Yes | Instagram IGTV | IGTV | 100–2,147,483,647 | 0.298 | C / D | IGTV Views [Max: 1M] [Start Time: 0-1 Hour] [Speed: 10K/Hour] 💧 |
| 777 | jap:8567 | Mapped / Yes | Instagram IGTV | IGTV | 100–2,147,483,647 | 1.0875 | C | IGTV Views [Max: 10M] [Start Time: 0-1 Hour] [Speed: 1M/Day] |
| 778 | jap:6493 | Mapped / Yes | Instagram IGTV | IGTV | 1,000–2,147,483,647 | 1.3566 | C / D | IGTV Views [Max: 1M] [Start Time: 2 Hours] [Speed: 5M/Day]  ⚡💧 |
| 779 | jap:6495 | Mapped / Yes | Instagram IGTV | IGTV | 100–20,000,000 | 1.3625 | C | IGTV Views [Max: 1M] [Start Time: 15 Minutes] [Speed: 5M/Day]  ⚡💧 |
| 780 | jap:3528 | Omitted / Yes | Instagram Reel | Reel | 100–2,147,483,647 | 0.0063 | C / D | Instagram Reel Views [Max: 10M] [Start Time: 0-1 Hour] [Speed: 5M/Day] 💧 |
| 781 | jap:5997 | Omitted / Yes | Instagram Reel | Reel | 100–2,147,483,647 | 0.0063 | C / D | Instagram Reel Views [Max: 5M] [Start Time: 0-1 Hour] [Speed: 500K/Day] |
| 782 | jap:639 | Omitted / No | Instagram Reel | Reel | 100–2,147,483,647 | 0.01 | C / D | Instagram Reel Views [Max: 1M] [Start Time: 0-1 Hour] [Speed: 1M/Day] 💧 |
| 783 | jap:6459 | Omitted / Yes | Instagram Reel | Reel | 100–2,147,483,647 | 0.07 | C / D | Instagram EMERGENCY Reel Views [Max: 5M] [Start Time: 0-1 Hour] [Speed: 5M/Day] 💧 |
| 784 | jap:6471 | Omitted / No | Instagram Reel | Named multiple | 100–2,147,483,647 | 0.10 | C / D | Instagram Views [REEL + IGTV + POSTS] [Max: 9M] [Start Time: 0-1 Hour] [Speed: 100K/Day] |
| 785 | jap:3529 | Omitted / No | Instagram Reel | Reel | 100–2,147,483,647 | 0.125 | C / D | Instagram Reel Views [Max: 1M] [Start Time: 0 - 1 Hr] [Speed: 50K/Hour] ⚡💧 |
| 786 | jap:5993 | Omitted / Yes | Instagram Reel | Reel | 100–2,147,483,647 | 0.20 | C | Instagram Reel Views [Max: 10M] [Start Time: 0-3 Hours] [Speed: 1M/Day] 💧 |
| 787 | jap:4358 | Omitted / No | Instagram Reel | All / All Links | 100–2,147,483,647 | 0.2063 | C / D | Instagram Views [ALL LINKS] [Max: 1M] [Start Time: 0 - 3 Hrs] [Speed: 500K/D] 💧 |
| 788 | jap:6462 | Omitted / No | Instagram Reel | Reel | 100–2,147,483,647 | 0.125 | C | Instagram EMERGENCY Reel Views [Max: 500K] [Start Time: 0 - 1 Hr] [Speed: 500K/D] 💧 |
| 789 | jap:5999 | Omitted / No | Instagram Reel | Reel | 100–2,147,483,647 | 0.2313 | C / D | Instagram Reel Views [Max: 5M] [Start Time: 0-3 Hours] [Speed: 500K/Day] 💧 |
| 790 | jap:6691 | Omitted / Yes | Instagram Reel | Reel | 1,000–2,147,483,647 | 0.24 | C / D | Instagram Reel Views [Max: 100M] [Start Time: 0-1 Hour] [Speed: 100M Per Day] 💧 |
| 791 | jap:6492 | Omitted / No | Instagram Reel | Reel | 100–2,147,483,647 | 0.2556 | C / D | Instagram Reel Views [Max: 1M] [Start Time: 2 Hours] [Speed: 5M/Day]  ⚡💧 |
| 793 | jap:7853 | Omitted / No | Instagram Reel | Reel | 100–100,000,000 | 0.01 | C / D | Instagram Reel Views [Max: 10M] [Start Time:0 - 1 Hours] [Speed: Up to 2M / Day] ⚡💧 |
| 795 | jap:6455 | Omitted / No | Instagram Reel | Reel | 100–2,147,483,647 | 0.298 | C / D | Instagram Reel Views [Max: 1M] [Start Time: 0-1 Hour] [Speed: 10K/Hour] 💧 |
| 796 | jap:6314 | Omitted / No | Instagram Reel | Reel | 100–2,147,483,647 | 0.625 | C / D | Instagram Reel  Views [Max: 10K] [Start Time: 0-1 Hour] [Speed: 10K/Day] 💧 |
| 799 | jap:3526 | Omitted / No | Instagram Reel | Reel | 100–2,147,483,647 | 0.26 | C / D | Instagram Reel Views [Refill: No] [Max: 20M] [Start Time: 0-1 Hour] [Speed: Fast] |
| 800 | jap:6494 | Omitted / No | Instagram Reel | Reel | 100–2,147,483,647 | 1.3516 | C / D | Instagram Reel Views [Max: 1M] [Start Time: 15 Minutes] [Speed: 5M/Day]  ⚡💧 |
| 801 | jap:5995 | Omitted / No | Instagram Reel | Reel | 100–2,147,483,647 | 1.4375 | C / D | Instagram Reel Views [Max: 1M] [Start Time: 0-1 Hour] [Speed: SUPER SPEED] 💧 |
