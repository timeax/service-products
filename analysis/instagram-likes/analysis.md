# Instagram Likes — mapping refresh analysis (approved for definition)

Reanalyzed 2026-11-15 after the latest `catalog-handler-service-ids.json` update. The user approved ProductDefinition work on 2026-11-15. Earlier reviews remain in dated files for history.

## Current scope and source status

- `handler services.json` has 5,734 records. It is a bare array without site/project name metadata. Relevant rows carry provider panel key `jap` and last-seen sync on 2026-11-13 UTC. The target site's identity is not encoded in the file.
- `catalog-handler-service-ids.json` now maps **226 unique IDs** to `instagram-likes-likes`. All 226 resolve to current rows; there are **zero stale IDs and zero duplicate IDs**. Every resolved mapped row is `is_enabled: true`, `is_locked: false`, `state_reason: null`, and `payload.type: Default` in this snapshot. This registry state does not prove service health or customer-facing availability.
- The map is a service-family candidate list, not proof every row fulfills the same customer order. Newly included rows cross category and target boundaries; preserve their distinctions in analysis.
- At analysis time, the catalog service was `not_started`; after approval, `products/instagram-likes.json` was created and the catalog is now `definition_created`. Threads Likes is a separate catalog service; Instagram Packages is also separate.
- Root registry `id` is what the catalog mapping lists and is used for ProductDefinition `service_id` bindings. `dgp_handler_id` and provider `external_id` remain distinct and are not used as service IDs. This follows the local HandlerService contract and the catalog map; target tenant metadata is still absent from the supplied registry.
- `.ai/README.md`, `WORKFLOW.md`, `DATA-MODEL.md`, `VALIDATION.md`, `agent-search.json`, the Builder snapshot dated 2026-11-13 (version unspecified), local `@elqora/dgp-spec` 1.6.0, and SDK state semantics were inspected. The example fixture informed the tag/fallback method only, not current service facts.

## Reconciliation of updated mapping

| Current raw category | Mapped rows | Notes |
| --- | ---: | --- |
| Instagram Likes | 96 | General family category; includes claims and bundles |
| Instagram Likes [BOTS] | 49 | 48 Likes-only and one Likes + Impressions |
| Instagram Likes [Targeted] | 43 | Geographic/audience claims; some bundles |
| Instagram Likes Per Minute | 12 | Six Likes-only; six also include Impressions |
| Instagram ENGAGEMENT Services | 14 | Includes named RAL/RAU, USA, female, and POWER claims |
| Instagram Engagement | 1 | Row 1152 says Likes from Verified Accounts |
| Instagram Comments | 3 | Comment Likes requiring a comment target; IDs 849, 850, 901 |
| Instagram Followers &amp; Likes [BOTS with NO REFILL] [CAN FULLY DROP] | 5 | Likes with profile pictures/posts, mixed category with Followers |
| Instagram TOP Services [EXCLUSIVE] | 1 | USA Likes row 46 |
| Instagram Western Europe + USA Services 🇪🇺 🇬🇧 🇺🇸 | 1 | USA Likes row 1323 |
| Instagram Auto Likes | 1 | Row 1262; Auto Likes category, but `type: Default` |

The 23 rows added beyond the prior 203 live mappings are `687–703` (14 current rows in the ENGAGEMENT category; not every integer in that span is present), `849, 850, 901, 1152, 1181–1184, 1186`. The root mapping is now complete for its included IDs, but direct Likes-category current rows still missing are `182, 11622, 267, 11665, 11666`. These are not automatically excluded from future consideration: they are unmapped and should be reviewed before handler assignment. Additional adjacent rows remain unmapped: 83 Auto Likes, five latest-post Power Likes (`337–341`, mapped to Instagram Packages), two Threads Likes (`25–26`, mapped to Threads Likes), and six Followers rows in the mixed Followers/Likes bot category (`1180, 1185, 1187–1190`).

## 2. Analyze and normalize variants

### Product family boundaries

Treat **likes on one Instagram post/content target** as the central service hypothesis, pending confirmation of accepted URL/content types in the target Builder. The updated mapping includes other target objects and order scopes, so keep the following outside a plain post-Likes fallback pool unless the site confirms identical input and outcome:

- **Comment Likes** (`849, 850, 901`): target is a comment link/specific comment, not simply the post. This is a distinct target/input shape and likely a separate family or explicit sub-service.
- **Auto Likes** (`1262`): category says Auto Likes; future-post behavior is possible but not proven. Its `Default` type does not establish that it accepts a single post target. Hold outside standard pool pending input/order confirmation.
- **Verified-account Likes** (`1152`): explicit verified-account promise. Keep as a distinct choice/pool unless the customer explicitly selects this claim.
- **Likes with Impressions/Reach**: extra delivered outcomes make these bundles; never use as fallback for plain Likes. The name does not give quantities for extra outcomes.
- **Latest-post package** (`337–341`) and **Threads Likes** (`25–26`): separate order/service scopes; not included in the current map and remain distinct catalog entries.

For ordinary post Likes, the example’s analysis groups remain useful as **overlapping tag viewpoints**: Standard, Quality, Bot, Targeted, Gender-targeted, Refill-eligible, Retention, Priority delivery, Controlled speed, Combined engagement, and Other/unresolved. A row may have several attributes at once. Use the customer promise as the primary grouping key, then attach all evidenced qualifiers; do not force every handler into one exclusive bucket.

### Meaningful customer-choice dimensions

| Viewpoint | Evidence and current interpretation | Effect on fallback eligibility |
| --- | --- | --- |
| Standard Likes | Baseline cohort should mean Likes-only, ordinary post target, with no added target/account/quality/speed promise. Many names in the general category still carry refill, speed, quality, or retention claims. | Do not treat every general-category row as equivalent standard capacity. Establish the promise first, then admit compatible candidates. |
| Quality | HQ/MQ/LQ, quality, real/real-looking, exclusive, POWER, natural increase, and RAL/RAU labels occur. | Keep source claims intact; no common verified quality scale is defined. Match only equivalent customer claims. |
| Bot/account | 49 mapped `[BOTS]` rows plus five mixed-category Likes with profile pictures/posts, explicit no-refill/full-drop wording. | Preserve bot/profile claims and retention constraints. Mixed rows need confirmation that fulfillment target/input is still the same post. |
| Geography/audience | Targeted category and other names include country/region, male/female, and combinations; USA rows also occur in special categories and general category. | Exact geography and demographics must match. Broad, narrow, and mixed-region claims are not interchangeable. |
| Refill-eligible | Use structured `payload.capabilities.refill.enabled` for operational support. Names may state duration or auto-refill separately. | Capability is required for refill support; duration/guarantee must match as a separate promise. |
| Retention | Names contain non-drop, low-drop, no-drop, and numeric drop claims. | These claims are separate from refill capability. Keep exact wording evidence; do not strengthen it. |
| Priority delivery | Names advertise instant, fast, emergency, and start/speed periods. | Match only when delivery timing is part of the selected customer promise; registry name alone is not a measured SLA. |
| Controlled speed | 12 per-minute rows: `325–330` Likes-only; `331–336` Likes + Impressions. | Match exact advertised rate and outcome. All 12 have `dripfeed.enabled: false`; fixed-rate service is not drip-feed capability. |
| Combined engagement | Mapped bundles are identified by name and listed in the cohort table. | Match exact contents. No bundle substitutes for plain Likes or a different bundle. |
| Other/unresolved | Use only for a named, reviewed cohort whose customer meaning is known. Comment Likes, verified-account, Auto Likes, and mixed-package targets are called out above. | Never use as a catch-all fallback for unreviewed rows. |

### Named outcome cohorts (all 226 mapped IDs)

| Cohort | Likes only | Likes + Impressions | Likes + Impressions + Reach |
| --- | ---: | ---: | ---: |
| General Likes | 89 | 3 | 4 |
| Bot/account | 48 | 1 | 0 |
| Targeted | 40 | 1 | 2 |
| USA/special source categories | 2 | 0 | 0 |
| Controlled rate | 6 | 6 | 0 |
| Auto Likes, boundary review | 1 | 0 | 0 |
| Cross-category Likes with profile picture/posts | 5 | 0 | 0 |
| Comment Likes | 3 | 0 | 0 |
| Verified-account Likes | 1 | 0 | 0 |
| ENGAGEMENT-category variants | 14 | 0 | 0 |
| **Total** | **209** | **11** | **6** |

The **209 Likes-only names include 17 rows whose target/account/order promise requires separate treatment** (Comment Likes, Auto Likes, Verified-account Likes, mixed profile/post bot Likes, and cross-category ENGAGEMENT claims). This is why the count is not a standard fallback pool.

### Candidate fallback strategy under high failure assumptions

The concern that many of the 200+ handlers may fail is a planning scenario, not an observed reliability statistic. The registry has no success rate, uptime, or health probe. Keep broad candidate pools while analyzing, then narrow each pool by promise compatibility. For a given order, an eligible fallback must match:

1. The target/input shape (post vs comment vs future/automatic; same accepted URL format).
2. Delivered outcome (Likes-only vs Impressions/Reach bundle and exact contents).
3. Explicit account, verification, geography, or audience claim.
4. Refill/retention and delivery-speed claims that are part of the chosen option.
5. Operational capabilities required and payload min/max covering the order quantity.

Once each candidate pool is confirmed, the ProductDefinition can specify ordered fallbacks where contract semantics support them. The current registry does not justify ranking primaries by rate, ID, or “enabled” state: all 226 mapped rows are enabled/unlocked, which is not runtime health evidence. Preserve multiple compatible alternatives for a promise where available; don’t count incompatible variants toward resilience.

### Quantity conflicts and payload rule

Use structured `payload.min` and `payload.max` as operational order bounds, per the owner’s direction. Do not replace these with conflicting numbers embedded in service names. Keep the source name in the appendix for audit, and avoid repeating its conflicting quantity in customer copy unless the owner later confirms it represents an additional cap. Refill is separate: the payload capability flag indicates support; a named duration/guarantee requires its own evidence. Across the 226 mapped rows, rates are source registry rates, not final customer prices. Structured bounds, rates, and flags are listed row by row below.

### Builder field plan and unresolved choices

