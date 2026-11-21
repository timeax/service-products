# Instagram Profile Visits

20 November 2026 · Proposed routing for site-owner approval

The roadmap entry is Instagram → Profile Visits → Instagram Profile Visits (`instagram-profile-visits-profile-visits`). It is `not_started` and has no canonical ProductDefinition. I propose one-time profile visits as the starting mode, with explicit choices for Story targets, Reel and Story bundles, and related combinations. **22 mapped handlers plus one omitted match** yield **22 customer choices and one fallback-only row**. Six choices are under **Others**.

## Sources and scope

All 22 unique mapped root row IDs resolve in the 5,717-row local registry. A full name and category scan, including misspellings, found 1096 (`jap:3429`). The source calls it `Instagram Story POFILE VISTS` under `Instagram Story`. Its name, category, outcome, pace and payload type align with mapped Story Profile Visits row 1097. Add it to the proposal as its own selectable route. Its 100 minimum versus 1097's 10 and its 1.00 raw rate versus 2.00 prevent either from replacing the other under the policy. The source is a local row array without embedded site or provider-account identity. Live site membership was not independently confirmed.

All 23 proposed rows are enabled and unlocked, have no state reason, and share JAP `panel_key: jap`, `dgp_handler_id: 1` and `payload.type: Default`. All were last seen 2026-11-18 at 08:02:54 UTC with zero missing streak, zero markup, and no rate adjustment. No row reports refill or contract capability. The proposal uses root row IDs. Provider external IDs are recorded separately.

| Omitted or adjacent registry rows | Decision |
| --- | --- |
| 1096 | Add as a selectable Story Profile Visits choice. |
| 1473, 1518 | Automatic profile visits with `Subscriptions` payloads. Separate future Instagram Subscriptions scope because they require recurring delivery inputs. |
| 1480 | Automatic impressions, reach and profile visits with `Subscriptions` payload. Same recurring scope distinction, with additional outcomes. |
| 1158–1162, 1170–1178 | Shares and reposts in the compound provider category. They belong to the existing Shares mapping. |
| 1169 | Highlights Views in the compound category. It belongs to the Highlights mapping. |
| 1179 | Automatic reposts. Different outcome and recurring `Subscriptions` payload. |

The subscription rows are visible in the local export and absent from the one-time Profile Visits mapping. Reconcile them against the Instagram Subscriptions roadmap before any future definition. No mapped row is excluded or stale.

[Roadmap](../../catalog.json) · [ID map](../../catalog-handler-service-ids.json) · [Registry](../../handler%20services.json)

## Proposed customer choices

Use **Profile Visits** as the root with 1163 as the preview default, and require a delivery choice under each tag. Each choice resolves one primary. Use explicit outcome labels for bundles. Start and pace are provider estimates. Story Profile Visits tracks visits attributed to stories, Reel bundles explicitly name Reels, and the generic impressions rows leave their precise post link scope to provider confirmation. Keep the two plain profile rows distinct from combinations and retain the two slash-labeled rows as written until their outcome is confirmed. All matching rows are one-time. Delivery wording alone supplies no evidence of retention, refill, or guarantees.

