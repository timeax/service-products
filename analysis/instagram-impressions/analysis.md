# Instagram Impressions

20 November 2026 · Proposed routing for site-owner approval

The roadmap entry is Instagram → Impressions → Instagram Impressions (`instagram-impressions-impressions`). It is `not_started` and has no canonical ProductDefinition. The proposal accounts for **41 mapped handlers** through **36 selectable choices**, including seven under **Others**, and **five fallback-only handlers**. The starting mode is one-time impressions, with 1104 as the preview default and a delivery choice required before submission.

## Sources and scope

All 41 mapped IDs are unique and resolve in the 5,717-row local registry. The export is an array without embedded site or account identity. All mapped handlers are enabled and unlocked and have a null state reason, JAP `panel_key: jap`, `dgp_handler_id: 1`, and `payload.type: Default`. They all have the same last-seen timestamp, 2026-11-18 08:02:54 UTC, zero missing streak and markup, and no rate adjustment. Cancellation and drip feed each appear on 34 rows. Refill and contract flags are false throughout. Root row IDs are used for routing, with provider external IDs recorded for traceability.

The full registry scan checked impression spellings and abbreviations in names, original categories, and catalog ownership. The exact `Instagram Impressions` category has 19 rows mapped here and three assigned to Profile Visits (1107, 1122, 1124). A category mentioning impressions, such as the automatic comments and saves category, does not make every record an impressions outcome. No additional one-time row was found without another catalog assignment. No mapped ID is stale, unavailable or locked. Current site or Builder membership still needs confirmation against the actual connected services.

| Omitted candidate IDs | Disposition |
| --- | --- |
| 161, 173, 174, 180, 181, 193, 211, 264, 278, 293, 305, 331, 332, 333, 334, 335, 336 | Likes bundles already assigned to Instagram Likes. |
| 182, 267 | Likes, reach and impressions with auto-refill, already assigned to Instagram Engagement. |
| 794, 798, 1070, 1071, 1076, 1077, 1078, 1107, 1122, 1124, 1149, 1155, 1164 | Bundles with profile visits assigned to Instagram Profile Visits. |
| 1230, 1243, 1244, 1273, 1274, 1276, 1280, 1297, 1308, 1472, 1474, 1475, 1479, 1480, 1481, 1482, 1483, 1509, 1515, 1516, 1517 | Recurring Instagram rows with JAP Subscriptions payloads. Track in the subscription review. |

[Roadmap](../../catalog.json) · [ID map](../../catalog-handler-service-ids.json) · [Registry](../../handler%20services.json)

## Customer choices

Group by ordered outcome and target. Generic impressions, placement-specific impressions and Story Impressions get separate modes. The reach and views modes explicitly name bundled outcomes. Regional labels are taken from the listings, and South Korea, Italy and Türkiye are bundled choices. Generic rows do not establish compatibility with any specific media type. Story, Photo, Reel and IGTV labels describe explicit target evidence. The pace and start figures are estimates drawn from listed wording. Avoid non-drop, quality, refill and retention claims from names or emojis.

77 and 81 have the same source names, capabilities and structured range. Their raw rates are 2.40 and 2.08, outside the fallback band. The proposal distinguishes the 77 option using its higher catalog rate. Verify that the customer price actually distinguishes the two routes before publication.