The current saved Builder snapshot supports `text/default` and `number/default` scalar inputs, and `select/default` as a single-choice input with options. Provisional inputs are a target URL/link and quantity plus one explicit variant selection. The saved Quantity template is a required `number` field named `quantity`, with placeholder `e.g. 100`, dynamic Min/Max preview tags, description “The number of units requested for this order.”, base pricing role, quantity binding `value_by: value` / `multiply: 1`, and template validation 10–10,000,000. Reuse the appropriate field shape/preview tags as confirmed in the target Builder, but use the selected handler's payload min/max for actual bounds; the template's numeric bounds and editor metadata are not universal.

**Drip-feed plan:** the inspected Ordering preview API supports visibility expressions against the current `preview`, including selected handler records in `preview.service_context`. A field expression can gate the toggle on the selected service capability, for example `preview.service_context.length > 0 && preview.service_context.every(service => service.capabilities?.dripfeed?.enabled === true)`. Using `every` keeps a multi-service selection hidden if even one selected service lacks drip-feed. Gate the runs/interval fields on both the same capability condition and the drip-feed toggle being on. In the updated 226-row map, **143** rows have drip-feed enabled and **83** do not. All 12 per-minute rows (`325–336`) have drip-feed disabled; per-minute delivery does not qualify a handler for the drip-feed controls. Fallback candidates for an order with drip-feed enabled must also support drip-feed, or be excluded from that order's eligible fallback pool.

Important distinction: `preview.service_context` is available while the Ordering preview evaluates visibility; the finalized portable `OrderSnapshot` removes `service_context`. The snapshot still contains selected `service_ids` and fallback mappings, but not the handler capability records. Thus expressions can inspect the selected handler's capabilities before submission, not look up capabilities from the final snapshot alone. The exact expression is supported by the installed local contract/runtime; recheck the open Builder if its version has changed. Hidden-field omission should be confirmed against the target Ordering behavior before relying on it for submission.

Accepted URL/content types, service binding IDs, tag graph, quantity selection behavior, and hidden-field submission need target Builder/runtime verification before authoring. Visibility expressions themselves are supported as described above. Do not copy template metadata from the saved Quantity authoring artifact. No publication policy changes are proposed.

Before ProductDefinition work, review: (1) whether Comment Likes, Auto Likes, Verified-account Likes, and profile/post bot Likes belong in this customer-facing scope or separate services; (2) which overlapping tag viewpoints/options customers should see; (3) whether named quality/retention/delivery claims are intended promises; (4) which rows are exact compatible fallback candidates for each chosen promise; (5) the target registry identity and Builder service binding.

## Appendix: complete mapped row evidence

Each mapped row is listed once with root ID, DGP handler ID, provider external ID, original source category/name, named outcome, payload min/max, rate, and enabled capabilities (`R` refill, `C` cancel, `D` dripfeed, `K` contract). Source `id` fields are preserved; outcomes are interpreted from the row name and should be reviewed before customer copy.

