# Instagram Likes — revised analysis (unapproved)

Updated 2026-11-15 with the expanded fallback-pool and tag-viewpoint analysis requested after the mapping review.

Reanalyzed 2026-11-14 after the mapping update and expanded 2026-11-15 to compare the example tags and map fallback candidate pools. The initial review is preserved as `analysis-2026-11-14-initial.md`. Scope: `instagram-likes-likes`. No ProductDefinition or catalog progress change.

## Source and mapping reconciliation

The current root `handler services.json` contains 5,734 records, but no top-level site/project identifier or export timestamp. Relevant rows use provider key `jap` and were last seen 2026-11-13 UTC. The intended site's identity remains unverified. The current `catalog-handler-service-ids.json` maps 210 unique root row IDs to Instagram Likes: **203 resolve; seven are stale** (`310–313`, `315–317`). All 203 resolved rows are enabled and unlocked with `payload.type: Default`. The mapping update added live IDs `46, 139, 167, 170, 177, 190, 270, 1262, 1323`. No mapped ID occurs in another catalog key.

| Raw source category | Current rows | Mapped | Omitted |
| --- | ---: | ---: | ---: |
| Instagram Likes | 98 | 96 | 2 |
| Instagram Likes [BOTS] | 50 | 49 | 1 |
| Instagram Likes [Targeted] | 45 | 43 | 2 |
| Instagram Likes Per Minute | 12 | 12 | 0 |
| Instagram TOP Services [EXCLUSIVE] | 1 relevant row | 1 | 0 |
| Instagram Western Europe + USA Services 🇪🇺 🇬🇧 🇺🇸 | 1 relevant row | 1 | 0 |
| Instagram Auto Likes | 84 | 1 | 83 |

Five current rows in the four direct Likes categories remain omitted: `182` and `267` (Likes + Reach + Impressions bundles), `11622` (plain Likes), `11665` and `11666` (Arab-targeted Likes). Other adjacent categories were searched: five Likes-named rows `1181–1184, 1186` sit in a mixed Followers/Likes bot category; five latest-post Power Likes rows `337–341` map to Instagram Packages; Threads Likes rows `25–26` map to the separate Threads Likes catalog service. The other 83 Auto Likes rows are outside this map. These are not silently added to the direct Likes cohort.

`catalog.json` still marks Instagram Likes `not_started` with no ProductDefinition file. The registry distinguishes root row `id`, `dgp_handler_id` (1 on all 203 mapped live rows), and provider `external_id`. The intended Builder's service-ID transformation is unverified; binding all variants to `1` would be wrong. The report uses `.ai/README.md`, `WORKFLOW.md`, `DATA-MODEL.md`, `VALIDATION.md`, `agent-search.json`, the 2026-11-13 Builder capability snapshot, local `@elqora/dgp-spec` 1.6.0 declarations, and SDK handler-state semantics. `examples/instagram-likes/` supplied method only, no current facts.

## 2. Analyze and normalize variants

### Service family boundary

Proposed core family: Likes on one specified Instagram content target. The registry does not define accepted URL formats or content types, so the target wording is provisional. Account type, geography, audience, advertised quality, refill/retention, and delivery timing can be variants when a specific row supports them. Additional delivered outcomes (Impressions or Reach) require an explicit bundle choice or a separate service. Auto Likes and latest-post packages suggest different target/order models from their category or name and need separate review. Threads Likes is already a separate catalog service. None is a plain-Likes fallback by default.

The proposed navigation is **outcome → target/account variant → delivery/refill detail**. Avoid a flat provider-row list or a generic “Other” option. Only customer choices with exact handler evidence should be authored.

### Distinct viewpoints

| Dimension | Current source evidence | Normalization rule |
| --- | --- | --- |
| Delivered outcome | Of 203 mapped live rows, 186 names describe Likes alone, 11 Likes + Impressions, and six Likes + Impressions + Reach. The 186 includes Auto Likes row 1262. | Keep the three outcomes distinct. The names do not specify the amount of additional Impressions/Reach. |
| Account type/quality | 49 mapped rows are in `[BOTS]`; other names say HQ/MQ/LQ, real-looking, profile picture/posts, RAU/RAL, exclusive, or natural increase. | Bot status is an explicit category claim. General rows have no proven non-bot guarantee. Marketing quality words are not a verified tier system. |
| Region/audience | 43 mapped `[Targeted]` rows, plus USA Likes rows 46 and 1323 and general row 217; row 166 says 80% female. Claims include country, region, gender, and mixed targets. | Preserve exact target. USA, Arab, Gulf, KSA, UAE, India, and mixed combinations are not interchangeable. Gender and other demographic qualifiers add constraints. |
| Refill/retention | Names mention no refill, periods from 7 to 365 days, lifetime, auto-refill, non-drop, and drop estimates. Operational `refill.enabled` is a separate flag. | Do not turn a named duration or retention phrase into a guarantee. Row 139 says 30D Auto but refill flag is false; row 270 says Auto-Refill 7 Days and flag is true. |
| Delivery | Instant/fast/emergency and daily/hourly speeds appear in names. Rows 325–336 offer fixed 1/5/10/25/50/60 Likes per minute; all have `dripfeed.enabled: false`. | Fixed provider rate is not the optional drip-feed capability. Keep precise speed tied to its row. |
| Limits/rate/capabilities | Each row has payload min/max, rate, and refill/cancel/dripfeed/contract flags, listed below. | Validate against the selected row. Provider rate is not a final customer price. No mapped row is disabled or locked. |

**Operational quantity rule:** use the structured `payload.min` and `payload.max` as the handler's order bounds. Do not substitute a number from the service name. Preserve the name verbatim in source analysis so the discrepancy remains auditable, but do not repeat its conflicting bound in customer-facing copy or use it to shrink the payload range. Examples: row 127's name says max 1M while payload max is 10M; row 279's name says max 50K while payload max is 300; omitted row 11622's name says max 2K while payload max is 10M. If the owner/provider later confirms that a name's smaller figure means an additional per-order restriction, record that separately as new evidence. Refill is different: the payload capability flag says whether the handler supports refill; a name's duration/guarantee is not established by that boolean. Row 166 says lifetime refill while `refill.enabled` is false, so exclude it from refill-eligible choices.

### Normalized cohorts with exact mapped IDs

These are **review cohorts**, not final Select options or approved primary/fallback bindings. Each resolved mapped row occurs in exactly one cohort. A narrower customer option must retain its exact handler identity, target, outcome, and bounds. The appendix retains every original name and operational field.

| Cohort | Named outcome | Mapped root row IDs |
| --- | --- | --- |
| General Likes (89) | Likes only | 127, 128, 129, 130, 131, 132, 133, 134, 135, 136, 137, 138, 139, 140, 141, 142, 143, 144, 145, 146, 147, 148, 149, 150, 151, 152, 153, 154, 155, 156, 157, 158, 159, 160, 162, 163, 164, 165, 166, 167, 168, 169, 170, 171, 172, 175, 176, 177, 178, 179, 183, 184, 185, 186, 187, 188, 189, 190, 191, 192, 194, 195, 196, 197, 198, 199, 200, 201, 202, 203, 204, 205, 206, 207, 208, 209, 210, 212, 213, 214, 215, 216, 217, 218, 219, 220, 221, 222, 223 |
| General Likes (3) | Likes + Impressions | 174, 181, 193 |
| General Likes (4) | Likes + Impressions + Reach | 161, 173, 180, 211 |
| Bot/account type (48) | Likes only | 224, 225, 226, 227, 228, 229, 230, 231, 232, 233, 234, 235, 236, 237, 238, 239, 240, 241, 242, 243, 244, 245, 246, 247, 248, 249, 250, 251, 252, 253, 254, 255, 256, 257, 258, 259, 260, 261, 262, 263, 265, 266, 268, 269, 270, 271, 272, 273 |
| Bot/account type (1) | Likes + Impressions | 264 |
| Targeted (40) | Likes only | 274, 275, 276, 277, 279, 280, 281, 282, 283, 284, 285, 286, 287, 288, 289, 290, 291, 292, 294, 295, 296, 297, 298, 299, 300, 302, 303, 304, 306, 307, 308, 309, 314, 318, 319, 320, 321, 322, 323, 324 |
| Targeted (1) | Likes + Impressions | 293 |
| Targeted (2) | Likes + Impressions + Reach | 278, 305 |
| USA special category (2) | Likes only | 46, 1323 |
| Controlled rate (6) | Likes only | 325, 326, 327, 328, 329, 330 |
| Controlled rate (6) | Likes + Impressions | 331, 332, 333, 334, 335, 336 |
| Auto Likes — boundary review (1) | Likes only | 1262 |

### Region/audience claims within the targeted cohorts

The following is a lookup of the 43 mapped `[Targeted]` rows plus USA-named rows `46`, `217`, and `1323`. These labels are **not** interchangeable fulfillment promises. Some rows in this table are bundles; cross-check the outcome cohort above before creating an option. Source names remain in the appendix.

| Named target claim | Mapped root row IDs |
| --- | --- |
| USA (including two special-category rows and one general row) | 46, 217, 274, 275, 304, 318, 319, 1323 |
| Brazil | 276, 277 |
| Korea | 278, 289, 290, 291, 305, 308 |
| Arab, unspecified | 279, 284, 303 |
| Egypt | 280 |
| Saudi Arabia / KSA | 281 |
| Arab + India + Turkey mix | 282 |
| UAE / Arab | 283 |
| India | 285, 286, 299, 300, 302 |
| Iran | 287, 309 |
| Arab + Iran mix | 288 |
| India women | 292 |
| Russian | 293 |
| Arab / Gulf | 294, 296, 323, 324 |
| UK | 295 |
| Spain | 297 |
| Taiwan | 298 |
| Hong Kong | 306 |
| Ukraine | 307 |
| Nigeria | 314 |
| China | 320 |
| Japan | 321 |
| African | 322 |

Row `166` has an “80% FEMALE” audience claim without a named region. Rows `318–319` combine USA, Afro-American, and male/female claims; row `292` combines India and women. Those qualifiers must stay attached to the specific row.

