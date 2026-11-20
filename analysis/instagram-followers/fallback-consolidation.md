# Instagram Followers fallback consolidation

2026-11-19 · Routing proposal for approval

## Result

The current Instagram → Followers → Instagram Followers Builder seed uses 449 distinct directly selectable handlers and 21 fallback-only handlers. It has 13 registered node chains across 11 distinct primary IDs. The previous scan found 320 directly selectable handlers that have a mechanically eligible backup and no registered chain anywhere on that primary. These are potential chain heads. Deciding which handlers can disappear from the options is a separate comparison.

| Routing | Current | Exact matches only | With flexible delivery |
| --- | ---: | ---: | ---: |
| Primary IDs in named branches | 301 | 301 | 296 |
| Individually selectable Others IDs | 148 | 146 | 138 |
| Fallback-only IDs | 21 | 23 | 36 |
| Total eligible mapped IDs | 470 | 470 | 470 |

The full proposal removes 15 current option rows and introduces 12 new chains, bringing the total to 25 registered node chains. Thirteen removed rows came from the original 320-handler pool and twelve retained members get their first chain, leaving 295 members of that original pool without a registered chain. This is a cohort count. It does not assume every candidate in the remaining pool will still qualify after the changes.

## Eligibility and placement

For this pass, both rows must be enabled and unlocked, use the same `Default` payload type, and have identical structured quantity limits and enabled capabilities. The current local rate policy accepts a candidate from 95% to 100% of the primary’s raw catalog rate. Keeping the range identical allows an option to be removed without losing any order size it previously offered. Candidates are within the same Builder selector and preserve the source category, audience, refill duration when available, account qualifiers, and reported workflow. The first two chains also preserve the listed start and delivery speed. The other eleven require customer-facing wording that describes the common delivery terms. The listed timings are estimates. Marketing icons, the order of qualifiers in the source name, and name-only maximums do not alter the structured bounds or capability flags.

| Builder field | Primary → ordered fallbacks | Order range | Rationale |
| --- | --- | --- | --- |
| `f:others-spam-off` | 574 → 624 | 10–100,000 | Spam Off and no refill. Same listed start window, speed, bounds and raw rate. |
| `f:others-spam-on` | 383 → 389 | 20–1,000,000 | Spam On and 365-day refill. Same listed start window, speed and bounds. |
| `f:refill-30` | 351 → 354 → 353 | 10–10,000,000 | 30-day refill. The source lists 2 hours or 0–2 hours and different delivery speeds. Present the shared 2-hour estimate and variable speed. |
| `f:guaranteed-extra-drop` | 350 → 349 | 10–100,000 | High drop and 30-day refill. Both list 0–1 hour. Delivery speed varies. |
| `f:brazil` | 1415 → 1395 | 10–100,000 | Brazil and 30-day refill. The listings span 0–1 and 0–3 hours. Use the broader 3-hour estimate. |
| `f:brazil` | 1405 → 1402 → 1398 | 10–100,000 | Brazil and no refill. All list 10K/day and a one-hour start or window. Keep 1402 first because its listed start matches the primary exactly. |
| `f:others-refill-review` | 360 → 356 | 10–100,000 | Refill is disabled in both payloads despite the names. Use the 3-hour start estimate and variable speed. |
| `f:others-spam-on` | 382 → 381 → 376 | 10–10,000,000 | Spam On and 30-day refill. All list 0–1 hour. Try the 100K/day estimate before the 50K/day estimate because it is closer to the primary’s 200K/day estimate. |
| `f:others-spam-on` | 410 → 393 | 10–20,000 | Spam On and 30-day refill. The listings span 0–1 and 0–2 hours. Delivery speed varies. |
| `f:others-spam-on` | 392 → 397 | 10–1,000,000 | Spam On. Both payloads disable refill despite the names. The same one-hour start window covers both. |
| `f:others-spam-on` | 385 → 414 | 10–1,000,000 | Spam On and 30-day refill. Both list a one-hour start window. Delivery speed varies. |
| `f:others-spam-on` | 552 → 549 | 10–10,000,000 | Spam On and no refill. Use the broader 2-hour start estimate and variable speed. |
| `f:others-spam-on` | 623 → 617 | 10–10,000,000 | Spam On and no refill. Use the broader 3-hour start estimate and variable speed. Keep the separate 2-hour route for customers who choose the shorter window. |

The ordered lists are node-scoped. Retain each selected primary’s current option ID. The 434 retained direct placements and the existing 21 fallback-only placements reconcile through the original inventory, with exactly the 15 newly listed backup IDs changing disposition. Keep all 13 Package rows, fixed-quantity options, and every tag’s default service binding.