| Root ID | DGP handler ID | External ID | Raw category | Outcome | Source name | Payload min–max | Rate | Enabled caps |
| ---: | ---: | --- | --- | --- | --- | ---: | ---: | --- |
| 46 | 1 | jap:9131 | Instagram TOP Services [EXCLUSIVE] | Likes only | 🇺🇸 Instagram Likes [USA] [Algorithm Tricking] [Refill: Auto - 30D] [Max: 1K] [Start Time: 0 - 1 Hr] [Speed: 5K/D] | 5–50000 | 2.08 | C |
| 127 | 1 | jap:1837 | Instagram Likes | Likes only | Instagram Likes [Refill: No] [Max: 1M] [Start Time: 0-1 Hr] [Speed: Up to 300K/D]💧 | 10–10000000 | 0.125 | D |
| 128 | 1 | jap:10237 | Instagram Likes | Likes only | Instagram Likes [Refill: No] [Max: 1M] [Start Time: 0 - 1 Hr] [Speed: 200K/D] 💧 | 10–3000000 | 0.175 | CD |
| 129 | 1 | jap:4343 | Instagram Likes | Likes only | Instagram Likes [Refill: No] [Max: 5M] [Start Time: 0 - 1 Hr] [Speed: 100K/D] ⛔💧 | 10–10000000 | 0.275 | CD |
| 130 | 1 | jap:1700 | Instagram Likes | Likes only | Instagram Likes [Refill: No] [Max: 500K] [Start Time: 0 - 1 Hr] [Speed: Up to 100K/D] 💧⛔ | 10–500000 | 0.1375 | D |
| 131 | 1 | jap:10296 | Instagram Likes | Likes only | Instagram Likes [Refill: 30D] [Max: 1M] [Start Time: 0 - 1 Hr] [Speed: 100K/D] 💧 | 100–1000000 | 0.1625 | D |
| 132 | 1 | jap:10126 | Instagram Likes | Likes only | Instagram Likes [Refill: 30D] [Max: 1.5M] [Start Time: 0 - 1 Hr] [Speed: Up to 100K/D] ⛔💧 | 10–1000000 | 0.2375 | CD |
| 133 | 1 | jap:10065 | Instagram Likes | Likes only | Instagram Likes [Refill: 30D] [Max: 500K] [Start Time: 0 - 1 Hr] [Speed: Up to 100K/D] 💧⛔♻️ | 10–500000 | 0.20 | D |
| 134 | 1 | jap:3866 | Instagram Likes | Likes only | Instagram Likes [Refill: No] [Max: 100K] [Start Time: 0 - 2 Hrs] [Speed: 100K/D]💧⛔️ | 10–100000 | 0.3625 | CD |
| 135 | 1 | jap:3242 | Instagram Likes | Likes only | Instagram Likes [Refill: 30D] [Max: 500K] [Start Time: 0-1 Hour] [Speed: 50K/D] 💧⛔♻️ | 10–200000 | 0.4125 | C |
| 136 | 1 | jap:1869 | Instagram Likes | Likes only | Instagram Likes [HQ] [Refill: No] [Max: 300K] [Start Time: 0-1 Hr] [Speed: 25k/D] 💧⛔ | 10–1000000 | 0.175 | CD |
| 137 | 1 | jap:8505 | Instagram Likes | Likes only | Instagram Likes [Refill: No] [Max: 1M] [Start Time: 0 - 2 Hrs] [Speed: Up to 50K/Day]💧 | 10–1000000 | 0.4875 | D |
| 138 | 1 | jap:10377 | Instagram Likes | Likes only | Instagram Likes [Refill: No] [Max: 5K] [Start Time: 0 - 1 Hr] [Speed: 500/D] 💧⛔️ | 10–5000 | 1.0625 | CD |
| 139 | 1 | jap:10442 | Instagram Likes | Likes only | Instagram Likes [Refill: 30D - Auto] [Max: 100K] [Start Time: 0 - 1 Hr] [Speed: 20K/D] 💧⛔♻️ | 10–1000000 | 0.125 | CD |
| 140 | 1 | jap:1845 | Instagram Likes | Likes only | Instagram Likes [HQ] [NON DROP] [Max: 25K] [Start Time: 0-1 Hr] [Speed: 5K/Hr] 💧⛔ | 100–25000 | 1.5625 | D |
| 141 | 1 | jap:1761 | Instagram Likes | Likes only | Instagram Likes [TOP QUALITY] [Refill: 30D] [60K] [Start Time: 0 - 1 Hr] [Speed: 60K/D] ♻️🔥 | 50–60000 | 1.4836 | D |
| 142 | 1 | jap:10066 | Instagram Likes | Likes only | Instagram Real Likes [Refill: 365] [Max: 100K] [Start Time: 0 - 1 Hr] [Speed: 20K/D] 💧⛔♻️ | 10–10000000 | 0.286 | CD |
| 143 | 1 | jap:8219 | Instagram Likes | Likes only | Instagram Likes [Refill: No] [Max: 150K] [Start Time: 0-1 Hour] [Speed: 100K/Day] ⛔💧 | 10–300000 | 0.1875 | CD |
| 144 | 1 | jap:8650 | Instagram Likes | Likes only | Instagram Likes [Refill: No] [Max: 100K] [Start Time: 0-1 Hr] [Speed: 100K/Day] ⛔ 💧 | 100–2500000 | 0.13 | CD |
| 145 | 1 | jap:1823 | Instagram Likes | Likes only | Instagram Likes [Max: 50K] [Start Time: 0-1 Hr] [Speed: 1K/Hour] ⛔🔥💧 | 10–150000 | 0.2375 | C |
| 146 | 1 | jap:1782 | Instagram Likes | Likes only | Instagram Likes [Max: 10K] [Start Time: 0-1 Hr] [Speed: 5K/Hr] 💧⛔ | 50–1000000 | 0.1875 | CD |
| 147 | 1 | jap:1805 | Instagram Likes | Likes only | Instagram Likes [Max: 100K] [Start Time: 0-1 Hr] [Speed: 25K/D] 💧⛔ | 10–100000 | 0.6875 | CD |
| 148 | 1 | jap:4289 | Instagram Likes | Likes only | Instagram Likes [HQ] [FEW DROPS] [Refill: 30D] [Max: 100K] [Speed: 10K/D]💧⛔ | 30–500000 | 0.1238 | D |
| 149 | 1 | jap:4173 | Instagram Likes | Likes only | Instagram Likes [Refill: 30] [Max: 30K]  [Start Time: 0 - 1 Hr] [Speed: 30K/Day] | 10–1000000 | 0.1413 | RCD |
| 150 | 1 | jap:1813 | Instagram Likes | Likes only | Instagram Likes [HQ] [Max: 10K] [Start Time: 0-1 Hr] [Speed: 10K/D] 💧 | 10–10000 | 0.40 | CD |
| 151 | 1 | jap:8966 | Instagram Likes | Likes only | Instagram Likes [Refill: No] [Max: 5K] [Start Time: 0 - 1 Hr] [Speed: 500/D] 💧⛔️♻️ | 20–6000 | 0.375 | RCD |
| 152 | 1 | jap:6094 | Instagram Likes | Likes only | Instagram Likes [WITH CANCELATION] [Max: 5K] [Start Time: 0-1 Hour] [Speed: INSTANT] 💧⚡⛔🔥 | 10–300000 | 0.225 | CD |
| 153 | 1 | jap:8216 | Instagram Likes | Likes only | Instagram Likes [Refill: NO REFILL ] [Max: 100K] [Start Time: 0-1 Hour] [Speed: 300K/Day] ⚡⛔💧 | 10–300000 | 0.1125 | C |
| 154 | 1 | jap:7788 | Instagram Likes | Likes only | Instagram Likes [Refill: 90D] [Max: 150K] [Start Time: 0-1 Hr] [Speed: 150K/Day] ♻️ ⛔ 💧 | 10–100000 | 0.1609 | D |
| 155 | 1 | jap:7563 | Instagram Likes | Likes only | Instagram Likes [Max: 10K] [Refill: No] [Start Time: 0 - 1 Hour] [Speed: 10K/Hour] 💧 | 10–300000 | 0.1125 | C |
| 156 | 1 | jap:7795 | Instagram Likes | Likes only | Instagram Likes [Refill: No] [Max: 80K] [Start Time: 0 - 1 Hour] [Speed: 80K/Day] 💧 | 10–500000 | 0.225 | C |
| 157 | 1 | jap:6372 | Instagram Likes | Likes only | Instagram Likes [Refill: No] [Low Drops] [Max: 200K] [Start Time: 0-1 Hour] [Speed: 100K/D] ⚡⛔ | 50–300000 | 0.225 | C |
| 158 | 1 | jap:6126 | Instagram Likes | Likes only | Instagram Likes [Max: 200K] [Refill: 30Days] [Start Time: 0 - 2 Hours] [Speed: 10K/Day] ⛔💧 | 10–150000 | 0.2375 | C |
| 159 | 1 | jap:7742 | Instagram Likes | Likes only | Instagram Likes [Max: 100K] [Refill: 30] [Start Time: 0 - 1 Hour] [Speed: 30K/Hour] | 10–20000 | 0.4125 | C |
| 160 | 1 | jap:1794 | Instagram Likes | Likes only | Instagram Likes [Refill: 30D] [Max: 250K] [Start Time: 0-1 Hr] [Speed: 50K/Day] | 10–300000 | 0.2375 | CD |
| 161 | 1 | jap:3336 | Instagram Likes | Likes + Impressions + Reach | Instagram Likes + Reach + Impressions [Refill: 30] [Max: 10K] [Start Time: 0 - 1 Hour] [Speed: 10K/Day] 💧 | 10–100000 | 0.30 | RC |
| 162 | 1 | jap:6361 | Instagram Likes | Likes only | Instagram Likes [Refill: No] [Max: 200K] [Start Time: 0-1 Hour] [Speed: 100K/Day] ⚡ | 50–100000 | 0.1114 | — |
| 163 | 1 | jap:6001 | Instagram Likes | Likes only | Instagram Likes [Refill: No / Low Drops] [Max: 150K] [Start Time: Instant] [Speed: 100K/Day] ⛔ | 50–200000 | 0.35 | C |
| 164 | 1 | jap:5956 | Instagram Likes | Likes only | Instagram Likes [Refill: 30D] [Max: 200K] [Start Time: Instant] [Speed: Up to 100K/D] 💧⛔️♻️ | 10–200000 | 0.225 | C |
| 165 | 1 | jap:7787 | Instagram Likes | Likes only | Instagram Likes [Refill: 30D] [Max: 100K] [Start Time: Instant - 1 Hour] [Speed: 30K/D] ⚡💧⛔️ | 10–100000 | 0.3125 | RCD |
| 166 | 1 | jap:7750 | Instagram Likes | Likes only | Instagram Likes [80% FEMALE] [Refill: LIFETIME GUARANTEED]  [Max: 25K] [Start Time:  Instant] [Speed: 10K/Hour] | 100–1000000 | 0.5625 | C |
| 167 | 1 | jap:6562 | Instagram Likes | Likes only | Instagram Likes [Refill: Auto-Refill 30 Days] [50K] [HQ] [Start Time: Instant] [Speed: 30K/Day] 💧⛔️♻️ | 10–50000 | 0.2063 | RCD |
| 168 | 1 | jap:7585 | Instagram Likes | Likes only | Instagram Likes [Max: 50K] [Start Time: 0 - 1 Hours] [Speed: 50K Per Day] 💧⛔ | 10–50000 | 0.3528 | C |
| 169 | 1 | jap:983 | Instagram Likes | Likes only | Instagram HQ Likes [Max: 100K] [Start Time: 0 - 1 Hour] [Speed: 10K/Day] 💧 | 10–20000 | 0.749 | RCD |
| 170 | 1 | jap:7508 | Instagram Likes | Likes only | Instagram Likes [Refill: 30D Auto] [Max: 100K] [Start Time: 0-1 Hr] [Speed: Up to 50K/D] | 50–100000 | 0.1188 | RCD |
| 171 | 1 | jap:7532 | Instagram Likes | Likes only | Instagram Likes [Refill: 30D] [200K] [Start Time: Instant] [Speed: 10K/D] ♻️💧⛔ | 50–200000 | 0.2503 | RCD |
| 172 | 1 | jap:1777 | Instagram Likes | Likes only | Instagram Likes [NO REFILL] [Max: 150K] [Start Time: 5 Minute] [Speed: 1K/Hour]💧🔥 | 50–150000 | 0.081 | CD |
| 173 | 1 | jap:6286 | Instagram Likes | Likes + Impressions + Reach | Instagram Likes + Reach + Impressions [Refill: 30D] [200K] [Start Time: Instant] [Speed: 25K/D] ♻️💧⛔️ | 10–200000 | 0.2001 | C |
| 174 | 1 | jap:1883 | Instagram Likes | Likes + Impressions | Instagram Likes + Impressions [Max: 45K] [Start Time: 0-1 Hr] [Speed: INSTANT]  🔥🔥🔥 | 10–500000 | 0.6875 | D |
| 175 | 1 | jap:7117 | Instagram Likes | Likes only | Instagram Likes [Refill: No] [Max: 200K] [Start Time: 0-1 Hour] [Speed: 200K/Day] ⚡⛔ | 10–200000 | 0.2375 | CD |
| 176 | 1 | jap:1788 | Instagram Likes | Likes only | Instagram Likes [Max: 200K] [Start Time: 1 Hour] [Speed: 50K/Day] 💧⛔️ | 50–200000 | 0.075 | CD |
| 177 | 1 | jap:6689 | Instagram Likes | Likes only | Instagram Likes [Refill: Auto 30 Days] [Start Time: 2 Hours] [Speed: 50k/Day]💧⛔️♻️ | 50–200000 | 0.10 | RCD |
| 178 | 1 | jap:7583 | Instagram Likes | Likes only | Instagram Likes [Max: 50K] [Start Time: 0-1 Hour] [Speed: INSTANT] 💧⚡🔥⛔ | 50–50000 | 0.1016 | CD |
| 179 | 1 | jap:1957 | Instagram Likes | Likes only | Instagram Likes [HQ][Refill: 30D] [Max: 30K] [Start Time: 0-1 Hr] [Speed: 10K/D] | 10–30000 | 0.3375 | D |
| 180 | 1 | jap:6582 | Instagram Likes | Likes + Impressions + Reach | Instagram Likes + Impressions + Reach [Max: 45K] [Start Time: Instant] [Speed: 30K/Day] ⚡ | 10–500000 | 1.1444 | D |
| 181 | 1 | jap:1768 | Instagram Likes | Likes + Impressions | Instagram Likes + Impressions [HQ] [Max: 7K] [Start Time: Instant] [Speed: 7K/Day]💧🔥 | 10–100000 | 0.1609 | D |
| 183 | 1 | jap:3343 | Instagram Likes | Likes only | Instagram Likes [Refill: No] [Max: 3K/order 30k/link] [Start Time: 0-12 Hours] | 50–30000 | 0.348 | CD |
| 184 | 1 | jap:1769 | Instagram Likes | Likes only | Instagram Likes [EXCLUSIVE - Up to 15% Drop Max] [Refill: 30 Days] [Max: 5K] [Start Time: 0-1 Hour] [Speed: 2K/Hour] 💧 | 10–8000 | 0.0756 | CD |
| 185 | 1 | jap:4394 | Instagram Likes | Likes only | Instagram Likes [Refill: 30D] [Max: 500K] [Start Time: 0-1 Hour] [Speed: 20K/Hour] 🔥⚡⚡⚡⛔ | 10–500000 | 0.50 | CD |
| 186 | 1 | jap:5628 | Instagram Likes | Likes only | Instagram Likes [Drops 5-7%] [Refill: 30D] [Max: 10K] [Start Time: 0-1 Hour [Speed: 1-2K/Hour] | 10–10000 | 0.20 | C |
| 187 | 1 | jap:5629 | Instagram Likes | Likes only | Instagram Likes [Drops 5-7%] [Refill: No] [Max: 5K] [Start Time: 0-1 Hour]  [Speed: 1-2K/Hour] | 50–100000 | 0.081 | CD |
| 188 | 1 | jap:5630 | Instagram Likes | Likes only | Instagram Likes [Drops LOW] [Refill: AR30D] [Max: 50K] [Start Time: 0-1 Hour] [Speed: 10K/D]♻️💧⛔ | 1–200000 | 0.5625 | RC |
| 189 | 1 | jap:3592 | Instagram Likes | Likes only | Instagram Likes [Refill: 30D] [Max: 10K] [Start Time: 0-1 Hour] [Speed: 1K+/Hour]💧♻️⛔ | 10–50000 | 0.50 | CD |
| 190 | 1 | jap:5631 | Instagram Likes | Likes only | Instagram Likes [Refill: 30D - AUTO] [Max: 100K] [Start Time: 0-1 Hr] [Speed: Up to 10K/D] 💧⛔️♻️ | 10–100000 | 0.30 | RCD |
| 191 | 1 | jap:3019 | Instagram Likes | Likes only | Instagram Likes [SUPER] [Refill: No] [Max:10K] [Start Time: 0-1 Hour] [Speed: 3K/Hour] | 10–1000000 | 0.1246 | C |
| 192 | 1 | jap:3349 | Instagram Likes | Likes only | Instagram Likes [Max: 150K] [Start Time: 0-1 Hour] [Speed: 5K/Day] 💧♻️🔥🔥 | 10–130000 | 0.247 | C |
| 193 | 1 | jap:5560 | Instagram Likes | Likes + Impressions | Instagram Likes + Impressions [Max: 2K] [Start Time: 1 Hour] [Speed: 2K/Day] ⚡ | 10–100000 | 0.1609 | D |
| 194 | 1 | jap:8442 | Instagram Likes | Likes only | Instagram Likes [Refill: 30 Days] [Max: 40K] [Start Time: 0-1 Hour] [Speed: Up to 15K/Day] 💧♻️ | 10–75000 | 0.7201 | D |
| 195 | 1 | jap:5670 | Instagram Likes | Likes only | Instagram Likes [Max: 10K] [Start Time: 0-1 Hour] [Speed: INSTANT] 💧⚡⚡⚡🔥 | 20–30000 | 0.35 | C |
| 196 | 1 | jap:3792 | Instagram Likes | Likes only | Instagram Likes [NON DROP] [Max: 8K] [Start Time: 0-1 Hour] [Speed: 8K/Day] 💧🔥🔥 | 10–1000000 | 0.2318 | CD |
| 197 | 1 | jap:1778 | Instagram Likes | Likes only | Instagram Likes [30K] [REAL ] [1H - 1k/Day] 💧⚡ | 5–50000 | 2.00 | C |
| 198 | 1 | jap:3788 | Instagram Likes | Likes only | Instagram Likes [Max: 10K] [Start Time: 0-1 Hour] [Speed: 10K/Day] | 10–10000000 | 0.51 | C |
| 199 | 1 | jap:8036 | Instagram Likes | Likes only | Instagram Likes [Refill: 365 Days] [Max: 10K] [Start Time: 0-1 Hours] [Speed: 10K/Day] 💧⛔ | 10–10000000 | 0.1788 | CD |
| 200 | 1 | jap:1789 | Instagram Likes | Likes only | Instagram Likes [Refill: 30D] [Max: 50K] [Start Time: 0-1 Hr] [Speed: 20K/Day] 💧♻️ | 10–100000 | 0.275 | D |
| 201 | 1 | jap:1916 | Instagram Likes | Likes only | Instagram Likes [Refill: No] [Max: 5K] [Start Time: 0-1 Hour] [Speed: 2K/Day] | 20–10000 | 1.35 | RCD |
| 202 | 1 | jap:1776 | Instagram Likes | Likes only | Instagram Likes [Refill: No] [Max: 200K] [Start Time: 0-1 Hour] [Speed: 100K/Day] ⛔💧 | 10–200000 | 0.2375 | CD |
| 203 | 1 | jap:3585 | Instagram Likes | Likes only | Instagram Likes [NON DROP] [Max: 5K] [Start Time: 0-1 Hour] [Speed: 500/Hour] | 20–5000 | 1.035 | CD |
| 204 | 1 | jap:3525 | Instagram Likes | Likes only | Instagram Likes [EXCLUSIVE] [NON DROP] [Max: 10K] [Start Time: 0-1 Hour] [Speed: 1K/Hour] | 50–10000 | 1.104 | CD |
| 205 | 1 | jap:4127 | Instagram Likes | Likes only | Instagram Likes [EMERGENCY] [NON DROP] [Max: 5K] [Start Time: 0-1 Hour] [Speed: 2K/Hour] 🔥🔥🔥 | 50–5000 | 1.15 | CD |
| 206 | 1 | jap:1950 | Instagram Likes | Likes only | Instagram Likes [EMERGENCY] [Max: 50K] [Start Time: 0-1 Hour] [Speed: 10/Day ] | 10–5000000 | 0.13 | C |
| 207 | 1 | jap:8562 | Instagram Likes | Likes only | Instagram Likes [FROM APP] [Refill: No] [Max: 100K] [Start Time: 0 - 1 Hour] [Speed: Up to 5K/Day] | 100–100000 | 0.36 | C |
| 208 | 1 | jap:4128 | Instagram Likes | Likes only | Instagram Likes [EMERGENCY] [Max: 10K] [Start Time: 0-1 Hour] [Speed: FAST] 🔥🔥🔥 | 10–100000 | 0.7695 | C |
| 209 | 1 | jap:4236 | Instagram Likes | Likes only | Instagram Likes [Max: 20K] [Start Time: 0-1 Hour] [Speed: FAST] 🔥🔥🔥 | 10–100000 | 1.3125 | CD |
| 210 | 1 | jap:1836 | Instagram Likes | Likes only | Instagram Likes [Max: 2K] [Start Time: 1 Hour] [Speed: 3K/Hour]💧 | 5–50000 | 2.40 | C |
| 211 | 1 | jap:3292 | Instagram Likes | Likes + Impressions + Reach | Instagram Likes + Impressions + Reach [English PUBLIC with Stories Accounts] [Max: 2K] [Start Time: 0-1 Hour] [Speed: 2K/Hour] 🔥🔥🔥 | 5–50000 | 2.00 | CD |
| 212 | 1 | jap:1865 | Instagram Likes | Likes only | Instagram Likes [Max: 10M] [Start Time: 0-3 Hrs] [Speed: 300K/D] 💧 | 10–10000000 | 0.125 | D |
| 213 | 1 | jap:1884 | Instagram Likes | Likes only | Instagram Likes [EMERGENCY] [Max: 50K] [Start Time: 0-1 Hour] [Speed: INSTANT] | 10–1000000 | 0.275 | C |
| 214 | 1 | jap:8397 | Instagram Likes | Likes only | Instagram RAU™ Likes [Refill: No Drop] [Max: 10K] [Start Time: 0-1 Hour] [Speed: 500/Hr] 💧 | 5–50000 | 2.352 | C |
| 215 | 1 | jap:3278 | Instagram Likes | Likes only | Instagram Likes [Max: 5K] [Start Time: 0-1 Hour] [Speed: 1K/Hour] | 50–100000 | 2.00 | CD |
| 216 | 1 | jap:1767 | Instagram Likes | Likes only | Instagram Likes [Refill: No] [Max: 50K] [Start Time: 0-1 Hour] [Speed: INSTANT] 💧⚡⚡⚡🔥 | 50–50000 | 2.15 | CD |
| 217 | 1 | jap:5715 | Instagram Likes | Likes only | Instagram Likes RAU™ [USA 🇺🇸] [Max: 1.5K] [Refill: 60D] [Start Time: 0 - 1 Hr] [Speed: 1.5K/D] 💧 | 10–20000 | 2.325 | D |
| 218 | 1 | jap:4301 | Instagram Likes | Likes only | Instagram Likes [REAL] [Max: 5K] [Start Time: 0-1 Hour] [Speed: 2K/Hour] | 20–3000 | 3.36 | D |
| 219 | 1 | jap:266 | Instagram Likes | Likes only | Instagram Likes [MIX] [Refill: No] [Max: 6K] [Start Time: 0-1 Hour] [Speed: INSTANT]💧⛔ | 20–3000 | 3.51 | D |
| 220 | 1 | jap:5917 | Instagram Likes | Likes only | Instagram Likes [REAL LOOKING] [Max: 50K] [Start Time: 0-1 Hour] [Speed: 20K/Day] | 10–500000 | 0.495 | CD |
| 221 | 1 | jap:1791 | Instagram Likes | Likes only | Instagram Likes [HQ] [Refill: No] [Start Time: Instant] [Speed: 50k/Day]💧⛔️ | 20–50000 | 3.08 | D |
| 222 | 1 | jap:8042 | Instagram Likes | Likes only | Instagram RAL™ Likes [Refill: Lifetime] [Max: 1K] [Start Time: 0-2 Hours] [Speed: 1K/Hour] ⚡💧 | 5–50000 | 2.40 | C |
| 223 | 1 | jap:3020 | Instagram Likes | Likes only | Instagram Likes [NON DROP] [Max: 10K] [Start Time: 0-1 Hour] [Speed: 10K/Day] | 100–25000 | 0.1728 | — |
| 224 | 1 | jap:1863 | Instagram Likes [BOTS] | Likes only | Instagram Likes [Refill: No] [Max: 1M] [Start time: 0 - 1 Hr] [Speed: 200K/D] 💧⛔️ | 10–1000000 | 0.1125 | CD |
| 225 | 1 | jap:5626 | Instagram Likes [BOTS] | Likes only | Instagram Likes [Refill: No] [Max: 500K] [Start Time: 0 - 1 Hr] [Speed: Up to 100K/D] 💧⛔ | 10–500000 | 0.1375 | D |
| 226 | 1 | jap:1967 | Instagram Likes [BOTS] | Likes only | Instagram Likes [Refill: No] [Max: 1M] [Start Time: 0-3 Hrs] [Speed: Up to 100K/D] 💧⛔ | 10–10000000 | 0.125 | — |
| 227 | 1 | jap:7455 | Instagram Likes [BOTS] | Likes only | Instagram Likes [Refill: 90D] [Max: 1M] [Start time: 0 - 1 Hr] [Speed: 200K/D] 💧⛔️♻️ | 10–1000000 | 0.20 | CD |
| 228 | 1 | jap:10149 | Instagram Likes [BOTS] | Likes only | Instagram Likes [Refill: No] [Max: 5M] [Start Time: 0-3 Hrs] [Speed: Up to 20K/D] 💧⛔ | 10–10000000 | 0.275 | C |
| 229 | 1 | jap:2148 | Instagram Likes [BOTS] | Likes only | Instagram Likes [Refill: 30D] [Max: 500K] [Start Time: 0-1 Hour] [Speed: 50K/D] 💧⛔♻️ | 10–500000 | 0.4125 | CD |
| 230 | 1 | jap:9529 | Instagram Likes [BOTS] | Likes only | Instagram Likes [HQ] [Refill: No] [Max: 500K] [Start Time: 0-3 Hrs] [Speed: 100K/D] 💧⛔️ | 10–10000000 | 0.125 | — |
| 231 | 1 | jap:9530 | Instagram Likes [BOTS] | Likes only | Instagram Likes [HQ] [Refill:NO] [Max: 500K] [Start Time: 0-3 Hrs] [Speed: 100K/D] 💧⛔️ | 10–10000000 | 0.125 | — |
| 232 | 1 | jap:4342 | Instagram Likes [BOTS] | Likes only | Instagram Likes [Refill: No] [Max: 500K] [Start Time: 0-1 Hr] [Speed: 10K/Day]  ⛔ 💧 | 50–100000 | 0.1114 | D |
| 233 | 1 | jap:2939 | Instagram Likes [BOTS] | Likes only | Instagram Likes [Refill: 90D] [Max: 150K] [Start Time: 0-1 Hr] [Speed: 150K/Day] ♻️ ⛔ 💧 | 10–100000 | 0.1609 | D |
| 234 | 1 | jap:1820 | Instagram Likes [BOTS] | Likes only | Instagram Likes [Refill: NO] [Max: 1M] [Start Time: 0-3 Hrs] [Speed: Up to 100K/D] 💧⛔♻️ | 10–10000000 | 0.1313 | — |
| 235 | 1 | jap:10150 | Instagram Likes [BOTS] | Likes only | Instagram Likes [Refill: 30D] [Max: 5M] [Start Time: 0-3 Hrs] [Speed: Up to 20K/D] 💧⛔♻️ | 10–10000000 | 0.1013 | D |
| 236 | 1 | jap:8586 | Instagram Likes [BOTS] | Likes only | Instagram Likes [BOTS] [Refill: No] [Max: 10K] [Start time: 1 Hour] [Speed: 10K/Day] 💧⛔️ | 10–1000000 | 0.1337 | CD |
| 237 | 1 | jap:8464 | Instagram Likes [BOTS] | Likes only | Instagram Likes [LQ] [Refill: No] [Max: 100K] [Start Time: 0 - 6 Hours] [Speed: 10K/Day] 💧⛔️ | 10–200000 | 0.1125 | CD |
| 238 | 1 | jap:8409 | Instagram Likes [BOTS] | Likes only | Instagram Likes [LQ] [Refill: 30D] [Max: 500K] [Start Time: 0 - 3 Hours] [Speed: 10K/Day] 💧⛔️ | 10–500000 | 0.42 | C |
| 239 | 1 | jap:9183 | Instagram Likes [BOTS] | Likes only | Instagram Likes [LQ] [Refill: 30D] [Max: 500K] [Start Time: 0 - 3 Hours] [Speed: 10K/Day] 💧⛔️ | 50–500000 | 0.075 | CD |
| 240 | 1 | jap:7797 | Instagram Likes [BOTS] | Likes only | Instagram Likes [BOTS] [Refill: No] [Max: 30K] [Start time: Instant] [Speed: 30K/Day] | 10–500000 | 0.2448 | C |
| 241 | 1 | jap:1864 | Instagram Likes [BOTS] | Likes only | Instagram Likes [Refill: 60D] [Max: 250k] [Start Time: 0 - 3 Hrs] [Speed: 25K/D] 💧♻️⛔️ | 10–100000 | 0.1674 | D |
| 242 | 1 | jap:2994 | Instagram Likes [BOTS] | Likes only | Instagram Likes [Refill: 90D] [Max: 250k] [Start Time: 0 - 3 Hrs] [Speed: 25K/D] 💧♻️⛔️ | 10–100000 | 0.1712 | D |
| 243 | 1 | jap:3130 | Instagram Likes [BOTS] | Likes only | Instagram Likes [Refill: 365D] [Max: 250k] [Start Time: 0 - 3 Hrs] [Speed: 25K/D] 💧♻️⛔️ | 10–100000 | 0.1738 | D |
| 244 | 1 | jap:5781 | Instagram Likes [BOTS] | Likes only | Instagram Likes [Refill: No] [Max: 10K] [Start Time: 1H] [Speed: 10K/Day] | 10–100000 | 0.1802 | D |
| 245 | 1 | jap:8561 | Instagram Likes [BOTS] | Likes only | Instagram Likes [Refill: 30 Days] [Max: 500K] [Start Time: 0 - 1 Hour] [Speed: 10K/Day] ⛔ | 10–50000 | 0.42 | C |
| 246 | 1 | jap:6125 | Instagram Likes [BOTS] | Likes only | Instagram Likes [Max: 500K] [BOTS] [Refill: 30D] [Start Time: 0 - 1 Hr] [Speed: 50K/Day] ⛔♻️ | 10–500000 | 0.42 | C |
| 247 | 1 | jap:2991 | Instagram Likes [BOTS] | Likes only | Instagram Likes [Refill: 30D] [Max: 300K] [Start Time: 0 - 2 Hrs] [Speed: 20K/Day] ⛔♻️ | 10–300000 | 0.247 | CD |
| 248 | 1 | jap:7796 | Instagram Likes [BOTS] | Likes only | Instagram Likes [Refill: 30D] [Max: 250K] [Start Time: 0 - 1 Hour] [Speed: 100K/Day] 💧⛔️ | 100–150000 | 0.1875 | RCD |
| 249 | 1 | jap:5948 | Instagram Likes [BOTS] | Likes only | Instagram Likes [BOTS] [Refill: 30] [Max: 20K] [Start Time: 0-1 Hour] [Speed: FAST] | 10–300000 | 0.434 | CD |
| 250 | 1 | jap:5949 | Instagram Likes [BOTS] | Likes only | Instagram Likes [BOTS] [Refill: 30 Days] [Max: 20K] [Start Time: 0-1 Hour] [Speed: 10k/Day] ♻️ | 10–300000 | 0.4256 | C |
| 251 | 1 | jap:7456 | Instagram Likes [BOTS] | Likes only | Instagram Likes [Bots] [Refill: 30 Days] [Max: 50K] [Start Time: 0-1 Hour] [Speed: 30-60K/Day] ♻️ | 10–300000 | 0.2375 | CD |
| 252 | 1 | jap:5955 | Instagram Likes [BOTS] | Likes only | Instagram Likes [Refill: No] [Max: 200K] [Start Time: 0-1 Hour] [Speed: 10K/Day] 💧⛔ | 10–50000 | 0.35 | C |
| 253 | 1 | jap:2997 | Instagram Likes [BOTS] | Likes only | Instagram Likes [Max: 50K] [Start Time: 0-1 Hour] [Speed: 1K/Hour] ⛔🔥💧 | 10–50000 | 0.2375 | CD |
| 254 | 1 | jap:7789 | Instagram Likes [BOTS] | Likes only | Instagram Likes [Refill: No] [Max: 30K] [Start Time: 0 - 1 Hour] [Speed: 30K/Day] 💧⛔️ | 10–300000 | 0.364 | C |
| 255 | 1 | jap:2993 | Instagram Likes [BOTS] | Likes only | Instagram Likes [Max: 50K] [Start Time: 0 - 1 Hours] [Speed: 50K Per Day] 💧⛔ | 10–50000 | 0.50 | CD |
| 256 | 1 | jap:2192 | Instagram Likes [BOTS] | Likes only | Instagram Likes [HQ] [Refill: 30D] [Max: 30K] [Start time: 0 - 1 Hr] [Speed: 10K/Day] | 10–30000 | 0.3375 | D |
| 257 | 1 | jap:1914 | Instagram Likes [BOTS] | Likes only | Instagram Likes [NATURAL INCREASE] [Refill: No] [Max: 25K]  🔥 | 10–100000 | 0.1931 | D |
| 258 | 1 | jap:1913 | Instagram Likes [BOTS] | Likes only | Instagram Likes [HQ] [Refill: No] [Max: 20K] [Start Time: 0-1 Hour] [Speed: FAST] 💧⛔ | 10–100000 | 0.1609 | D |
| 259 | 1 | jap:2983 | Instagram Likes [BOTS] | Likes only | Instagram Likes [Bots with PP] [Refill: AR30] [Max: 300K] [Start Time: 0-1 Hour] [Speed: FAST] ⛔♻️ | 10–300000 | 0.20 | RC |
| 260 | 1 | jap:8454 | Instagram Likes [BOTS] | Likes only | Instagram Likes [Refill: No] [Max: 5K] [Start Time: 6 Hours] [Speed: 5K/Day] | 10–500000 | 0.243 | CD |
| 261 | 1 | jap:8404 | Instagram Likes [BOTS] | Likes only | Instagram Likes [Refill: No] [Max: 1K] [Start Time: 0 - 6 Hours] [Speed: 1K/Day] | 10–200000 | 0.234 | CD |
| 262 | 1 | jap:5899 | Instagram Likes [BOTS] | Likes only | Instagram Likes [HQ] [Max: 5K] [Start Time: Instant] [Speed: Instant] 🔥⛔ | 100–25000 | 1.5625 | D |
| 263 | 1 | jap:2998 | Instagram Likes [BOTS] | Likes only | Instagram Likes [Refill: 30 Days] [Max: 5K] [Start Time: 6 Hours] [Speed: 5K/Day] | 10–200000 | 0.2375 | CD |
| 264 | 1 | jap:3226 | Instagram Likes [BOTS] | Likes + Impressions | Instagram Likes + Impressions [Refill: 30 Days] [Max: 30K] [Start Time: 0-1 Hour] [Speed: 1-3K/Hour] ♻️ | 50–100000 | 0.1609 | D |
| 265 | 1 | jap:1817 | Instagram Likes [BOTS] | Likes only | Instagram Likes [MQ] [Refill: 30 Days] [Max: 500K] [Start Time: 0-1 Hour] [Speed: 5K/Day] 💧⛔ | 10–100000 | 0.1609 | D |
| 266 | 1 | jap:1797 | Instagram Likes [BOTS] | Likes only | Instagram Likes [MQ] [Refill: 180 Days] [Max: 50K] [Start Time: 0-1 Hour] [Speed: INSTANT] ♻️⚡ | 50–50000 | 1.2482 | RCD |
| 268 | 1 | jap:4172 | Instagram Likes [BOTS] | Likes only | Instagram Likes [Refill: No] [Max: 150K] [Start Time: 1 Hour] [Speed: 3K/Day] | 10–150000 | 0.32 | RC |
| 269 | 1 | jap:2259 | Instagram Likes [BOTS] | Likes only | Instagram Likes [Refill: No] [Max: 20K] [Start Time: 0-1 Hour] [Speed: 10K/Hour] 🔥⚡⛔ | 10–20000 | 0.1609 | D |
| 270 | 1 | jap:4234 | Instagram Likes [BOTS] | Likes only | Instagram Likes [NO DROP] [Auto-Refill: 7 Days] [Max: 20K] [Start Time: 0-1 Hour] [Speed: 10K/Day] 🔥💧♻️⛔️ | 10–20000 | 0.264 | RCD |
| 271 | 1 | jap:4429 | Instagram Likes [BOTS] | Likes only | Instagram Likes [Refill: 30 Days] [Max: 100K] [Start Time: 1 Hour] [Speed: 20K/Day] ♻️💧🔥 | 10–100000 | 0.1609 | D |
| 272 | 1 | jap:1849 | Instagram Likes [BOTS] | Likes only | Instagram Likes [MQ] [Refill: No] [Max: 100K] [Start Time: 1 Hour] [Speed: 5K/Day]💧 | 10–100000 | 0.96 | D |
| 273 | 1 | jap:1844 | Instagram Likes [BOTS] | Likes only | Instagram Likes [MQ] [Refill: 180 Days] [Max: 30K] [Start Time: 0-1 Hour] [Speed: INSTANT] 💧♻️⚡⚡⚡ | 10–100000 | 2.70 | D |
| 274 | 1 | jap:1819 | Instagram Likes [Targeted] | Likes only | Instagram Likes RAU™ [USA 🇺🇸] [Max: 1.5K] [Refill: 60D] [Start Time: 0 - 1 Hr] [Speed: 1.5K/D] 💧 | 5–50000 | 2.9124 | CD |
| 275 | 1 | jap:8851 | Instagram Likes [Targeted] | Likes only | Instagram Likes [USA 🇺🇸] [Max: 12K] [Refill: 120D] [Start Time: 0 - 1 Hr] [Speed: 10K/D] 💧⛔♻️ | 10–12000 | 2.25 | D |
| 276 | 1 | jap:10209 | Instagram Likes [Targeted] | Likes only | Instagram Likes [BR 🇧🇷] [Refill: No] [Max: 5K] [Start Time: 0 - 1 Hr] [Speed: 5K/D] 💧⛔️ | 50–5000 | 0.525 | CD |
| 277 | 1 | jap:10210 | Instagram Likes [Targeted] | Likes only | Instagram Likes [BR 🇧🇷] [Refill: No] [Max: 100K] [Start Time: 0 - 1 Hr] [Speed: 50K/D] 💧⛔️ | 50–200000 | 0.6875 | CD |
| 278 | 1 | jap:1018 | Instagram Likes [Targeted] | Likes + Impressions + Reach | 🇰🇷🇰🇵 Instagram Likes + Impressions + Reach [Korea] [HQ] [Refill: 90 Days] [Max: 10K] [Start Time: 0 - 1 Hour] [Speed: 10K/Day] | 20–10000 | 10.40 | D |
| 279 | 1 | jap:8782 | Instagram Likes [Targeted] | Likes only | Instagram Likes [ARAB] [Refill: 30D] [Max: 50K] [Start Time: 0 - 12 Hrs] [Speed: Up to 10K/D] 💧⛔ | 50–300 | 2.325 | D |
| 280 | 1 | jap:10211 | Instagram Likes [Targeted] | Likes only | Instagram Likes [EG 🇪🇬] [Refill: No] [Max: 100K] [Start Time: 0 - 1 Hr] [Speed: 50K/D] 💧⛔️ | 50–100000 | 1.0625 | CD |
| 281 | 1 | jap:10212 | Instagram Likes [Targeted] | Likes only | Instagram Likes [KSA 🇸🇦] [Refill: No] [Max: 100K] [Start Time: 0 - 1 Hr] [Speed: 50K/D] 💧⛔️ | 10–100000 | 1.7438 | CD |
| 282 | 1 | jap:1031 | Instagram Likes [Targeted] | Likes only | Instagram Likes [🇦🇪 ARAB / 🇮🇳 INDIA / 🇹🇷 TURK MIX] [Refill: 30D] [Max: 200K] [Start Time: 0 - 1 Hr] [Speed: 20K/D] 💧♻️⛔ | 100–200000 | 1.25 | CD |
| 283 | 1 | jap:1030 | Instagram Likes [Targeted] | Likes only | 🇦🇪 Instagram Likes [UAE - ARAB] [Refill: 45D] [Max: 50K] [Start Time: 0 - 1 Hr] [Speed: 5K/D] ⛔💧♻️ | 100–10000 | 2.1875 | D |
| 284 | 1 | jap:89 | Instagram Likes [Targeted] | Likes only | Instagram Likes [ARAB] [Refill: No] [Max: 5K] Start Time: 0-1 Hour] [Speed: 2K/Day] | 20–3000 | 3.36 | D |
| 285 | 1 | jap:5731 | Instagram Likes [Targeted] | Likes only | 🇮🇳 Instagram Likes [INDIA] [Refill: 30 Days] [Max: 100K] [Start Time: Instant] [Speed: 10K/Day] | 10–10000 | 1.75 | CD |
| 286 | 1 | jap:1028 | Instagram Likes [Targeted] | Likes only | 🇮🇳 Instagram Likes [INDIA] [Refill: 30D] [Max: 100K] [Start Time: Instant] [Speed: 15K/Day] | 10–10000 | 2.24 | CD |
| 287 | 1 | jap:1822 | Instagram Likes [Targeted] | Likes only | 🇮🇷Instagram Likes [IRAN] [Refill: No] [Max: 10K] [Start Time: 0-1 Hour] [Speed: 5K/Day] | 100–100000 | 0.88 | — |
| 288 | 1 | jap:2987 | Instagram Likes [Targeted] | Likes only | 🇸🇦🇮🇷Instagram Likes [ARAB - IRAN MIX] [Refill: No] [Max: 10K] [Start Time: 0-1 Hour] [Speed: 5K/Day] | 100–100000 | 0.99 | — |
| 289 | 1 | jap:8788 | Instagram Likes [Targeted] | Likes only | 🇰🇷 Instagram Likes [KOREA] [Refill: No] [Max: 200K] [Start Time: 0-3 Hrs] [Speed: 2K/Day] | 20–200000 | 1.6313 | C |
| 290 | 1 | jap:10087 | Instagram Likes [Targeted] | Likes only | 🇰🇷 Instagram Likes [KOREA] [HQ] [Refill: No] [Max: 50K] [Start Time: 0-3 Hrs] [Speed: 10K/D]💧 | 10–50000 | 7.5525 | D |
| 291 | 1 | jap:10088 | Instagram Likes [Targeted] | Likes only | 🇰🇷 Instagram Likes [KOREA] [HQ] [Refill: 30D] [Max: 50K] [Start Time: 0-3 Hrs] [Speed: 10K/D]💧 | 10–50000 | 9.4288 | CD |
| 292 | 1 | jap:8574 | Instagram Likes [Targeted] | Likes only | 🇮🇳 Instagram Likes [INDIA WOMEN] [Refill: 30 Days] [Max: 10K] [Start Time: Instant] [Speed: 10K/Day] | 10–10000 | 2.1875 | CD |
| 293 | 1 | jap:3381 | Instagram Likes [Targeted] | Likes + Impressions | 🇷🇺Instagram Likes + Impressions [RUSSIAN] [NON-DROP] [Max: 150K] [Refill: 30 Days] [Start Time: 1 Hour] [Speed: 2K/Day] 💧🔥♻️ | 50–200000 | 5.00 | D |
| 294 | 1 | jap:8048 | Instagram Likes [Targeted] | Likes only | Instagram Likes [🇦🇪 🇸🇦 ARAB - GULF] [SUPER REAL] [Refill: No] [Max: 3K] [Start Time: 0-1 Hour] [Speed: 3K/Day] | 20–10000 | 2.75 | D |
| 295 | 1 | jap:1037 | Instagram Likes [Targeted] | Likes only | Instagram Likes [Max: 2K] [UK 🇬🇧 ] [Refill: No] [Speed: 2K/Day] [Start Time: 0 - 1 Hours] | 20–2000 | 4.125 | D |
| 296 | 1 | jap:8253 | Instagram Likes [Targeted] | Likes only | Instagram Likes Male [ARAB-GULF] [Max: 50K] [Refill: 30 Days] [Start Time: 0 - 1 Hours] [Speed: 500/Day] | 20–50000 | 2.7875 | RC |
| 297 | 1 | jap:8051 | Instagram Likes [Targeted] | Likes only | Instagram Likes [Max: 2K] [SPAIN 🇪🇸 ] [Refill: No] [Speed: 2K/Day] [Start Time: 0 - 1 Hours] | 20–2000 | 4.125 | D |
| 298 | 1 | jap:8050 | Instagram Likes [Targeted] | Likes only | Instagram Likes [Max: 1K] [TAIWAN 🇹🇼 ] [Refill: No] [Speed: 1K/Day] [Start Time: 0 - 1 Hours] | 20–1000 | 3.50 | D |
| 299 | 1 | jap:2294 | Instagram Likes [Targeted] | Likes only | 🇮🇳 Instagram Likes [INDIA] [Refill: 30D] [Max: 30K] [Start Time: Instant] [Speed: 10K/D] | 10–30000 | 0.3375 | — |
| 300 | 1 | jap:411 | Instagram Likes [Targeted] | Likes only | 🇮🇳 Instagram Likes [INDIA] [Refill: 30D] [Max: 20K] [Start Time: Instant] [Speed: 3K/D] | 10–20000 | 0.275 | D |
| 302 | 1 | jap:7839 | Instagram Likes [Targeted] | Likes only | 🇮🇳 Instagram Likes [INDIA] [Start Time: 0 - 1 Hour] [Speed: 5K/Day] | 20–3000 | 1.32 | — |
| 303 | 1 | jap:3794 | Instagram Likes [Targeted] | Likes only | Instagram Likes [ARAB] [Refill: 30D] [Max: 20K] [Start Time: 1 Hour] [Speed: Up to 5K/Day] | 250–15000 | 3.75 | D |
| 304 | 1 | jap:1032 | Instagram Likes [Targeted] | Likes only | Instagram Likes [Max: 15K] [USA 🇺🇸 ] [Refill: 90 Days] [Speed: 10K/Day] [Start Time: 0 - 1 Hours] 💧 ⛔️ ♻️ | 20–15000 | 1.375 | D |
| 305 | 1 | jap:3518 | Instagram Likes [Targeted] | Likes + Impressions + Reach | 🇰🇷🇰🇵Instagram Likes [Korea] + Impressions + Reach [Refill: No] [Max: 15K] [Start Time: 1 Hour] [Speed: 5K/Day] | 20–10000 | 12.80 | — |
| 306 | 1 | jap:7842 | Instagram Likes [Targeted] | Likes only | 🇭🇰 Instagram Likes [HONG KONG] [Start Time: 0 - 1 Hour] [Speed: 1K/Day] | 20–1000 | 3.36 | D |
| 307 | 1 | jap:1034 | Instagram Likes [Targeted] | Likes only | Instagram Likes [10K] [UKRAINE] [1H - 10K/Day] | 20–50000 | 23.75 | — |
| 308 | 1 | jap:7844 | Instagram Likes [Targeted] | Likes only | 🇰🇷 Instagram Likes [KOREA] [Start Time: 0 - 1 Hour] [Speed: 2K/Day] | 20–3000 | 3.36 | — |
| 309 | 1 | jap:7847 | Instagram Likes [Targeted] | Likes only | 🇮🇷 Instagram Likes [IRAN] [Start Time: 0 - 1 Hour] [Speed: 1K/Day] | 20–7000 | 4.32 | — |
| 314 | 1 | jap:4207 | Instagram Likes [Targeted] | Likes only | 🇳🇬Instagram Likes [NIGERIA] [Refill: No] [Max: 2K] [Start Time: 1 Hour] [Speed: 2K/Day] | 100–5000 | 25.00 | — |
| 318 | 1 | jap:1041 | Instagram Likes [Targeted] | Likes only | Instagram Likes [MALE] [Afro-Americans] [USA] [250/Day] [NO DROP] | 30–2500 | 13.20 | — |
| 319 | 1 | jap:1042 | Instagram Likes [Targeted] | Likes only | Instagram Likes [FEMALE] [Afro-Americans] [USA] [250/Day] [NO DROP] | 30–2500 | 13.20 | — |
| 320 | 1 | jap:7540 | Instagram Likes [Targeted] | Likes only | 🇨🇳 Instagram Likes [CHINA] [Refill: No] [Max: 6K] [Start Time: Instant] [Speed: 3K/Day] | 20–6000 | 1.50 | — |
| 321 | 1 | jap:8460 | Instagram Likes [Targeted] | Likes only | 🇯🇵 Instagram Likes [JAPAN] [Start Time: 0 - 1 Hour] [Speed: 2K/Day] | 20–1000 | 3.50 | D |
| 322 | 1 | jap:1237 | Instagram Likes [Targeted] | Likes only | Instagram Likes [10K] [AFRICAN] [1H - 10K/Day] | 100–10000 | 39.50 | — |
| 323 | 1 | jap:8227 | Instagram Likes [Targeted] | Likes only | Instagram Likes [ARAB-GULF] [Max: 50K] [Refill: 30 Days] [Start Time: 0 - 1 Hours] [Speed: 500/Day] | 5–2500 | 1.035 | R |
| 324 | 1 | jap:8228 | Instagram Likes [Targeted] | Likes only | Instagram Likes Female [ARAB-GULF] [Max: 50K] [Refill: 30 Days] [Start Time: 0 - 1 Hours] [Speed: 500/Day] | 50–10000 | 2.7875 | RC |
| 325 | 1 | jap:5825 | Instagram Likes Per Minute | Likes only | Instagram Likes [1 Like Per Minute] [Max: 10K] [Start Time: 0-1 Hour] | 20–10000 | 1.35 | — |
| 326 | 1 | jap:5820 | Instagram Likes Per Minute | Likes only | Instagram Likes [5 Likes Per Minute] [Max: 10K] [Start Time: 0-1 Hour] | 20–10000 | 1.35 | — |
| 327 | 1 | jap:5821 | Instagram Likes Per Minute | Likes only | Instagram Likes [10 Likes Per Minute] [Max: 10K] [Start Time: 0-1 Hour] | 20–10000 | 1.35 | — |
| 328 | 1 | jap:5822 | Instagram Likes Per Minute | Likes only | Instagram Likes [25 Likes Per Minute] [Max: 10K] [Start Time: 0-1 Hour] | 20–10000 | 1.35 | — |
| 329 | 1 | jap:5823 | Instagram Likes Per Minute | Likes only | Instagram Likes [50 Likes Per Minute] [Max: 10K] [Start Time: 0-1 Hour] | 20–10000 | 1.35 | — |
| 330 | 1 | jap:5824 | Instagram Likes Per Minute | Likes only | Instagram Likes [60 Likes Per Minute] [Max: 10K] [Start Time: 0-1 Hour] | 20–10000 | 1.35 | — |
| 331 | 1 | jap:5826 | Instagram Likes Per Minute | Likes + Impressions | Instagram Likes + Impressions [1 Like Per Minute] [Max: 10K] [Start Time: 0-1 Hour] | 20–10000 | 1.50 | — |
| 332 | 1 | jap:5827 | Instagram Likes Per Minute | Likes + Impressions | Instagram Likes + Impressions [5 Likes Per Minute] [Max: 10K] [Start Time: 0-1 Hour] | 20–10000 | 1.50 | — |
| 333 | 1 | jap:5828 | Instagram Likes Per Minute | Likes + Impressions | Instagram Likes + Impressions [10 Likes Per Minute] [Max: 10K] [Start Time: 0-1 Hour] | 20–10000 | 1.50 | — |
| 334 | 1 | jap:5829 | Instagram Likes Per Minute | Likes + Impressions | Instagram Likes + Impressions [25 Likes Per Minute] [Max: 10K] [Start Time: 0-1 Hour] | 20–10000 | 1.50 | — |
| 335 | 1 | jap:5830 | Instagram Likes Per Minute | Likes + Impressions | Instagram Likes + Impressions [50 Likes Per Minute] [Max: 10K] [Start Time: 0-1 Hour] | 20–10000 | 1.50 | — |
| 336 | 1 | jap:5831 | Instagram Likes Per Minute | Likes + Impressions | Instagram Likes + Impressions [60 Likes Per Minute] [Max: 10K] [Start Time: 0-1 Hour] | 20–10000 | 1.50 | — |
| 687 | 1 | jap:8043 | Instagram ENGAGEMENT Services | Likes only | Instagram RAL™ Likes [Refill: No Drop] [Max: 15K] [Start Time: 0-8 Hours] [Speed: 2K/Day] ⚡💧 | 50–15000 | 6.875 | D |
| 689 | 1 | jap:7499 | Instagram ENGAGEMENT Services | Likes only | Instagram Likes RAU™ [USA 🇺🇸] [Max: 7K] [Refill: 60D] [Start Time: 0 - 1 Hr] [Speed: 1.5K/D] 💧 | 10–20000 | 3.20 | D |
| 690 | 1 | jap:3576 | Instagram ENGAGEMENT Services | Likes only | 🔥🔥🔥 [EXCLUSIVE] Instagram POWER Likes [TOP IN MARKET] [Max: 50K] [Start Time: 0-1 Hr] [Speed: 20K/Day] 🔥🔥🔥 | 10–100000 | 0.275 | D |
| 691 | 1 | jap:7507 | Instagram ENGAGEMENT Services | Likes only | Instagram USA Likes [Refill: No Drop] [Max: 2K] [Start Time: 0-1 Hour] [Speed: 2K/Hour] 💧 | 5–50000 | 2.72 | C |
| 692 | 1 | jap:1867 | Instagram ENGAGEMENT Services | Likes only | Instagram Female Likes [Engagement Booster] | 100–10000 | 12.00 | D |
| 693 | 1 | jap:6520 | Instagram ENGAGEMENT Services | Likes only | Instagram Female Likes [Engagement Booster] [Start Time: 0 - 1 Hour] [Speed: 1K/Day] | 100–1000 | 1.00 | D |
| 694 | 1 | jap:1824 | Instagram ENGAGEMENT Services | Likes only | Instagram RAL™ Likes [FEMALE] [Refill: No Drop] [Max: 7K] [Start Time: 0-8 Hours] [Speed: 2K/Day] ⚡💧 | 50–7000 | 7.125 | D |
| 695 | 1 | jap:7496 | Instagram ENGAGEMENT Services | Likes only | Instagram RAL™ Likes [MALE] [Refill: No Drop] [Max: 5K] [Start Time: 0-8 Hours] [Speed: 2K/Day] ⚡💧 | 30–5000 | 7.125 | D |
| 698 | 1 | jap:307 | Instagram ENGAGEMENT Services | Likes only | Instagram Likes [Refill: No] [Max: 10K] [Start Time: 0-1 Hour] [Speed: 2-5K/Day] 🔥🔥🔥🔥💧 | 50–10000 | 0.75 | CD |
| 699 | 1 | jap:3476 | Instagram ENGAGEMENT Services | Likes only | 🔥🔥🔥 [EXCLUSIVE] Instagram POWER Likes [TOP IN MARKET] [Max: 10K] [Start Time: 1 Hour] [Speed: 5K/Day] 🔥🔥🔥 | 10–250000 | 0.7875 | D |
| 700 | 1 | jap:1992 | Instagram ENGAGEMENT Services | Likes only | 🔥🔥🔥 [EXCLUSIVE] Instagram POWER Likes [TOP IN MARKET] [Max: 10K] [Start Time: 0-1 Hour] [Speed: 5K/Day]  🔥🔥🔥 | 100–100000 | 0.825 | D |
| 701 | 1 | jap:1178 | Instagram ENGAGEMENT Services | Likes only | Instagram POWER Likes [PERFECT QUALITY] [Max: 10K] [Start Time: 0-6 Hours] [Speed: INSTANT] 🔥🔥🔥 | 10–500000 | 1.625 | D |
| 702 | 1 | jap:2147 | Instagram ENGAGEMENT Services | Likes only | 🔥🔥🔥 [EXCLUSIVE] Instagram POWER Likes [TOP IN MARKET] [Max: 50K] [Start Time: 0-1 Hour] [Speed: 2K/Day] 🔥🔥🔥 | 10–80000 | 0.7875 | D |
| 703 | 1 | jap:1784 | Instagram ENGAGEMENT Services | Likes only | Instagram POWER Likes [Max: 50K] [Start Time: 0-6 Hours] [Speed: INSTANT] 💧 | 50–50000 | 2.15 | CD |
| 849 | 1 | jap:10255 | Instagram Comments | Comment Likes | Instagram Comment Likes [COMMENT LINK] [Refill: No] [Max: 1K] [Start Time: 0-1 Hr] [Speed: 1K/D]💧 | 20–1000 | 0.875 | CD |
| 850 | 1 | jap:9564 | Instagram Comments | Comment Likes | Instagram Comment Likes [LINK OF COMMENT] [Refill: No] [Max: 20K] [Start Time: 0-1 Hr] [Speed: 20K/D]💧 | 10–20000 | 2.50 | D |
| 901 | 1 | jap:459 | Instagram Comments | Comment Likes | Instagram Comment Likes [5K] [SPECIFIC COMMENT] [Refill: No] [Max: 5K] [Start Time: 0-1 Hour] [Speed: 5K/Day] ⚡️ | 10–20000 | 3.00 | — |
| 1152 | 1 | jap:5932 | Instagram Engagement | Likes from verified accounts | Instagram Likes [FROM VERIFIED ACCOUNTS] [DONE IN 24 HOURS] | 1–16 | 875.00 | — |
| 1181 | 1 | jap:4107 | Instagram Followers &amp; Likes [BOTS with NO REFILL] [CAN FULLY DROP] | Likes only | Instagram Likes [With PP &amp; Posts] [Refill: No] [Max: 5K] [Start Time: 1 Hour] [Speed: 500/Hour] | 50–100000 | 0.10 | — |
| 1182 | 1 | jap:4108 | Instagram Followers &amp; Likes [BOTS with NO REFILL] [CAN FULLY DROP] | Likes only | Instagram Likes [With PP &amp; Posts] [Refill: No] [Max: 10K] [Start Time 1 Hour] [Speed: 500/Hour] | 50–200000 | 0.1375 | — |
| 1183 | 1 | jap:4109 | Instagram Followers &amp; Likes [BOTS with NO REFILL] [CAN FULLY DROP] | Likes only | Instagram Likes [With PP &amp; Posts] [Refill: No] [Max: 30K] [Start Time: 1 Hour] [Speed: 500/Hour] | 50–300000 | 0.1625 | — |
| 1184 | 1 | jap:4110 | Instagram Followers &amp; Likes [BOTS with NO REFILL] [CAN FULLY DROP] | Likes only | Instagram Likes [With PP &amp; Posts] [Refill: No] [Max: 50K] [Start Time: 1 Hour] [Speed: 500/Hour] | 50–400000 | 0.175 | — |
| 1186 | 1 | jap:4111 | Instagram Followers &amp; Likes [BOTS with NO REFILL] [CAN FULLY DROP] | Likes only | Instagram Likes [With PP &amp; Posts] [Refill: No] [Max: 100K] [Start Time: 1 Hour] [Speed: 500/Hour] | 50–500000 | 0.1375 | — |
| 1262 | 1 | jap:954 | Instagram Auto Likes | Auto Likes (review boundary) | Instagram Auto Likes [Max: 100K] [Start Time: 0-1 Hours] [Speed: 20K/Day] | 100–2500000 | 0.13 | CD |
| 1323 | 1 | jap:6107 | Instagram Western Europe + USA Services 🇪🇺 🇬🇧 🇺🇸 | Likes only | 🇺🇸 Instagram Likes [USA] [Algorithm Tricking] [Refill: Auto - 30D] [Max: 5K] [Start Time: 0 - 1 Hr] [Speed: 5K/D] | 10–20000 | 4.16 | — |


