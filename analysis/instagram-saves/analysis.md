# Instagram Saves

20 November 2026 · Proposed routing for site-owner approval

The roadmap entry is Instagram → Saves → Instagram Saves (`instagram-saves-saves`). It is `not_started` and has no canonical ProductDefinition. The 15 mapped handlers can be covered by **nine selectable choices and six fallback-only handlers**. Include one additional **Reel Saves** choice if row 792 is confirmed in the target Builder registry. With that choice, the proposal covers 16 handlers through 10 selectable choices and six fallbacks.

## Sources and scope

The project-root export is a 5,717-row JSON array without embedded site or provider-account identity. All 15 mapped IDs resolve, and they account for every row in the original `Instagram Saves` category. All proposed rows, including 792, are enabled and unlocked, have a null state reason, use JAP `panel_key: jap`, share `dgp_handler_id: 1` and `payload.type: Default`, and were last seen 2026-11-18 at 08:02:54 UTC with zero missing streak, zero markup and no rate adjustment. All 15 mapped rows support drip feed. Only 1130 and 792 support cancellation, and 792 lacks drip feed. Refill and contract flags are false for all 16. The routing IDs are root row IDs. Provider external IDs are listed separately.

The independent full-registry scan matched saves, bookmarks and the source category. It found the following records outside the mapping. No mapped row was stale, unavailable or locked.

| Adjacent IDs | Outcome and disposition |
| --- | --- |
| 792 | One-time Instagram Reel Saves under `Instagram Reel`, with JAP external ID `jap:3593`. The local name and payload support a selectable Reel route. This row is absent from all catalog mappings. Confirm the target Builder recognizes it before binding it. Local enabled state alone does not establish Builder membership. |
| 55, 123–126 | Custom Comments Package bundles that include saves among other outcomes. These are already assigned to Instagram Packages. |
| 1477, 1478, 1484, 1485 | Instagram Auto Saves with `Subscriptions` payloads. They require the separate recurring order flow and are candidates for the Instagram Subscriptions review. |

[Roadmap](../../catalog.json) · [Catalog ID map](../../catalog-handler-service-ids.json) · [Registry](../../handler%20services.json)

## Customer choices and routing

Saves is the starting mode with 1128 as its preview default. Require a delivery choice under Saves and Others, then resolve one service. The pack has one outcome, saving the supplied Instagram media. Generic source names leave the precise accepted link types open. Row 792 explicitly identifies Reels and has different capabilities. Keep it in its own direct tag if confirmed. Timing and pace figures are estimates. Use plain pace and minimum-order wording in option labels. The `HQ` label has no supporting description or capability and is not a customer promise.

| Tag | Choice | Primary | Ordered backups |
| --- | --- | ---: | --- |
| Saves | 100K/day · Starts within 1 hour | 1128 | — |
| Saves | 5K/day · Starts within 1 hour | 1129 | — |
| Saves | 50K/day · Starts within 1 hour | 1127 | 1135 |
| Saves | Starts within 1 hour · Delivery pace varies | 1126 | 1131, 1132, 1134, 1133 |
| Saves | 150K/day · Orders from 1 | 1130 | — |
| Saves | 15K–100K/day · Starts within 1 hour | 1138 | 1137 |
| Reel Saves | Instant delivery · Starts within 1 hour | 792 | — |
| Others | 50K/day · Starts in about 1 hour | 1136 | — |
| Others | 3K/day · Starts within 1 hour | 1139 | — |
| Others | Up to 50K/day · Orders from 100 | 1140 | — |

## Fallback decisions

All ordered pairs were checked against the local Builder's strict 95%–100% raw rate policy, exact payload type, full structured range coverage and capability fit. Every backup below has the same generic saves outcome and assumes a compatible accepted link.