| Tag | Customer choice | Primary | Ordered backups |
| --- | --- | ---: | --- |
| Impressions | 50K/day · Starts within 1 hour | 1104 | — |
| Impressions | Instant delivery · Starts within 1 hour | 1108 | — |
| Impressions | 500K/day · Starts in about 1 hour | 1109 | — |
| Impressions | 500K/day · Starts within 1 hour | 1112 | — |
| Impressions | Starts within 1 hour · Delivery pace varies | 1113 | 1106 |
| Impressions | 20K/day · Starts in about 1 hour | 1123 | — |
| Placement | Photo · Explore and Home | 1110 | — |
| Placement | Explore, Home, Location and Profile | 1114 | — |
| Placement | Explore | 1115 | — |
| Placement | Home | 1116 | — |
| Placement | Home, Explore and other placements | 1118 | — |
| Story Impressions | Impressions · 1M/day | 1093 | — |
| Story Impressions | Views + Impressions · 100K/day | 1067 | — |
| Story Impressions | Views + Impressions · 10K/day | 1079 | — |
| Story Impressions | Views + Likes + Impressions | 1074 | — |
| Impressions + Reach | 100K–250K/day · Starts within 1 hour | 1111 | 1143, 1141 |
| Impressions + Reach | 50K/day · Starts within 1 hour | 1105 | — |
| Impressions + Reach | Instant delivery · Starts within 1 hour | 1119 | — |
| Impressions + Reach | Explore impressions · 40K/day | 1142 | — |
| Impressions + Reach | Starts within 1 hour · Delivery pace varies | 1144 | 1146 |
| Impressions + Reach | Instant start · 100K/hour | 1148 | — |
| Impressions + Reach | 100K/day · Starts within 1 hour | 1150 | — |
| Views + Impressions | Views + Impressions · Reach may be included | 745 | 721 |
| Views + Impressions | Photo Views + Impressions | 723 | — |
| Views + Impressions | Reel Views + Impressions | 802 | — |
| Regional | USA Impressions | 1125 | — |
| Regional | South Korea · Likes + Reach + Impressions | 1423 | — |
| Regional | Italy · Likes + Reach + Impressions | 1432 | — |
| Regional | Türkiye · Likes + Reach + Impressions | 1443 | — |
| Others | English public accounts · Likes + Reach + Impressions | 81 | — |
| Others | English public accounts · Likes + Reach + Impressions · Higher rate | 77 | — |
| Others | IGTV Views + Impressions | 776 | — |
| Others | Other placements · 10K/day | 1117 | — |
| Others | Other placements · 500K/day | 1121 | — |
| Others | 50K/day · Starts in about 1 hour | 1120 | — |
| Others | Engagement + Shares + Reach + Impressions | 1154 | — |

## Fallback decisions

The local Builder default uses a strict 95%–100% rate band and capability fit. Check the primary's full quantity range and exact payload type, then compare destination, promised outcomes and delivery wording. Attach the following chains to their specific choices in `fallbacks.nodes`.

- **1111 → 1143 → 1141.** All three provide reach and impressions, start within one hour by the listing, cover 10–1,000,000 at a raw rate of 0.05, and support cancellation and drip feed. 1143 matches 250K/day and comes first. 1141 lists 100K/day and comes last. The choice expresses the range. 1142 explicitly adds Explore as a constraint and remains independently selectable.
- **1113 → 1106.** Both provide generic impressions with cancellation and drip feed, cover 10–1,000,000, and list a within-hour start. The rates are 0.0700 and 0.0698. The listing changes from 100K/day to instant delivery, so the choice leaves pace flexible. Keep 1108 as its own instant option.
- **1144 → 1146.** Both provide reach and impressions over 10–1,000,000 and retain cancellation and drip feed. The rate moves from 0.0845 to 0.0813, inside the band. 1146 lists an approximately one-hour start and 100K/day. The choice leaves pace flexible.
- **745 → 721.** Both supply views and impressions on an unspecified Instagram target. They share the full structured range of 100–2,147,483,647, with cancellation and drip feed. 0.2375 fits the 0.24 rate band. 721 explicitly adds reach and lists 500K/day rather than 50M/day. The choice says reach may be included and makes no pace promise. This is a last-resort backup pending confirmation that the two handlers accept the same link and that the extra metric is acceptable on this choice.

Other numerical matches either change the explicit placement or target, remove a bundled outcome, or lose a capability. 1109 to 1110 would impose a Photo/Explore/Home scope on a generic choice. The matches across 1114–1118 would change specified placement coverage, and 1118 also lacks drip feed. 1079 to 1148 would exchange Story Views for Reach. 1119 and 1120 disagree on Reach, 1121 and 1123 disagree on the named placement, and 1154 to 1150 would drop engagement and shares. Unlisted pairs fail at least one rate, type, bounds or capability check. Actual retry behavior and the site's effective policy are unverified.

## Complete handler inventory

The structured limits below drive local ordering metadata. Provider-name limits can differ substantially, particularly for 721, 745, 776 and 802. 1120 and 1123 include refill-related symbols despite false structured refill flags. Check accepted quantities before launch and avoid representing the larger figures or refill as promises. C indicates cancellation and D indicates drip feed.