## Definition created — 2026-11-15

The user approved proceeding with the ProductDefinition after the mapping refresh analysis. Created `products/instagram-likes.json`; the catalog service is now `definition_created` and points to that file. This is a draft definition, not Builder-validated or evidence of live availability.

### Product choices authored

The definition follows the example’s tag viewpoints with current registry IDs only: Standard Likes (root handler 212); HQ-labeled; Bot Likes and bot Likes with profile pictures/posts; specific geography and gender/audience targets; refill-enabled; retention and delivery labels; controlled Likes-per-minute rates; Likes + Impressions / Reach bundles; Likes from verified accounts; and POWER-labeled choices. Comment Likes and Auto Likes remain outside this product because the rows indicate a different target/order scope. Other mapped rows remain candidates, not silently folded into a generic option.

Required inputs are an Instagram post URL and quantity. Quantity uses the saved template’s required number shape, quantity binding, placeholder, and dynamic preview Min/Max tags; it has no hard-coded universal min/max validation. The order limits come from the bound handler's payload. The Drip-feed button is bound to `t:root`; `f:runs` and `f:interval` have no `bind_id` and are included through `includes_for_buttons["f:drip_feed"]`. Their visibility still requires drip-feed capability on every selected service and the toggle to be on. The portable final OrderSnapshot omits `service_context`; the condition is evaluated against preview data before snapshot creation. Inspection of installed `@elqora/dgp-ordering` 1.1.1 `snapshot.js` confirms its submitted `inputs.form` is assembled only from the resolved visible field IDs, so hidden runs/interval fields are omitted in that version.

