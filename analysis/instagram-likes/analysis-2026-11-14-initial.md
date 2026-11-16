# Instagram Likes — current registry analysis (unapproved)

Prepared 2026-11-14 for review. Scope: `catalog.json` service `instagram-likes-likes` only. No ProductDefinition or catalog status has been changed.

## Sources and scope

- `handler services.json`: current project-root, user-supplied registry, 5,734 records. It is a bare JSON array without a top-level site/project identifier or export timestamp. Relevant rows all have `payload.panel_key = jap` and `payload.catalog_sync.last_seen_at = 2026-11-13T18:00:15+00:00`. This establishes a provider-key/sync context, **not** the intended site's identity. Confirm this is the target site's export before binding any ProductDefinition.
- `catalog-handler-service-ids.json`: 201 root-row IDs mapped to `instagram-likes-likes`; lookup candidates, not complete current inventory.
- `catalog.json`: Instagram → Likes → Instagram Likes, `not_started`, `product_definition_file: null`; `product_definitions` is empty. Threads Likes is a separate service entry under Instagram → Likes.
- `.ai/service-builder-capabilities.json`: user-provided Builder snapshot dated 2026-11-13, Builder version unspecified. `.ai/README.md`, `WORKFLOW.md`, `DATA-MODEL.md`, `VALIDATION.md`, and `agent-search.json` define the analysis method.
- Local `@elqora/dgp-spec` 1.6.0 declarations, `dgp-sdk` handler state semantics, and Service Builder guidance were inspected. `examples/instagram-likes/` was used for analytical method only. Its 202-row fixture, IDs, and counts are historical and have not supplied current facts.

The registry keeps three distinct identifiers: root `id` is the row ID used by the catalog map; `dgp_handler_id` is `1` across these 194 resolved rows; `external_id` is a distinct `jap:<provider-service-key>` per resolved row. The ProductDefinition contract's `service_id` is a handler service identity, but this export alone does not prove whether the intended Builder expects the root row ID, a transformed service ID, or another site-specific key. Resolve that binding in the target site before implementation. Do not use `dgp_handler_id = 1` as though it identified one Likes variant.

## Reconciliation and classification

The 201 mapped IDs are unique. **194 resolve; seven are stale:** `310, 311, 312, 313, 315, 316, 317`. No mapped row is disabled or locked: all 194 have `is_enabled: true`, `is_locked: false`, and `state_reason: null`. Their source category breakdown is 91 `Instagram Likes`, 48 `Instagram Likes [BOTS]`, 43 `Instagram Likes [Targeted]`, and 12 `Instagram Likes Per Minute`. These four source categories contain 205 current rows in all, leaving **11 relevant current rows omitted from the map** (listed below). No mapped ID is assigned to another catalog key.

| Raw source category | Current rows | Mapped/resolved | Omitted | Treatment |
| --- | ---: | ---: | ---: | --- |
| Instagram Likes | 98 | 91 | 7 | Core Likes candidates, including some bundled outcomes |
| Instagram Likes [BOTS] | 50 | 48 | 2 | Bot/account-type candidates, including one bundle |
| Instagram Likes [Targeted] | 45 | 43 | 2 | Geography/audience candidates, including some bundles |
| Instagram Likes Per Minute | 12 | 12 | 0 | Controlled delivery rate; six plain, six with Impressions |
| Instagram Auto Likes | 84 | 0 | 84 | Separate catalog family: future-post automation, not a normal single-post order |
| Instagram POWER Likes [Latest Posts] | 5 | 0 | 5 | Latest-post package, not a single-post quantity order |
| Instagram THREADS Likes | 2 | 0 | 2 | Separate Threads Likes service under Instagram per source/catalog |
| Instagram Followers &amp; Likes [BOTS with NO REFILL] [CAN FULLY DROP] | 11 | 0 | 11 | Mixed category: five Likes rows, six Followers rows; not silently included in the direct Likes map |

The last four categories were searched as related/adjacent rows, not counted as the 11 omitted direct-category rows. The five Likes rows in the mixed Followers/Likes category are `1181–1184, 1186`; they may be compatible bot Likes candidates but require separate review because their source category also contains Followers. The 84 Auto Likes rows include some bundles; they belong to another order shape. All 84, five latest-post rows, two Threads rows, and eleven mixed-category rows are outside this service's existing mapping. Similar words in names are insufficient for direct fallback assignment.

## Product boundary and variant viewpoints

**Proposed core service:** Likes on a specified Instagram content URL, with quantity and one fulfillment choice. The accepted content type and link format must be confirmed from the target handler/Builder; the registry's `payload.type = Default` does not specify an input schema. Keep Instagram Auto Likes (future posts), latest-post packages, and Threads Likes separate. Bundles that add Impressions, Reach, or Views alter the delivered outcome; either a clearly labeled choice with exact handler binding or another service family is required. Do not treat a bundled handler as a fallback for plain Likes.

| Viewpoint | Current evidence | Design implication |
| --- | --- | --- |
| Account type/quality | Source categories say `[BOTS]`; names also say HQ, MQ, LQ, real-looking, real, and profile picture/posts. | Separate account-type and quality claims; do not infer a verified account quality or customer promise from marketing labels. |
| Geography/audience | `[Targeted]` rows include USA, Brazil, Korea, Arab/Gulf, India, UK, Spain, Taiwan, Nigeria, China, Japan, and mixed regions; some specify male/female. | Use exact target wording. Mixed regions and combined demographic constraints need their own explicit choices. |
| Refill/retention | Names advertise No, 7D, 30D, 90D, 365D, lifetime, auto-refill, non-drop, low-drop; only 15 of 194 mapped rows have `payload.capabilities.refill.enabled = true`. | Label claims conservatively. A named refill duration does not prove a usable refill capability; reconcile before offering it. |
| Delivery | Names specify instant/fast/emergency or per-minute rates; 12 rows use `Instagram Likes Per Minute`. | Controlled rate is a distinct option/dimension from ordinary speed. `dripfeed` capability is separate from the per-minute provider category. |
| Other capabilities | Among mapped rows, 121 `dripfeed`, 107 `cancel`, 15 `refill`, 0 `contract` enabled. | Only show optional capability controls for handlers whose flags support them; hidden inputs must follow actual ordering semantics. |
| Quantity/rate | Mapped payload min ranges 1–250, payload max 300–10,000,000; rates 0.075–39.5 in registry units, not final customer prices. | Validate against the selected handler's payload bounds. Do not apply the saved Quantity template's 10–10,000,000 bounds globally. |

The registry frequently conflicts with its own name text: e.g. row `127` says `[Max: 1M]` but payload max is 10,000,000; row `279` says `[Max: 50K]` but payload max is 300; row `11622` says `[Max: 2K]` but payload max is 10,000,000. Row `139` advertises 30-day auto refill yet has `refill.enabled = false`; row `166` advertises lifetime refill yet also has `refill.enabled = false`. Treat payload bounds/capability flags as operational registry fields and preserve the conflicting name claims for site-owner review. Do not promise the larger bound or refill behavior without confirmation.

## Provisional handler and field plan

- **Selection:** a single explicit choice, grouped by outcome and then target/account/delivery characteristics if that remains readable. The exact candidate handler row is bound to each offered choice; no generic “Other” bucket. Examples for discussion: plain non-targeted `127` (no refill capability), bot `224`, USA targeted `275`, per-minute plain `325`, and per-minute Likes + Impressions `331`. These are **illustrative candidates, not approved primary/fallback mappings**. The last one cannot substitute for plain Likes. The seven stale IDs cannot be bound.
- **Fallbacks:** none proposed yet. An alternate must match delivered outcomes, target, account type, refill promise/capability, input shape, and the selected quantity range. Matching rate or name alone is insufficient. The contract supports explicit `fallbacks.nodes`/`fallbacks.global` lists; no list is justified by this inventory alone.
- **Post link:** required scalar `text/default` field, pending target-site URL/input validation. The snapshot registers this control with no option or multi-value support. Do not invent link validation rules from the category name.
- **Quantity:** required scalar `number/default` field with integer `step: 1` if the target Builder accepts that property. Bind quantity via the DGP `quantity` rule and validate against the selected handler. The saved Quantity template is an editor artifact, not a universal definition; its example bounds and template metadata must not be copied.
- **Variant control:** `select/default` supports single selection with options (`optionCapability.supported: true`, `multiCapability.supported: false`). A `radio/default` is another supported single-choice control. `multiselect/default` and `treeselect/default` support multiple values, but multiple independently selected handler variants would be incoherent for one order, so they are not proposed. `checkbox/default` is scalar despite exposing an `options` UI property; `checkbox/options` is a separate multiple-value registration. Do not use either as an unverified variant picker.
- **Optional drip feed:** only after inspecting actual Builder/order submission behavior. The snapshot registers `toggle/default` as scalar and `number/default` for dependent run/interval values; `dripfeed.enabled` is true on 121 mapped rows. Capability-aware visibility must show the toggle only for supporting handler choices and omit hidden dependent inputs if the runtime promises that behavior. Per-minute rows `325–336` have `dripfeed.enabled = false` despite their provider delivery rate wording.
- **Optional refill/cancel:** flags establish capability, not necessarily customer-facing order controls or duration guarantees. Do not create controls or promises until the target workflow specifies them.