- **1127 → 1135.** Both list 50K/day with a within-hour start and support drip feed over 10–1,000,000. Rate 0.10 is inside the 0.098325–0.1035 band. The primary name says HQ. No quality claim is shown on the choice.
- **1126 → 1131 → 1132 → 1134 → 1133.** All five cover 10–1,000,000 at 0.0938 with drip feed. The primary lists 50K/day. The backups with numeric pace follow in closest order, up to 20K/day, 10K/day and 5K/day. 1134 also lists a one-hour start. 1133 is last because its name says instant delivery with no numeric pace. The choice keeps delivery pace flexible and makes no quality or fixed-pace promise.
- **1138 → 1137.** Both are 0.20, cover 10–1,000,000, support drip feed and list a within-hour start. The listings say 100K and 15K/day, respectively. The option reflects that range.

The other numerical matches run in reverse or between members of the same planned pool. They add no new coverage. The other primary rows lack a rate-and-range-compatible alternate. The Reel route has no compatible alternate and should not fall back to a generic saves choice. Put each chain on its choice in `fallbacks.nodes`. Current host policy, actual link compatibility, and retry behavior are unverified.

## Complete registry evidence

Structured min/max and capabilities below come from the export. Fifteen of the 16 names have a maximum that differs from the structured maximum. For example, 1130 has 150K in its name and 100M in its payload, 792 has 100K versus 217,545,811, and 1140 has 50K in its name versus 25K in the payload. Use the structured limits for local previews and confirm accepted quantities before publication. The original figures remain in the evidence. C indicates cancellation and D indicates drip feed.

| Row | JAP external ID | Original category | Structured min–max | Raw rate | Caps | Original provider name |
| ---: | --- | --- | ---: | ---: | --- | --- |
| 792 | jap:3593 | Instagram Reel | 100–217,545,811 | 0.1485 | C | Instagram Reel Saves [Max: 100K] [Start Time: 0-1 Hour] [Speed: INSTANT] |
| 1126 | jap:8693 | Instagram Saves | 10–1,000,000 | 0.0938 | D | Instagram Saves [HQ] [Max: 50K] [Start Time: 0 - 1 Hr] [Speed: 50K/D] 💧⛔ |
| 1127 | jap:9334 | Instagram Saves | 10–1,000,000 | 0.1035 | D | Instagram Saves [HQ] [Max: 50K] [Start Time: 0 - 1 Hr] [Speed: 50K/D] 💧⛔ |
| 1128 | jap:7672 | Instagram Saves | 10–100,000 | 0.0024 | D | Instagram Saves [Max: 100K] [Start Time: 0-1 Hour] [Speed: 100K/Day] 💧 |
| 1129 | jap:8394 | Instagram Saves | 10–100,000 | 0.0075 | D | Instagram Saves [Max: 5K] [Start Time: 0 - 1 Hour] [Speed: 5K/Day] 💧 |
| 1130 | jap:4434 | Instagram Saves | 1–100,000,000 | 0.1224 | C D | Instagram Save [Max: 150K] [Start Time: 1 Hour] [Speed: 150K/Day] |
| 1131 | jap:8791 | Instagram Saves | 10–1,000,000 | 0.0938 | D | Instagram Saves [Max: 50K] [Start Time: 0-1 Hr] [Speed: Up to 20K/D] 💧 |
| 1132 | jap:2932 | Instagram Saves | 10–1,000,000 | 0.0938 | D | Instagram Saves [Max: 20K] [Start Time: 0-1 Hr] [Speed: 10K/D] 💧 |
| 1133 | jap:778 | Instagram Saves | 10–1,000,000 | 0.0938 | D | Instagram Saves [Max: 15K] [Start Time: 0-1 Hour] [Speed: INSTANT] 💧 |
| 1134 | jap:781 | Instagram Saves | 10–1,000,000 | 0.0938 | D | Instagram Saves [Max: 5K] [Start Time: 1 Hour] [Speed: 5K/Day] |
| 1135 | jap:901 | Instagram Saves | 10–1,000,000 | 0.10 | D | Instagram Saves [Max: 50K] [Start Time: 0-1 Hour] [Speed: 50K/Day] |
| 1136 | jap:4371 | Instagram Saves | 10–1,000,000 | 0.1125 | D | Instagram Saves [Max: 50K] [Start Time: 1 Hour] [Speed: 50K/Day] ⛔️💧 |
| 1137 | jap:448 | Instagram Saves | 10–1,000,000 | 0.20 | D | Instagram Saves [Max: 400K] [Start Time: 0-1 Hour] [Speed: 15K/Day] 💧 |
| 1138 | jap:406 | Instagram Saves | 10–1,000,000 | 0.20 | D | Instagram Saves [Max: 400K] [Start Time: 0-1 Hour] [Speed: 100K/Day] 💧 |
| 1139 | jap:8517 | Instagram Saves | 10–1,000,000 | 1.50 | D | Instagram Saves [Max: 3K] [Start Time: 0 - 1 Hour] [Speed: 3K/Day] 💧 |
| 1140 | jap:10233 | Instagram Saves | 100–25,000 | 0.1338 | D | Instagram Saves [HQ] [Max: 50K] [Start Time: 0 - 1 Hr] [Speed: Up to 50K/D] 💧 |