### Primary and fallback bindings

Fallbacks are ordered, node-scoped, and only included where every fallback's payload min/max covers the primary's full range and the row supports the same stated outcome/target. When drip-feed is supported by the primary, fallback candidates also have drip-feed enabled. Refill-tag candidates and fallbacks require the refill capability. The exact candidate sets are:

| Choice node | Primary root ID | Ordered fallbacks | Compatibility basis |
| --- | ---: | --- | --- |
| t:standard | 212 | 127, 129 | Same general Likes-only target; payload range 10–10,000,000; all support drip-feed. |
| o:bot:standard | 224 | 236 | Both mapped in Bots category, Likes-only, same 10–1,000,000 bounds and drip-feed support. |
| o:bot:profile_posts | 1181 | 1182 | Same profile-picture/posts bot claim; fallback covers the primary 50–100,000 range. |
| o:target:brazil | 276 | 277 | Both Brazil-targeted Likes, no-refill wording, drip-feed support; fallback covers 50–5,000. |
| o:target:india | 285 | 286 | Both India-targeted Likes, same 10–10,000 bounds and capability set. |
| o:refill:30d | 167 | 149 | Both advertise 30-day refill, support refill and drip-feed; fallback covers 10–50,000. |
| o:bundle:impressions | 193 | 174 | Same Likes + Impressions outcome, no extra target claim; fallback covers 10–100,000. |
| o:power:top_market | 690 | 699 | Both POWER Likes with Top-in-Market wording; fallback covers 10–100,000. |
| o:target:usa_algorithm | 1323 | 46 | Both USA Likes with Algorithm-Tricking wording; fallback covers 10–20,000. |
| o:gender:female_engagement | 693 | 692 | Same Female Engagement Booster wording; fallback covers 100–1,000. |