`@elqora/dgp-spec` 1.6.0 defines `ProductDefinition` schema version `1`, `filters`, `fields`, `order_for_tags`, option `service_id`, `visibility_expression`, `quantity`, and `fallbacks`. The present report proposes concepts only. Exact graph/tag IDs, root binding, filter behavior, expression syntax, and site-specific service-ID transformation need a target Builder inspection before JSON authoring. No policy changes are proposed.

## Decisions needed before implementation

1. Confirm this root registry is the intended site/project export and establish the exact service identity that the target Builder expects for a registry row. The bare file does not identify a site.
2. Confirm the boundary for Likes + Impressions/Reach bundles and the five mixed-category bot Likes rows. Recommendation: keep bundles outside the plain-Likes choice set unless clearly labeled as a distinct outcome; review the mixed-category Likes rows as potential bot variants.
3. Confirm which customer choices to expose now. A compact first scope could be plain Likes plus clearly named bot, targeted, and controlled-rate choices, excluding unsupported promises. This is a product decision, not evidence of live storefront availability.
4. Resolve operational conflicts between names and payload limits/refill flags before selecting primary handlers or making refill/retention claims.
5. Inspect the current Builder/ordering behavior for service bindings, capability visibility, hidden-field submission, and URL validation before converting this plan to JSON.

## Appendix: row-level reconciliation

Below, `M` means currently mapped, `O` means omitted from the map, and `S` means stale mapped ID. Capabilities list enabled flags only: `R` refill, `C` cancel, `D` dripfeed, `K` contract. Source names are preserved. Numeric rate is registry data, not a customer price. Every live direct-category row and every stale mapped ID is listed.