### Source evidence for the changed chains

All members of each changed chain use the same JAP configuration (`dgp_handler_id: 1`). The IDs in the placement table are root handler row IDs. The provider ID and rate below come from `external_id` and `payload.rate`. Rows within a chain have the same enabled capabilities and payload range except 1402, which is the existing wider-range Brazil backup.

| Primary ID | Root ID → provider ID at raw rate, primary first | Enabled capabilities |
| ---: | --- | --- |
| 574 | 574 → jap:9554 at 2.375; 624 → jap:9537 at 2.375 | cancel, dripfeed |
| 383 | 383 → jap:2181 at 4.55; 389 → jap:9573 at 4.375 | cancel, refill |
| 351 | 351 → jap:10147 at 2.75; 354 → jap:6331 at 2.75; 353 → jap:10152 at 2.728 | cancel, refill |
| 350 | 350 → jap:10323 at 1.1125; 349 → jap:10321 at 1.1125 | cancel, refill |
| 1415 | 1415 → jap:7860 at 7.625; 1395 → jap:3531 at 7.50 | cancel, dripfeed, refill |
| 1405 | 1405 → jap:8401 at 1.5375; 1402 → jap:4359 at 1.5125; 1398 → jap:1790 at 1.5375 | cancel, dripfeed |
| 360 | 360 → jap:9430 at 2.5258; 356 → jap:3456 at 2.50 | cancel, dripfeed |
| 382 | 382 → jap:1804 at 2.75; 381 → jap:9571 at 2.7468; 376 → jap:8839 at 2.75 | cancel, refill |
| 410 | 410 → jap:1969 at 2.725; 393 → jap:7592 at 2.7032 | cancel, refill |
| 392 | 392 → jap:9558 at 1.6625; 397 → jap:1812 at 1.6038 | cancel, dripfeed |
| 385 | 385 → jap:6560 at 3.08; 414 → jap:525 at 3.00 | cancel, dripfeed, refill |
| 552 | 552 → jap:10029 at 1.125; 549 → jap:5897 at 1.125 | cancel |
| 623 | 623 → jap:9429 at 0.715; 617 → jap:9569 at 0.6875 | cancel |

## Further consolidation to review

A wider handler can cover a narrower primary and still have order sizes that need a visible route. For example, 501 can back up 601 for 10–10M followers at a lower eligible rate, with matching listed speed and start. Row 501 also serves up to 50M and supports drip feed. It can be investigated as a shared backup while retaining the wider order route. Some same-range offers are spread across a parent and child, such as routes 343 and 366 for 365-day refill. Merging those requires a navigation decision about where to find the combined option and how to describe its delivery estimates. Neither case is counted in the 15.

Rate differences also stop a longer chain even when adjacent pairs would qualify. On the Spam On 365-day route, 389 can follow 383. Its rate is more than 5% below 378, so an ordered chain starting at 378 cannot include 389 under the current policy. This snapshot contains no fulfillment success or failure evidence. Production retry behavior and provider reliability are unverified.

## Coverage and Builder verification

The catalog still lists this product as `not_started`. The scoped mapping contains 474 root row IDs. The current registry resolves 470 enabled, unlocked rows in `Default` (457) and `Package` (13). The four missing IDs remain 373, 500, 616 and 1380, with the last inspected live lab recording them locked. The independently checked omitted candidates remain 11689, the clear standalone match that needs membership confirmation, and 640 and 2837, whose platform evidence conflicts. Threads 27–29, NFT variants 112–115, and follower-containing bundles remain separate service families. The [full inventory and dispositions](analysis.md) supply all unchanged mappings and the detailed source evidence for excluded and omitted IDs.

Use the existing `select/default` single-choice fields with their placeholders, `text/default` profile link, `number/default` quantity for variable Default orders, and capability-aware `toggle/default` Drip feed with help text and conditional Runs and Interval. Preserve the exact option quantity for fixed Default choices and internal quantity one for packages. These changes only alter route labels and fallback registration in the proposal. An in-memory copy of the local seed passed the installed DGP validator with the local strict rate and capability policy. The coverage check found exactly 434 direct IDs and 36 fallback-only IDs, with no overlap and a union of 470. [Registry](../../handler%20services.json) · [Catalog mapping](../../catalog-handler-service-ids.json) · [Builder capabilities](../../.ai/service-builder-capabilities.json) · [JAP fields](../../.ai/JAP-SERVICE-TYPES.md)