Other authored service options have no fallback because the mapped registry did not provide a second row that safely covers the same promise and primary bounds. This includes the single-rate choices and several exact target, retention, bundle, or account claims. A missing fallback is recorded as a coverage gap, not proof that other mapped rows are unusable.

### Mapped row disposition

The updated map contains 226 current IDs. The definition binds 60 primary IDs and 11 distinct fallback IDs (71 unique mapped services used). The other mapped rows were intentionally left out of this initial offer set or retained as separate-scope candidates; they are not hidden in an “Other” choice.

| Raw registry category | Mapped but not bound in this definition | Review disposition |
| --- | ---: | --- |
| Instagram Likes | 128, 130, 131, 132, 133, 134, 135, 137, 138, 139, 140, 141, 142, 143, 144, 145, 146, 147, 148, 150, 151, 152, 153, 154, 155, 156, 158, 159, 160, 161, 162, 163, 164, 165, 166, 168, 169, 170, 171, 172, 173, 175, 176, 177, 179, 181, 183, 184, 185, 187, 188, 189, 190, 191, 192, 194, 195, 196, 197, 198, 199, 200, 201, 202, 204, 206, 207, 209, 210, 211, 213, 214, 215, 216, 217, 218, 219, 220, 221, 222, 223 | Mapped alternatives not needed for the initial named choices; retain for later matching fallback review. |
| Instagram Likes [BOTS] | 225, 226, 227, 228, 229, 230, 231, 232, 233, 234, 235, 237, 238, 239, 240, 241, 242, 243, 244, 245, 246, 247, 248, 249, 250, 251, 252, 253, 254, 255, 256, 257, 258, 259, 260, 261, 262, 263, 264, 265, 266, 268, 269, 270, 271, 272, 273 | Mapped alternatives not needed for the initial named choices; retain for later matching fallback review. |
| Instagram Likes [Targeted] | 274, 278, 284, 290, 291, 293, 294, 299, 300, 302, 303, 304, 305, 308, 309 | Mapped alternatives not needed for the initial named choices; retain for later matching fallback review. |
| Instagram ENGAGEMENT Services | 687, 694, 695, 700, 702 | Mapped alternatives not needed for the initial named choices; retain for later matching fallback review. |
| Instagram Comments | 849, 850, 901 | Comment-target input scope; separate service/analysis. |
| Instagram Followers &amp; Likes [BOTS with NO REFILL] [CAN FULLY DROP] | 1183, 1184, 1186 | Mixed-category bot variants not included in the first Bot Likes choices; keep as candidates. |
| Instagram Auto Likes | 1262 | Auto Likes order model not established as one-post Likes. |