| Status | Root ID | DGP handler ID | External ID | Raw category | Name | Payload min–max | Rate | Enabled capabilities |
| --- | ---: | ---: | --- | --- | --- | ---: | ---: | --- |
| M | 127 | 1 | jap:1837 | Instagram Likes | Instagram Likes [Refill: No] [Max: 1M] [Start Time: 0-1 Hr] [Speed: Up to 300K/D]💧 | 10–10000000 | 0.125 | D |
| M | 128 | 1 | jap:10237 | Instagram Likes | Instagram Likes [Refill: No] [Max: 1M] [Start Time: 0 - 1 Hr] [Speed: 200K/D] 💧 | 10–3000000 | 0.175 | CD |
| M | 129 | 1 | jap:4343 | Instagram Likes | Instagram Likes [Refill: No] [Max: 5M] [Start Time: 0 - 1 Hr] [Speed: 100K/D] ⛔💧 | 10–10000000 | 0.275 | CD |
| M | 130 | 1 | jap:1700 | Instagram Likes | Instagram Likes [Refill: No] [Max: 500K] [Start Time: 0 - 1 Hr] [Speed: Up to 100K/D] 💧⛔ | 10–500000 | 0.1375 | D |
| M | 131 | 1 | jap:10296 | Instagram Likes | Instagram Likes [Refill: 30D] [Max: 1M] [Start Time: 0 - 1 Hr] [Speed: 100K/D] 💧 | 100–1000000 | 0.1625 | D |
| M | 132 | 1 | jap:10126 | Instagram Likes | Instagram Likes [Refill: 30D] [Max: 1.5M] [Start Time: 0 - 1 Hr] [Speed: Up to 100K/D] ⛔💧 | 10–1000000 | 0.2375 | CD |
| M | 133 | 1 | jap:10065 | Instagram Likes | Instagram Likes [Refill: 30D] [Max: 500K] [Start Time: 0 - 1 Hr] [Speed: Up to 100K/D] 💧⛔♻️ | 10–500000 | 0.20 | D |
| M | 134 | 1 | jap:3866 | Instagram Likes | Instagram Likes [Refill: No] [Max: 100K] [Start Time: 0 - 2 Hrs] [Speed: 100K/D]💧⛔️ | 10–100000 | 0.3625 | CD |
| M | 135 | 1 | jap:3242 | Instagram Likes | Instagram Likes [Refill: 30D] [Max: 500K] [Start Time: 0-1 Hour] [Speed: 50K/D] 💧⛔♻️ | 10–200000 | 0.4125 | C |
| M | 136 | 1 | jap:1869 | Instagram Likes | Instagram Likes [HQ] [Refill: No] [Max: 300K] [Start Time: 0-1 Hr] [Speed: 25k/D] 💧⛔ | 10–1000000 | 0.175 | CD |
| M | 137 | 1 | jap:8505 | Instagram Likes | Instagram Likes [Refill: No] [Max: 1M] [Start Time: 0 - 2 Hrs] [Speed: Up to 50K/Day]💧 | 10–1000000 | 0.4875 | D |
| M | 138 | 1 | jap:10377 | Instagram Likes | Instagram Likes [Refill: No] [Max: 5K] [Start Time: 0 - 1 Hr] [Speed: 500/D] 💧⛔️ | 10–5000 | 1.0625 | CD |
| O | 139 | 1 | jap:10442 | Instagram Likes | Instagram Likes [Refill: 30D - Auto] [Max: 100K] [Start Time: 0 - 1 Hr] [Speed: 20K/D] 💧⛔♻️ | 10–1000000 | 0.125 | CD |
| M | 140 | 1 | jap:1845 | Instagram Likes | Instagram Likes [HQ] [NON DROP] [Max: 25K] [Start Time: 0-1 Hr] [Speed: 5K/Hr] 💧⛔ | 100–25000 | 1.5625 | D |
| M | 141 | 1 | jap:1761 | Instagram Likes | Instagram Likes [TOP QUALITY] [Refill: 30D] [60K] [Start Time: 0 - 1 Hr] [Speed: 60K/D] ♻️🔥 | 50–60000 | 1.4836 | D |
| M | 142 | 1 | jap:10066 | Instagram Likes | Instagram Real Likes [Refill: 365] [Max: 100K] [Start Time: 0 - 1 Hr] [Speed: 20K/D] 💧⛔♻️ | 10–10000000 | 0.286 | CD |
| M | 143 | 1 | jap:8219 | Instagram Likes | Instagram Likes [Refill: No] [Max: 150K] [Start Time: 0-1 Hour] [Speed: 100K/Day] ⛔💧 | 10–300000 | 0.1875 | CD |
| M | 144 | 1 | jap:8650 | Instagram Likes | Instagram Likes [Refill: No] [Max: 100K] [Start Time: 0-1 Hr] [Speed: 100K/Day] ⛔ 💧 | 100–2500000 | 0.13 | CD |
| M | 145 | 1 | jap:1823 | Instagram Likes | Instagram Likes [Max: 50K] [Start Time: 0-1 Hr] [Speed: 1K/Hour] ⛔🔥💧 | 10–150000 | 0.2375 | C |
| M | 146 | 1 | jap:1782 | Instagram Likes | Instagram Likes [Max: 10K] [Start Time: 0-1 Hr] [Speed: 5K/Hr] 💧⛔ | 50–1000000 | 0.1875 | CD |
| M | 147 | 1 | jap:1805 | Instagram Likes | Instagram Likes [Max: 100K] [Start Time: 0-1 Hr] [Speed: 25K/D] 💧⛔ | 10–100000 | 0.6875 | CD |
| M | 148 | 1 | jap:4289 | Instagram Likes | Instagram Likes [HQ] [FEW DROPS] [Refill: 30D] [Max: 100K] [Speed: 10K/D]💧⛔ | 30–500000 | 0.1238 | D |
| M | 149 | 1 | jap:4173 | Instagram Likes | Instagram Likes [Refill: 30] [Max: 30K]  [Start Time: 0 - 1 Hr] [Speed: 30K/Day] | 10–1000000 | 0.1413 | RCD |
| M | 150 | 1 | jap:1813 | Instagram Likes | Instagram Likes [HQ] [Max: 10K] [Start Time: 0-1 Hr] [Speed: 10K/D] 💧 | 10–10000 | 0.40 | CD |
| M | 151 | 1 | jap:8966 | Instagram Likes | Instagram Likes [Refill: No] [Max: 5K] [Start Time: 0 - 1 Hr] [Speed: 500/D] 💧⛔️♻️ | 20–6000 | 0.375 | RCD |
| M | 152 | 1 | jap:6094 | Instagram Likes | Instagram Likes [WITH CANCELATION] [Max: 5K] [Start Time: 0-1 Hour] [Speed: INSTANT] 💧⚡⛔🔥 | 10–300000 | 0.225 | CD |
| M | 153 | 1 | jap:8216 | Instagram Likes | Instagram Likes [Refill: NO REFILL ] [Max: 100K] [Start Time: 0-1 Hour] [Speed: 300K/Day] ⚡⛔💧 | 10–300000 | 0.1125 | C |
| M | 154 | 1 | jap:7788 | Instagram Likes | Instagram Likes [Refill: 90D] [Max: 150K] [Start Time: 0-1 Hr] [Speed: 150K/Day] ♻️ ⛔ 💧 | 10–100000 | 0.1609 | D |
| M | 155 | 1 | jap:7563 | Instagram Likes | Instagram Likes [Max: 10K] [Refill: No] [Start Time: 0 - 1 Hour] [Speed: 10K/Hour] 💧 | 10–300000 | 0.1125 | C |
| M | 156 | 1 | jap:7795 | Instagram Likes | Instagram Likes [Refill: No] [Max: 80K] [Start Time: 0 - 1 Hour] [Speed: 80K/Day] 💧 | 10–500000 | 0.225 | C |
| M | 157 | 1 | jap:6372 | Instagram Likes | Instagram Likes [Refill: No] [Low Drops] [Max: 200K] [Start Time: 0-1 Hour] [Speed: 100K/D] ⚡⛔ | 50–300000 | 0.225 | C |
| M | 158 | 1 | jap:6126 | Instagram Likes | Instagram Likes [Max: 200K] [Refill: 30Days] [Start Time: 0 - 2 Hours] [Speed: 10K/Day] ⛔💧 | 10–150000 | 0.2375 | C |
| M | 159 | 1 | jap:7742 | Instagram Likes | Instagram Likes [Max: 100K] [Refill: 30] [Start Time: 0 - 1 Hour] [Speed: 30K/Hour] | 10–20000 | 0.4125 | C |
| M | 160 | 1 | jap:1794 | Instagram Likes | Instagram Likes [Refill: 30D] [Max: 250K] [Start Time: 0-1 Hr] [Speed: 50K/Day] | 10–300000 | 0.2375 | CD |
| M | 161 | 1 | jap:3336 | Instagram Likes | Instagram Likes + Reach + Impressions [Refill: 30] [Max: 10K] [Start Time: 0 - 1 Hour] [Speed: 10K/Day] 💧 | 10–100000 | 0.30 | RC |
| M | 162 | 1 | jap:6361 | Instagram Likes | Instagram Likes [Refill: No] [Max: 200K] [Start Time: 0-1 Hour] [Speed: 100K/Day] ⚡ | 50–100000 | 0.1114 | — |
| M | 163 | 1 | jap:6001 | Instagram Likes | Instagram Likes [Refill: No / Low Drops] [Max: 150K] [Start Time: Instant] [Speed: 100K/Day] ⛔ | 50–200000 | 0.35 | C |
| M | 164 | 1 | jap:5956 | Instagram Likes | Instagram Likes [Refill: 30D] [Max: 200K] [Start Time: Instant] [Speed: Up to 100K/D] 💧⛔️♻️ | 10–200000 | 0.225 | C |
| M | 165 | 1 | jap:7787 | Instagram Likes | Instagram Likes [Refill: 30D] [Max: 100K] [Start Time: Instant - 1 Hour] [Speed: 30K/D] ⚡💧⛔️ | 10–100000 | 0.3125 | RCD |
| M | 166 | 1 | jap:7750 | Instagram Likes | Instagram Likes [80% FEMALE] [Refill: LIFETIME GUARANTEED]  [Max: 25K] [Start Time:  Instant] [Speed: 10K/Hour] | 100–1000000 | 0.5625 | C |
| O | 167 | 1 | jap:6562 | Instagram Likes | Instagram Likes [Refill: Auto-Refill 30 Days] [50K] [HQ] [Start Time: Instant] [Speed: 30K/Day] 💧⛔️♻️ | 10–50000 | 0.2063 | RCD |
| M | 168 | 1 | jap:7585 | Instagram Likes | Instagram Likes [Max: 50K] [Start Time: 0 - 1 Hours] [Speed: 50K Per Day] 💧⛔ | 10–50000 | 0.3528 | C |
| M | 169 | 1 | jap:983 | Instagram Likes | Instagram HQ Likes [Max: 100K] [Start Time: 0 - 1 Hour] [Speed: 10K/Day] 💧 | 10–20000 | 0.749 | RCD |
| O | 170 | 1 | jap:7508 | Instagram Likes | Instagram Likes [Refill: 30D Auto] [Max: 100K] [Start Time: 0-1 Hr] [Speed: Up to 50K/D] | 50–100000 | 0.1188 | RCD |
| M | 171 | 1 | jap:7532 | Instagram Likes | Instagram Likes [Refill: 30D] [200K] [Start Time: Instant] [Speed: 10K/D] ♻️💧⛔ | 50–200000 | 0.2503 | RCD |
| M | 172 | 1 | jap:1777 | Instagram Likes | Instagram Likes [NO REFILL] [Max: 150K] [Start Time: 5 Minute] [Speed: 1K/Hour]💧🔥 | 50–150000 | 0.081 | CD |
| M | 173 | 1 | jap:6286 | Instagram Likes | Instagram Likes + Reach + Impressions [Refill: 30D] [200K] [Start Time: Instant] [Speed: 25K/D] ♻️💧⛔️ | 10–200000 | 0.2001 | C |
| M | 174 | 1 | jap:1883 | Instagram Likes | Instagram Likes + Impressions [Max: 45K] [Start Time: 0-1 Hr] [Speed: INSTANT]  🔥🔥🔥 | 10–500000 | 0.6875 | D |
| M | 175 | 1 | jap:7117 | Instagram Likes | Instagram Likes [Refill: No] [Max: 200K] [Start Time: 0-1 Hour] [Speed: 200K/Day] ⚡⛔ | 10–200000 | 0.2375 | CD |
| M | 176 | 1 | jap:1788 | Instagram Likes | Instagram Likes [Max: 200K] [Start Time: 1 Hour] [Speed: 50K/Day] 💧⛔️ | 50–200000 | 0.075 | CD |
| O | 177 | 1 | jap:6689 | Instagram Likes | Instagram Likes [Refill: Auto 30 Days] [Start Time: 2 Hours] [Speed: 50k/Day]💧⛔️♻️ | 50–200000 | 0.10 | RCD |
| M | 178 | 1 | jap:7583 | Instagram Likes | Instagram Likes [Max: 50K] [Start Time: 0-1 Hour] [Speed: INSTANT] 💧⚡🔥⛔ | 50–50000 | 0.1016 | CD |
| M | 179 | 1 | jap:1957 | Instagram Likes | Instagram Likes [HQ][Refill: 30D] [Max: 30K] [Start Time: 0-1 Hr] [Speed: 10K/D] | 10–30000 | 0.3375 | D |
| M | 180 | 1 | jap:6582 | Instagram Likes | Instagram Likes + Impressions + Reach [Max: 45K] [Start Time: Instant] [Speed: 30K/Day] ⚡ | 10–500000 | 1.1444 | D |
| M | 181 | 1 | jap:1768 | Instagram Likes | Instagram Likes + Impressions [HQ] [Max: 7K] [Start Time: Instant] [Speed: 7K/Day]💧🔥 | 10–100000 | 0.1609 | D |
| O | 182 | 1 | jap:5958 | Instagram Likes | Instagram Likes + Reach + Impressions [Auto-Refill: 30 Days] [300K] [MQ] [Start Time: Instant] [Speed: 20K/Day] ♻️💧⛔️ | 10–300000 | 0.2063 | RCD |
| M | 183 | 1 | jap:3343 | Instagram Likes | Instagram Likes [Refill: No] [Max: 3K/order 30k/link] [Start Time: 0-12 Hours] | 50–30000 | 0.348 | CD |
| M | 184 | 1 | jap:1769 | Instagram Likes | Instagram Likes [EXCLUSIVE - Up to 15% Drop Max] [Refill: 30 Days] [Max: 5K] [Start Time: 0-1 Hour] [Speed: 2K/Hour] 💧 | 10–8000 | 0.0756 | CD |
| M | 185 | 1 | jap:4394 | Instagram Likes | Instagram Likes [Refill: 30D] [Max: 500K] [Start Time: 0-1 Hour] [Speed: 20K/Hour] 🔥⚡⚡⚡⛔ | 10–500000 | 0.50 | CD |
| M | 186 | 1 | jap:5628 | Instagram Likes | Instagram Likes [Drops 5-7%] [Refill: 30D] [Max: 10K] [Start Time: 0-1 Hour [Speed: 1-2K/Hour] | 10–10000 | 0.20 | C |
| M | 187 | 1 | jap:5629 | Instagram Likes | Instagram Likes [Drops 5-7%] [Refill: No] [Max: 5K] [Start Time: 0-1 Hour]  [Speed: 1-2K/Hour] | 50–100000 | 0.081 | CD |
| M | 188 | 1 | jap:5630 | Instagram Likes | Instagram Likes [Drops LOW] [Refill: AR30D] [Max: 50K] [Start Time: 0-1 Hour] [Speed: 10K/D]♻️💧⛔ | 1–200000 | 0.5625 | RC |
| M | 189 | 1 | jap:3592 | Instagram Likes | Instagram Likes [Refill: 30D] [Max: 10K] [Start Time: 0-1 Hour] [Speed: 1K+/Hour]💧♻️⛔ | 10–50000 | 0.50 | CD |
| O | 190 | 1 | jap:5631 | Instagram Likes | Instagram Likes [Refill: 30D - AUTO] [Max: 100K] [Start Time: 0-1 Hr] [Speed: Up to 10K/D] 💧⛔️♻️ | 10–100000 | 0.30 | RCD |
| M | 191 | 1 | jap:3019 | Instagram Likes | Instagram Likes [SUPER] [Refill: No] [Max:10K] [Start Time: 0-1 Hour] [Speed: 3K/Hour] | 10–1000000 | 0.1246 | C |
| M | 192 | 1 | jap:3349 | Instagram Likes | Instagram Likes [Max: 150K] [Start Time: 0-1 Hour] [Speed: 5K/Day] 💧♻️🔥🔥 | 10–130000 | 0.247 | C |
| M | 193 | 1 | jap:5560 | Instagram Likes | Instagram Likes + Impressions [Max: 2K] [Start Time: 1 Hour] [Speed: 2K/Day] ⚡ | 10–100000 | 0.1609 | D |
| M | 194 | 1 | jap:8442 | Instagram Likes | Instagram Likes [Refill: 30 Days] [Max: 40K] [Start Time: 0-1 Hour] [Speed: Up to 15K/Day] 💧♻️ | 10–75000 | 0.7201 | D |
| M | 195 | 1 | jap:5670 | Instagram Likes | Instagram Likes [Max: 10K] [Start Time: 0-1 Hour] [Speed: INSTANT] 💧⚡⚡⚡🔥 | 20–30000 | 0.35 | C |
| M | 196 | 1 | jap:3792 | Instagram Likes | Instagram Likes [NON DROP] [Max: 8K] [Start Time: 0-1 Hour] [Speed: 8K/Day] 💧🔥🔥 | 10–1000000 | 0.2318 | CD |
| M | 197 | 1 | jap:1778 | Instagram Likes | Instagram Likes [30K] [REAL ] [1H - 1k/Day] 💧⚡ | 5–50000 | 2.00 | C |
| M | 198 | 1 | jap:3788 | Instagram Likes | Instagram Likes [Max: 10K] [Start Time: 0-1 Hour] [Speed: 10K/Day] | 10–10000000 | 0.51 | C |
| M | 199 | 1 | jap:8036 | Instagram Likes | Instagram Likes [Refill: 365 Days] [Max: 10K] [Start Time: 0-1 Hours] [Speed: 10K/Day] 💧⛔ | 10–10000000 | 0.1788 | CD |
| M | 200 | 1 | jap:1789 | Instagram Likes | Instagram Likes [Refill: 30D] [Max: 50K] [Start Time: 0-1 Hr] [Speed: 20K/Day] 💧♻️ | 10–100000 | 0.275 | D |
| M | 201 | 1 | jap:1916 | Instagram Likes | Instagram Likes [Refill: No] [Max: 5K] [Start Time: 0-1 Hour] [Speed: 2K/Day] | 20–10000 | 1.35 | RCD |
| M | 202 | 1 | jap:1776 | Instagram Likes | Instagram Likes [Refill: No] [Max: 200K] [Start Time: 0-1 Hour] [Speed: 100K/Day] ⛔💧 | 10–200000 | 0.2375 | CD |
| M | 203 | 1 | jap:3585 | Instagram Likes | Instagram Likes [NON DROP] [Max: 5K] [Start Time: 0-1 Hour] [Speed: 500/Hour] | 20–5000 | 1.035 | CD |
| M | 204 | 1 | jap:3525 | Instagram Likes | Instagram Likes [EXCLUSIVE] [NON DROP] [Max: 10K] [Start Time: 0-1 Hour] [Speed: 1K/Hour] | 50–10000 | 1.104 | CD |
| M | 205 | 1 | jap:4127 | Instagram Likes | Instagram Likes [EMERGENCY] [NON DROP] [Max: 5K] [Start Time: 0-1 Hour] [Speed: 2K/Hour] 🔥🔥🔥 | 50–5000 | 1.15 | CD |
| M | 206 | 1 | jap:1950 | Instagram Likes | Instagram Likes [EMERGENCY] [Max: 50K] [Start Time: 0-1 Hour] [Speed: 10/Day ] | 10–5000000 | 0.13 | C |
| M | 207 | 1 | jap:8562 | Instagram Likes | Instagram Likes [FROM APP] [Refill: No] [Max: 100K] [Start Time: 0 - 1 Hour] [Speed: Up to 5K/Day] | 100–100000 | 0.36 | C |
| M | 208 | 1 | jap:4128 | Instagram Likes | Instagram Likes [EMERGENCY] [Max: 10K] [Start Time: 0-1 Hour] [Speed: FAST] 🔥🔥🔥 | 10–100000 | 0.7695 | C |
| M | 209 | 1 | jap:4236 | Instagram Likes | Instagram Likes [Max: 20K] [Start Time: 0-1 Hour] [Speed: FAST] 🔥🔥🔥 | 10–100000 | 1.3125 | CD |
| M | 210 | 1 | jap:1836 | Instagram Likes | Instagram Likes [Max: 2K] [Start Time: 1 Hour] [Speed: 3K/Hour]💧 | 5–50000 | 2.40 | C |
| M | 211 | 1 | jap:3292 | Instagram Likes | Instagram Likes + Impressions + Reach [English PUBLIC with Stories Accounts] [Max: 2K] [Start Time: 0-1 Hour] [Speed: 2K/Hour] 🔥🔥🔥 | 5–50000 | 2.00 | CD |
| M | 212 | 1 | jap:1865 | Instagram Likes | Instagram Likes [Max: 10M] [Start Time: 0-3 Hrs] [Speed: 300K/D] 💧 | 10–10000000 | 0.125 | D |
| M | 213 | 1 | jap:1884 | Instagram Likes | Instagram Likes [EMERGENCY] [Max: 50K] [Start Time: 0-1 Hour] [Speed: INSTANT] | 10–1000000 | 0.275 | C |
| M | 214 | 1 | jap:8397 | Instagram Likes | Instagram RAU™ Likes [Refill: No Drop] [Max: 10K] [Start Time: 0-1 Hour] [Speed: 500/Hr] 💧 | 5–50000 | 2.352 | C |
| M | 215 | 1 | jap:3278 | Instagram Likes | Instagram Likes [Max: 5K] [Start Time: 0-1 Hour] [Speed: 1K/Hour] | 50–100000 | 2.00 | CD |
| M | 216 | 1 | jap:1767 | Instagram Likes | Instagram Likes [Refill: No] [Max: 50K] [Start Time: 0-1 Hour] [Speed: INSTANT] 💧⚡⚡⚡🔥 | 50–50000 | 2.15 | CD |
| M | 217 | 1 | jap:5715 | Instagram Likes | Instagram Likes RAU™ [USA 🇺🇸] [Max: 1.5K] [Refill: 60D] [Start Time: 0 - 1 Hr] [Speed: 1.5K/D] 💧 | 10–20000 | 2.325 | D |
| M | 218 | 1 | jap:4301 | Instagram Likes | Instagram Likes [REAL] [Max: 5K] [Start Time: 0-1 Hour] [Speed: 2K/Hour] | 20–3000 | 3.36 | D |
| M | 219 | 1 | jap:266 | Instagram Likes | Instagram Likes [MIX] [Refill: No] [Max: 6K] [Start Time: 0-1 Hour] [Speed: INSTANT]💧⛔ | 20–3000 | 3.51 | D |
| M | 220 | 1 | jap:5917 | Instagram Likes | Instagram Likes [REAL LOOKING] [Max: 50K] [Start Time: 0-1 Hour] [Speed: 20K/Day] | 10–500000 | 0.495 | CD |
| M | 221 | 1 | jap:1791 | Instagram Likes | Instagram Likes [HQ] [Refill: No] [Start Time: Instant] [Speed: 50k/Day]💧⛔️ | 20–50000 | 3.08 | D |
| M | 222 | 1 | jap:8042 | Instagram Likes | Instagram RAL™ Likes [Refill: Lifetime] [Max: 1K] [Start Time: 0-2 Hours] [Speed: 1K/Hour] ⚡💧 | 5–50000 | 2.40 | C |
| M | 223 | 1 | jap:3020 | Instagram Likes | Instagram Likes [NON DROP] [Max: 10K] [Start Time: 0-1 Hour] [Speed: 10K/Day] | 100–25000 | 0.1728 | — |
| M | 224 | 1 | jap:1863 | Instagram Likes [BOTS] | Instagram Likes [Refill: No] [Max: 1M] [Start time: 0 - 1 Hr] [Speed: 200K/D] 💧⛔️ | 10–1000000 | 0.1125 | CD |
| M | 225 | 1 | jap:5626 | Instagram Likes [BOTS] | Instagram Likes [Refill: No] [Max: 500K] [Start Time: 0 - 1 Hr] [Speed: Up to 100K/D] 💧⛔ | 10–500000 | 0.1375 | D |
| M | 226 | 1 | jap:1967 | Instagram Likes [BOTS] | Instagram Likes [Refill: No] [Max: 1M] [Start Time: 0-3 Hrs] [Speed: Up to 100K/D] 💧⛔ | 10–10000000 | 0.125 | — |
| M | 227 | 1 | jap:7455 | Instagram Likes [BOTS] | Instagram Likes [Refill: 90D] [Max: 1M] [Start time: 0 - 1 Hr] [Speed: 200K/D] 💧⛔️♻️ | 10–1000000 | 0.20 | CD |
| M | 228 | 1 | jap:10149 | Instagram Likes [BOTS] | Instagram Likes [Refill: No] [Max: 5M] [Start Time: 0-3 Hrs] [Speed: Up to 20K/D] 💧⛔ | 10–10000000 | 0.275 | C |
| M | 229 | 1 | jap:2148 | Instagram Likes [BOTS] | Instagram Likes [Refill: 30D] [Max: 500K] [Start Time: 0-1 Hour] [Speed: 50K/D] 💧⛔♻️ | 10–500000 | 0.4125 | CD |
| M | 230 | 1 | jap:9529 | Instagram Likes [BOTS] | Instagram Likes [HQ] [Refill: No] [Max: 500K] [Start Time: 0-3 Hrs] [Speed: 100K/D] 💧⛔️ | 10–10000000 | 0.125 | — |
| M | 231 | 1 | jap:9530 | Instagram Likes [BOTS] | Instagram Likes [HQ] [Refill:NO] [Max: 500K] [Start Time: 0-3 Hrs] [Speed: 100K/D] 💧⛔️ | 10–10000000 | 0.125 | — |
| M | 232 | 1 | jap:4342 | Instagram Likes [BOTS] | Instagram Likes [Refill: No] [Max: 500K] [Start Time: 0-1 Hr] [Speed: 10K/Day]  ⛔ 💧 | 50–100000 | 0.1114 | D |
| M | 233 | 1 | jap:2939 | Instagram Likes [BOTS] | Instagram Likes [Refill: 90D] [Max: 150K] [Start Time: 0-1 Hr] [Speed: 150K/Day] ♻️ ⛔ 💧 | 10–100000 | 0.1609 | D |
| M | 234 | 1 | jap:1820 | Instagram Likes [BOTS] | Instagram Likes [Refill: NO] [Max: 1M] [Start Time: 0-3 Hrs] [Speed: Up to 100K/D] 💧⛔♻️ | 10–10000000 | 0.1313 | — |
| M | 235 | 1 | jap:10150 | Instagram Likes [BOTS] | Instagram Likes [Refill: 30D] [Max: 5M] [Start Time: 0-3 Hrs] [Speed: Up to 20K/D] 💧⛔♻️ | 10–10000000 | 0.1013 | D |
| M | 236 | 1 | jap:8586 | Instagram Likes [BOTS] | Instagram Likes [BOTS] [Refill: No] [Max: 10K] [Start time: 1 Hour] [Speed: 10K/Day] 💧⛔️ | 10–1000000 | 0.1337 | CD |
| M | 237 | 1 | jap:8464 | Instagram Likes [BOTS] | Instagram Likes [LQ] [Refill: No] [Max: 100K] [Start Time: 0 - 6 Hours] [Speed: 10K/Day] 💧⛔️ | 10–200000 | 0.1125 | CD |
| M | 238 | 1 | jap:8409 | Instagram Likes [BOTS] | Instagram Likes [LQ] [Refill: 30D] [Max: 500K] [Start Time: 0 - 3 Hours] [Speed: 10K/Day] 💧⛔️ | 10–500000 | 0.42 | C |
| M | 239 | 1 | jap:9183 | Instagram Likes [BOTS] | Instagram Likes [LQ] [Refill: 30D] [Max: 500K] [Start Time: 0 - 3 Hours] [Speed: 10K/Day] 💧⛔️ | 50–500000 | 0.075 | CD |
| M | 240 | 1 | jap:7797 | Instagram Likes [BOTS] | Instagram Likes [BOTS] [Refill: No] [Max: 30K] [Start time: Instant] [Speed: 30K/Day] | 10–500000 | 0.2448 | C |
| M | 241 | 1 | jap:1864 | Instagram Likes [BOTS] | Instagram Likes [Refill: 60D] [Max: 250k] [Start Time: 0 - 3 Hrs] [Speed: 25K/D] 💧♻️⛔️ | 10–100000 | 0.1674 | D |
| M | 242 | 1 | jap:2994 | Instagram Likes [BOTS] | Instagram Likes [Refill: 90D] [Max: 250k] [Start Time: 0 - 3 Hrs] [Speed: 25K/D] 💧♻️⛔️ | 10–100000 | 0.1712 | D |
| M | 243 | 1 | jap:3130 | Instagram Likes [BOTS] | Instagram Likes [Refill: 365D] [Max: 250k] [Start Time: 0 - 3 Hrs] [Speed: 25K/D] 💧♻️⛔️ | 10–100000 | 0.1738 | D |
| M | 244 | 1 | jap:5781 | Instagram Likes [BOTS] | Instagram Likes [Refill: No] [Max: 10K] [Start Time: 1H] [Speed: 10K/Day] | 10–100000 | 0.1802 | D |
| M | 245 | 1 | jap:8561 | Instagram Likes [BOTS] | Instagram Likes [Refill: 30 Days] [Max: 500K] [Start Time: 0 - 1 Hour] [Speed: 10K/Day] ⛔ | 10–50000 | 0.42 | C |
| M | 246 | 1 | jap:6125 | Instagram Likes [BOTS] | Instagram Likes [Max: 500K] [BOTS] [Refill: 30D] [Start Time: 0 - 1 Hr] [Speed: 50K/Day] ⛔♻️ | 10–500000 | 0.42 | C |
| M | 247 | 1 | jap:2991 | Instagram Likes [BOTS] | Instagram Likes [Refill: 30D] [Max: 300K] [Start Time: 0 - 2 Hrs] [Speed: 20K/Day] ⛔♻️ | 10–300000 | 0.247 | CD |
| M | 248 | 1 | jap:7796 | Instagram Likes [BOTS] | Instagram Likes [Refill: 30D] [Max: 250K] [Start Time: 0 - 1 Hour] [Speed: 100K/Day] 💧⛔️ | 100–150000 | 0.1875 | RCD |
| M | 249 | 1 | jap:5948 | Instagram Likes [BOTS] | Instagram Likes [BOTS] [Refill: 30] [Max: 20K] [Start Time: 0-1 Hour] [Speed: FAST] | 10–300000 | 0.434 | CD |
| M | 250 | 1 | jap:5949 | Instagram Likes [BOTS] | Instagram Likes [BOTS] [Refill: 30 Days] [Max: 20K] [Start Time: 0-1 Hour] [Speed: 10k/Day] ♻️ | 10–300000 | 0.4256 | C |
| M | 251 | 1 | jap:7456 | Instagram Likes [BOTS] | Instagram Likes [Bots] [Refill: 30 Days] [Max: 50K] [Start Time: 0-1 Hour] [Speed: 30-60K/Day] ♻️ | 10–300000 | 0.2375 | CD |
| M | 252 | 1 | jap:5955 | Instagram Likes [BOTS] | Instagram Likes [Refill: No] [Max: 200K] [Start Time: 0-1 Hour] [Speed: 10K/Day] 💧⛔ | 10–50000 | 0.35 | C |
| M | 253 | 1 | jap:2997 | Instagram Likes [BOTS] | Instagram Likes [Max: 50K] [Start Time: 0-1 Hour] [Speed: 1K/Hour] ⛔🔥💧 | 10–50000 | 0.2375 | CD |
| M | 254 | 1 | jap:7789 | Instagram Likes [BOTS] | Instagram Likes [Refill: No] [Max: 30K] [Start Time: 0 - 1 Hour] [Speed: 30K/Day] 💧⛔️ | 10–300000 | 0.364 | C |
| M | 255 | 1 | jap:2993 | Instagram Likes [BOTS] | Instagram Likes [Max: 50K] [Start Time: 0 - 1 Hours] [Speed: 50K Per Day] 💧⛔ | 10–50000 | 0.50 | CD |
| M | 256 | 1 | jap:2192 | Instagram Likes [BOTS] | Instagram Likes [HQ] [Refill: 30D] [Max: 30K] [Start time: 0 - 1 Hr] [Speed: 10K/Day] | 10–30000 | 0.3375 | D |
| M | 257 | 1 | jap:1914 | Instagram Likes [BOTS] | Instagram Likes [NATURAL INCREASE] [Refill: No] [Max: 25K]  🔥 | 10–100000 | 0.1931 | D |
| M | 258 | 1 | jap:1913 | Instagram Likes [BOTS] | Instagram Likes [HQ] [Refill: No] [Max: 20K] [Start Time: 0-1 Hour] [Speed: FAST] 💧⛔ | 10–100000 | 0.1609 | D |
| M | 259 | 1 | jap:2983 | Instagram Likes [BOTS] | Instagram Likes [Bots with PP] [Refill: AR30] [Max: 300K] [Start Time: 0-1 Hour] [Speed: FAST] ⛔♻️ | 10–300000 | 0.20 | RC |
| M | 260 | 1 | jap:8454 | Instagram Likes [BOTS] | Instagram Likes [Refill: No] [Max: 5K] [Start Time: 6 Hours] [Speed: 5K/Day] | 10–500000 | 0.243 | CD |
| M | 261 | 1 | jap:8404 | Instagram Likes [BOTS] | Instagram Likes [Refill: No] [Max: 1K] [Start Time: 0 - 6 Hours] [Speed: 1K/Day] | 10–200000 | 0.234 | CD |
| M | 262 | 1 | jap:5899 | Instagram Likes [BOTS] | Instagram Likes [HQ] [Max: 5K] [Start Time: Instant] [Speed: Instant] 🔥⛔ | 100–25000 | 1.5625 | D |
| M | 263 | 1 | jap:2998 | Instagram Likes [BOTS] | Instagram Likes [Refill: 30 Days] [Max: 5K] [Start Time: 6 Hours] [Speed: 5K/Day] | 10–200000 | 0.2375 | CD |
| M | 264 | 1 | jap:3226 | Instagram Likes [BOTS] | Instagram Likes + Impressions [Refill: 30 Days] [Max: 30K] [Start Time: 0-1 Hour] [Speed: 1-3K/Hour] ♻️ | 50–100000 | 0.1609 | D |
| M | 265 | 1 | jap:1817 | Instagram Likes [BOTS] | Instagram Likes [MQ] [Refill: 30 Days] [Max: 500K] [Start Time: 0-1 Hour] [Speed: 5K/Day] 💧⛔ | 10–100000 | 0.1609 | D |
| M | 266 | 1 | jap:1797 | Instagram Likes [BOTS] | Instagram Likes [MQ] [Refill: 180 Days] [Max: 50K] [Start Time: 0-1 Hour] [Speed: INSTANT] ♻️⚡ | 50–50000 | 1.2482 | RCD |
| O | 267 | 1 | jap:5959 | Instagram Likes [BOTS] | Instagram Likes + Reach + Impressions [Auto-Refill: 30 Days] [300K] [MQ] [Start Time: Instant] [Speed: 20K/Day] 💧♻️⛔️ | 10–300000 | 0.2063 | RCD |
| M | 268 | 1 | jap:4172 | Instagram Likes [BOTS] | Instagram Likes [Refill: No] [Max: 150K] [Start Time: 1 Hour] [Speed: 3K/Day] | 10–150000 | 0.32 | RC |
| M | 269 | 1 | jap:2259 | Instagram Likes [BOTS] | Instagram Likes [Refill: No] [Max: 20K] [Start Time: 0-1 Hour] [Speed: 10K/Hour] 🔥⚡⛔ | 10–20000 | 0.1609 | D |
| O | 270 | 1 | jap:4234 | Instagram Likes [BOTS] | Instagram Likes [NO DROP] [Auto-Refill: 7 Days] [Max: 20K] [Start Time: 0-1 Hour] [Speed: 10K/Day] 🔥💧♻️⛔️ | 10–20000 | 0.264 | RCD |
| M | 271 | 1 | jap:4429 | Instagram Likes [BOTS] | Instagram Likes [Refill: 30 Days] [Max: 100K] [Start Time: 1 Hour] [Speed: 20K/Day] ♻️💧🔥 | 10–100000 | 0.1609 | D |
| M | 272 | 1 | jap:1849 | Instagram Likes [BOTS] | Instagram Likes [MQ] [Refill: No] [Max: 100K] [Start Time: 1 Hour] [Speed: 5K/Day]💧 | 10–100000 | 0.96 | D |
| M | 273 | 1 | jap:1844 | Instagram Likes [BOTS] | Instagram Likes [MQ] [Refill: 180 Days] [Max: 30K] [Start Time: 0-1 Hour] [Speed: INSTANT] 💧♻️⚡⚡⚡ | 10–100000 | 2.70 | D |
| M | 274 | 1 | jap:1819 | Instagram Likes [Targeted] | Instagram Likes RAU™ [USA 🇺🇸] [Max: 1.5K] [Refill: 60D] [Start Time: 0 - 1 Hr] [Speed: 1.5K/D] 💧 | 5–50000 | 2.9124 | CD |
| M | 275 | 1 | jap:8851 | Instagram Likes [Targeted] | Instagram Likes [USA 🇺🇸] [Max: 12K] [Refill: 120D] [Start Time: 0 - 1 Hr] [Speed: 10K/D] 💧⛔♻️ | 10–12000 | 2.25 | D |
| M | 276 | 1 | jap:10209 | Instagram Likes [Targeted] | Instagram Likes [BR 🇧🇷] [Refill: No] [Max: 5K] [Start Time: 0 - 1 Hr] [Speed: 5K/D] 💧⛔️ | 50–5000 | 0.525 | CD |
| M | 277 | 1 | jap:10210 | Instagram Likes [Targeted] | Instagram Likes [BR 🇧🇷] [Refill: No] [Max: 100K] [Start Time: 0 - 1 Hr] [Speed: 50K/D] 💧⛔️ | 50–200000 | 0.6875 | CD |
| M | 278 | 1 | jap:1018 | Instagram Likes [Targeted] | 🇰🇷🇰🇵 Instagram Likes + Impressions + Reach [Korea] [HQ] [Refill: 90 Days] [Max: 10K] [Start Time: 0 - 1 Hour] [Speed: 10K/Day] | 20–10000 | 10.40 | D |
| M | 279 | 1 | jap:8782 | Instagram Likes [Targeted] | Instagram Likes [ARAB] [Refill: 30D] [Max: 50K] [Start Time: 0 - 12 Hrs] [Speed: Up to 10K/D] 💧⛔ | 50–300 | 2.325 | D |
| M | 280 | 1 | jap:10211 | Instagram Likes [Targeted] | Instagram Likes [EG 🇪🇬] [Refill: No] [Max: 100K] [Start Time: 0 - 1 Hr] [Speed: 50K/D] 💧⛔️ | 50–100000 | 1.0625 | CD |
| M | 281 | 1 | jap:10212 | Instagram Likes [Targeted] | Instagram Likes [KSA 🇸🇦] [Refill: No] [Max: 100K] [Start Time: 0 - 1 Hr] [Speed: 50K/D] 💧⛔️ | 10–100000 | 1.7438 | CD |
| M | 282 | 1 | jap:1031 | Instagram Likes [Targeted] | Instagram Likes [🇦🇪 ARAB / 🇮🇳 INDIA / 🇹🇷 TURK MIX] [Refill: 30D] [Max: 200K] [Start Time: 0 - 1 Hr] [Speed: 20K/D] 💧♻️⛔ | 100–200000 | 1.25 | CD |
| M | 283 | 1 | jap:1030 | Instagram Likes [Targeted] | 🇦🇪 Instagram Likes [UAE - ARAB] [Refill: 45D] [Max: 50K] [Start Time: 0 - 1 Hr] [Speed: 5K/D] ⛔💧♻️ | 100–10000 | 2.1875 | D |
| M | 284 | 1 | jap:89 | Instagram Likes [Targeted] | Instagram Likes [ARAB] [Refill: No] [Max: 5K] Start Time: 0-1 Hour] [Speed: 2K/Day] | 20–3000 | 3.36 | D |
| M | 285 | 1 | jap:5731 | Instagram Likes [Targeted] | 🇮🇳 Instagram Likes [INDIA] [Refill: 30 Days] [Max: 100K] [Start Time: Instant] [Speed: 10K/Day] | 10–10000 | 1.75 | CD |
| M | 286 | 1 | jap:1028 | Instagram Likes [Targeted] | 🇮🇳 Instagram Likes [INDIA] [Refill: 30D] [Max: 100K] [Start Time: Instant] [Speed: 15K/Day] | 10–10000 | 2.24 | CD |
| M | 287 | 1 | jap:1822 | Instagram Likes [Targeted] | 🇮🇷Instagram Likes [IRAN] [Refill: No] [Max: 10K] [Start Time: 0-1 Hour] [Speed: 5K/Day] | 100–100000 | 0.88 | — |
| M | 288 | 1 | jap:2987 | Instagram Likes [Targeted] | 🇸🇦🇮🇷Instagram Likes [ARAB - IRAN MIX] [Refill: No] [Max: 10K] [Start Time: 0-1 Hour] [Speed: 5K/Day] | 100–100000 | 0.99 | — |
| M | 289 | 1 | jap:8788 | Instagram Likes [Targeted] | 🇰🇷 Instagram Likes [KOREA] [Refill: No] [Max: 200K] [Start Time: 0-3 Hrs] [Speed: 2K/Day] | 20–200000 | 1.6313 | C |
| M | 290 | 1 | jap:10087 | Instagram Likes [Targeted] | 🇰🇷 Instagram Likes [KOREA] [HQ] [Refill: No] [Max: 50K] [Start Time: 0-3 Hrs] [Speed: 10K/D]💧 | 10–50000 | 7.5525 | D |
| M | 291 | 1 | jap:10088 | Instagram Likes [Targeted] | 🇰🇷 Instagram Likes [KOREA] [HQ] [Refill: 30D] [Max: 50K] [Start Time: 0-3 Hrs] [Speed: 10K/D]💧 | 10–50000 | 9.4288 | CD |
| M | 292 | 1 | jap:8574 | Instagram Likes [Targeted] | 🇮🇳 Instagram Likes [INDIA WOMEN] [Refill: 30 Days] [Max: 10K] [Start Time: Instant] [Speed: 10K/Day] | 10–10000 | 2.1875 | CD |
| M | 293 | 1 | jap:3381 | Instagram Likes [Targeted] | 🇷🇺Instagram Likes + Impressions [RUSSIAN] [NON-DROP] [Max: 150K] [Refill: 30 Days] [Start Time: 1 Hour] [Speed: 2K/Day] 💧🔥♻️ | 50–200000 | 5.00 | D |
| M | 294 | 1 | jap:8048 | Instagram Likes [Targeted] | Instagram Likes [🇦🇪 🇸🇦 ARAB - GULF] [SUPER REAL] [Refill: No] [Max: 3K] [Start Time: 0-1 Hour] [Speed: 3K/Day] | 20–10000 | 2.75 | D |
| M | 295 | 1 | jap:1037 | Instagram Likes [Targeted] | Instagram Likes [Max: 2K] [UK 🇬🇧 ] [Refill: No] [Speed: 2K/Day] [Start Time: 0 - 1 Hours] | 20–2000 | 4.125 | D |
| M | 296 | 1 | jap:8253 | Instagram Likes [Targeted] | Instagram Likes Male [ARAB-GULF] [Max: 50K] [Refill: 30 Days] [Start Time: 0 - 1 Hours] [Speed: 500/Day] | 20–50000 | 2.7875 | RC |
| M | 297 | 1 | jap:8051 | Instagram Likes [Targeted] | Instagram Likes [Max: 2K] [SPAIN 🇪🇸 ] [Refill: No] [Speed: 2K/Day] [Start Time: 0 - 1 Hours] | 20–2000 | 4.125 | D |
| M | 298 | 1 | jap:8050 | Instagram Likes [Targeted] | Instagram Likes [Max: 1K] [TAIWAN 🇹🇼 ] [Refill: No] [Speed: 1K/Day] [Start Time: 0 - 1 Hours] | 20–1000 | 3.50 | D |
| M | 299 | 1 | jap:2294 | Instagram Likes [Targeted] | 🇮🇳 Instagram Likes [INDIA] [Refill: 30D] [Max: 30K] [Start Time: Instant] [Speed: 10K/D] | 10–30000 | 0.3375 | — |
| M | 300 | 1 | jap:411 | Instagram Likes [Targeted] | 🇮🇳 Instagram Likes [INDIA] [Refill: 30D] [Max: 20K] [Start Time: Instant] [Speed: 3K/D] | 10–20000 | 0.275 | D |
| M | 302 | 1 | jap:7839 | Instagram Likes [Targeted] | 🇮🇳 Instagram Likes [INDIA] [Start Time: 0 - 1 Hour] [Speed: 5K/Day] | 20–3000 | 1.32 | — |
| M | 303 | 1 | jap:3794 | Instagram Likes [Targeted] | Instagram Likes [ARAB] [Refill: 30D] [Max: 20K] [Start Time: 1 Hour] [Speed: Up to 5K/Day] | 250–15000 | 3.75 | D |
| M | 304 | 1 | jap:1032 | Instagram Likes [Targeted] | Instagram Likes [Max: 15K] [USA 🇺🇸 ] [Refill: 90 Days] [Speed: 10K/Day] [Start Time: 0 - 1 Hours] 💧 ⛔️ ♻️ | 20–15000 | 1.375 | D |
| M | 305 | 1 | jap:3518 | Instagram Likes [Targeted] | 🇰🇷🇰🇵Instagram Likes [Korea] + Impressions + Reach [Refill: No] [Max: 15K] [Start Time: 1 Hour] [Speed: 5K/Day] | 20–10000 | 12.80 | — |
| M | 306 | 1 | jap:7842 | Instagram Likes [Targeted] | 🇭🇰 Instagram Likes [HONG KONG] [Start Time: 0 - 1 Hour] [Speed: 1K/Day] | 20–1000 | 3.36 | D |
| M | 307 | 1 | jap:1034 | Instagram Likes [Targeted] | Instagram Likes [10K] [UKRAINE] [1H - 10K/Day] | 20–50000 | 23.75 | — |
| M | 308 | 1 | jap:7844 | Instagram Likes [Targeted] | 🇰🇷 Instagram Likes [KOREA] [Start Time: 0 - 1 Hour] [Speed: 2K/Day] | 20–3000 | 3.36 | — |
| M | 309 | 1 | jap:7847 | Instagram Likes [Targeted] | 🇮🇷 Instagram Likes [IRAN] [Start Time: 0 - 1 Hour] [Speed: 1K/Day] | 20–7000 | 4.32 | — |
| M | 314 | 1 | jap:4207 | Instagram Likes [Targeted] | 🇳🇬Instagram Likes [NIGERIA] [Refill: No] [Max: 2K] [Start Time: 1 Hour] [Speed: 2K/Day] | 100–5000 | 25.00 | — |
| M | 318 | 1 | jap:1041 | Instagram Likes [Targeted] | Instagram Likes [MALE] [Afro-Americans] [USA] [250/Day] [NO DROP] | 30–2500 | 13.20 | — |
| M | 319 | 1 | jap:1042 | Instagram Likes [Targeted] | Instagram Likes [FEMALE] [Afro-Americans] [USA] [250/Day] [NO DROP] | 30–2500 | 13.20 | — |
| M | 320 | 1 | jap:7540 | Instagram Likes [Targeted] | 🇨🇳 Instagram Likes [CHINA] [Refill: No] [Max: 6K] [Start Time: Instant] [Speed: 3K/Day] | 20–6000 | 1.50 | — |
| M | 321 | 1 | jap:8460 | Instagram Likes [Targeted] | 🇯🇵 Instagram Likes [JAPAN] [Start Time: 0 - 1 Hour] [Speed: 2K/Day] | 20–1000 | 3.50 | D |
| M | 322 | 1 | jap:1237 | Instagram Likes [Targeted] | Instagram Likes [10K] [AFRICAN] [1H - 10K/Day] | 100–10000 | 39.50 | — |
| M | 323 | 1 | jap:8227 | Instagram Likes [Targeted] | Instagram Likes [ARAB-GULF] [Max: 50K] [Refill: 30 Days] [Start Time: 0 - 1 Hours] [Speed: 500/Day] | 5–2500 | 1.035 | R |
| M | 324 | 1 | jap:8228 | Instagram Likes [Targeted] | Instagram Likes Female [ARAB-GULF] [Max: 50K] [Refill: 30 Days] [Start Time: 0 - 1 Hours] [Speed: 500/Day] | 50–10000 | 2.7875 | RC |
| M | 325 | 1 | jap:5825 | Instagram Likes Per Minute | Instagram Likes [1 Like Per Minute] [Max: 10K] [Start Time: 0-1 Hour] | 20–10000 | 1.35 | — |
| M | 326 | 1 | jap:5820 | Instagram Likes Per Minute | Instagram Likes [5 Likes Per Minute] [Max: 10K] [Start Time: 0-1 Hour] | 20–10000 | 1.35 | — |
| M | 327 | 1 | jap:5821 | Instagram Likes Per Minute | Instagram Likes [10 Likes Per Minute] [Max: 10K] [Start Time: 0-1 Hour] | 20–10000 | 1.35 | — |
| M | 328 | 1 | jap:5822 | Instagram Likes Per Minute | Instagram Likes [25 Likes Per Minute] [Max: 10K] [Start Time: 0-1 Hour] | 20–10000 | 1.35 | — |
| M | 329 | 1 | jap:5823 | Instagram Likes Per Minute | Instagram Likes [50 Likes Per Minute] [Max: 10K] [Start Time: 0-1 Hour] | 20–10000 | 1.35 | — |
| M | 330 | 1 | jap:5824 | Instagram Likes Per Minute | Instagram Likes [60 Likes Per Minute] [Max: 10K] [Start Time: 0-1 Hour] | 20–10000 | 1.35 | — |
| M | 331 | 1 | jap:5826 | Instagram Likes Per Minute | Instagram Likes + Impressions [1 Like Per Minute] [Max: 10K] [Start Time: 0-1 Hour] | 20–10000 | 1.50 | — |
| M | 332 | 1 | jap:5827 | Instagram Likes Per Minute | Instagram Likes + Impressions [5 Likes Per Minute] [Max: 10K] [Start Time: 0-1 Hour] | 20–10000 | 1.50 | — |
| M | 333 | 1 | jap:5828 | Instagram Likes Per Minute | Instagram Likes + Impressions [10 Likes Per Minute] [Max: 10K] [Start Time: 0-1 Hour] | 20–10000 | 1.50 | — |
| M | 334 | 1 | jap:5829 | Instagram Likes Per Minute | Instagram Likes + Impressions [25 Likes Per Minute] [Max: 10K] [Start Time: 0-1 Hour] | 20–10000 | 1.50 | — |
| M | 335 | 1 | jap:5830 | Instagram Likes Per Minute | Instagram Likes + Impressions [50 Likes Per Minute] [Max: 10K] [Start Time: 0-1 Hour] | 20–10000 | 1.50 | — |
| M | 336 | 1 | jap:5831 | Instagram Likes Per Minute | Instagram Likes + Impressions [60 Likes Per Minute] [Max: 10K] [Start Time: 0-1 Hour] | 20–10000 | 1.50 | — |
| O | 11622 | 1 | jap:4356 | Instagram Likes | Instagram Likes [Refill: 365D] [Max: 2K] [Start Time: 0 - 1 Hr] [Speed: Up to 10K/D] 💧 | 10–10000000 | 0.2125 | RC |
| O | 11665 | 1 | jap:109 | Instagram Likes [Targeted] | Instagram Likes [ARAB -  عرب متفاعلين] [Refill: 90 Days] [Max: 500] [Start Time: 0 -12 Hours] [Speed: 500/Day] 💧♻️ | 5–2500 | 1.1025 | R |
| O | 11666 | 1 | jap:8785 | Instagram Likes [Targeted] | 🇸🇦Instagram Likes [ARAB] [SUPER REAL] [Refill: No] [Max: 2K] [Start Time: 0-3 Hrs] [Speed: 500/Day] | 5–2500 | 0.96 | — |
| S | 310 | — | — | — | No current registry row | — | — | — |
| S | 311 | — | — | — | No current registry row | — | — | — |
| S | 312 | — | — | — | No current registry row | — | — | — |
| S | 313 | — | — | — | No current registry row | — | — | — |
| S | 315 | — | — | — | No current registry row | — | — | — |
| S | 316 | — | — | — | No current registry row | — | — | — |
| S | 317 | — | — | — | No current registry row | — | — | — |