| Row | JAP external ID | Original source category | Structured min–max | Raw rate | Caps | Original provider name |
| ---: | --- | --- | ---: | ---: | --- | --- |
| 77 | jap:4232 | Instagram TOP Services [EXCLUSIVE] | 5–50,000 | 2.40 | C | Instagram Likes + Impressions + Reach [NON DROP] [English PUBLIC with Stories Accounts] [Max: 7K] [Start Time: 0-1 Hour] [Speed: FAST] 💧🔥🔥🔥 |
| 81 | jap:5714 | Instagram TOP Services [EXCLUSIVE] | 5–50,000 | 2.08 | C | Instagram Likes + Impressions + Reach [NON DROP] [Max: 7K] [Start Time: 0-1 Hour] [Speed: FAST] 💧🔥🔥🔥 |
| 721 | jap:634 | Instagram Views | 100–2,147,483,647 | 0.2375 | C D | Instagram Views + Reach + Impressions [Max: 10M] [Start Time: 0-1 Hr] [Speed: 500K/D] 💧 |
| 723 | jap:7589 | Instagram Views | 100–10,000,000 | 0.0375 | D | Instagram Photo Views + Impressions [Max: 500K] [Start Time: 0-1 Hour] [Speed: 500K/D] ⛔ |
| 745 | jap:3350 | Instagram Views | 100–2,147,483,647 | 0.24 | C D | Instagram Views + Impression [Max: 100M] [Start Time: 0-1 Hour] [Speed: 50M/Day] 💧 |
| 776 | jap:638 | Instagram IGTV | 100–2,147,483,647 | 0.6078 | C D | Instagram IGTV Views + Impressions [Max: 1M] [Start Time: 0-1 Hour] [Speed: 1M/Day] 💧 |
| 802 | jap:733 | Instagram Reel | 100–2,147,483,647 | 2.14 | C D | Instagram Reel Views + Impressions [Max: 1M] [Start Time: 0-1 Hour] [Speed: 1M/Day] 💧 |
| 1067 | jap:8301 | Instagram Story | 10–100,000 | 0.1563 | D | Instagram Story Views + Impressions [Max: 100K] [Start Time: 0-1 Hour] [Speed: 100K/Day] |
| 1074 | jap:8305 | Instagram Story | 20–100,000 | 0.2688 | D | Instagram Story Views + Likes + Impressions [Max: 100K] [Start Time: 0-1 Hour] [Speed: 100K/Day] |
| 1079 | jap:5692 | Instagram Story | 200–10,000 | 0.50 | D | Instagram Story Views + Impressions [Max: 10K] [Start Time: 0-1 Hour] [Speed: 10K/Day] |
| 1093 | jap:5691 | Instagram Story | 200–1,000,000 | 0.12 | — | Instagram Story Impressions [Max: 1M] [Start Time: 0-1 Hour] [Speed: 1M/Day] |
| 1104 | jap:7590 | Instagram Impressions | 10–1,000,000 | 0.0194 | C D | Instagram Impressions [Max: 500K] [Start Time: 0 - 1 Hr] [Speed: 50K/D] |
| 1105 | jap:1799 | Instagram Impressions | 10–500,000 | 0.0238 | C D | Instagram Impressions + Reach [Max: 500K] [Start Time: 0 - 1 Hr] [Speed: 50K/D] |
| 1106 | jap:7038 | Instagram Impressions | 10–1,000,000 | 0.0698 | C D | Instagram Impressions [Max: 1M] [Start Time: 0-1 Hour] [Speed: INSTANT] |
| 1108 | jap:6316 | Instagram Impressions | 10–1,000,000 | 0.0423 | C D | Instagram Impressions [Max: 5M] [Start Time: 0-1 Hour] [Speed: INSTANT] 💧 |
| 1109 | jap:576 | Instagram Impressions | 10–1,000,000 | 0.046 | C D | Instagram Impressions [Max: 1M] [Start Time: 1 Hour] [Speed: 500K/Day] |
| 1110 | jap:669 | Instagram Impressions | 10–1,000,000 | 0.045 | C D | Instagram Impressions [Photo + Explore + Home] [Max: 1M] [Start Time: 0-1 Hour] [Speed: INSTANT] |
| 1111 | jap:7536 | Instagram Impressions | 10–1,000,000 | 0.05 | C D | Instagram Reach + Impressions [Max: 1M] [Start Time: 0 - 1 Hour] [Speed: 250K/Day] |
| 1112 | jap:429 | Instagram Impressions | 10–1,000,000 | 0.06 | C D | Instagram Impressions [Max: 1M] [Start Time: 0-1 Hour] [Speed: 500K/Day] |
| 1113 | jap:616 | Instagram Impressions | 10–1,000,000 | 0.07 | C D | Instagram Impressions [Max: 100K] [Start Time: 0-1 Hour] [Speed: 100K/Day] |
| 1114 | jap:661 | Instagram Impressions | 10–1,000,000 | 0.07 | C D | Instagram Impressions [EXPLORE - HOME - LOCATION - PROFILE] [Max: 10M] [Start Time: 0-1 Hour] [Speed: 500K/Day] |
| 1115 | jap:3594 | Instagram Impressions | 10–1,000,000 | 0.0719 | C D | Instagram Impression [Explore] [Max: 10K] [Start Time: 0-1 Hour] [Speed: 10K/Day] |
| 1116 | jap:3595 | Instagram Impressions | 10–1,000,000 | 0.0719 | C D | Instagram Impression [Home] [Max: 10K] [Start Time: 0-1 Hour] [Speed: 10K/Day] |
| 1117 | jap:3597 | Instagram Impressions | 10–1,000,000 | 0.0719 | C D | Instagram Impression [Others] [Max: 10K] [Start Time: 0-1 Hour] [Speed: 10K/Day] |
| 1118 | jap:3598 | Instagram Impressions | 10–1,000,000 | 0.0719 | C | Instagram Impression [Home+ Explore + Discover Others] [Max: 100K] [Start Time: 0-1 Hour] [Speed: 100K/Day] |
| 1119 | jap:4337 | Instagram Impressions | 10–1,000,000 | 0.075 | C D | Instagram Impressions + Reach [Max: 250K] [Start Time: 0-1 Hour] [Speed: INSTANT] 💧 |
| 1120 | jap:3591 | Instagram Impressions | 10–1,000,000 | 0.075 | C D | Instagram Impressions [Max: 1M] [Start Time: 1 Hour] [Speed: 50K/Day] 💧♻🛑 |
| 1121 | jap:809 | Instagram Impressions | 10–1,000,000 | 0.10 | C | Instagram Impressions [OTHER] [Max: 10M] [Start Time: 0-1 Hour] [Speed: 500K/Day] |
| 1123 | jap:254 | Instagram Impressions | 10–1,000,000 | 0.0998 | C D | Instagram Impressions [Max: 1M] [Start Time: 1 Hour] [Speed: 20K/Day] 💧♻🛑 |
| 1125 | jap:833 | Instagram Impressions | 10–1,000,000 | 0.27 | C D | Instagram USA Impressions [Max: 100K] [Start Time: 0-1 Hour] [Speed: 100K/Day] 💧 |
| 1141 | jap:865 | Instagram Reach | 10–1,000,000 | 0.05 | C D | Instagram Reach + Impressions [Max: 300K] [Start Time: 0-1 Hour] [Speed: 100K/Day] 💧⛔️ |
| 1142 | jap:8396 | Instagram Reach | 10–1,000,000 | 0.05 | C D | Instagram Reach + EXPLORE Impressions [Max: 40K] [Start Time: 0-1 Hour] [Speed: 40K/Day] 💧⛔️ |
| 1143 | jap:7537 | Instagram Reach | 10–1,000,000 | 0.05 | C D | Instagram Reach + Impressions [1M] [Start Time: 0 - 1 Hour] [Speed: 250K/Day] ⛔💧 |
| 1144 | jap:6317 | Instagram Reach | 10–1,000,000 | 0.0845 | C D | Instagram Reach + Impressions [Max: 5M] [Start Time: 0-1 Hour] [Speed: INSTANT] 💧 |
| 1146 | jap:4372 | Instagram Reach | 10–1,000,000 | 0.0813 | C D | Instagram Reach + Impression [Max: 100K] [Start Time: 1 Hour] [Speed: 100K/Day] ⛔️💧 |
| 1148 | jap:7524 | Instagram Reach | 10–1,000,000 | 0.50 | C D | Instagram Reach + Impressions [Max: 100K] [Start Time: INSTANT] [Speed: 100k/Hr] |
| 1150 | jap:1068 | Instagram Reach | 10–1,000,000 | 0.8125 | C D | Instagram Reach + Impressions [Max: 100K] [Start Time: 0-1Hour] [Speed: 100K/Day] ⚡️💧🔥 |
| 1154 | jap:7527 | Instagram Engagement | 100–100,000 | 0.85 | — | Instagram Engagement + Shares + Reach + Impressions [Max: 100K] [Start Time: INSTANT] [Speed: 100k/Hr] |
| 1423 | jap:1332 | Instagram SOUTH KOREA Services 🇰🇷 | 20–10,000 | 10.40 | D | 🇰🇷🇰🇵 Instagram Likes + Impressions + Reach [Korea] [HQ] [Refill: 90 Days] [Max: 10K] [Start Time: 0 - 1 Hour] [Speed: 10K/Day] |
| 1432 | jap:4396 | Instagram ITALY Services 🇮🇹 | 10–5,000 | 11.5875 | C | 🇮🇹Instagram Likes + Impressions + Reach [ITALY] [NON DROP] [Max: 2.5K] [Start Time: 4 Hours] [Speed: 1K/Day] |
| 1443 | jap:6273 | Instagram TURKEY Services 🇹🇷 | 47–10,000 | 0.1932 | C D | 🇹🇷 Instagram Likes + Reach + Impressions [REAL - TURKEY] [No Refill] [Max: 40K] [Start Time: 1 Hour] [Speed: 40K/Day] |