| Tag | Choice | Primary | Ordered backups |
| --- | --- | ---: | --- |
| Profile Visits | 50K/day | 1163 | — |
| Profile Visits | 1M/day · provider lists a one-hour start | 1165 | — |
| Story Profile Visits | 100K/day · orders from 10 | 1097 | — |
| Story Profile Visits | 100K/day · alternate | 1096 | — |
| Story Bundles | Story Views + Profile Visits · delivery pace varies | 1050 | 1056 |
| Story Bundles | Story Views + Profile Visits · 6K/day · drip feed | 1057 | — |
| Story Bundles | Story Views + Impressions + Profile Visits | 1070 | — |
| Story Bundles | Story Views + Impressions + Profile Visits + Interactions · 100K/day | 1071 | — |
| Story Bundles | Story Views + Impressions + Profile Visits + Interactions · instant delivery | 1076 | — |
| Story Bundles | Story Views + Likes + Impressions + Profile Visits | 1077 | — |
| Story Bundles | Story Views + Likes + Impressions + Profile Visits + Interactions | 1078 | — |
| Reel Bundles | Impressions + Reach + Profile Visits · instant delivery | 794 | — |
| Reel Bundles | Impressions + Reach + Profile Visits · orders from 10 | 798 | — |
| Impressions + Reach | Impressions + Reach + Profile Visits · 50K/day | 1107 | — |
| Impressions + Reach | Impressions + Reach + Profile Visits · instant delivery | 1122 | — |
| Impressions + Reach | Reach + Impressions + Profile Visits · 100K/hour | 1149 | — |
| Others | Impressions + Reach + Profile Visits · instant delivery alternate | 1124 | — |
| Others | Engagement + Shares + Reach + Impressions + Profile Visits | 1155 | — |
| Others | Profile Visits + Reach + Impressions · 50K/day | 1164 | — |
| Others | Profile Visits + Reach · 12K/day | 1166 | — |
| Others | Profile Visits / Views · 10K/hour | 1167 | — |
| Others | Profile Visits / Views · 100K/day | 1168 | — |

## Fallback decisions

Screened every ordered pair for identical payload type, full primary range coverage, the local strict 95%–100% rate band, and capability fit. Then compared advertised outcome and target.

- **1050 → 1056** is the matching Story Views + Profile Visits backup. Both are 10–15,000 at 0.35, start within one hour by provider wording, and support cancellation. 1056 also supports drip feed, while 1050 does not. The choice allows delivery pace to vary because the listings say 50K/day and 5K/day. Leave drip feed off for this route. Keep the chain attached to the choice in `fallbacks.nodes`. The reverse would lose drip feed.
- **1070 → 1124** has numerical and capability fit, but would exchange Story Views for a reach bundle with an unspecified target surface.
- **1122 → 1167** has numerical and capability fit, but the alternate's Profile Visits / Views wording does not support the full impressions and reach bundle.
- **1155 → 1168** has numerical and capability fit, but would remove the listed engagement, shares, reach and impressions.
- 1057's wider range cannot fall back to 1050 or 1056. The two plain profile handlers and two Story Profile Visits handlers have raw rates too far apart to share a chain. The remaining pairs fail the numerical screen.

## Complete registry evidence

Structured bounds describe the exported service record and drive local previews. Provider names contain conflicting maxima, especially 798 (25K in its name versus 217,545,811 in payload) and 1096 (100K versus 10M). Confirm the real accepted limits before publication and avoid advertising the larger figures as provider guarantees. Both 1122 and 1124 list instant delivery with the same structured range, but have different raw rates and different name maxima. Offer 1124 as the explicit alternate choice under Others. Reconfirm the meaning of the slash in 1167 and 1168. C means cancellation and D means drip feed.