The special-category USA rows `46` and `1323` describe USA Likes, so their raw merchandising/regional category is retained but they are reviewed with other targeted choices. `1262` is the only newly mapped Auto Likes row; it has registry `type: Default`, while 83 other Auto Likes rows have `type: Subscriptions`. That difference does **not** establish that 1262 is safe to merge into single-target Likes. Its target/order behavior is unresolved. General-category row `217` also has USA wording; row `166` has a female-audience claim. Thus raw category alone cannot finalize a customer choice.

### Candidate customer-choice language and handler rules

| Candidate choice | Eligible cohort/pool | Required distinction before binding |
| --- | --- | --- |
| General Likes | General Likes, Likes only | Decide which exact row promises only the intended Likes outcome; general category alone does not prove non-bot accounts, quality, refill, or speed. |
| Bot Likes | Bot/account type, Likes only | Keep explicit bot label; split further only for evidenced profile/quality/refill claims. |
| Targeted Likes | Targeted or USA special-category Likes-only rows, plus specifically named general-category rows such as 217 | Make region and any gender/ethnic qualifier exact. Do not merge broad Arab with KSA/UAE or combined regions. |
| Controlled-rate Likes | Controlled-rate, Likes only, IDs 325–330 | Rate options are exactly 1/5/10/25/50/60 Likes per minute; not a drip-feed toggle. |
| Likes + Impressions | Only named bundle cohorts | Do not substitute plain Likes. Any targeted or rate-specific promise still needs an exact row. |
| Likes + Impressions + Reach | Only named three-outcome bundle cohorts | Do not substitute either two-outcome or plain Likes. No quantity claim for secondary outcomes is evidenced. |

These choices are a proposed vocabulary, **not a commitment to expose all of them**. No primary or fallback is selected. A fallback would need the same delivered outcomes, target, account claim, refill/capability promise, input shape, and sufficient min/max range. Rates, quality adjectives, and names alone do not establish substitutability. The seven stale IDs cannot be used.

### Cross-cutting tag viewpoints and fallback pools

The example’s tags are useful **viewpoints**, not automatically mutually exclusive service families. A current handler can belong to several at once: target + bot + refill claim + delivery + outcome. The revised grouping therefore separates the customer promise from its qualification tags, so a fallback is chosen from the same promise intersection. Do not put a row into `Other` simply because its wording is unusual; keep a named unresolved subgroup until its meaning is known.

| Example-style viewpoint | Current registry evidence / candidate rows | Fallback compatibility rule |
| --- | --- | --- |
| Standard Likes | General Likes-only pool in the cohort table; not all rows are truly “standard” because many have refill, retention, quality, or speed claims. | Pool only rows that satisfy the chosen baseline promise. Do not silently include bot, geography-targeted, controlled-rate, or bundled rows. |
| Quality | Names with HQ/MQ/LQ/quality/real wording: 136, 140, 141, 142, 148, 150, 167, 169, 179, 181, 197, 218, 220, 221, 230, 231, 237, 238, 239, 256, 258, 262, 265, 266, 272, 273, 278, 290, 291, 294. | Keep only rows supporting the same explicit tier claim. These labels are inconsistent and unverified; no standardized tier promises yet. |
| Bot Likes | 49 mapped rows in raw `[BOTS]` category; 48 Likes-only and row 264 with Impressions. | Exact account-type and outcome must match. Row 264 cannot back up plain bot Likes. |
| Targeted / gender targeted | Mapped region/audience IDs are broken out in the target lookup above; row 166 also says 80% female. | Exact geography and demographic constraint must match; do not use broad or mixed-region rows for a narrower claim. |
| Refill eligible | Operational `refill.enabled=true`: 149, 151, 161, 165, 167, 169, 170, 171, 177, 188, 190, 201, 248, 259, 266, 268, 270, 296, 323, 324. | Use the capability flag to determine whether refill is supported. Treat advertised duration/guarantee as a separate claim; require matching duration evidence before making it a customer choice or fallback constraint. |
| Retention | Explicit non-drop/low-drop/drop-range wording: 140, 157, 163, 186, 187, 196, 203, 204, 205, 214, 223, 270, 293, 318, 319. | Preserve the exact claim and distinguish it from refill. The registry does not validate the claim. |
| Priority delivery | Names contain instant/fast/emergency: 152, 163, 164, 165, 166, 167, 171, 173, 174, 178, 180, 181, 195, 205, 206, 208, 209, 213, 216, 219, 221, 240, 249, 258, 259, 262, 266, 273, 285, 286, 292, 299, 300, 320. | Only use where start/speed promise is compatible and credible. Name-based marketing wording does not establish an SLA. |
| Controlled speed | IDs 325–336: six Likes-only rates and six rates with Impressions. | Match exact rate and delivered outcome; never mix these with ordinary drip-feed capability. |
| Combined engagement | Bundle IDs listed in the outcome cohort (11 with Impressions; six with Impressions + Reach). | Same package contents required. No bundle is fallback for plain Likes or a different bundle. |

**Resilience approach:** the user's planning assumption that a large share of handlers may fail is a capacity scenario, not a fact established by `is_enabled` or the registry snapshot. Keep multiple **candidate** fallbacks for each customer promise where evidence supports them; do not narrow each tag to one ID too early. At definition time, build an ordered pool only after checking each row against the same outcome, target/account claims, required capabilities, link/input shape, and the customer's quantity bounds. Min/max compatibility must cover the order being placed. The current registry provides no health, success-rate, uptime, or provider reliability measure, so it cannot justify a primary ranking or guarantee a given failure percentage. A “large pool” of incompatible rows is not resilience.

## Builder field plan and constraints

The 2026-11-13 Builder snapshot registers `text/default` as scalar with no option/multi support, `number/default` as scalar with no option/multi support, and `select/default` as a single-choice control with `optionCapability.supported: true` and `multiCapability.supported: false`. A single Select is a plausible variant picker. `radio/default` is also supported for single choice. `multiselect/default` and `treeselect/default` support multiple values, but a multi-handler choice is not proposed for one order. `checkbox/default` is scalar despite exposing an `options` UI property; `checkbox/options` is a separate multiple-value variant. The snapshot permits `toggle/default` as scalar, but a drip-feed toggle should appear only when the selected handler has `dripfeed.enabled` and actual ordering behavior is confirmed.

Provisional required inputs are one Instagram content URL (`text/default`) and quantity (`number/default`, integer step 1), plus one variant choice. Exact accepted URL/content type and link validation are not supplied by the handler rows. The saved Quantity template is an editor artifact: its 10–10,000,000 bounds, tags, pricing role, and metadata must not be copied uncritically. Across mapped live rows, payload minimums range 1–250 and maximums range 300–10,000,000. Rates range 0.075–39.5 in registry units, not final customer prices. Enabled capability counts are refill 20, cancel 115, dripfeed 128, contract 0. Optional refill/cancel controls are not inferred from flags alone. Builder version is unspecified; recheck open Builder if it may have changed since the snapshot.

The local `@elqora/dgp-spec` 1.6.0 contract defines schema version 1 ProductDefinition fields, options with `service_id`, quantity rules, visibility expressions, and node/global fallback lists. Exact root/filter/tag binding, site-specific service identity, capability visibility, and hidden-field submission must be checked in the target Builder and ordering runtime before authoring JSON. No publication policy change is proposed.

## Conflicts, assumptions, and decisions for owner

1. Confirm the target site/project for this bare registry export and the actual Builder service identity corresponding to root `id` / `dgp_handler_id` / `external_id`.
2. Decide whether the newly mapped Auto Likes row `1262` belongs in this single-target service. Its `Default` type makes the boundary ambiguous; its source category is Auto Likes.
3. Decide whether Likes + Impressions and Likes + Impressions + Reach are explicit choices here or separate ProductDefinitions. Keep their handler coverage distinct either way.
4. Decide the initial customer-facing choice set: general, bot, targeted regions, controlled-rate, and/or bundles. The cohort inventory does not imply that every source row should be offered.
5. Use payload min/max as the operational quantity bounds when service-name figures conflict; verify what the target URL, optional drip feed, and hidden-field submission actually support. Refill duration claims remain separate from the refill capability flag.
6. Review the five direct-category omitted rows and five mixed-category bot Likes rows before final handler assignment. Their exclusion from the current map is not proof they are unavailable.

This is an **unapproved analysis**. Per `AGENTS.md` and `.ai/WORKFLOW.md`, wait for explicit approval of the reviewed service scope before creating/editing a ProductDefinition or changing its catalog status. Material source/mapping changes require renewed review.

## Row-level reconciliation appendix

`M` = mapped live row; `O` = current direct-category row omitted from map; `S` = mapped ID absent from registry. `R/C/D/K` are enabled refill/cancel/dripfeed/contract flags; `—` means none enabled. Source name/category and payload values are retained. Every resolved mapped row, every omitted direct-category row, and every stale mapped ID appears once.