## Builder field plan

The local Service Builder consumes DGP Spec 1.6.0, Core 1.1.0, Validation 1.2.1 and Ordering 1.1.1. The 13 November capability snapshot supplies the registered variants. Use Builder's generic placeholder property for the text, number and select fields.

| Input | Proposed Builder configuration |
| --- | --- |
| Delivery | Required `select/default`, one choice, options supported and no multi-value. Map options to exact primary IDs. Search enabled for Others. Placeholder “Choose a delivery option”. |
| Instagram link | Required scalar `text/default`, “Paste the Instagram link”. Send `link`. Identify explicit Story, Reel, Photo and IGTV routes in customer copy. Confirm accepted link shapes before imposing strict rules for generic options. |
| Quantity | Required scalar `number/default` with step 1 and “Enter a quantity”. Send `quantity` and derive the base quantity from it. Display structured bounds from the selected handler. Verify site-side range enforcement and the meaning of quantity for bundles. |
| Drip feed | Scalar `toggle/default`. Show it only on a route whose primary and backups support it. |
| Runs and Interval (minutes) | Scalar `number/default` with step 1 and placeholders “e.g. 5” and “e.g. 60”. Require both when the toggle is active. Send `runs` and `interval` for drip-feed orders, and keep the toggle as Builder state. |