| Row | JAP external ID | Original category | Structured min–max | Raw rate | Caps | Original provider name |
| ---: | --- | --- | ---: | ---: | --- | --- |
| 794 | jap:3910 | Instagram Reel | 100–100,000,000 | 0.22 | — | Instagram Reel Impressions + Profile Visits + Reach [Max: 100M] [Start Time: 0-1 Hour] [Speed: INSTANT] |
| 798 | jap:3816 | Instagram Reel | 10–217,545,811 | 0.0767 | C | Instagram Reel Impressions + Reach + Profile Visits [Max: 25K] |
| 1050 | jap:617 | Instagram Story | 10–15,000 | 0.35 | C | Instagram Story Views + Profile Visits [Max: 1M] [Start Time: 0 - 1 Hr] [Speed: 50K/D] 💧 |
| 1056 | jap:3744 | Instagram Story | 10–15,000 | 0.35 | C D | Instagram Story Views + Profile Visits [Max: 15K] [Start Time: 0-1 Hr] [Speed: 5K/D] 💧⛔ |
| 1057 | jap:3273 | Instagram Story | 10–26,000 | 0.3625 | C D | Instagram HQ Story Views + Profile Visits [Max: 6K] [Start Time: 0-1 Hr] [Speed: 6K/D] 💧⛔ |
| 1070 | jap:8302 | Instagram Story | 10–100,000 | 0.225 | D | Instagram Story Views + Impressions + Profile Visits [Max: 100K] [Start Time: 0-1 Hour] [Speed: 100K/Day] |
| 1071 | jap:8303 | Instagram Story | 20–100,000 | 0.2438 | D | Instagram Story Views + Impressions + Profile Visits + Interactions [Max: 100K] [Start Time: 0-1 Hour] [Speed: 100K/Day] |
| 1076 | jap:3345 | Instagram Story | 100–100,000 | 0.30 | D | Instagram Story Views + Story Profile Visits + Story Impressions + Story Interactions [Max: 100K] [Start Time: 0-1 Hour] [Speed: INSTANT] |
| 1077 | jap:8306 | Instagram Story | 20–100,000 | 0.3125 | D | Instagram Story Views + Likes + Impressions + Profile Visits [Max: 100K] [Start Time: 0-1 Hour] [Speed: 100K/Day] |
| 1078 | jap:8304 | Instagram Story | 20–100,000 | 0.3375 | D | Instagram Story Views + Likes + Impressions + Profile Visits + Interactions [Max: 100K] [Start Time: 0-1 Hour] [Speed: 100K/Day] |
| 1096 | jap:3429 | Instagram Story | 100–10,000,000 | 1.00 | — | Instagram Story POFILE VISTS [Max: 100K] [Start Time: 0-1 Hour] [Speed: 100K/Day] |
| 1097 | jap:3275 | Instagram Story | 10–100,000 | 2.00 | — | Instagram Story Profile Visits [Max: 100K] [Start Time: 0-1 Hour] [Speed: 100K/Day] |
| 1107 | jap:3596 | Instagram Impressions | 10–1,000,000 | 0.035 | C D | Instagram Impressions + Reach + Profile Visits [Max: 1M] [Start Time: 0-1 Hour] [Speed: 50K/Day] 💧 |
| 1122 | jap:4410 | Instagram Impressions | 10–1,000,000 | 0.127 | C D | Instagram Impressions + Reach + Profile Visits [Max: 5M] [Start Time: 0-1 Hour] [Speed: INSTANT] 💧 |
| 1124 | jap:3855 | Instagram Impressions | 10–1,000,000 | 0.225 | C D | Instagram Impressions + Reach + Profile Visits [Max: 10K] [Start Time: 0-1 Hour] [Speed: INSTANT] 💧 |
| 1149 | jap:7525 | Instagram Reach | 10–1,000,000 | 0.55 | C D | Instagram Reach + Impressions + Profile Visits [Max: 100K] [Start Time: INSTANT] [Speed: 100k/Hr] |
| 1155 | jap:7528 | Instagram Engagement | 100–100,000 | 0.8925 | — | Instagram Engagement + Shares + Reach + Impressions + Profile Visits [Max: 100K] [Start Time: INSTANT] [Speed: 100k/Hr] |
| 1163 | jap:1163 | Instagram Profile Visits / Highlights / Shares | 10–1,000,000 | 0.025 | C D | Instagram Profile Visits [Max: 500K] [Start Time: 0 - 1 Hr] [Speed: 50K/Day]💧⛔ |
| 1164 | jap:8220 | Instagram Profile Visits / Highlights / Shares | 10–1,000,000 | 0.075 | C D | Instagram Profile Visits + Reach + Impressions [Max: 1M] [Start Time: 0 to 1 Hour] [Speed: 50K/Day] ⛔️💧 |
| 1165 | jap:4409 | Instagram Profile Visits / Highlights / Shares | 10–1,000,000 | 0.0813 | C D | Instagram Profile Visits [Max: 5M] [Start Time: 1 Hour] [Speed: 1M/Day]💧⛔ |
| 1166 | jap:7701 | Instagram Profile Visits / Highlights / Shares | 100–1,000,000 | 0.0945 | C D | Instagram Profile Visits + Reach [Max: 12K] [Start Time: 0 to 1 Hour] [Speed: 12K/Day] ⛔️💧 |
| 1167 | jap:1891 | Instagram Profile Visits / Highlights / Shares | 10–1,000,000 | 0.125 | C D | Instagram Profile Visits / Views [Max: 100K] [Start Time: 0-1 Hour] [Speed: 10K/Hour] |
| 1168 | jap:1067 | Instagram Profile Visits / Highlights / Shares | 10–1,000,000 | 0.875 | C D | Instagram Profile Visits / Views [Max: 100K] [Start Time: 0-1 Hour] [Speed: 100K/Day] ⚡️💧🔥 |

