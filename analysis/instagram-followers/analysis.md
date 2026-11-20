# Instagram Followers routing reanalysis

2026-11-19 · Full-coverage proposal for approval

## Scope and result

The product is **Instagram → Followers → Instagram Followers** (`instagram-followers-followers`). The catalog entry is `not_started`. The previous Builder preview referenced 301 distinct primary handlers and 17 fallback-only handlers, leaving 152 available rows outside the routing. The full coverage rule requires an actual route or selectable option for each available, unlocked handler in the confirmed product set. [Workspace rules](../../AGENTS.md) · [Catalog](../../catalog.json) · [Workflow](../../.ai/WORKFLOW.md)

The current 5,717-row source export resolves 470 of the 474 mapped root IDs. All 470 are enabled and unlocked in the export, use JAP configuration `dgp_handler_id: 1`, and were last seen at 08:02:54 UTC on 2026-11-18. The 470 consist of 457 `Default` and 13 `Package` rows. The live lab was previously inspected and displayed 470 available and four locked attachments. This reanalysis uses that last verified membership and the project export. The export has no embedded tenant or provider-account identity. Root row IDs are binding IDs. The `external_id` identifies a separate provider record. [Registry](../../handler%20services.json) · [ID map](../../catalog-handler-service-ids.json) · [Last inspected lab](https://tygerbooster.com/labs/224)

| Proposed disposition | Distinct IDs |
| --- | ---: |
| Primary in the existing named branches | 301 |
| Fallback-only in ordered chains | 21 |
| Explicit selectable options under Others | 148 |
| **Total available mapped handlers** | **470** |
| Locked attachments outside proposed routing | 4 |
| **Total mapped attachments reconciled** | **474** |

The 148 Others choices are primary bindings when explicitly selected. The proposal therefore offers 449 distinct direct handlers and 21 fallback-only handlers. Two new fallback chains start on Others options (468 and 470). Two more attach to separate delivery-flexible options using existing primary rows 545 and 503. Those alternate paths reuse existing primary IDs. The specifically labeled delivery options retain their existing bindings.

## Layout and ordering

Keep the current named branches for **Guaranteed**, **Not Guaranteed**, **Followers by Region**, **Followers by Account Type**, **Bot Followers**, and **Verified Follower Packages**. The existing quantity-based root uses 526. Guaranteed retains 344 with its 30-day refill route. Not Guaranteed retains 526. Region, account and bot qualifiers stay visible in options. The raw Guaranteed category contains 155 current rows, with refill explicitly enabled for 94. The raw Not Guaranteed category contains 128 and includes the payload/name conflict at 567. The retained preview routes already cover delivery and refill variants, drop severity, account quality and targeted variants.

Add an **Others** branch with child tags for the option families below. Each residual ID has its own selectable option and stable value based on the root row ID. Customer-visible labels should retain the meaningful terms in the source, with quantity based on the payload. For indistinguishable labels on separate routes, show a neutral numbered alternative. Administrator evidence preserves the exact name, rate and ID. Use a required single-choice field on each subtag. Each tag needs its own default binding, taken from the applicable option list, with explicit option selection controlling the active handler. The two flexible options below should explain that listed delivery and retention details can vary within the generic route.

### Order inputs and exceptions

- `Default` uses the Instagram profile link and integer quantity. Keep the existing capability-aware Drip feed description, Runs and Interval. Eligibility comes from `dripfeed.enabled`. Hidden inputs must be omitted from the outgoing form.
- Fixed-quantity `Default` rows go in their own selector, with the exact `payload.min = payload.max` displayed. The order must send that exact quantity as a `Default` request. A proposed Builder implementation is a dedicated scalar `number/default` field bound to the fixed-quantity tag, with the option's value effect setting the exact value and the field read-only. Confirm that the actual host sends `quantity` after selection and resets it when switching routes. For 72 and 74 the payload quantity is 1,000, while the names describe pricing for 50 and 300 followers. Preserve the disagreement without promising either delivered count from the field alone.
- `Package` uses link and package selection with internal quantity one. Others includes 1453 as an explicit Turkey verified package with follower count unspecified. Keep the variable quantity and Drip feed inputs out of that branch.
- Use `select/default` for each single-choice selector, `text/default` for link, `number/default` for quantity, runs and interval, and `toggle/default` for Drip feed. Preserve useful placeholders and the toggle description. The installed local ProductDefinition contract is DGP schema v1 (`dgp-spec` 1.6.0). The capability snapshot supplies exact control support and the JAP guide supplies the request shapes. [Builder capabilities](../../.ai/service-builder-capabilities.json) · [JAP fields](../../.ai/JAP-SERVICE-TYPES.md)

## Ordered fallbacks

The checked local Builder policy requires capability fit and uses `lte_primary` at 5%. For each proposed backup I checked current availability, exact `Default` payload type, full structured quantity coverage, enabled primary capabilities, and a raw rate from 95% to 100% of the primary. The live lab's effective fallback policy was not refreshed. The order uses the closest eligible match first. Where two backups preserve the same listing, the one with closer bounds goes first. Duplicate membership in a chain does not create a second distinct fallback handler. [Local fallback editor](<D:/Projects/GitHub/service-builder/src/react/canonical-fallbacks.tsx:27>)

| Primary | Ordered fallback IDs | Placement and evidence |
| ---: | --- | --- |
| 344 | 345 | Existing 30-day refill option and its applicable default nodes. Same 10–10M structured bounds, rate, capabilities and listed start and speed. |
| 563 | 550 | Existing no-refill within-one-hour / 100K/day option. Same 10–250K bounds and cancellation. The backup also supports drip feed. |
| 1187 | 1188 → 1189 | Existing bot profile pictures/posts choice, same delivery and rate. Maxima increase from 25K to 30K and 50K. |
| 1191 | 1192 → 1194 → 1197 → 1200 | Existing bot delivery variant. Same named start, speed and duration wording, with the refill flag disabled on all. Increasing maxima keep closer ranges first. |
| 1193 | 1195 → 1198 → 1201 → 1203 | Existing bot delivery variant. Matching listed delivery and duration wording, with refill disabled on all. Closest quantity coverage first. |
| 1196 | 1199 → 1202 → 1204 → 1205 | Existing bot delivery variant. Matching listed delivery and duration wording, with refill disabled on all. Closest quantity coverage first. |
| 1405 | 1402 | Existing Brazil route. Matching normalized name terms other than the name maximum. The backup covers the primary's complete payload range and capabilities. |
| 468 | 472 | New Others guarantee discrepancy option. Both list a one-hour start and 5K/day. Refill is disabled for both despite the name. Same raw rate, and 472 covers the full 100–15K range. |
| 470 | 472 → 469 | New Others guarantee discrepancy option. Same delivery wording and capabilities. 472 covers the primary's 100–30K with closer 100–50K bounds and a 1.52% lower rate. Row 469 has wider 10–10M bounds and an equal rate. |
| 545 | 565 | New **Others → Flexible delivery → 100–100K** option. Both have cancellation and no refill or drip feed. The backup has 10–10M bounds and a 3.20% lower rate. Start and speed labels differ, so use this backup only on the flexible option. |
| 503 | 508 | New **Others → Flexible delivery → 10–100K** option. Both support cancellation and drip feed with refill disabled. The backup has the same bounds and a 4.17% lower rate. The primary names a drop estimate and the other row gives none. Use this backup only on the flexible option with no specific retention or speed selection. |

Rows 386 and 413 pass mechanical checks against some other Guaranteed routes. Their explicit Spam Off condition has unresolved operational meaning, so their placement is an explicit option rather than a silent substitute. The Brazil row 1401 has a real contradiction between its refill flag and name. It remains selectable under the discrepancy group with that fact documented. A provider qualifier alone, such as male or female, is not a fallback disqualifier. Keep named choices grounded in what selecting them promises, and use broader routes only where the choice allows the variation.

## Mapped IDs by retained primary route

The IDs below are unique within this table. Package rows are counted once even where the Builder preview also offers the same choices from a shared package selector.

| Builder tag key | Primary rows | Root row IDs |
| --- | ---: | --- |
| account | 4 | 696–697, 1153, 1441 |
| asia | 13 | 643, 648–649, 655–656, 658–659, 664, 667, 671–672, 683, 1319 |
| bot-delivery | 4 | 1180, 1191, 1193, 1196 |
| bot-profiles | 2 | 1187, 1190 |
| bots | 4 | 558, 562, 570, 1185 |
| brazil | 24 | 651, 685, 1375, 1378, 1393–1396, 1398–1399, 1405–1409, 1411–1419 |
| europe | 30 | 20–21, 71, 633–634, 660, 669, 1021, 1024, 1027–1029, 1031–1032, 1038, 1322, 1340, 1344, 1349, 1353, 1355–1357, 1362–1363, 1368–1370, 1433–1434 |
| fast-start-over-100k | 4 | 509, 527, 538, 568 |
| fast-start-up-to-100k | 18 | 512, 514–516, 518, 530–531, 537, 540, 543, 563, 590, 593, 595, 597–598, 600–601 |
| fast-start-up-to-20k | 17 | 502, 513, 521–523, 525, 534, 536, 554, 585–586, 588–589, 592, 596, 612, 626 |
| faster-start | 1 | 541 |
| general | 4 | 501, 519, 524, 526 |
| guaranteed-extra-drop | 5 | 349–350, 402, 446, 11624 |
| guaranteed-extra-quality | 3 | 369, 454, 465 |
| guaranteed-quality | 5 | 352, 368, 406, 448, 464 |
| guaranteed-refill | 7 | 343–344, 348, 363, 365, 459, 462 |
| guaranteed-retention | 5 | 346–347, 362, 11623, 11625 |
| middle-east | 19 | 16, 75, 639, 641–642, 644–647, 650, 661–663, 665, 668, 673, 681, 1440, 1442 |
| more-no-guarantee-quality | 3 | 533, 561, 569 |
| more-no-guarantee-retention | 12 | 504–506, 594, 603, 606–607, 609–610, 614, 618–619 |
| more-profiles | 6 | 19, 45, 48–49, 73, 688 |
| more-regions | 8 | 636–637, 652–654, 666, 676, 1341 |
| one-hour-start | 10 | 559–560, 604, 608, 613, 615, 620–621, 627, 629 |
| other-start-times | 11 | 511, 517, 528, 532, 544–545, 571–572, 581, 599, 625 |
| packages-egypt | 10 | 1462–1471 |
| packages-turkey | 2 | 1451–1452 |
| quality | 5 | 535, 539, 555, 602, 628 |
| refill-30 | 21 | 351, 353–354, 364, 371, 437, 442–445, 450–453, 463, 466, 478–481, 483 |
| refill-365 | 4 | 359, 366, 374, 441 |
| refill-other | 2 | 455–456 |
| region | 10 | 12, 630, 632, 635, 657, 682, 1392, 1397, 1429, 1439 |
| retention | 4 | 503, 507, 520, 557 |
| usa | 15 | 13, 17–18, 58–59, 83, 98, 102, 631, 686, 1020, 1332, 1335–1336, 1351 |
| usa-uk-europe | 9 | 54, 62, 67–69, 1016–1018, 1030 |


## Others option inventory

Every row below is a proposed, explicit option. The source-name column is evidence for review. It is not final storefront copy or a confirmation of the provider's claims. Additional workflow, flag and provider-instruction wording needs verification before publication. The values in the payload columns are the authoritative route inputs. Rates are raw source rates. `R` denotes refill, `C` cancellation and `D` drip feed. The two flexible choices described in the fallback table reuse 503 and 545, which are already counted above.

| Others subgroup | Selectable rows |
| --- | ---: |
| Delivery alternatives | 5 |
| Fixed-quantity orders | 20 |
| Guarantee and refill discrepancies | 29 |
| Provider workflow or instructions | 12 |
| Spam Off | 12 |
| Spam On | 60 |
| Spam On waiting / Spam Off success | 9 |
| Verified package with unspecified count | 1 |

### Delivery alternatives

| Root ID | Provider ID | Payload type | Payload min–max | Rate | Flags | Original provider name |
| ---: | --- | --- | --- | ---: | --- | --- |
| 510 | jap:10352 | Default | 10–10,000,000 | 4.125 | CD | Instagram Followers [Max 5M]  [Start Time: 0 - 1Hr] [Refill: No] [Speed: Up to 500K/D] 💧⛔ |
| 566 | jap:2012 | Default | 10–10,000,000 | 0.8525 | C | Instagram Followers [WORKING] [Refill: No] [Max: 5M] [Start Time: 0 - 1Hr] [Speed: 100K/D] 💧⛔️ |
| 684 | jap:8741 | Default | 10–100,000 | 1.711 | CD | 🇧🇷 Instagram Followers [BRAZIL] [Refill: NO] [Max: 10K] [Start Time: 0 - 1 Hr] [Speed: 10K/D] ⛔️💧 |
| 1400 | jap:10246 | Default | 1–50,000 | 3.125 | CD | Instagram Followers [BR 🇧🇷] [Refill: 30D] [Max: 100K] [Start Time: 0 - 2 Hrs] [Speed: Up to 2K/D] 💧 |
| 1410 | jap:8095 | Default | 10–100,000 | 10.00 | CD | 🇧🇷 Instagram Followers [BRAZIL] [Auto-Refill: 30 Days] [Max: 50K] [Start Time: 0 - 1 Hours] [Speed: 10K/Day] 💧 |

### Fixed-quantity orders

| Root ID | Provider ID | Payload type | Payload min–max | Rate | Flags | Original provider name |
| ---: | --- | --- | --- | ---: | --- | --- |
| 72 | jap:4121 | Default | 1,000–1,000 | 5.04 | — | Instagram Followers FEMALE TOP ACCOUNTS [PRICE IS FOR 50 FOLLOWERS] [Max: 50] [Start Time: 0-9 Hours] [Speed: 50/Day] |
| 74 | jap:7673 | Default | 1,000–1,000 | 11.40 | — | Instagram Followers FEMALE TOP ACCOUNTS [PRICE IS FOR 300 FOLLOWERS] [Max: 300] [Start Time: 0-9 Hours] [Speed: 300/Day] |
| 484 | jap:3024 | Default | 11,000–11,000 | 3.168 | C | 🔥🔥🔥 [EXCLUSIVE] Instagram Followers [Spam On] [Refill: 65 Days] [Max: 100K/username - 11K/order] [Start Time: 0-1 Hour] [Speed: 5-10K/Day] ♻️🔥🔥🔥 |
| 485 | jap:3025 | Default | 12,000–12,000 | 3.168 | C | 🔥🔥🔥 [EXCLUSIVE] Instagram Followers [Spam On] [Refill: 65 Days] [Max: 100K/username - 12K/order] [Start Time: 0-1 Hour] [Speed: 5-10K/Day] ♻️🔥🔥🔥 |
| 486 | jap:3026 | Default | 13,000–13,000 | 3.168 | C | 🔥🔥🔥 [EXCLUSIVE] Instagram Followers [Spam On] [Refill: 65 Days] [Max: 100K/username - 13K/order] [Start Time: 0-1 Hour] [Speed: 5-10K/Day] ♻️🔥🔥🔥 |
| 487 | jap:2208 | Default | 700–700 | 3.168 | C | 🔥🔥🔥 [EXCLUSIVE] Instagram Followers [Spam On] [Refill: 65 Days] [Max: 100K/username - 700/order] [Start Time: 0-1 Hour] [Speed: 700/Day] ♻️🔥🔥🔥 |
| 488 | jap:2207 | Default | 290–290 | 3.168 | C | 🔥🔥🔥 [EXCLUSIVE] Instagram Followers [Spam On] [Refill: 65 Days] [Max: 100K/username - 290/order] [Start Time: 0-1 Hour] [Speed: 290/Day] ♻️🔥🔥🔥 |
| 489 | jap:2206 | Default | 140–140 | 3.168 | CD | 🔥🔥🔥 [EXCLUSIVE] Instagram Followers [Spam On] [Refill: 65 Days] [Max: 100K/username - 140/order] [Start Time: 0-1 Hour] [Speed: 140/Day] ♻️🔥🔥🔥 |
| 490 | jap:2209 | Default | 1,000–1,000 | 3.168 | C | 🔥🔥🔥 [EXCLUSIVE] Instagram Followers [Spam On] [Refill: 65 Days] [Max: 100K/username - 1K/order] [Start Time: 0-1 Hour] [Speed: 1K/Day] ♻️🔥🔥🔥 |
| 491 | jap:3023 | Default | 9,100–9,100 | 3.168 | C | 🔥🔥🔥 [EXCLUSIVE] Instagram Followers [Spam On] [Refill: 65 Days] [Max: 100K/username - 9.1K/order] [Start time: 0-1 Hour] [Speed: 9.1K/Day] ♻️🔥🔥🔥 |
| 492 | jap:3022 | Default | 8,400–8,400 | 3.168 | C | 🔥🔥🔥 [EXCLUSIVE] Instagram Followers [Spam On] [Refill: 65 Days] [Max: 100K/username - 8.4K/order] [Start Time: 0-1 Hour] [Speed: 8.4K/Day] ♻️🔥🔥🔥 |
| 493 | jap:3021 | Default | 7,500–7,500 | 3.168 | C | 🔥🔥🔥 [EXCLUSIVE] Instagram Followers [Spam On] [Refill: 65 Days] [Max: 100K/username - 7.5K/order] [Start Time: 0-1 Hour] [Speed: 7.5K/Day] ♻️🔥🔥🔥 |
| 494 | jap:2153 | Default | 5,900–5,900 | 3.168 | C | 🔥🔥🔥 [EXCLUSIVE] Instagram Followers [Spam On] [Refill: 65 Days] [Max: 100K/username - 5.9K/order] [Start Time: 0-1 Hours] [Speed: 5.9K/Day] ♻️🔥🔥🔥 |
| 495 | jap:2212 | Default | 4,400–4,400 | 3.168 | C | 🔥🔥🔥 [EXCLUSIVE] Instagram Followers [Spam On] [Refill: 365 Days] [Max: 100K/username - 4.4K/order] [Start Time: 0-1 Hours] [Speed: 4.4K/Day] ♻️🔥🔥🔥 |
| 496 | jap:2211 | Default | 2,900–2,900 | 3.168 | C | 🔥🔥🔥 [EXCLUSIVE] Instagram Followers [Spam On] [Refill: 65 Days] [Max: 100K/username - 2.9K/order] [Start Time: 0-1 Hour] [Speed: 2.9K/Day] ♻️🔥🔥🔥 |
| 497 | jap:2210 | Default | 1,400–1,400 | 3.168 | C | 🔥🔥🔥 [EXCLUSIVE] Instagram Followers [Spam On] [Refill: 65 Days] [Max: 100K/username - 1.4K/order] [Start Time: 0-1 Hour] [Speed: 1.4K/Day] ♻️🔥🔥🔥 |
| 498 | jap:3028 | Default | 15,000–15,000 | 3.30 | CD | 🔥🔥🔥 [EXCLUSIVE] Instagram Followers [Spam On] [Refill: 365 Days] [Max: 100K/username - 15K/order] [Start Time: 0-1 Hour] [Speed: 5-10K/Day] ♻️🔥🔥🔥 |
| 499 | jap:3027 | Default | 14,000–14,000 | 3.168 | C | 🔥🔥🔥 [EXCLUSIVE] Instagram Followers [Spam On] [Refill: 65 Days] [Max: 100K/username - 14K/order] [Start Time: 0-1 Hour] [Speed: 5-10K/Day] ♻️🔥🔥🔥 |
| 678 | jap:4306 | Default | 1,000–1,000 | 18.75 | — | Instagram Followers [EAST AFRICA] [Refill: No Drop] [Max: 1k] [Start Time: 4 Hours] [Speed: 1K/Day] |
| 679 | jap:4307 | Default | 1,000–1,000 | 18.75 | — | Instagram Followers [WEST AFRICA] [Refill: No Drop] [Max: 1K] [Start Time: 4 Hours] [Speed: 1K/Day] |

### Guarantee and refill discrepancies

| Root ID | Provider ID | Payload type | Payload min–max | Rate | Flags | Original provider name |
| ---: | --- | --- | --- | ---: | --- | --- |
| 342 | jap:10362 | Default | 10–100,000 | 6.00 | CD | Instagram Followers [VERY LOW DROP] [Refill: 30D] [Max: 100K] [Start Time: 0 - 1 Hr] [Speed: Up to 15K/D] 💧 |
| 355 | jap:6594 | Default | 10–100,000 | 1.9375 | CD | Instagram Followers [Refill: 30 Days] [Max: 500K] [Start Time: 0-2 Hrs] [Speed: Up to 50K/D] 💧♻️ |
| 356 | jap:3456 | Default | 10–100,000 | 2.50 | CD | Instagram Followers [Refill: 30D] [Max: 1M] [Start Time: 0 - 1 Hr] [Speed: Up to 50K/D] 💧♻️ |
| 358 | jap:10142 | Default | 10–100,000 | 2.5625 | C | Instagram Followers [HIGH DROP] [Refill: 30D] [Max: 5M] [Start Time: 0 - 2Hrs] [Speed: Up to 500K/D] ♻️💧⛔ |
| 360 | jap:9430 | Default | 10–100,000 | 2.5258 | CD | Instagram Followers [Refill: 30D] [Max: 1M] [Start Time: 0 - 3 Hrs] [Speed: Up to 100K/D] 💧♻️ |
| 361 | jap:10030 | Default | 50–500,000 | 2.625 | D | Instagram Followers [Refill: 30D] [Max: 500K] [Start Time: 0-2 Hrs] [Speed: Up to 100K/D] 💧 |
| 367 | jap:1766 | Default | 10–500,000 | 2.00 | CD | Instagram Followers [HQ] [Max 100K] [Start Time: 0 - 1Hr] [Refill: 30D] [Speed: Up to 40K/D] 💧⛔ |
| 370 | jap:1881 | Default | 20–1,000,000 | 2.6719 | CD | Instagram Followers [Max 1M] [Start Time: 0 - 1Hr] [Refill: 7D] [Speed: Up to 50K/D] 💧♻️ |
| 399 | jap:10083 | Default | 10–56,000 | 1.6763 | D | 🇧🇷 Instagram Followers [Max: 40K] [Refill: 30D] [Start Time: 0 - 1 Hour] [Speed: Up to 10K/Day] ♻️💧⛔ |
| 435 | jap:524 | Default | 10–1,000,000 | 1.875 | CD | Instagram Followers HIGH DROP [Refill: 30D] [Max: 500K] [Start Time: 0-3 Hrs] [Speed: 25K/Day] 💧♻️ |
| 438 | jap:7469 | Default | 20–5,000 | 2.79 | CD | Instagram Followers [Refill: 30 Days] [Max: 5K] [Start Time: 0-1 Hour] [Speed: 10-15K/Day] ♻️ |
| 439 | jap:1808 | Default | 10–500,000 | 1.708 | CD | Instagram Followers [Refill:  30 Days] [Max: 200K] [HIGH DROP] [Start Time: 2 Hours] [Speed: 20K/Day] ♻️ |
| 449 | jap:6837 | Default | 10–200,000 | 4.1875 | CD | Instagram Followers [Max: 100K] [Refill: 365D] [Start Time: 0 - 1 Hr] [Speed: 25K/Day] ♻️💧⛔ |
| 457 | jap:5566 | Default | 100–6,000 | 2.79 | CD | Instagram Followers [Refill: 30 Days] [Max: 6K] [Start Time: 1 Hour] [Speed: 6K/Day] ♻️ |
| 458 | jap:5567 | Default | 100–12,000 | 2.88 | CD | Instagram Followers [Refill: 30 Days] [Max: 12K] [Start Time: 1 Hour] [Speed: 12K/Day] ♻️ |
| 460 | jap:3746 | Default | 100–5,000 | 2.9025 | CD | Instagram Followers [Refill: 30 Days] [Max: 5K] [Start Time: 1 Hour] [Speed: 5K/Day] ♻️ |
| 461 | jap:8443 | Default | 10–85,000 | 1.6223 | D | Instagram Followers [Max: 100K] [Refill: 30 Days] [Start Time: 0 - 1 Hour] [Speed: Up to 10K/Day] ♻️ |
| 467 | jap:3747 | Default | 100–10,000 | 2.88 | C | Instagram Followers [Refill: 30 Days] [Max: 10K] [Start Time: 1 Hour] [Speed: 5K/Day] ♻️ |
| 468 | jap:3748 | Default | 100–15,000 | 2.925 | CD | Instagram Followers [Refill: 30 Days] [Max: 15K] [Start Time: 1 Hour] [Speed: 5K/Day] ♻️ |
| 470 | jap:3750 | Default | 100–30,000 | 2.97 | CD | Instagram Followers [Refill: 30 Days] [Max: 30K] [Start Time: 1 Hour] [Speed: 5K/Day] ♻️ |
| 471 | jap:5632 | Default | 10–10,000,000 | 2.9935 | CD | Instagram Followers [Drops 5-20%] [Auto-Refill: 30 Days] [Max: 10K] [Start Time: 0-1 Hour] [Speed: 5K/Day] ♻️ |
| 473 | jap:3245 | Default | 50–75,000 | 3.75 | C | Instagram Followers [Refill: 30 Days] [Max: 75K] [Start Time: 1 Hour] [Speed: 1K/Day] ♻️🔥 |
| 475 | jap:5633 | Default | 20–20,000 | 3.0965 | CD | Instagram Followers [Drops 5-20%] [Auto-Refill: 30 Days] [Max: 20K] [Start Time: 1 Hour] [Speed: 5K/Day] ♻️ |
| 477 | jap:1719 | Default | 10–100,000 | 3.4622 | D | Instagram Followers [Refill: 30 Days] [Max: 10K] [Start Time: 6 Hours] [Speed: 20K/Day] ♻️🔥 |
| 482 | jap:1868 | Default | 10–12,000 | 5.04 | D | Instagram Followers [3K] [AUTO R15] [1H - INSTANT] 💧⛔♻🔥 |
| 567 | jap:1873 | Default | 10–100,000 | 1.625 | RC | Instagram Followers [Max 100K] [Start Time: 0 - 1Hr] [Refill: No] [Speed: 5K/D] 💧⛔ |
| 1401 | jap:7542 | Default | 10–1,000,000 | 7.50 | RCD | 🇧🇷 Instagram Followers [BRAZIL] [Max: 20K] [Refill: No] [Start Time: 0 - 1 Hour] [Speed: 1K/Day] |
| 1403 | jap:6312 | Default | 10–10,000 | 12.9883 | RCD | 🇧🇷 Instagram Followers [BRAZIL] [60%] [Refill: No] [Max: 20K] [Start Time: 1 Hour] [Speed: 5K/Day] |
| 11656 | jap:10241 | Default | 10–100,000 | 6.875 | C | 🇺🇸 Instagram Followers [USA] [Refill 30 Days ~ Low Drop] [Max: 100K] [Start Time: 0 - 1 Hr] [Speed: 2K/D] ⛔️ |

### Provider workflow or instructions

| Root ID | Provider ID | Payload type | Payload min–max | Rate | Flags | Original provider name |
| ---: | --- | --- | --- | ---: | --- | --- |
| 47 | jap:9132 | Default | 5–1,000,000,000 | 7.50 | RD | 🇺🇸 Instagram Followers [USA] [Algorithm Tricking] [Refill: NON DROP] [Max: 5K] [Start Time: 0 - 1 Hr] [Speed: 5K/D] |
| 422 | jap:1346 | Default | 10–500,000 | 10.00 | RD | Instagram Followers [SPAN ON] [Refill: 365D] [Max: 500K] [Start Time: 0 - 1 Hr] [Speed: 100K/D] 💧♻️ |
| 476 | jap:2193 | Default | 10–10,000,000 | 3.19 | RC | Instagram Followers [SPAN ON] [Refill: 30D] [Max: 100K] [Start Time: 1 Hour] [Speed: 25K/Day] 💧⛔♻️ |
| 542 | jap:10080 | Default | 10–100,000 | 1.1125 | C | Instagram Followers [FLAG OFF] [Refill: No] [Max: 100K] [Start Time: 0-2 Hrs] [Speed: 100K/D] 💧⛔️ |
| 556 | jap:2989 | Default | 10–25,000 | 0.2125 | CD | Instagram PRANK Followers [READ DESCRIPTION] [Refill: No] [Max: 25K] [Start Time: 0-1 Hour] [Speed: 10K/Day] 💧⛔️ |
| 564 | jap:2293 | Default | 10–10,000,000 | 0.488 | CD | Instagram Followers [SPAM ON] [NO REFILL] [ NO REFUND] [Max: 1M] [Start Time: 0-1 Hr] [Speed: 50K/Day] 💧⛔ |
| 575 | jap:8217 | Default | 10–10,000,000 | 0.6875 | C | Instagram PRANK Followers [READ DESCRIPTION] [Refill: No] [Max: 1K] [Start Time: Instant] [Speed: 1K/Day] |
| 576 | jap:8218 | Default | 10–10,000,000 | 0.693 | C | Instagram PRANK Followers [READ DESCRIPTION] [Refill: No] [Max: 5K] [Start Time: Instant] [Speed: 5K/Day] |
| 1324 | jap:6108 | Default | 5–1,000,000,000 | 6.50 | RD | 🇺🇸 Instagram Followers [USA] [Algorithm Tricking] [Refill: NON DROP] [Max: 5K] [Start Time: 0 - 1 Hr] [Speed: 5K/D] |
| 1334 | jap:8298 | Default | 20–3,000 | 7.75 | D | 🇺🇸 Instagram Followers [USA] [Refill: 30 Days] [Private Accounts] [Start Time: 0 - 1 Hour] [Speed: 3K/Day] |
| 1358 | jap:7838 | Default | 20–15,000 | 7.44 | — | 🇪🇺🇺🇸 Instagram Followers [EU/US] [Start Time: 0 - 1 Hour] [Speed: 500/Day][NO REFILL/NO REFUND] |
| 11664 | jap:1834 | Default | 10–1,000,000 | 1.25 | — | Instagram Followers [PRANK FOLLOWERS] [READ DESCRIPTION] [No Refill] [Max: 10K] [Start Time: 0-1 Hour] [Speed: 5K to 10K/Day] |

### Spam Off

| Root ID | Provider ID | Payload type | Payload min–max | Rate | Flags | Original provider name |
| ---: | --- | --- | --- | ---: | --- | --- |
| 386 | jap:9574 | Default | 10–1,000,000 | 2.875 | RCD | Instagram Followers [SPAM OFF] [Max: 1M] [Refill: 30D] [Start Time: 0 - 1 Hr] [Speed: Up to 100K/D] ♻️⛔💧 |
| 391 | jap:9559 | Default | 50–500,000 | 1.5438 | CD | Instagram Followers [SPAM OFF] [Refill: 30D] [Max: 1M] [Start Time: 0-1 Hr] [Speed: 20K/Day] ♻️ 💧 ⛔ |
| 412 | jap:9556 | Default | 10–5,000,000 | 2.85 | RCD | Instagram Followers [SPAM OFF] [Refill: 15D] [Max: 5K] [Start Time: 0-1 Hr] [Speed: Up to 100K/D] 💧⛔♻️ |
| 413 | jap:9557 | Default | 10–1,000,000 | 3.1238 | RCD | Instagram Followers [SPAM OFF] [Refill: 30D] [Max: 1M] [Start Time: 0-1 Hr] [Speed: Up to 100K/D] 💧⛔♻️ |
| 546 | jap:7950 | Default | 10–50,000 | 1.625 | CD | Instagram Followers [Max 20k] [SPAM OFF] [Start Time: 0 - 1Hr] [Refill: No] [Speed: Up to 20K/D] 💧⛔ |
| 551 | jap:9553 | Default | 10–5,000 | 2.1375 | CD | Instagram Followers [SPAM OFF] [Refill: No] [Max: 5K] [Start Time: 0-1 Hr] [Speed: Up to 5K/D] 💧⛔ |
| 574 | jap:9554 | Default | 10–100,000 | 2.375 | CD | Instagram Followers [SPAM OFF] [Refill: No] [Max: 100K] [Start Time: 0-1 Hr] [Speed: Up to 100K/D] 💧⛔ |
| 577 | jap:9555 | Default | 10–1,000,000 | 2.5532 | CD | Instagram Followers [SPAM OFF] [Refill: No] [Max: 1M] [Start Time: 0-1 Hr] [Speed: Up to 100K/D] 💧⛔ |
| 579 | jap:3304 | Default | 10–5,000,000 | 0.9375 | CD | Instagram Followers [SPAM OFF] [Refill: No] [Max: 1M] [Start Time: 0-1 Hour] [Speed: 20K/D] 💧⛔ |
| 580 | jap:1136 | Default | 10–500,000 | 1.425 | CD | Instagram Followers [WORKING - SPAM OFF] [Max: 1M] [Refill: No] [Start Time: 0 - 1 Hr] [Speed: 5K/D] 💧⛔️ |
| 583 | jap:9437 | Default | 10–10,000,000 | 0.935 | C | Instagram Followers [SPAM OFF] [Refill: No] [Max: 1M] [Start Time: 0 - 3 Hrs] [Speed: Up to 200K/D] 💧⛔ |
| 624 | jap:9537 | Default | 10–100,000 | 2.375 | CD | Instagram Followers [Max 1M] [SPAM OFF] [Start Time: 0 - 1Hr] [Refill: No] [Speed: Up to 100K/D] 💧⛔ |

### Spam On

| Root ID | Provider ID | Payload type | Payload min–max | Rate | Flags | Original provider name |
| ---: | --- | --- | --- | ---: | --- | --- |
| 372 | jap:3305 | Default | 10–500,000 | 3.90 | D | Instagram Followers [TOP QUALITY] [SPAM ON] [Refill: 30D] [500K] [Start Time: 0 - 1 Hr] [Speed: 50K/D] ♻️🔥 |
| 375 | jap:1861 | Default | 5–50,000 | 2.1125 | CD | Instagram Followers [Refill: 30D] [Max 5M] [SPAM ON] [Start Time: 0 - 3Hrs] [Speed: Up to 100K/D] 💧⛔♻️ |
| 376 | jap:8839 | Default | 10–10,000,000 | 2.75 | RC | Instagram Followers [SPAM ON] [Refill: 30D] [Max: 7M] [Start Time: 0-1 Hr] [Speed: Up to 50K/D] 💧⛔♻️ |
| 377 | jap:10014 | Default | 10–1,000,000 | 1.875 | CD | Instagram Followers [SPAM ON] [Refill: 30D] [Max: 5M] [Start Time: 0-1 Hr] [Speed: Up to 100K/D] 💧♻️ |
| 378 | jap:8838 | Default | 20–1,000,000 | 4.725 | RC | Instagram Followers [SPAM ON] [Refill: 365D] [Max: 7M] [Start Time: 0-1 Hr] [Speed: Up to 50K/D] 💧⛔♻️ |
| 379 | jap:2290 | Default | 10–20,000 | 2.725 | RCD | Instagram Followers [Refill: 30D] [SPAM ON] [Max: 1M] [Start Time: 0-1 Hr] [Speed: Up to 100K/D] 💧⛔♻️ |
| 380 | jap:9142 | Default | 10–100,000 | 1.56 | RC | Instagram Followers [Refill: 30] [SPAM ON] [Max: 1M] [Start Time: 0-1 Hr] [Speed: Up to 100K/D] 💧⛔♻️ |
| 381 | jap:9571 | Default | 10–10,000,000 | 2.7468 | RC | Instagram Followers [SPAM ON] [Refill: 30D] [Max: 5M] [Start Time: 0-1 Hr] [Speed: Up to 100K/D] 💧⛔♻️ |
| 382 | jap:1804 | Default | 10–10,000,000 | 2.75 | RC | Instagram Followers [SPAM ON] [Refill: 30D] [Max: 5M] [Start Time: 0-1 Hr] [Speed: Up to 200K/D] 💧⛔♻️ |
| 383 | jap:2181 | Default | 20–1,000,000 | 4.55 | RC | Instagram Followers [Refill: 365D] [Max 1M] [SPAM ON] [Start Time: 0 - 1Hr] [Speed: Up to 100K/D] 💧⛔♻️ |
| 384 | jap:9412 | Default | 10–1,000,000 | 2.4375 | RC | Instagram Followers [SPAM ON] [Refill:30D] [Max: 200K] [Start Time: 0-1 Hr] [Speed: Up to 100K/D] 💧⛔♻️ |
| 385 | jap:6560 | Default | 10–1,000,000 | 3.08 | RCD | Instagram Followers [SPAM ON] [Max: 500K] [Refill: 30D] [Start Time: 0 - 1 Hr] [Speed: Up to 25K/D]💧♻️⛔️ |
| 387 | jap:5662 | Default | 50–1,000,000,000 | 4.00 | RC | Instagram Followers [SPAM ON] [Refill: 30D] [Max: 100K] [Start Time: 0-1 Hr] [Speed: Up to 5K/D] 💧⛔♻️ |
| 388 | jap:9570 | Default | 10–30,000,000 | 2.7686 | RC | Instagram Followers [SPAM ON] [Refill: 30D] [Max: 1M] [Start Time: 0-1 Hr] [Speed: Up to 100K/D] 💧♻️ |
| 389 | jap:9573 | Default | 20–1,000,000 | 4.375 | RC | Instagram Followers [SPAM ON] [Refill: 365D] [Max: 1M] [Start Time: 0-1 Hr] [Speed: Up to 100K/D] 💧♻️ |
| 390 | jap:1995 | Default | 50–1,000,000,000 | 4.00 | RCD | Instagram Followers [SPAM ON] [Refill: Auto -30D] [Max: 100K] [Start Time: 0 - 24 Hrs] [Speed: 10K/D] ♻️💧⛔ |
| 392 | jap:9558 | Default | 10–1,000,000 | 1.6625 | CD | Instagram Followers [SPAM ON] [Refill: 30D] [Max: 1M] [Start Time: 0-1 Hr] [Speed: 30K/Day] ♻️ 💧 ⛔ |
| 393 | jap:7592 | Default | 10–20,000 | 2.7032 | RC | Instagram Followers [SPAM ON] [Refill: 30D] [Max: 1M] [Start Time: 0 - 2 Hrs] [Speed: Up to 25K/D] ♻️💧⛔ |
| 394 | jap:5989 | Default | 10–50,000 | 2.4875 | CD | Instagram Followers [SPAM ON] [Auto Refill: 30 Days] [Max: 50K] [Start Time: 4 Hours] [Speed: 30K/Day] 💧♻️⛔️ |
| 395 | jap:9408 | Default | 10–1,000,000 | 3.375 | RCD | Instagram Followers [SPAM ON] [Max: 1M] [Refill: 30D] [Start Time: 0 - 1 Hr] [Speed: 20K/D] ♻️💧⛔ |
| 396 | jap:2182 | Default | 10–1,000,000 | 1.5438 | CD | Instagram Followers [Refill: 30D] [SPAM ON] [Max: 1M] [Start Time: 0-1 Hr] [Speed: Up to 20K/D] 💧⛔ |
| 397 | jap:1812 | Default | 10–1,000,000 | 1.6038 | CD | Instagram Followers [SPAM ON] [Max: 1M] [Refill: 30D] [Start Time: 0 - 1 Hr] [Speed: 10K/D] ♻️💧⛔ |
| 398 | jap:3438 | Default | 10–100,000 | 3.649 | RCD | Instagram Followers [SPAM ON] [Max: 250K] [Refill: 30D] [Start Time: 0 - 1 Hr] [Speed: 50K/D] ♻️💧⛔ |
| 400 | jap:9431 | Default | 10–100,000 | 1.65 | CD | Instagram Followers [SPAM ON] [Refill: 60D] [Max: 1M] [Start Time: 0 - 3 Hrs] [Speed: Up to 100K/D] 💧⛔ ♻️ |
| 408 | jap:579 | Default | 10–10,000,000 | 2.8125 | CD | Instagram Followers [SPAM ON] [Max: 1M] [Refill: 30D] [Start Time: 0 - 1 Hour] [Speed: 25K/Day] ♻️💧⛔ |
| 409 | jap:1862 | Default | 20–200,000 | 4.6075 | CD | Instagram Followers [Max 200K] [SPAM ON] [Start Time: 0 - 1Hr] [Refill: 365D] [Speed: Up to 75K/D] ♻️💧⛔ |
| 410 | jap:1969 | Default | 10–20,000 | 2.725 | RC | Instagram Followers [Max 500K] [SPAM ON] [Start Time: 0 - 1Hr] [Refill: 30D] [Speed: Up to 5K/D] ♻️💧⛔ |
| 411 | jap:1977 | Default | 10–100,000 | 2.5625 | C | Instagram Followers [SPAM ON] [Refill:  30D] [Max: 500K] [Start Time: 0 - 3Hrs] [Speed: Up to 50K/D] ♻️💧⛔ |
| 414 | jap:525 | Default | 10–1,000,000 | 3.00 | RCD | Instagram Followers [SPAM ON] [Max: 1M] [Refill: 30D] [Start Time: 0 - 1 Hour] [Speed: 50K/Day] ♻️💧⛔ |
| 415 | jap:1259 | Default | 10–1,000,000 | 4.75 | RCD | Instagram Followers [SPAM ON] [Max: 1M] [Refill: 365D] [Start Time: 0 - 1 Hour] [Speed: 50K/Day] ♻️💧⛔ |
| 416 | jap:28 | Default | 10–10,000,000 | 4.3125 | RCD | Instagram Followers [SPAM ON] [Max: 1M] [Refill: 90D] [Start Time: 0 - 1 Hour] [Speed: Up to 50K/Day] ♻️💧⛔ |
| 417 | jap:4278 | Default | 10–10,000,000 | 4.3125 | RCD | Instagram Followers [SPAM ON] [Max: 1M] [Refill: 365D] [Start Time: 0 - 1 Hour] [Speed: 25K/Day] ♻️💧⛔ |
| 418 | jap:3256 | Default | 10–500,000 | 9.508 | RD | Instagram Followers [SPAM ON] [Refill: 30D] [Max: 500K] [Start Time: 0 - 1 Hr] [Speed: 50K/D] 💧♻️ |
| 419 | jap:2966 | Default | 20–300,000 | 3.125 | RCD | Instagram Followers [Max 300K] [SPAM ON] [Start Time: 0 - 1Hr] [Refill: 30D] [Speed: Up to 300K/D] ♻️💧⛔ |
| 420 | jap:3865 | Default | 20–10,000,000 | 4.6313 | CD | Instagram Followers [Max 500K] [SPAM ON] [Start Time: 0 - 1Hr] [Refill: 365D] [Speed: Up to 500K/D] ♻️💧⛔ |
| 421 | jap:2289 | Default | 10–500,000 | 6.25 | RD | Instagram Followers [SPAM ON] [Refill: 30D] [Max: 100K] [Start Time: 0 - 1 Hr] [Speed: 100K/D] 💧♻️ |
| 423 | jap:1814 | Default | 10–10,000,000 | 4.375 | RCD | Instagram Followers [SPAM ON] [Refill: 30D] [Max: 200K] [Start Time: 0-1 Hour] [Speed: 50K/Day] 💧⛔♻️🔥 |
| 424 | jap:1717 | Default | 10–10,000,000 | 4.875 | RCD | Instagram Followers [SPAM ON] [Refill: 365D] [Max: 1M] [Start Time: 0-1 Hour] [Speed: 100K/Day] 💧⛔♻️🔥 |
| 425 | jap:9141 | Default | 10–20,000 | 3.597 | RC | Instagram Followers [SPAM ON] [Refill: 30D] [OLD Accs 15+ Posts] [Max: 5M] [Start Time: 0-1 Hr] [Speed: Up to 200K/D] 💧⛔♻️ |
| 426 | jap:471 | Default | 20–25,000 | 2.25 | RCD | Instagram Followers [SPAM ON] [Max: 25K] [Refill: 15D] [Start Time: 0 - 1 Hr] [Speed: 20K/Day] ♻️💧 |
| 427 | jap:685 | Default | 10–1,000,000,000 | 5.875 | D | Instagram Followers [SPAM ON] [Refill: 30D] [Max: 100K] [Start Time: 0 - 24Hrs] [Speed: 5K/D] ♻️💧⛔ |
| 429 | jap:1994 | Default | 5–50,000 | 2.1125 | CD | Instagram Followers [SPAM ON] [Auto Refill: 30D] [Max: 50K] [Start Time: 0 - 2 Hrs] [Speed: 5K/D] 💧♻️⛔️ |
| 430 | jap:3374 | Default | 1–1,000,000 | 2.3389 | CD | Instagram Followers [SPAM ON] [Max: 100K] [Refill: 60D] [Start Time: 0 - 1 Hour] [Speed: 20K/Day] ♻️💧⛔ |
| 431 | jap:1064 | Default | 20–40,000 | 2.6875 | RCD | Instagram Followers [SPAM ON] [Max: 25K] [Refill: 30D] [Start Time: 0 - 1 Hr] [Speed: 20K/Day] ♻️💧 |
| 436 | jap:7109 | Default | 10–10,000,000 | 2.75 | RC | Instagram Followers [SPAM ON] [Max: 250K] [Refill: 60 Days] [Start Time: 0-1 Hour] [Speed 15K/Day] ♻️ |
| 447 | jap:6713 | Default | 10–1,000,000 | 2.86 | RCD | Instagram Followers [SPAM ON] [Max: 1M] [Refill: 30D] [Start Time: 0 - 1 Hr] [Speed: Up to 50K/D]💧♻️⛔️ |
| 474 | jap:1718 | Default | 10–100,000,000 | 2.8125 | CD | Instagram Followers [SPAM ON] [Refill: 30D] [Max: 100K] [Start Time: 1 Hour] [Speed: 15K/Day]  💧⛔♻️ |
| 547 | jap:10015 | Default | 10–50,000 | 1.1475 | CD | Instagram Followers [SPAM ON] [Refill: No] [Max: 5M] [Start Time: 0-1 Hr] [Speed: Up to 100K/D] 💧 |
| 548 | jap:7591 | Default | 10–100,000 | 0.675 | C | Instagram Followers [Max 10M] [SPAM ON] [Start Time: 0 - 1Hr] [Refill: No] [Speed: Up to 500K/D] 💧⛔ |
| 549 | jap:5897 | Default | 10–10,000,000 | 1.125 | C | Instagram Followers [Max 1M] [SPAM ON] [Start Time: 0 - 1Hr] [Refill: No] [Speed: Up to 100K/D] 💧⛔ |
| 552 | jap:10029 | Default | 10–10,000,000 | 1.125 | C | Instagram Followers [SPAM ON] [Refill: No] [Max: 10M] [Start Time: 0-2 Hrs] [Speed: Up to 500K/D] 💧⛔ |
| 553 | jap:1809 | Default | 10–5,000,000 | 0.88 | C | Instagram Followers [Max 1M] [SPAM ON] [Start Time: 0 - 1Hr] [Refill: No] [Speed: Up to 50K/D] 💧⛔ |
| 573 | jap:9563 | Default | 10–200,000 | 1.95 | CD | Instagram Followers [Max 1M] [SPAM ON] [Start Time: 0 - 1Hr] [Refill: No] [Speed: Up to 50K/D] 💧⛔ |
| 584 | jap:9536 | Default | 10–100,000 | 2.375 | C | Instagram Followers [Max 1M] [SPAM ON] [Start Time: 0 - 1Hr] [Refill: No] [Speed: Up to 100K/D] 💧⛔ |
| 587 | jap:102 | Default | 10–10,000 | 1.875 | CD | Instagram Followers [WORKING - SPAM ON] [Refill: No] [Max: 10K] [Start Time: 0 - 1Hr] [Speed: 3K/D] 💧⛔️ |
| 605 | jap:5903 | Default | 10–500,000 | 0.6875 | CD | Instagram Followers [SPAM ON] [Refill: No] [Max: 1M] [Start Time: 0-1 Hour] [Speed: 20K/D] 💧⛔ |
| 611 | jap:719 | Default | 10–1,000,000 | 2.5625 | CD | Instagram Followers [Max 1M] [WORKING - SPAM ON] [Start Time: 0 - 1 Hrs] [Refill: No] [Speed: Up to 70K/D] 💧⛔ |
| 617 | jap:9569 | Default | 10–10,000,000 | 0.6875 | C | Instagram Followers [Max 1M] [SPAM ON] [Start Time: 0 - 1Hr] [Refill: No] [Speed: Up to 50K/D] 💧⛔ |
| 622 | jap:969 | Default | 10–1,000,000 | 3.1875 | CD | Instagram Followers [WORKING - SPAM ON] [Max: 1M] [Refill: No] [Start Time: 0 - 1 Hr] [Speed: 50K/D] 💧⛔️ |
| 623 | jap:9429 | Default | 10–10,000,000 | 0.715 | C | Instagram Followers [SPAM ON] [Refill: No] [Max: 1M] [Start Time: 0 - 3 Hrs] [Speed: Up to 100K/D] 💧⛔ |

### Spam On waiting / Spam Off success

| Root ID | Provider ID | Payload type | Payload min–max | Rate | Flags | Original provider name |
| ---: | --- | --- | --- | ---: | --- | --- |
| 428 | jap:7872 | Default | 20–500,000 | 4.3125 | RCD | Instagram Followers  [SPAM ON : WAITING / SPAM OFF SUCCESS] [AI] [Refill: 15D] [Max: 500K] [Start Time: 0-1 Hr] [Speed: 50K/D] 💧⛔♻️🔥 |
| 432 | jap:46 | Default | 100–150,000 | 2.418 | RCD | Instagram Followers [SPAM ON : WAITING / SPAM OF SUCCESS] [AI] [Refill: 15 Days] [Max: 100K] [Start Time: 0 - 1 Hour] [Speed: 20K/Day] 💧♻️ |
| 433 | jap:7849 | Default | 10–200,000 | 3.0625 | RCD | Instagram Followers [SPAM ON : WAITING / SPAM OF SUCCESS] [AI] [Refill: 30D] [Max: 350K] [Start Time: 0 - 1 Hour] [Speed: 50K/D] 💧⛔♻️ |
| 434 | jap:2291 | Default | 10–200,000 | 3.6024 | RCD | Instagram Followers [SPAM ON : WAITING / SPAM OF SUCCESS] [AI] [Refill: 30 Days] [Max: 300K] [Start Time: 0 - 1 Hour] [Speed: 50K/Day] 💧⛔♻️ |
| 440 | jap:7470 | Default | 10–100,000 | 3.375 | RCD | Instagram Followers [Refill: 30 Days] [SPAM ON : WAITING / SPAM OFF SUCCESS] [AI] [Max: 100K] [Start Time: 0-1 Hour] [Speed: 10-15K/Day] 💧♻️⛔️ |
| 578 | jap:7871 | Default | 10–5,000 | 2.35 | CD | Instagram Followers [SPAM ON : WAITING / SPAM OF SUCCESS] [AI] [Refill: No] [Max: 5K] [Start Time: 0-1 Hr] [Speed: 5K/D] 💧🔥 |
| 582 | jap:2937 | Default | 10–120,000 | 3.75 | CD | Instagram Followers [ [SPAM ON : WAITING / SPAM OF SUCCESS] [AI] [Refill: No] [Max: 80K] [Start Time: 0-1 Hr] [Speed: 50K/D] 💧🔥 |
| 591 | jap:3372 | Default | 10–500,100 | 3.77 | CD | Instagram Followers [SPAM ON : WAITING / SPAM OF SUCCESS] [AI] [Refill: No] [Max: 50K] [Start Time: 1 Hour] [Speed: 10K/Day] 💧 |
| 670 | jap:7840 | Default | 10–5,000 | 3.5438 | CD | 🇮🇳 Instagram Followers [SPAM ON : WAITING / SPAM OF SUCCESS] [AI] [Start Time: 0 - 1 Hour] [Speed: 5K/Day] |

### Verified package with unspecified count

| Root ID | Provider ID | Payload type | Payload min–max | Rate | Flags | Original provider name |
| ---: | --- | --- | --- | ---: | --- | --- |
| 1453 | jap:6677 | Package | 1–1 | 13.20 | — | 🇹🇷 Instagram VERIFIED Followers [From Youtuber:  @mehmetuygaraksuu] |


## Locked rows and omitted candidates

| Root row ID | Provider ID | Disposition |
| ---: | --- | --- |
| 373 | jap:964 | Absent from current export. The last lab check showed Locked with `provider_catalog_missing`. Exclude. |
| 500 | jap:10364 | Absent from current export. The last lab check showed Locked with `provider_catalog_missing`. Exclude. |
| 616 | jap:3481 | Absent from current export. The last lab check showed Locked with `provider_catalog_missing`. Exclude. |
| 1380 | jap:10371 | Absent from current export. The last lab check showed Locked with `provider_catalog_missing`. Exclude. |

The historical snapshot resolves the four external IDs for reconciliation. Their locked state comes from the last live lab inspection. The present source search also found the following related rows outside the mapped lab scope. [Historical registry](../../examples/registry-snapshots/handler-services-before-2026-11-16-import.json)

| Current row IDs | Evidence and proposed placement |
| --- | --- |
| 11689 | Clear additional standalone Instagram Followers candidate. Enabled, unlocked, `jap:4407`, `Default`, 100–50,000 at raw rate 3.168, refill and cancellation enabled. Propose **Guaranteed → Drop & Retention → Low Drop · 30-day refill · 2–5K/day** after confirming lab membership or approving an addition. Keep it outside the 470 baseline until then. |
| 2837 | Name says Instagram Followers. Category says TikTok Followers. Clarify intended platform and connection before proposing a binding. |
| 640 | In the Instagram Targeted category, with a TikTok Followers name. Preserve the conflicting evidence. |
| 27–29 | Threads Followers variants in the Instagram Threads category. Separate service-family review under Instagram → Followers. |
| 112–115 | NFT-account Followers in the Instagram NFT category. Separate qualifier and package review. |
| 22–24, 55, 116–126 | Growth or engagement packages that include or mention followers. Their outcomes warrant their own package scope. |

## Verification and approval

Verified the 470 available mapped IDs have a single disposition, the 21 fallback-only IDs all pass the modeled local type, full bounds, capability and rate checks, and the 148 Others rows each have their own proposed option. Core product definitions, the catalog, the local seed, and the live lab were outside the write scope of this analysis. Builder validation has not been run on this coverage proposal. Before implementing, confirm the live policy and the fixed-quantity field behavior, and review the provider wording associated with the selectable Others routes. ProductDefinition JSON changes require explicit approval of this proposal.