| Status | Root ID | DGP handler ID | External ID | Raw category | Normalized cohort | Named outcome | Source name | Payload min–max | Rate | Enabled caps |
| --- | ---: | ---: | --- | --- | --- | --- | --- | ---: | ---: | --- |
| M | 46 | 1 | jap:9131 | Instagram TOP Services [EXCLUSIVE] | USA special category | Likes only | 🇺🇸 Instagram Likes [USA] [Algorithm Tricking] [Refill: Auto - 30D] [Max: 1K] [Start Time: 0 - 1 Hr] [Speed: 5K/D] | 5–50000 | 2.08 | C |
| M | 127 | 1 | jap:1837 | Instagram Likes | General Likes | Likes only | Instagram Likes [Refill: No] [Max: 1M] [Start Time: 0-1 Hr] [Speed: Up to 300K/D]💧 | 10–10000000 | 0.125 | D |
| M | 128 | 1 | jap:10237 | Instagram Likes | General Likes | Likes only | Instagram Likes [Refill: No] [Max: 1M] [Start Time: 0 - 1 Hr] [Speed: 200K/D] 💧 | 10–3000000 | 0.175 | CD |
| M | 129 | 1 | jap:4343 | Instagram Likes | General Likes | Likes only | Instagram Likes [Refill: No] [Max: 5M] [Start Time: 0 - 1 Hr] [Speed: 100K/D] ⛔💧 | 10–10000000 | 0.275 | CD |
| M | 130 | 1 | jap:1700 | Instagram Likes | General Likes | Likes only | Instagram Likes [Refill: No] [Max: 500K] [Start Time: 0 - 1 Hr] [Speed: Up to 100K/D] 💧⛔ | 10–500000 | 0.1375 | D |
| M | 131 | 1 | jap:10296 | Instagram Likes | General Likes | Likes only | Instagram Likes [Refill: 30D] [Max: 1M] [Start Time: 0 - 1 Hr] [Speed: 100K/D] 💧 | 100–1000000 | 0.1625 | D |
| M | 132 | 1 | jap:10126 | Instagram Likes | General Likes | Likes only | Instagram Likes [Refill: 30D] [Max: 1.5M] [Start Time: 0 - 1 Hr] [Speed: Up to 100K/D] ⛔💧 | 10–1000000 | 0.2375 | CD |
| M | 133 | 1 | jap:10065 | Instagram Likes | General Likes | Likes only | Instagram Likes [Refill: 30D] [Max: 500K] [Start Time: 0 - 1 Hr] [Speed: Up to 100K/D] 💧⛔♻️ | 10–500000 | 0.20 | D |
| M | 134 | 1 | jap:3866 | Instagram Likes | General Likes | Likes only | Instagram Likes [Refill: No] [Max: 100K] [Start Time: 0 - 2 Hrs] [Speed: 100K/D]💧⛔️ | 10–100000 | 0.3625 | CD |
| M | 135 | 1 | jap:3242 | Instagram Likes | General Likes | Likes only | Instagram Likes [Refill: 30D] [Max: 500K] [Start Time: 0-1 Hour] [Speed: 50K/D] 💧⛔♻️ | 10–200000 | 0.4125 | C |
| M | 136 | 1 | jap:1869 | Instagram Likes | General Likes | Likes only | Instagram Likes [HQ] [Refill: No] [Max: 300K] [Start Time: 0-1 Hr] [Speed: 25k/D] 💧⛔ | 10–1000000 | 0.175 | CD |
| M | 137 | 1 | jap:8505 | Instagram Likes | General Likes | Likes only | Instagram Likes [Refill: No] [Max: 1M] [Start Time: 0 - 2 Hrs] [Speed: Up to 50K/Day]💧 | 10–1000000 | 0.4875 | D |
| M | 138 | 1 | jap:10377 | Instagram Likes | General Likes | Likes only | Instagram Likes [Refill: No] [Max: 5K] [Start Time: 0 - 1 Hr] [Speed: 500/D] 💧⛔️ | 10–5000 | 1.0625 | CD |
| M | 139 | 1 | jap:10442 | Instagram Likes | General Likes | Likes only | Instagram Likes [Refill: 30D - Auto] [Max: 100K] [Start Time: 0 - 1 Hr] [Speed: 20K/D] 💧⛔♻️ | 10–1000000 | 0.125 | CD |
| M | 140 | 1 | jap:1845 | Instagram Likes | General Likes | Likes only | Instagram Likes [HQ] [NON DROP] [Max: 25K] [Start Time: 0-1 Hr] [Speed: 5K/Hr] 💧⛔ | 100–25000 | 1.5625 | D |
| M | 141 | 1 | jap:1761 | Instagram Likes | General Likes | Likes only | Instagram Likes [TOP QUALITY] [Refill: 30D] [60K] [Start Time: 0 - 1 Hr] [Speed: 60K/D] ♻️🔥 | 50–60000 | 1.4836 | D |
| M | 142 | 1 | jap:10066 | Instagram Likes | General Likes | Likes only | Instagram Real Likes [Refill: 365] [Max: 100K] [Start Time: 0 - 1 Hr] [Speed: 20K/D] 💧⛔♻️ | 10–10000000 | 0.286 | CD |
| M | 143 | 1 | jap:8219 | Instagram Likes | General Likes | Likes only | Instagram Likes [Refill: No] [Max: 150K] [Start Time: 0-1 Hour] [Speed: 100K/Day] ⛔💧 | 10–300000 | 0.1875 | CD |
| M | 144 | 1 | jap:8650 | Instagram Likes | General Likes | Likes only | Instagram Likes [Refill: No] [Max: 100K] [Start Time: 0-1 Hr] [Speed: 100K/Day] ⛔ 💧 | 100–2500000 | 0.13 | CD |
| M | 145 | 1 | jap:1823 | Instagram Likes | General Likes | Likes only | Instagram Likes [Max: 50K] [Start Time: 0-1 Hr] [Speed: 1K/Hour] ⛔🔥💧 | 10–150000 | 0.2375 | C |
| M | 146 | 1 | jap:1782 | Instagram Likes | General Likes | Likes only | Instagram Likes [Max: 10K] [Start Time: 0-1 Hr] [Speed: 5K/Hr] 💧⛔ | 50–1000000 | 0.1875 | CD |
| M | 147 | 1 | jap:1805 | Instagram Likes | General Likes | Likes only | Instagram Likes [Max: 100K] [Start Time: 0-1 Hr] [Speed: 25K/D] 💧⛔ | 10–100000 | 0.6875 | CD |
| M | 148 | 1 | jap:4289 | Instagram Likes | General Likes | Likes only | Instagram Likes [HQ] [FEW DROPS] [Refill: 30D] [Max: 100K] [Speed: 10K/D]💧⛔ | 30–500000 | 0.1238 | D |
| M | 149 | 1 | jap:4173 | Instagram Likes | General Likes | Likes only | Instagram Likes [Refill: 30] [Max: 30K]  [Start Time: 0 - 1 Hr] [Speed: 30K/Day] | 10–1000000 | 0.1413 | RCD |
| M | 150 | 1 | jap:1813 | Instagram Likes | General Likes | Likes only | Instagram Likes [HQ] [Max: 10K] [Start Time: 0-1 Hr] [Speed: 10K/D] 💧 | 10–10000 | 0.40 | CD |
| M | 151 | 1 | jap:8966 | Instagram Likes | General Likes | Likes only | Instagram Likes [Refill: No] [Max: 5K] [Start Time: 0 - 1 Hr] [Speed: 500/D] 💧⛔️♻️ | 20–6000 | 0.375 | RCD |
| M | 152 | 1 | jap:6094 | Instagram Likes | General Likes | Likes only | Instagram Likes [WITH CANCELATION] [Max: 5K] [Start Time: 0-1 Hour] [Speed: INSTANT] 💧⚡⛔🔥 | 10–300000 | 0.225 | CD |
| M | 153 | 1 | jap:8216 | Instagram Likes | General Likes | Likes only | Instagram Likes [Refill: NO REFILL ] [Max: 100K] [Start Time: 0-1 Hour] [Speed: 300K/Day] ⚡⛔💧 | 10–300000 | 0.1125 | C |
| M | 154 | 1 | jap:7788 | Instagram Likes | General Likes | Likes only | Instagram Likes [Refill: 90D] [Max: 150K] [Start Time: 0-1 Hr] [Speed: 150K/Day] ♻️ ⛔ 💧 | 10–100000 | 0.1609 | D |
| M | 155 | 1 | jap:7563 | Instagram Likes | General Likes | Likes only | Instagram Likes [Max: 10K] [Refill: No] [Start Time: 0 - 1 Hour] [Speed: 10K/Hour] 💧 | 10–300000 | 0.1125 | C |
| M | 156 | 1 | jap:7795 | Instagram Likes | General Likes | Likes only | Instagram Likes [Refill: No] [Max: 80K] [Start Time: 0 - 1 Hour] [Speed: 80K/Day] 💧 | 10–500000 | 0.225 | C |
| M | 157 | 1 | jap:6372 | Instagram Likes | General Likes | Likes only | Instagram Likes [Refill: No] [Low Drops] [Max: 200K] [Start Time: 0-1 Hour] [Speed: 100K/D] ⚡⛔ | 50–300000 | 0.225 | C |
| M | 158 | 1 | jap:6126 | Instagram Likes | General Likes | Likes only | Instagram Likes [Max: 200K] [Refill: 30Days] [Start Time: 0 - 2 Hours] [Speed: 10K/Day] ⛔💧 | 10–150000 | 0.2375 | C |
| M | 159 | 1 | jap:7742 | Instagram Likes | General Likes | Likes only | Instagram Likes [Max: 100K] [Refill: 30] [Start Time: 0 - 1 Hour] [Speed: 30K/Hour] | 10–20000 | 0.4125 | C |
| M | 160 | 1 | jap:1794 | Instagram Likes | General Likes | Likes only | Instagram Likes [Refill: 30D] [Max: 250K] [Start Time: 0-1 Hr] [Speed: 50K/Day] | 10–300000 | 0.2375 | CD |
| M | 161 | 1 | jap:3336 | Instagram Likes | General Likes | Likes + Impressions + Reach | Instagram Likes + Reach + Impressions [Refill: 30] [Max: 10K] [Start Time: 0 - 1 Hour] [Speed: 10K/Day] 💧 | 10–100000 | 0.30 | RC |
| M | 162 | 1 | jap:6361 | Instagram Likes | General Likes | Likes only | Instagram Likes [Refill: No] [Max: 200K] [Start Time: 0-1 Hour] [Speed: 100K/Day] ⚡ | 50–100000 | 0.1114 | — |
| M | 163 | 1 | jap:6001 | Instagram Likes | General Likes | Likes only | Instagram Likes [Refill: No / Low Drops] [Max: 150K] [Start Time: Instant] [Speed: 100K/Day] ⛔ | 50–200000 | 0.35 | C |
| M | 164 | 1 | jap:5956 | Instagram Likes | General Likes | Likes only | Instagram Likes [Refill: 30D] [Max: 200K] [Start Time: Instant] [Speed: Up to 100K/D] 💧⛔️♻️ | 10–200000 | 0.225 | C |
| M | 165 | 1 | jap:7787 | Instagram Likes | General Likes | Likes only | Instagram Likes [Refill: 30D] [Max: 100K] [Start Time: Instant - 1 Hour] [Speed: 30K/D] ⚡💧⛔️ | 10–100000 | 0.3125 | RCD |
| M | 166 | 1 | jap:7750 | Instagram Likes | General Likes | Likes only | Instagram Likes [80% FEMALE] [Refill: LIFETIME GUARANTEED]  [Max: 25K] [Start Time:  Instant] [Speed: 10K/Hour] | 100–1000000 | 0.5625 | C |
| M | 167 | 1 | jap:6562 | Instagram Likes | General Likes | Likes only | Instagram Likes [Refill: Auto-Refill 30 Days] [50K] [HQ] [Start Time: Instant] [Speed: 30K/Day] 💧⛔️♻️ | 10–50000 | 0.2063 | RCD |
| M | 168 | 1 | jap:7585 | Instagram Likes | General Likes | Likes only | Instagram Likes [Max: 50K] [Start Time: 0 - 1 Hours] [Speed: 50K Per Day] 💧⛔ | 10–50000 | 0.3528 | C |
| M | 169 | 1 | jap:983 | Instagram Likes | General Likes | Likes only | Instagram HQ Likes [Max: 100K] [Start Time: 0 - 1 Hour] [Speed: 10K/Day] 💧 | 10–20000 | 0.749 | RCD |
| M | 170 | 1 | jap:7508 | Instagram Likes | General Likes | Likes only | Instagram Likes [Refill: 30D Auto] [Max: 100K] [Start Time: 0-1 Hr] [Speed: Up to 50K/D] | 50–100000 | 0.1188 | RCD |
| M | 171 | 1 | jap:7532 | Instagram Likes | General Likes | Likes only | Instagram Likes [Refill: 30D] [200K] [Start Time: Instant] [Speed: 10K/D] ♻️💧⛔ | 50–200000 | 0.2503 | RCD |
| M | 172 | 1 | jap:1777 | Instagram Likes | General Likes | Likes only | Instagram Likes [NO REFILL] [Max: 150K] [Start Time: 5 Minute] [Speed: 1K/Hour]💧🔥 | 50–150000 | 0.081 | CD |
| M | 173 | 1 | jap:6286 | Instagram Likes | General Likes | Likes + Impressions + Reach | Instagram Likes + Reach + Impressions [Refill: 30D] [200K] [Start Time: Instant] [Speed: 25K/D] ♻️💧⛔️ | 10–200000 | 0.2001 | C |
| M | 174 | 1 | jap:1883 | Instagram Likes | General Likes | Likes + Impressions | Instagram Likes + Impressions [Max: 45K] [Start Time: 0-1 Hr] [Speed: INSTANT]  🔥🔥🔥 | 10–500000 | 0.6875 | D |
| M | 175 | 1 | jap:7117 | Instagram Likes | General Likes | Likes only | Instagram Likes [Refill: No] [Max: 200K] [Start Time: 0-1 Hour] [Speed: 200K/Day] ⚡⛔ | 10–200000 | 0.2375 | CD |
| M | 176 | 1 | jap:1788 | Instagram Likes | General Likes | Likes only | Instagram Likes [Max: 200K] [Start Time: 1 Hour] [Speed: 50K/Day] 💧⛔️ | 50–200000 | 0.075 | CD |
| M | 177 | 1 | jap:6689 | Instagram Likes | General Likes | Likes only | Instagram Likes [Refill: Auto 30 Days] [Start Time: 2 Hours] [Speed: 50k/Day]💧⛔️♻️ | 50–200000 | 0.10 | RCD |
| M | 178 | 1 | jap:7583 | Instagram Likes | General Likes | Likes only | Instagram Likes [Max: 50K] [Start Time: 0-1 Hour] [Speed: INSTANT] 💧⚡🔥⛔ | 50–50000 | 0.1016 | CD |
| M | 179 | 1 | jap:1957 | Instagram Likes | General Likes | Likes only | Instagram Likes [HQ][Refill: 30D] [Max: 30K] [Start Time: 0-1 Hr] [Speed: 10K/D] | 10–30000 | 0.3375 | D |
| M | 180 | 1 | jap:6582 | Instagram Likes | General Likes | Likes + Impressions + Reach | Instagram Likes + Impressions + Reach [Max: 45K] [Start Time: Instant] [Speed: 30K/Day] ⚡ | 10–500000 | 1.1444 | D |
| M | 181 | 1 | jap:1768 | Instagram Likes | General Likes | Likes + Impressions | Instagram Likes + Impressions [HQ] [Max: 7K] [Start Time: Instant] [Speed: 7K/Day]💧🔥 | 10–100000 | 0.1609 | D |
| O | 182 | 1 | jap:5958 | Instagram Likes | General Likes | Likes + Impressions + Reach | Instagram Likes + Reach + Impressions [Auto-Refill: 30 Days] [300K] [MQ] [Start Time: Instant] [Speed: 20K/Day] ♻️💧⛔️ | 10–300000 | 0.2063 | RCD |
| M | 183 | 1 | jap:3343 | Instagram Likes | General Likes | Likes only | Instagram Likes [Refill: No] [Max: 3K/order 30k/link] [Start Time: 0-12 Hours] | 50–30000 | 0.348 | CD |
| M | 184 | 1 | jap:1769 | Instagram Likes | General Likes | Likes only | Instagram Likes [EXCLUSIVE - Up to 15% Drop Max] [Refill: 30 Days] [Max: 5K] [Start Time: 0-1 Hour] [Speed: 2K/Hour] 💧 | 10–8000 | 0.0756 | CD |
| M | 185 | 1 | jap:4394 | Instagram Likes | General Likes | Likes only | Instagram Likes [Refill: 30D] [Max: 500K] [Start Time: 0-1 Hour] [Speed: 20K/Hour] 🔥⚡⚡⚡⛔ | 10–500000 | 0.50 | CD |
| M | 186 | 1 | jap:5628 | Instagram Likes | General Likes | Likes only | Instagram Likes [Drops 5-7%] [Refill: 30D] [Max: 10K] [Start Time: 0-1 Hour [Speed: 1-2K/Hour] | 10–10000 | 0.20 | C |
| M | 187 | 1 | jap:5629 | Instagram Likes | General Likes | Likes only | Instagram Likes [Drops 5-7%] [Refill: No] [Max: 5K] [Start Time: 0-1 Hour]  [Speed: 1-2K/Hour] | 50–100000 | 0.081 | CD |
| M | 188 | 1 | jap:5630 | Instagram Likes | General Likes | Likes only | Instagram Likes [Drops LOW] [Refill: AR30D] [Max: 50K] [Start Time: 0-1 Hour] [Speed: 10K/D]♻️💧⛔ | 1–200000 | 0.5625 | RC |
| M | 189 | 1 | jap:3592 | Instagram Likes | General Likes | Likes only | Instagram Likes [Refill: 30D] [Max: 10K] [Start Time: 0-1 Hour] [Speed: 1K+/Hour]💧♻️⛔ | 10–50000 | 0.50 | CD |
| M | 190 | 1 | jap:5631 | Instagram Likes | General Likes | Likes only | Instagram Likes [Refill: 30D - AUTO] [Max: 100K] [Start Time: 0-1 Hr] [Speed: Up to 10K/D] 💧⛔️♻️ | 10–100000 | 0.30 | RCD |
| M | 191 | 1 | jap:3019 | Instagram Likes | General Likes | Likes only | Instagram Likes [SUPER] [Refill: No] [Max:10K] [Start Time: 0-1 Hour] [Speed: 3K/Hour] | 10–1000000 | 0.1246 | C |
| M | 192 | 1 | jap:3349 | Instagram Likes | General Likes | Likes only | Instagram Likes [Max: 150K] [Start Time: 0-1 Hour] [Speed: 5K/Day] 💧♻️🔥🔥 | 10–130000 | 0.247 | C |
| M | 193 | 1 | jap:5560 | Instagram Likes | General Likes | Likes + Impressions | Instagram Likes + Impressions [Max: 2K] [Start Time: 1 Hour] [Speed: 2K/Day] ⚡ | 10–100000 | 0.1609 | D |
| M | 194 | 1 | jap:8442 | Instagram Likes | General Likes | Likes only | Instagram Likes [Refill: 30 Days] [Max: 40K] [Start Time: 0-1 Hour] [Speed: Up to 15K/Day] 💧♻️ | 10–75000 | 0.7201 | D |
| M | 195 | 1 | jap:5670 | Instagram Likes | General Likes | Likes only | Instagram Likes [Max: 10K] [Start Time: 0-1 Hour] [Speed: INSTANT] 💧⚡⚡⚡🔥 | 20–30000 | 0.35 | C |
| M | 196 | 1 | jap:3792 | Instagram Likes | General Likes | Likes only | Instagram Likes [NON DROP] [Max: 8K] [Start Time: 0-1 Hour] [Speed: 8K/Day] 💧🔥🔥 | 10–1000000 | 0.2318 | CD |
| M | 197 | 1 | jap:1778 | Instagram Likes | General Likes | Likes only | Instagram Likes [30K] [REAL ] [1H - 1k/Day] 💧⚡ | 5–50000 | 2.00 | C |
| M | 198 | 1 | jap:3788 | Instagram Likes | General Likes | Likes only | Instagram Likes [Max: 10K] [Start Time: 0-1 Hour] [Speed: 10K/Day] | 10–10000000 | 0.51 | C |
| M | 199 | 1 | jap:8036 | Instagram Likes | General Likes | Likes only | Instagram Likes [Refill: 365 Days] [Max: 10K] [Start Time: 0-1 Hours] [Speed: 10K/Day] 💧⛔ | 10–10000000 | 0.1788 | CD |
| M | 200 | 1 | jap:1789 | Instagram Likes | General Likes | Likes only | Instagram Likes [Refill: 30D] [Max: 50K] [Start Time: 0-1 Hr] [Speed: 20K/Day] 💧♻️ | 10–100000 | 0.275 | D |
| M | 201 | 1 | jap:1916 | Instagram Likes | General Likes | Likes only | Instagram Likes [Refill: No] [Max: 5K] [Start Time: 0-1 Hour] [Speed: 2K/Day] | 20–10000 | 1.35 | RCD |
| M | 202 | 1 | jap:1776 | Instagram Likes | General Likes | Likes only | Instagram Likes [Refill: No] [Max: 200K] [Start Time: 0-1 Hour] [Speed: 100K/Day] ⛔💧 | 10–200000 | 0.2375 | CD |
| M | 203 | 1 | jap:3585 | Instagram Likes | General Likes | Likes only | Instagram Likes [NON DROP] [Max: 5K] [Start Time: 0-1 Hour] [Speed: 500/Hour] | 20–5000 | 1.035 | CD |
| M | 204 | 1 | jap:3525 | Instagram Likes | General Likes | Likes only | Instagram Likes [EXCLUSIVE] [NON DROP] [Max: 10K] [Start Time: 0-1 Hour] [Speed: 1K/Hour] | 50–10000 | 1.104 | CD |
| M | 205 | 1 | jap:4127 | Instagram Likes | General Likes | Likes only | Instagram Likes [EMERGENCY] [NON DROP] [Max: 5K] [Start Time: 0-1 Hour] [Speed: 2K/Hour] 🔥🔥🔥 | 50–5000 | 1.15 | CD |
| M | 206 | 1 | jap:1950 | Instagram Likes | General Likes | Likes only | Instagram Likes [EMERGENCY] [Max: 50K] [Start Time: 0-1 Hour] [Speed: 10/Day ] | 10–5000000 | 0.13 | C |
| M | 207 | 1 | jap:8562 | Instagram Likes | General Likes | Likes only | Instagram Likes [FROM APP] [Refill: No] [Max: 100K] [Start Time: 0 - 1 Hour] [Speed: Up to 5K/Day] | 100–100000 | 0.36 | C |
| M | 208 | 1 | jap:4128 | Instagram Likes | General Likes | Likes only | Instagram Likes [EMERGENCY] [Max: 10K] [Start Time: 0-1 Hour] [Speed: FAST] 🔥🔥🔥 | 10–100000 | 0.7695 | C |
| M | 209 | 1 | jap:4236 | Instagram Likes | General Likes | Likes only | Instagram Likes [Max: 20K] [Start Time: 0-1 Hour] [Speed: FAST] 🔥🔥🔥 | 10–100000 | 1.3125 | CD |
| M | 210 | 1 | jap:1836 | Instagram Likes | General Likes | Likes only | Instagram Likes [Max: 2K] [Start Time: 1 Hour] [Speed: 3K/Hour]💧 | 5–50000 | 2.40 | C |
| M | 211 | 1 | jap:3292 | Instagram Likes | General Likes | Likes + Impressions + Reach | Instagram Likes + Impressions + Reach [English PUBLIC with Stories Accounts] [Max: 2K] [Start Time: 0-1 Hour] [Speed: 2K/Hour] 🔥🔥🔥 | 5–50000 | 2.00 | CD |
| M | 212 | 1 | jap:1865 | Instagram Likes | General Likes | Likes only | Instagram Likes [Max: 10M] [Start Time: 0-3 Hrs] [Speed: 300K/D] 💧 | 10–10000000 | 0.125 | D |
| M | 213 | 1 | jap:1884 | Instagram Likes | General Likes | Likes only | Instagram Likes [EMERGENCY] [Max: 50K] [Start Time: 0-1 Hour] [Speed: INSTANT] | 10–1000000 | 0.275 | C |
| M | 214 | 1 | jap:8397 | Instagram Likes | General Likes | Likes only | Instagram RAU™ Likes [Refill: No Drop] [Max: 10K] [Start Time: 0-1 Hour] [Speed: 500/Hr] 💧 | 5–50000 | 2.352 | C |
| M | 215 | 1 | jap:3278 | Instagram Likes | General Likes | Likes only | Instagram Likes [Max: 5K] [Start Time: 0-1 Hour] [Speed: 1K/Hour] | 50–100000 | 2.00 | CD |
| M | 216 | 1 | jap:1767 | Instagram Likes | General Likes | Likes only | Instagram Likes [Refill: No] [Max: 50K] [Start Time: 0-1 Hour] [Speed: INSTANT] 💧⚡⚡⚡🔥 | 50–50000 | 2.15 | CD |
| M | 217 | 1 | jap:5715 | Instagram Likes | General Likes | Likes only | Instagram Likes RAU™ [USA 🇺🇸] [Max: 1.5K] [Refill: 60D] [Start Time: 0 - 1 Hr] [Speed: 1.5K/D] 💧 | 10–20000 | 2.325 | D |
| M | 218 | 1 | jap:4301 | Instagram Likes | General Likes | Likes only | Instagram Likes [REAL] [Max: 5K] [Start Time: 0-1 Hour] [Speed: 2K/Hour] | 20–3000 | 3.36 | D |
| M | 219 | 1 | jap:266 | Instagram Likes | General Likes | Likes only | Instagram Likes [MIX] [Refill: No] [Max: 6K] [Start Time: 0-1 Hour] [Speed: INSTANT]💧⛔ | 20–3000 | 3.51 | D |
| M | 220 | 1 | jap:5917 | Instagram Likes | General Likes | Likes only | Instagram Likes [REAL LOOKING] [Max: 50K] [Start Time: 0-1 Hour] [Speed: 20K/Day] | 10–500000 | 0.495 | CD |
| M | 221 | 1 | jap:1791 | Instagram Likes | General Likes | Likes only | Instagram Likes [HQ] [Refill: No] [Start Time: Instant] [Speed: 50k/Day]💧⛔️ | 20–50000 | 3.08 | D |
| M | 222 | 1 | jap:8042 | Instagram Likes | General Likes | Likes only | Instagram RAL™ Likes [Refill: Lifetime] [Max: 1K] [Start Time: 0-2 Hours] [Speed: 1K/Hour] ⚡💧 | 5–50000 | 2.40 | C |
| M | 223 | 1 | jap:3020 | Instagram Likes | General Likes | Likes only | Instagram Likes [NON DROP] [Max: 10K] [Start Time: 0-1 Hour] [Speed: 10K/Day] | 100–25000 | 0.1728 | — |
| M | 224 | 1 | jap:1863 | Instagram Likes [BOTS] | Bot/account type | Likes only | Instagram Likes [Refill: No] [Max: 1M] [Start time: 0 - 1 Hr] [Speed: 200K/D] 💧⛔️ | 10–1000000 | 0.1125 | CD |
| M | 225 | 1 | jap:5626 | Instagram Likes [BOTS] | Bot/account type | Likes only | Instagram Likes [Refill: No] [Max: 500K] [Start Time: 0 - 1 Hr] [Speed: Up to 100K/D] 💧⛔ | 10–500000 | 0.1375 | D |
| M | 226 | 1 | jap:1967 | Instagram Likes [BOTS] | Bot/account type | Likes only | Instagram Likes [Refill: No] [Max: 1M] [Start Time: 0-3 Hrs] [Speed: Up to 100K/D] 💧⛔ | 10–10000000 | 0.125 | — |
| M | 227 | 1 | jap:7455 | Instagram Likes [BOTS] | Bot/account type | Likes only | Instagram Likes [Refill: 90D] [Max: 1M] [Start time: 0 - 1 Hr] [Speed: 200K/D] 💧⛔️♻️ | 10–1000000 | 0.20 | CD |
| M | 228 | 1 | jap:10149 | Instagram Likes [BOTS] | Bot/account type | Likes only | Instagram Likes [Refill: No] [Max: 5M] [Start Time: 0-3 Hrs] [Speed: Up to 20K/D] 💧⛔ | 10–10000000 | 0.275 | C |
| M | 229 | 1 | jap:2148 | Instagram Likes [BOTS] | Bot/account type | Likes only | Instagram Likes [Refill: 30D] [Max: 500K] [Start Time: 0-1 Hour] [Speed: 50K/D] 💧⛔♻️ | 10–500000 | 0.4125 | CD |
| M | 230 | 1 | jap:9529 | Instagram Likes [BOTS] | Bot/account type | Likes only | Instagram Likes [HQ] [Refill: No] [Max: 500K] [Start Time: 0-3 Hrs] [Speed: 100K/D] 💧⛔️ | 10–10000000 | 0.125 | — |
| M | 231 | 1 | jap:9530 | Instagram Likes [BOTS] | Bot/account type | Likes only | Instagram Likes [HQ] [Refill:NO] [Max: 500K] [Start Time: 0-3 Hrs] [Speed: 100K/D] 💧⛔️ | 10–10000000 | 0.125 | — |
| M | 232 | 1 | jap:4342 | Instagram Likes [BOTS] | Bot/account type | Likes only | Instagram Likes [Refill: No] [Max: 500K] [Start Time: 0-1 Hr] [Speed: 10K/Day]  ⛔ 💧 | 50–100000 | 0.1114 | D |
| M | 233 | 1 | jap:2939 | Instagram Likes [BOTS] | Bot/account type | Likes only | Instagram Likes [Refill: 90D] [Max: 150K] [Start Time: 0-1 Hr] [Speed: 150K/Day] ♻️ ⛔ 💧 | 10–100000 | 0.1609 | D |
| M | 234 | 1 | jap:1820 | Instagram Likes [BOTS] | Bot/account type | Likes only | Instagram Likes [Refill: NO] [Max: 1M] [Start Time: 0-3 Hrs] [Speed: Up to 100K/D] 💧⛔♻️ | 10–10000000 | 0.1313 | — |
| M | 235 | 1 | jap:10150 | Instagram Likes [BOTS] | Bot/account type | Likes only | Instagram Likes [Refill: 30D] [Max: 5M] [Start Time: 0-3 Hrs] [Speed: Up to 20K/D] 💧⛔♻️ | 10–10000000 | 0.1013 | D |
| M | 236 | 1 | jap:8586 | Instagram Likes [BOTS] | Bot/account type | Likes only | Instagram Likes [BOTS] [Refill: No] [Max: 10K] [Start time: 1 Hour] [Speed: 10K/Day] 💧⛔️ | 10–1000000 | 0.1337 | CD |
| M | 237 | 1 | jap:8464 | Instagram Likes [BOTS] | Bot/account type | Likes only | Instagram Likes [LQ] [Refill: No] [Max: 100K] [Start Time: 0 - 6 Hours] [Speed: 10K/Day] 💧⛔️ | 10–200000 | 0.1125 | CD |
| M | 238 | 1 | jap:8409 | Instagram Likes [BOTS] | Bot/account type | Likes only | Instagram Likes [LQ] [Refill: 30D] [Max: 500K] [Start Time: 0 - 3 Hours] [Speed: 10K/Day] 💧⛔️ | 10–500000 | 0.42 | C |
| M | 239 | 1 | jap:9183 | Instagram Likes [BOTS] | Bot/account type | Likes only | Instagram Likes [LQ] [Refill: 30D] [Max: 500K] [Start Time: 0 - 3 Hours] [Speed: 10K/Day] 💧⛔️ | 50–500000 | 0.075 | CD |
| M | 240 | 1 | jap:7797 | Instagram Likes [BOTS] | Bot/account type | Likes only | Instagram Likes [BOTS] [Refill: No] [Max: 30K] [Start time: Instant] [Speed: 30K/Day] | 10–500000 | 0.2448 | C |
| M | 241 | 1 | jap:1864 | Instagram Likes [BOTS] | Bot/account type | Likes only | Instagram Likes [Refill: 60D] [Max: 250k] [Start Time: 0 - 3 Hrs] [Speed: 25K/D] 💧♻️⛔️ | 10–100000 | 0.1674 | D |
| M | 242 | 1 | jap:2994 | Instagram Likes [BOTS] | Bot/account type | Likes only | Instagram Likes [Refill: 90D] [Max: 250k] [Start Time: 0 - 3 Hrs] [Speed: 25K/D] 💧♻️⛔️ | 10–100000 | 0.1712 | D |
| M | 243 | 1 | jap:3130 | Instagram Likes [BOTS] | Bot/account type | Likes only | Instagram Likes [Refill: 365D] [Max: 250k] [Start Time: 0 - 3 Hrs] [Speed: 25K/D] 💧♻️⛔️ | 10–100000 | 0.1738 | D |
| M | 244 | 1 | jap:5781 | Instagram Likes [BOTS] | Bot/account type | Likes only | Instagram Likes [Refill: No] [Max: 10K] [Start Time: 1H] [Speed: 10K/Day] | 10–100000 | 0.1802 | D |
| M | 245 | 1 | jap:8561 | Instagram Likes [BOTS] | Bot/account type | Likes only | Instagram Likes [Refill: 30 Days] [Max: 500K] [Start Time: 0 - 1 Hour] [Speed: 10K/Day] ⛔ | 10–50000 | 0.42 | C |
| M | 246 | 1 | jap:6125 | Instagram Likes [BOTS] | Bot/account type | Likes only | Instagram Likes [Max: 500K] [BOTS] [Refill: 30D] [Start Time: 0 - 1 Hr] [Speed: 50K/Day] ⛔♻️ | 10–500000 | 0.42 | C |
| M | 247 | 1 | jap:2991 | Instagram Likes [BOTS] | Bot/account type | Likes only | Instagram Likes [Refill: 30D] [Max: 300K] [Start Time: 0 - 2 Hrs] [Speed: 20K/Day] ⛔♻️ | 10–300000 | 0.247 | CD |
| M | 248 | 1 | jap:7796 | Instagram Likes [BOTS] | Bot/account type | Likes only | Instagram Likes [Refill: 30D] [Max: 250K] [Start Time: 0 - 1 Hour] [Speed: 100K/Day] 💧⛔️ | 100–150000 | 0.1875 | RCD |
| M | 249 | 1 | jap:5948 | Instagram Likes [BOTS] | Bot/account type | Likes only | Instagram Likes [BOTS] [Refill: 30] [Max: 20K] [Start Time: 0-1 Hour] [Speed: FAST] | 10–300000 | 0.434 | CD |
| M | 250 | 1 | jap:5949 | Instagram Likes [BOTS] | Bot/account type | Likes only | Instagram Likes [BOTS] [Refill: 30 Days] [Max: 20K] [Start Time: 0-1 Hour] [Speed: 10k/Day] ♻️ | 10–300000 | 0.4256 | C |
| M | 251 | 1 | jap:7456 | Instagram Likes [BOTS] | Bot/account type | Likes only | Instagram Likes [Bots] [Refill: 30 Days] [Max: 50K] [Start Time: 0-1 Hour] [Speed: 30-60K/Day] ♻️ | 10–300000 | 0.2375 | CD |
| M | 252 | 1 | jap:5955 | Instagram Likes [BOTS] | Bot/account type | Likes only | Instagram Likes [Refill: No] [Max: 200K] [Start Time: 0-1 Hour] [Speed: 10K/Day] 💧⛔ | 10–50000 | 0.35 | C |
| M | 253 | 1 | jap:2997 | Instagram Likes [BOTS] | Bot/account type | Likes only | Instagram Likes [Max: 50K] [Start Time: 0-1 Hour] [Speed: 1K/Hour] ⛔🔥💧 | 10–50000 | 0.2375 | CD |
| M | 254 | 1 | jap:7789 | Instagram Likes [BOTS] | Bot/account type | Likes only | Instagram Likes [Refill: No] [Max: 30K] [Start Time: 0 - 1 Hour] [Speed: 30K/Day] 💧⛔️ | 10–300000 | 0.364 | C |
| M | 255 | 1 | jap:2993 | Instagram Likes [BOTS] | Bot/account type | Likes only | Instagram Likes [Max: 50K] [Start Time: 0 - 1 Hours] [Speed: 50K Per Day] 💧⛔ | 10–50000 | 0.50 | CD |
| M | 256 | 1 | jap:2192 | Instagram Likes [BOTS] | Bot/account type | Likes only | Instagram Likes [HQ] [Refill: 30D] [Max: 30K] [Start time: 0 - 1 Hr] [Speed: 10K/Day] | 10–30000 | 0.3375 | D |
| M | 257 | 1 | jap:1914 | Instagram Likes [BOTS] | Bot/account type | Likes only | Instagram Likes [NATURAL INCREASE] [Refill: No] [Max: 25K]  🔥 | 10–100000 | 0.1931 | D |
| M | 258 | 1 | jap:1913 | Instagram Likes [BOTS] | Bot/account type | Likes only | Instagram Likes [HQ] [Refill: No] [Max: 20K] [Start Time: 0-1 Hour] [Speed: FAST] 💧⛔ | 10–100000 | 0.1609 | D |
| M | 259 | 1 | jap:2983 | Instagram Likes [BOTS] | Bot/account type | Likes only | Instagram Likes [Bots with PP] [Refill: AR30] [Max: 300K] [Start Time: 0-1 Hour] [Speed: FAST] ⛔♻️ | 10–300000 | 0.20 | RC |
| M | 260 | 1 | jap:8454 | Instagram Likes [BOTS] | Bot/account type | Likes only | Instagram Likes [Refill: No] [Max: 5K] [Start Time: 6 Hours] [Speed: 5K/Day] | 10–500000 | 0.243 | CD |
| M | 261 | 1 | jap:8404 | Instagram Likes [BOTS] | Bot/account type | Likes only | Instagram Likes [Refill: No] [Max: 1K] [Start Time: 0 - 6 Hours] [Speed: 1K/Day] | 10–200000 | 0.234 | CD |
| M | 262 | 1 | jap:5899 | Instagram Likes [BOTS] | Bot/account type | Likes only | Instagram Likes [HQ] [Max: 5K] [Start Time: Instant] [Speed: Instant] 🔥⛔ | 100–25000 | 1.5625 | D |
| M | 263 | 1 | jap:2998 | Instagram Likes [BOTS] | Bot/account type | Likes only | Instagram Likes [Refill: 30 Days] [Max: 5K] [Start Time: 6 Hours] [Speed: 5K/Day] | 10–200000 | 0.2375 | CD |
| M | 264 | 1 | jap:3226 | Instagram Likes [BOTS] | Bot/account type | Likes + Impressions | Instagram Likes + Impressions [Refill: 30 Days] [Max: 30K] [Start Time: 0-1 Hour] [Speed: 1-3K/Hour] ♻️ | 50–100000 | 0.1609 | D |
| M | 265 | 1 | jap:1817 | Instagram Likes [BOTS] | Bot/account type | Likes only | Instagram Likes [MQ] [Refill: 30 Days] [Max: 500K] [Start Time: 0-1 Hour] [Speed: 5K/Day] 💧⛔ | 10–100000 | 0.1609 | D |
| M | 266 | 1 | jap:1797 | Instagram Likes [BOTS] | Bot/account type | Likes only | Instagram Likes [MQ] [Refill: 180 Days] [Max: 50K] [Start Time: 0-1 Hour] [Speed: INSTANT] ♻️⚡ | 50–50000 | 1.2482 | RCD |
| O | 267 | 1 | jap:5959 | Instagram Likes [BOTS] | Bot/account type | Likes + Impressions + Reach | Instagram Likes + Reach + Impressions [Auto-Refill: 30 Days] [300K] [MQ] [Start Time: Instant] [Speed: 20K/Day] 💧♻️⛔️ | 10–300000 | 0.2063 | RCD |
| M | 268 | 1 | jap:4172 | Instagram Likes [BOTS] | Bot/account type | Likes only | Instagram Likes [Refill: No] [Max: 150K] [Start Time: 1 Hour] [Speed: 3K/Day] | 10–150000 | 0.32 | RC |
| M | 269 | 1 | jap:2259 | Instagram Likes [BOTS] | Bot/account type | Likes only | Instagram Likes [Refill: No] [Max: 20K] [Start Time: 0-1 Hour] [Speed: 10K/Hour] 🔥⚡⛔ | 10–20000 | 0.1609 | D |
| M | 270 | 1 | jap:4234 | Instagram Likes [BOTS] | Bot/account type | Likes only | Instagram Likes [NO DROP] [Auto-Refill: 7 Days] [Max: 20K] [Start Time: 0-1 Hour] [Speed: 10K/Day] 🔥💧♻️⛔️ | 10–20000 | 0.264 | RCD |
| M | 271 | 1 | jap:4429 | Instagram Likes [BOTS] | Bot/account type | Likes only | Instagram Likes [Refill: 30 Days] [Max: 100K] [Start Time: 1 Hour] [Speed: 20K/Day] ♻️💧🔥 | 10–100000 | 0.1609 | D |
| M | 272 | 1 | jap:1849 | Instagram Likes [BOTS] | Bot/account type | Likes only | Instagram Likes [MQ] [Refill: No] [Max: 100K] [Start Time: 1 Hour] [Speed: 5K/Day]💧 | 10–100000 | 0.96 | D |
| M | 273 | 1 | jap:1844 | Instagram Likes [BOTS] | Bot/account type | Likes only | Instagram Likes [MQ] [Refill: 180 Days] [Max: 30K] [Start Time: 0-1 Hour] [Speed: INSTANT] 💧♻️⚡⚡⚡ | 10–100000 | 2.70 | D |
| M | 274 | 1 | jap:1819 | Instagram Likes [Targeted] | Targeted | Likes only | Instagram Likes RAU™ [USA 🇺🇸] [Max: 1.5K] [Refill: 60D] [Start Time: 0 - 1 Hr] [Speed: 1.5K/D] 💧 | 5–50000 | 2.9124 | CD |
| M | 275 | 1 | jap:8851 | Instagram Likes [Targeted] | Targeted | Likes only | Instagram Likes [USA 🇺🇸] [Max: 12K] [Refill: 120D] [Start Time: 0 - 1 Hr] [Speed: 10K/D] 💧⛔♻️ | 10–12000 | 2.25 | D |
| M | 276 | 1 | jap:10209 | Instagram Likes [Targeted] | Targeted | Likes only | Instagram Likes [BR 🇧🇷] [Refill: No] [Max: 5K] [Start Time: 0 - 1 Hr] [Speed: 5K/D] 💧⛔️ | 50–5000 | 0.525 | CD |
| M | 277 | 1 | jap:10210 | Instagram Likes [Targeted] | Targeted | Likes only | Instagram Likes [BR 🇧🇷] [Refill: No] [Max: 100K] [Start Time: 0 - 1 Hr] [Speed: 50K/D] 💧⛔️ | 50–200000 | 0.6875 | CD |
| M | 278 | 1 | jap:1018 | Instagram Likes [Targeted] | Targeted | Likes + Impressions + Reach | 🇰🇷🇰🇵 Instagram Likes + Impressions + Reach [Korea] [HQ] [Refill: 90 Days] [Max: 10K] [Start Time: 0 - 1 Hour] [Speed: 10K/Day] | 20–10000 | 10.40 | D |
| M | 279 | 1 | jap:8782 | Instagram Likes [Targeted] | Targeted | Likes only | Instagram Likes [ARAB] [Refill: 30D] [Max: 50K] [Start Time: 0 - 12 Hrs] [Speed: Up to 10K/D] 💧⛔ | 50–300 | 2.325 | D |
| M | 280 | 1 | jap:10211 | Instagram Likes [Targeted] | Targeted | Likes only | Instagram Likes [EG 🇪🇬] [Refill: No] [Max: 100K] [Start Time: 0 - 1 Hr] [Speed: 50K/D] 💧⛔️ | 50–100000 | 1.0625 | CD |
| M | 281 | 1 | jap:10212 | Instagram Likes [Targeted] | Targeted | Likes only | Instagram Likes [KSA 🇸🇦] [Refill: No] [Max: 100K] [Start Time: 0 - 1 Hr] [Speed: 50K/D] 💧⛔️ | 10–100000 | 1.7438 | CD |
| M | 282 | 1 | jap:1031 | Instagram Likes [Targeted] | Targeted | Likes only | Instagram Likes [🇦🇪 ARAB / 🇮🇳 INDIA / 🇹🇷 TURK MIX] [Refill: 30D] [Max: 200K] [Start Time: 0 - 1 Hr] [Speed: 20K/D] 💧♻️⛔ | 100–200000 | 1.25 | CD |
| M | 283 | 1 | jap:1030 | Instagram Likes [Targeted] | Targeted | Likes only | 🇦🇪 Instagram Likes [UAE - ARAB] [Refill: 45D] [Max: 50K] [Start Time: 0 - 1 Hr] [Speed: 5K/D] ⛔💧♻️ | 100–10000 | 2.1875 | D |
| M | 284 | 1 | jap:89 | Instagram Likes [Targeted] | Targeted | Likes only | Instagram Likes [ARAB] [Refill: No] [Max: 5K] Start Time: 0-1 Hour] [Speed: 2K/Day] | 20–3000 | 3.36 | D |
| M | 285 | 1 | jap:5731 | Instagram Likes [Targeted] | Targeted | Likes only | 🇮🇳 Instagram Likes [INDIA] [Refill: 30 Days] [Max: 100K] [Start Time: Instant] [Speed: 10K/Day] | 10–10000 | 1.75 | CD |
| M | 286 | 1 | jap:1028 | Instagram Likes [Targeted] | Targeted | Likes only | 🇮🇳 Instagram Likes [INDIA] [Refill: 30D] [Max: 100K] [Start Time: Instant] [Speed: 15K/Day] | 10–10000 | 2.24 | CD |
| M | 287 | 1 | jap:1822 | Instagram Likes [Targeted] | Targeted | Likes only | 🇮🇷Instagram Likes [IRAN] [Refill: No] [Max: 10K] [Start Time: 0-1 Hour] [Speed: 5K/Day] | 100–100000 | 0.88 | — |
| M | 288 | 1 | jap:2987 | Instagram Likes [Targeted] | Targeted | Likes only | 🇸🇦🇮🇷Instagram Likes [ARAB - IRAN MIX] [Refill: No] [Max: 10K] [Start Time: 0-1 Hour] [Speed: 5K/Day] | 100–100000 | 0.99 | — |
| M | 289 | 1 | jap:8788 | Instagram Likes [Targeted] | Targeted | Likes only | 🇰🇷 Instagram Likes [KOREA] [Refill: No] [Max: 200K] [Start Time: 0-3 Hrs] [Speed: 2K/Day] | 20–200000 | 1.6313 | C |
| M | 290 | 1 | jap:10087 | Instagram Likes [Targeted] | Targeted | Likes only | 🇰🇷 Instagram Likes [KOREA] [HQ] [Refill: No] [Max: 50K] [Start Time: 0-3 Hrs] [Speed: 10K/D]💧 | 10–50000 | 7.5525 | D |
| M | 291 | 1 | jap:10088 | Instagram Likes [Targeted] | Targeted | Likes only | 🇰🇷 Instagram Likes [KOREA] [HQ] [Refill: 30D] [Max: 50K] [Start Time: 0-3 Hrs] [Speed: 10K/D]💧 | 10–50000 | 9.4288 | CD |
| M | 292 | 1 | jap:8574 | Instagram Likes [Targeted] | Targeted | Likes only | 🇮🇳 Instagram Likes [INDIA WOMEN] [Refill: 30 Days] [Max: 10K] [Start Time: Instant] [Speed: 10K/Day] | 10–10000 | 2.1875 | CD |
| M | 293 | 1 | jap:3381 | Instagram Likes [Targeted] | Targeted | Likes + Impressions | 🇷🇺Instagram Likes + Impressions [RUSSIAN] [NON-DROP] [Max: 150K] [Refill: 30 Days] [Start Time: 1 Hour] [Speed: 2K/Day] 💧🔥♻️ | 50–200000 | 5.00 | D |
| M | 294 | 1 | jap:8048 | Instagram Likes [Targeted] | Targeted | Likes only | Instagram Likes [🇦🇪 🇸🇦 ARAB - GULF] [SUPER REAL] [Refill: No] [Max: 3K] [Start Time: 0-1 Hour] [Speed: 3K/Day] | 20–10000 | 2.75 | D |
| M | 295 | 1 | jap:1037 | Instagram Likes [Targeted] | Targeted | Likes only | Instagram Likes [Max: 2K] [UK 🇬🇧 ] [Refill: No] [Speed: 2K/Day] [Start Time: 0 - 1 Hours] | 20–2000 | 4.125 | D |
| M | 296 | 1 | jap:8253 | Instagram Likes [Targeted] | Targeted | Likes only | Instagram Likes Male [ARAB-GULF] [Max: 50K] [Refill: 30 Days] [Start Time: 0 - 1 Hours] [Speed: 500/Day] | 20–50000 | 2.7875 | RC |
| M | 297 | 1 | jap:8051 | Instagram Likes [Targeted] | Targeted | Likes only | Instagram Likes [Max: 2K] [SPAIN 🇪🇸 ] [Refill: No] [Speed: 2K/Day] [Start Time: 0 - 1 Hours] | 20–2000 | 4.125 | D |
| M | 298 | 1 | jap:8050 | Instagram Likes [Targeted] | Targeted | Likes only | Instagram Likes [Max: 1K] [TAIWAN 🇹🇼 ] [Refill: No] [Speed: 1K/Day] [Start Time: 0 - 1 Hours] | 20–1000 | 3.50 | D |
| M | 299 | 1 | jap:2294 | Instagram Likes [Targeted] | Targeted | Likes only | 🇮🇳 Instagram Likes [INDIA] [Refill: 30D] [Max: 30K] [Start Time: Instant] [Speed: 10K/D] | 10–30000 | 0.3375 | — |
| M | 300 | 1 | jap:411 | Instagram Likes [Targeted] | Targeted | Likes only | 🇮🇳 Instagram Likes [INDIA] [Refill: 30D] [Max: 20K] [Start Time: Instant] [Speed: 3K/D] | 10–20000 | 0.275 | D |
| M | 302 | 1 | jap:7839 | Instagram Likes [Targeted] | Targeted | Likes only | 🇮🇳 Instagram Likes [INDIA] [Start Time: 0 - 1 Hour] [Speed: 5K/Day] | 20–3000 | 1.32 | — |
| M | 303 | 1 | jap:3794 | Instagram Likes [Targeted] | Targeted | Likes only | Instagram Likes [ARAB] [Refill: 30D] [Max: 20K] [Start Time: 1 Hour] [Speed: Up to 5K/Day] | 250–15000 | 3.75 | D |
| M | 304 | 1 | jap:1032 | Instagram Likes [Targeted] | Targeted | Likes only | Instagram Likes [Max: 15K] [USA 🇺🇸 ] [Refill: 90 Days] [Speed: 10K/Day] [Start Time: 0 - 1 Hours] 💧 ⛔️ ♻️ | 20–15000 | 1.375 | D |
| M | 305 | 1 | jap:3518 | Instagram Likes [Targeted] | Targeted | Likes + Impressions + Reach | 🇰🇷🇰🇵Instagram Likes [Korea] + Impressions + Reach [Refill: No] [Max: 15K] [Start Time: 1 Hour] [Speed: 5K/Day] | 20–10000 | 12.80 | — |
| M | 306 | 1 | jap:7842 | Instagram Likes [Targeted] | Targeted | Likes only | 🇭🇰 Instagram Likes [HONG KONG] [Start Time: 0 - 1 Hour] [Speed: 1K/Day] | 20–1000 | 3.36 | D |
| M | 307 | 1 | jap:1034 | Instagram Likes [Targeted] | Targeted | Likes only | Instagram Likes [10K] [UKRAINE] [1H - 10K/Day] | 20–50000 | 23.75 | — |
| M | 308 | 1 | jap:7844 | Instagram Likes [Targeted] | Targeted | Likes only | 🇰🇷 Instagram Likes [KOREA] [Start Time: 0 - 1 Hour] [Speed: 2K/Day] | 20–3000 | 3.36 | — |
| M | 309 | 1 | jap:7847 | Instagram Likes [Targeted] | Targeted | Likes only | 🇮🇷 Instagram Likes [IRAN] [Start Time: 0 - 1 Hour] [Speed: 1K/Day] | 20–7000 | 4.32 | — |
| M | 314 | 1 | jap:4207 | Instagram Likes [Targeted] | Targeted | Likes only | 🇳🇬Instagram Likes [NIGERIA] [Refill: No] [Max: 2K] [Start Time: 1 Hour] [Speed: 2K/Day] | 100–5000 | 25.00 | — |
| M | 318 | 1 | jap:1041 | Instagram Likes [Targeted] | Targeted | Likes only | Instagram Likes [MALE] [Afro-Americans] [USA] [250/Day] [NO DROP] | 30–2500 | 13.20 | — |
| M | 319 | 1 | jap:1042 | Instagram Likes [Targeted] | Targeted | Likes only | Instagram Likes [FEMALE] [Afro-Americans] [USA] [250/Day] [NO DROP] | 30–2500 | 13.20 | — |
| M | 320 | 1 | jap:7540 | Instagram Likes [Targeted] | Targeted | Likes only | 🇨🇳 Instagram Likes [CHINA] [Refill: No] [Max: 6K] [Start Time: Instant] [Speed: 3K/Day] | 20–6000 | 1.50 | — |
| M | 321 | 1 | jap:8460 | Instagram Likes [Targeted] | Targeted | Likes only | 🇯🇵 Instagram Likes [JAPAN] [Start Time: 0 - 1 Hour] [Speed: 2K/Day] | 20–1000 | 3.50 | D |
| M | 322 | 1 | jap:1237 | Instagram Likes [Targeted] | Targeted | Likes only | Instagram Likes [10K] [AFRICAN] [1H - 10K/Day] | 100–10000 | 39.50 | — |
| M | 323 | 1 | jap:8227 | Instagram Likes [Targeted] | Targeted | Likes only | Instagram Likes [ARAB-GULF] [Max: 50K] [Refill: 30 Days] [Start Time: 0 - 1 Hours] [Speed: 500/Day] | 5–2500 | 1.035 | R |
| M | 324 | 1 | jap:8228 | Instagram Likes [Targeted] | Targeted | Likes only | Instagram Likes Female [ARAB-GULF] [Max: 50K] [Refill: 30 Days] [Start Time: 0 - 1 Hours] [Speed: 500/Day] | 50–10000 | 2.7875 | RC |
| M | 325 | 1 | jap:5825 | Instagram Likes Per Minute | Controlled rate | Likes only | Instagram Likes [1 Like Per Minute] [Max: 10K] [Start Time: 0-1 Hour] | 20–10000 | 1.35 | — |
| M | 326 | 1 | jap:5820 | Instagram Likes Per Minute | Controlled rate | Likes only | Instagram Likes [5 Likes Per Minute] [Max: 10K] [Start Time: 0-1 Hour] | 20–10000 | 1.35 | — |
| M | 327 | 1 | jap:5821 | Instagram Likes Per Minute | Controlled rate | Likes only | Instagram Likes [10 Likes Per Minute] [Max: 10K] [Start Time: 0-1 Hour] | 20–10000 | 1.35 | — |
| M | 328 | 1 | jap:5822 | Instagram Likes Per Minute | Controlled rate | Likes only | Instagram Likes [25 Likes Per Minute] [Max: 10K] [Start Time: 0-1 Hour] | 20–10000 | 1.35 | — |
| M | 329 | 1 | jap:5823 | Instagram Likes Per Minute | Controlled rate | Likes only | Instagram Likes [50 Likes Per Minute] [Max: 10K] [Start Time: 0-1 Hour] | 20–10000 | 1.35 | — |
| M | 330 | 1 | jap:5824 | Instagram Likes Per Minute | Controlled rate | Likes only | Instagram Likes [60 Likes Per Minute] [Max: 10K] [Start Time: 0-1 Hour] | 20–10000 | 1.35 | — |
| M | 331 | 1 | jap:5826 | Instagram Likes Per Minute | Controlled rate | Likes + Impressions | Instagram Likes + Impressions [1 Like Per Minute] [Max: 10K] [Start Time: 0-1 Hour] | 20–10000 | 1.50 | — |
| M | 332 | 1 | jap:5827 | Instagram Likes Per Minute | Controlled rate | Likes + Impressions | Instagram Likes + Impressions [5 Likes Per Minute] [Max: 10K] [Start Time: 0-1 Hour] | 20–10000 | 1.50 | — |
| M | 333 | 1 | jap:5828 | Instagram Likes Per Minute | Controlled rate | Likes + Impressions | Instagram Likes + Impressions [10 Likes Per Minute] [Max: 10K] [Start Time: 0-1 Hour] | 20–10000 | 1.50 | — |
| M | 334 | 1 | jap:5829 | Instagram Likes Per Minute | Controlled rate | Likes + Impressions | Instagram Likes + Impressions [25 Likes Per Minute] [Max: 10K] [Start Time: 0-1 Hour] | 20–10000 | 1.50 | — |
| M | 335 | 1 | jap:5830 | Instagram Likes Per Minute | Controlled rate | Likes + Impressions | Instagram Likes + Impressions [50 Likes Per Minute] [Max: 10K] [Start Time: 0-1 Hour] | 20–10000 | 1.50 | — |
| M | 336 | 1 | jap:5831 | Instagram Likes Per Minute | Controlled rate | Likes + Impressions | Instagram Likes + Impressions [60 Likes Per Minute] [Max: 10K] [Start Time: 0-1 Hour] | 20–10000 | 1.50 | — |
| M | 1262 | 1 | jap:954 | Instagram Auto Likes | Auto Likes — boundary review | Likes only | Instagram Auto Likes [Max: 100K] [Start Time: 0-1 Hours] [Speed: 20K/Day] | 100–2500000 | 0.13 | CD |
| M | 1323 | 1 | jap:6107 | Instagram Western Europe + USA Services 🇪🇺 🇬🇧 🇺🇸 | USA special category | Likes only | 🇺🇸 Instagram Likes [USA] [Algorithm Tricking] [Refill: Auto - 30D] [Max: 5K] [Start Time: 0 - 1 Hr] [Speed: 5K/D] | 10–20000 | 4.16 | — |
| O | 11622 | 1 | jap:4356 | Instagram Likes | General Likes | Likes only | Instagram Likes [Refill: 365D] [Max: 2K] [Start Time: 0 - 1 Hr] [Speed: Up to 10K/D] 💧 | 10–10000000 | 0.2125 | RC |
| O | 11665 | 1 | jap:109 | Instagram Likes [Targeted] | Targeted | Likes only | Instagram Likes [ARAB -  عرب متفاعلين] [Refill: 90 Days] [Max: 500] [Start Time: 0 -12 Hours] [Speed: 500/Day] 💧♻️ | 5–2500 | 1.1025 | R |
| O | 11666 | 1 | jap:8785 | Instagram Likes [Targeted] | Targeted | Likes only | 🇸🇦Instagram Likes [ARAB] [SUPER REAL] [Refill: No] [Max: 2K] [Start Time: 0-3 Hrs] [Speed: 500/Day] | 5–2500 | 0.96 | — |
| S | 310 | — | — | — | Stale | — | No current registry row | — | — | — |
| S | 311 | — | — | — | Stale | — | No current registry row | — | — | — |
| S | 312 | — | — | — | Stale | — | No current registry row | — | — | — |
| S | 313 | — | — | — | Stale | — | No current registry row | — | — | — |
| S | 315 | — | — | — | Stale | — | No current registry row | — | — | — |
| S | 316 | — | — | — | Stale | — | No current registry row | — | — | — |
| S | 317 | — | — | — | Stale | — | No current registry row | — | — | — |