## Builder fields and order contract

The installed contract is DGP Spec 1.6.0, DGP Core 1.1.0, DGP Validation 1.2.1 and DGP Ordering 1.1.1. The 13 November capability snapshot is authoritative for its registered controls. Use supported variants and the Builder's generic placeholder property.

| Input | Proposed control and binding |
| --- | --- |
| Delivery | Required `select/default`, single with options, no multi-value. Use “Choose a delivery option” and enable search under Others. Bind choices to root row IDs. If enabled, the Reel tag has one direct binding. |
| Instagram link | Required scalar `text/default`. Use “Paste the Instagram link” and a Reel-specific label or help on the Reel mode where supported. Submit `link`. Confirm accepted target URLs before narrowing validation. |
| Quantity | Required scalar `number/default`, step 1, positive whole number, with “Enter the number of saves” and base quantity derived from the value. Submit `quantity`. Show the selected service's structured bounds and verify enforcement at the target host. |
| Drip feed | Scalar `toggle/default`. Show when the primary and any configured backups support it. Hide for Reel 792. |
| Runs and Interval (minutes) | Required scalar `number/default` when the toggle is on, with step 1 and placeholders “e.g. 5” and “e.g. 60”. Submit only when active. Check that a route switch discards hidden values from the order. |

All proposed `Default` routes use scalar link and quantity fields. There are no newline-list inputs and no subscription controls.

[Builder capability snapshot](../../.ai/service-builder-capabilities.json) · [JAP type guide](../../.ai/JAP-SERVICE-TYPES.md) · [Local source index](../../.ai/agent-search.json)

## Verification and approval

The static check verified all 15 mapped rows and the omitted-candidate scan, reconciled every proposed placement, and checked all six backup assignments against type, bounds, rate and capabilities. Builder validation and live fulfillment have not run. Approve the mapped routing before creating `products/instagram-saves.json`. Confirm 792's membership in the target Builder registry before including the proposed Reel route. Verify target links, provider-name limits and site-side range enforcement before publication.


## Approved implementation and verification

On 21 November 2026 the site owner approved the 15 mapped handlers. The [canonical ProductDefinition](../../products/instagram-saves.json) has nine choices under Saves and Others, with 1128 as the initial preview binding and a required delivery selection. Six handlers appear in three ordered fallback chains. Reel Saves row 792 remains pending confirmation in the target Builder and has no binding in the definition. The catalog entry remains `not_started`.

- Local DGP structural and semantic validation returned zero diagnostics against the 15 mapped rows, the Builder capability snapshot and the local 5% fallback rate policy. All three chains resolve in the approved order.
- Local ordering checks passed all nine choices, each resolving one primary and its structured quantity bounds. Missing links, fractional quantities and missing required drip-feed inputs were rejected. Ordinary orders omit stale runs and interval values.
- Live Builder acceptance, site-side quantity enforcement, accepted link formats and fulfillment remain unverified.