## Builder field plan

The installed local contract is DGP Spec 1.6.0, DGP Core 1.1.0, DGP Validation 1.2.1 and DGP Ordering 1.1.1. Use the registered controls in the 13 November capability snapshot. The Builder properties panel exposes the generic `defaults.placeholder` property.

| Input | Builder control and payload |
| --- | --- |
| Delivery choice | Required `select/default`, single, with service-bound options and “Choose a delivery option” placeholder. Enable search in Others. The selection is routing state. |
| Instagram link | Required `text/default` scalar with a placeholder such as “Paste the Instagram link”. Send `link`. Use target-specific label or help on profile, Story and Reel modes where supported. Exact accepted link shapes for generic and slash-labeled options need confirmation. |
| Quantity | Required `number/default` scalar, step 1, with “Enter a quantity” placeholder. Send `quantity` and use it as base quantity. Preview the structured service bounds. Verify host enforcement before publication, since local DGP Ordering can expose bounds without rejecting all out-of-range snapshots. |
| Drip feed | `toggle/default` scalar. Show it only when the resolved primary and its configured backups support it. The fallback-capable 1050 choice leaves it hidden. |
| Runs and Interval (minutes) | Required `number/default` scalar controls when enabled, step 1, with placeholders “e.g. 5” and “e.g. 60”. Send `runs` and `interval` only for active drip feed. Verify the snapshot omits stale values when hidden. |

These `Default` routes have no newline-list input. Confirm that a bundle's quantity has the expected meaning across all its named outcomes. Avoid per-metric promises or separate counters without provider evidence.

[Builder capability snapshot](../../.ai/service-builder-capabilities.json) · [JAP order fields](../../.ai/JAP-SERVICE-TYPES.md) · [Local contract index](../../.ai/agent-search.json)

## Verification and approval

The local check reconciled the complete mapped and omitted ID sets, checked state and coverage for all 23 proposed handlers, and screened every possible backup pair. Builder validation and provider fulfillment have not run. Review the inclusion of 1096, the one-time scope, and the one proposed fallback. Confirm accepted target links, slash-label meaning, bundle quantities, effective site fallback policy and conflicting provider maxima before going live. Approval is required before creating `products/instagram-profile-visits.json`.


## Approved implementation and verification

On 20 November 2026 the site owner approved the 23-handler routing and creation of the [canonical ProductDefinition](../../products/instagram-profile-visits.json). Profile Visits is the starting tag with 1163 as its preview default. All six tags require a delivery choice, and the root delivery selector is hidden on child tags. Text, numeric and select inputs have placeholders. Profile, Story and Reel tags include link guidance. The catalog status remains `not_started`.

- Local DGP validation returned zero structural and semantic diagnostics using the 23 approved registry rows, the Builder capability snapshot, and the strict local 5% fallback rate band.
- DGP Core resolved the approved 1050 → 1056 fallback and confirmed coverage of all 23 approved IDs.
- DGP Ordering resolved one primary and the expected structured bounds for all 22 choices. It rejected missing delivery choices and fractional quantities, showed drip feed on 16 routes, required both dependent inputs when enabled, and omitted stale runs and interval values when hidden.
- Builder UI validation, site-side quantity enforcement and live provider fulfillment were not run. Provider link formats, conflicting maxima and the exact meaning of quantities for bundles remain open.


## Builder scope correction

On 20 November 2026 the site owner reported `service_reference_unknown` for row 1096 at `o:story-profile-visits:100k-day-alternate` and requested removal. The local export still records 1096 as enabled and unlocked. The Builder's current registry did not resolve it. Removed only that option from the canonical definition. The remaining 22 mapped handlers are covered by 21 selectable choices and one fallback. Local DGP validation against the mapped registry returned zero diagnostics, and the Story Profile Visits route resolved to 1097 in the ordering preview.