These one-time payloads use no newline-separated list input. All selectors must resolve one service, with no option selected from a previous mode. Check conditional submission and hidden values in the intended ordering path.

[Builder capability snapshot](../../.ai/service-builder-capabilities.json) · [JAP order fields](../../.ai/JAP-SERVICE-TYPES.md) · [Local contract index](../../.ai/agent-search.json)

## Review and verification

Static checks verified all 41 IDs, state, exact-scope omissions, and type, rates, ranges and capabilities for the five proposed backup assignments. Builder validation and provider fulfillment have not run. The site-owner review should focus on the 745 backup's optional reach, the parallel English public account prices, accepted link types, conflicting quantity limits, and bundle quantity semantics. Approval is required before creating `products/instagram-impressions.json`.


## Approved implementation and verification

On 20 November 2026 the site owner approved the proposed routing. The [canonical ProductDefinition](../../products/instagram-impressions.json) preserves the 36 reviewed labels and includes all 41 mapped rows. Impressions is the starting tag with 1104 as its preview default. Each of the seven tags requires a delivery choice. Others supports search, and the text, numeric and select controls have placeholders. The catalog status remains `not_started`.

- Local DGP validation returned zero structural and semantic diagnostics with the 41 mapped registry rows, the Builder capability snapshot, and the strict local 5% fallback rate band.
- DGP Core resolved all four approved chains in order. The five fallback-only service IDs match the proposed assignments.
- DGP Ordering resolved exactly one primary and the expected structured quantity bounds on each of 36 choices. It rejected missing choices and fractional quantities. Drip feed is available on 29 choices and requires both runs and interval. Ordinary orders omit both values even if the form still contains them.
- Builder UI validation, current site registry membership, site-side quantity enforcement and live provider fulfillment remain unverified. The link compatibility and added-reach behavior for 745 → 721 and the displayed price distinction between 77 and 81 remain open provider or site checks.