Current direct Likes-category rows still missing from the map are `182, 267, 11622, 11665, 11666`; they were not added to the definition. Other historical/provider alternatives remain unselected until their customer promise and fallback compatibility are reviewed.

### Validation record

- Parsed the ProductDefinition JSON and ran local `@elqora/dgp-validation` 1.2.0 `validateProductDefinition` with the 226 current mapped HandlerService records and registered Builder field type/variant capabilities: **valid, zero diagnostics**.
- Checked every ProductDefinition service reference against the current Likes mapping.
- Checked all ordered fallback IDs against the primary's payload bounds and applicable drip-feed/refill capabilities.
- Builder publication validation: **not run**. The hidden-field omission behavior above is verified in the installed local Ordering 1.1.1 source; the open Builder version is unspecified. No claim is made about rendered appearance, live service health, accepted Instagram URL formats, or fulfillment.

### Drip-feed button inclusion update — 2026-11-16

Per the requested relationship, `f:runs` and `f:interval` are included by button `f:drip_feed` via `includes_for_buttons`. Their direct `bind_id: t:root` relationships have been removed. The service-capability and toggle visibility checks remain in place.

### Filter-tag default service bindings — 2026-11-16

Every ProductDefinition filter now has a `service_id`. The root tag uses the distinct, previously unbound service 128; each variant tag uses the first option service defined for its corresponding field. All IDs resolve in the current 226-row map.

| Filter tag | Default handler row ID |
| --- | ---: |
| `t:root` | 128 |
| `t:standard` | 212 |
| `t:quality` | 136 |
| `t:bot` | 224 |
| `t:target` | 275 |
| `t:gender` | 292 |
| `t:refill` | 167 |
| `t:retention` | 203 |
| `t:priority` | 178 |
| `t:controlled` | 325 |
| `t:bundle` | 193 |
| `t:bundle_controlled` | 331 |
| `t:account` | 1152 |
| `t:power` | 690 |
