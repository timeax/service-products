# Instagram Stories

20 November 2026 · Proposed routing for site-owner approval

Instagram → Stories → Instagram Stories is the customer-facing roadmap entry `instagram-stories-stories`. It is `not_started`, with no canonical ProductDefinition. I propose a **Story Views** product with explicit choices for all stories, the latest story, regional delivery, and 30-day automatic views. All **21 mapped rows** have a proposed placement across **19 selectable choices and two fallback-only rows**. Nine choices are under **Others**.

## Source and scope

The catalog map contains 21 unique root row IDs, all resolved in the current 5,717-row registry. The local mapping defines the proposed product scope and the export supplies the detailed payload evidence. The export is a JSON array without embedded site or provider-account identifiers. I used only the project-root export for handler facts, with no rows imported from examples or other snapshots.

All 21 rows are enabled, unlocked, and have no state reason. They share `dgp_handler_id: 1`, JAP `panel_key: jap`, `payload.type: Default`, the last-seen time 2026-11-18 08:02:54 UTC, zero missing streak and markup, and no rate adjustment. The numeric IDs below are root row IDs. JAP external IDs are listed separately. Row 52 comes from the raw category `Instagram TOP Services [EXCLUSIVE]`. The other 20 come from `Instagram Story`.

[Catalog](../../catalog.json) · [Mapped row IDs](../../catalog-handler-service-ids.json) · [Registry](../../handler%20services.json)

## Proposed customer choices

Keep **All Stories** as the starting route with 1055, because it explicitly describes all-story delivery and supports drip feed. Use one selected mode at a time. General views, regional views, and Others use a required single-choice selector where the tag contains multiple routes. All Stories, Latest Story and Automatic each have one direct route. Any default bindings on the selector tags are for initial resolution and preview. Verify that selecting an option yields exactly one fulfillment service and that required choices prevent submission on a preview default.

Delivery labels below summarize provider wording and are estimates. The rows distinguish target scope (generic, all, latest), audience (USA/Europe, Gulf Arab, and provider-listed male/female), timing (on demand versus 30-day automatic), and pace (instant wording versus daily pace). The source supplies no refill or contract capability. Provider wording such as “instant” alongside a one-hour start is ambiguous, so preserve the two source concepts as delivery pace and start estimate. Accepted links and what generic Story Views covers are provider details to confirm.

| Tag | Choice | Primary | Ordered backups |
| --- | --- | ---: | --- |
| Story Views | 100K/day, starts within 1 hour | 1049 | — |
| Story Views | 50K/day, starts within 1 hour | 1052 | — |
| Story Views | 4K/day, starts in 1 hour | 1054 | — |
| Story Views | Starts within 1 hour, 80K–100K/day listed pace | 1059 | 1058 |
| Story Views | Instant delivery, starts within 1 hour | 1060 | — |
| All Stories | Views across all stories | 1055 | — |
| Latest Story | Views on the latest story | 1061 | — |
| Regional | USA / Europe | 52 | — |
| Regional | Gulf Arab | 1080 | — |
| Automatic | Automatic story views · 30 days | 1103 | — |
| Others | 40K/day · cancellation and drip feed | 1053 | — |
| Others | 30K/day · orders from 10 | 1062 | — |
| Others | Instant delivery · orders from 50 · cancellation and drip feed | 1063 | — |
| Others | 30K/day · cancellation and drip feed | 1065 | — |
| Others | Instant delivery · one-hour start · cancellation and drip feed | 1066 | — |
| Others | 40K/day · standard delivery | 1068 | — |
| Others | 20K/day · drip feed | 1069 | — |
| Others | 30K/day · audience varies by availability | 1072 | 1073 |
| Others | 30K/day · standard delivery | 1075 | — |

## Fallback decisions

I screened every ordered pair using the local Builder's default strict priority policy, with capability fit and a candidate rate from 95% through 100% of the primary. Proposed backups have the same payload type, cover the primary's full bounds, and preserve its capabilities. Attach the backups to their specific choices in `fallbacks.nodes`, so like-for-like choices control their own alternatives. DGP Core resolves the node list in order before any global candidates.

- **1059 → 1058.** The rows have equal rate (0.1425) and range (100–15,000). Both support cancellation, and 1058 also supports drip feed. Their listed daily pace differs (100K versus 80K), so the choice describes the range and leaves drip feed hidden. Same generic Story Views wording supports a provisional link compatibility assumption.
- **1072 → 1073.** Both have rate 0.25, range 20–30,000, start within an hour and list 30K/day. The primary says male and the alternative says female. Offer an explicit audience-flexible choice whose description says the provider may use male or female accounts. There is no customer targeting promise or drip-feed control on this choice.
- **Other numerical matches.** 1058 → 1059 loses drip feed. 1073 → 1072 also loses drip feed. 1060 → 1055 would switch to explicitly all stories. 1060 → 1061 would switch to the latest story and lose drip feed. 1080 → 1072 or 1073 would drop Gulf Arab targeting. The remaining pairs fail the full-bounds or rate check. No backup crosses into automatic delivery or a different region.

The local default supports these two proposals. The site's effective fallback setting and provider retry behavior still need confirmation.

## Complete mapped inventory

Ranges and rates come from structured payload fields. Provider name maxima sometimes conflict with the payload. For example, 1054 lists 4K in its name and has an API maximum of 1,000,000, and 1063 lists 800 in its name and has an API maximum of 50,000. Use the structured values as current Builder inputs, retain the conflicting evidence, and confirm actual provider acceptance before publishing the affected ranges. Rates are raw catalog rates, with no retail-price claim. C means cancellation and D means drip feed. All capability flags absent from the column are false in the registry.

| Row | JAP external ID | Structured min–max | Raw rate | Caps | Provider name |
| ---: | --- | ---: | ---: | --- | --- |
| 52 | jap:7444 | 100–5,000 | 12.50 | — | 🇺🇸🇪🇺Instagram Story Views [USA/Europe] [Refill: No] [Max: 10K] [Start Time: 0-4 Hours] [Speed: 500-3K/Day] |
| 1049 | jap:312 | 100–1,000,000 | 0.0032 | D | Instagram Story Views [Max: 100K] [Start Time: 0-1 Hour] [Speed: 100K/Day] |
| 1052 | jap:8792 | 50–40,000 | 0.0688 | C D | Instagram Story Views [Max: 50K] [Start Time: 0-1 Hr] [Speed: 50K/D] |
| 1053 | jap:9333 | 50–10,000 | 0.075 | C D | Instagram Story Views [Max: 40K] [Start Time: 0-1 Hr] [Speed: 40K/D]💧⛔ |
| 1054 | jap:4435 | 10–1,000,000 | 0.0168 | — | Instagram Story Views [Max: 4K] [Start Time: 1 Hour] [Speed: 4K/Day] |
| 1055 | jap:414 | 100–50,000 | 0.10 | D | Instagram Story Views [ALL STORIES] [Max: 50K] [Start Time: 0 - 1 Hr] [Speed: 15K/Day] |
| 1058 | jap:900 | 100–15,000 | 0.1425 | C D | Instagram Story Views [Max: 80K] [Start Time: 0-1 Hour] [Speed: 80K/Day] |
| 1059 | jap:6458 | 100–15,000 | 0.1425 | C | Instagram Story Views [Max: 100K] [Start Time: 1 Hour] [Speed: 100K/Day] |
| 1060 | jap:3428 | 100–10,000 | 0.10 | D | Instagram Story Views [Max: 10K] [Start Time: 0-1 Hour] [Speed: INSTANT] ⚡️⭐ |
| 1061 | jap:667 | 20–30,000 | 0.10 | — | Instagram Story Views [LAST STORY ONLY] [Max: 30K] [Start Time: 0-1 Hour] [Speed: 30K/Day] |
| 1062 | jap:546 | 10–50,000 | 0.1063 | C D | Instagram Story Views [Max: 30K] [Start Time: 0-1 Hour] [Speed: 30K/Day] |
| 1063 | jap:8566 | 50–50,000 | 1.125 | C D | Instagram Story Views [Max: 800] [Start Time: 0 - 1 Hr] [Speed: INSTANT] ⛔️💧 |
| 1065 | jap:764 | 100–10,000 | 0.125 | C D | Instagram Story Views [Max: 30K] [Start Time: 0-1 Hour] [Speed: 30K/Day] |
| 1066 | jap:813 | 100–12,000 | 0.1375 | C D | Instagram Story Views [Max: 35K] [Start Time: 1 Hour] [Speed: INSTANT] ⛔️💧 |
| 1068 | jap:413 | 100–40,000 | 0.20 | — | Instagram Story Views [Max: 40K] [Start Time: 0-1 Hour] [Speed: 40K/Day] |
| 1069 | jap:570 | 100–20,000 | 0.22 | D | Instagram Story Views [Max: 20K] [Start Time: 0-1 Hour] [Speed: 20K/Day] |
| 1072 | jap:662 | 20–30,000 | 0.25 | — | Instagram Story Views [MALE] [Max: 30K] [Start Time: 0-1 Hour] [Speed: 30K/Day] |
| 1073 | jap:663 | 20–30,000 | 0.25 | D | Instagram Story Views [FEMALE] [Max: 30K] [Start Time: 0-1 Hour] [Speed: 30K/Day] |
| 1075 | jap:92 | 100–30,000 | 0.30 | — | Instagram Story Views [Max: 30K] [Start Time: 0-1 Hour] [Speed: 30K/Day] |
| 1080 | jap:864 | 20–5,000 | 0.2625 | — | Instagram Story Views [GULF ARAB] [Max: 5K] [Refill: No] [Start Time: 0 - 3 Hrs] [Speed: 5K/D] |
| 1103 | jap:665 | 500–10,000 | 20.00 | — | Instagram AUTO Story Views [30 DAYS] [Max: 10K] [Start Time: 0-1 Hour] [Speed: 10K/Day] |

## Omitted registry rows

A full name/category scan found 34 additional rows in the exact `Instagram Story` provider category. They are outside the mapped product set. The table records each row's disposition. Their presence in the export does not establish product membership. No mapped row was excluded, and no missing or stale ID was inferred from gaps in row numbering.

| Candidate root row IDs | Registry evidence and disposition |
| --- | --- |
| 1051 | Plain views candidate marked `LAST POST` (JAP `jap:10251`, enabled/unlocked, Default, 50–1,000, rate 0.15, C/D). The target wording is ambiguous. If the site owner confirms it belongs here and accepts the same target as Latest Story, give it a distinct choice. It cannot back up 1061 because of its price and narrower bounds. |
| 1050, 1056, 1057, 1064, 1067, 1070, 1071, 1074, 1076, 1077, 1078, 1079 | Story Views bundled with Profile Visits, Likes, Impressions or Interactions. Distinct outcomes. The roadmap associates several with Profile Visits or Impressions. |
| 1081, 1082, 1083, 1084 | Story Likes. Different outcome from views, including a Gulf Arab variant. |
| 1085 | Custom Story Reply. `Custom Comments` requires a link and newline-separated replies. The list supplies quantity. |
| 1086, 1087, 1088, 1089, 1090, 1091, 1092 | Story Poll Votes, with YES/NO, fixed positions, and unspecified option wording. Their payload type is Default. |
| 1093, 1094, 1095, 1096, 1097, 1098, 1099, 1100, 1102 | Different outcomes: impressions (1093), link clicks (1094), provider-labeled Trend (1095), profile visits (1096–1097), slider votes (1098), swipe-ups (1099), sticker link presses (1100), tag taps (1102). |

The wider scan also found 77 and 211 (likes/reach bundles whose audience wording mentions stories), 95 and 123–126 (engagement packages that include story views), and 1169 (Highlights Views, mapped to Instagram Highlights). Rows 1158–1168 and 1170–1179 use the compound Highlights/Visits/Shares category, with names for shares, reposts or profile visits. These rows stay with their respective outcomes and target surfaces.

## Builder fields and contract

The local installed contract is DGP Spec 1.6.0, DGP Core 1.1.0, DGP Validation 1.2.1 and DGP Ordering 1.1.1. The Builder capability snapshot is dated 13 November and does not specify a version. The proposed fields use its registered variants and cardinalities.

| Field | Builder control and binding |
| --- | --- |
| Delivery option | `select/default`, single, options supported, no multi-value. Use the supported search capability on Others. Bind each option to its primary row ID. The selector itself is product routing metadata. |
| Instagram link | Required `text/default`, scalar, under root. Send `link`. Use a description that reflects the chosen target once the accepted link formats are confirmed. Avoid a strict story permalink check until all, latest and automatic formats are known. |
| Quantity | Required `number/default`, scalar with step 1, under root. Use a positive integer as `quantity` and base pricing quantity. Resolve min/max and display bounds from the selected service. The saved Quantity template supplies authoring context and its example bounds are irrelevant here. |
| Drip feed | `toggle/default`, scalar, under root. Show it only when the chosen route's primary and configured backups support it. Use the resolved service capability for the primary and ensure backup fit. |
| Runs and Interval (minutes) | Two `number/default` scalar controls. Require both as positive whole numbers when Drip feed is active, with the toggle including the dependent fields. Send `runs` and `interval` only when applicable. The toggle itself is a Builder control. Verify hidden-field omission in the intended order path. |

1103 is explicitly marketed as automatic for 30 days, but its structured type is `Default`. Its provisional path uses `link` and `quantity`, with no drip feed. Confirm whether it needs a profile link and what quantity measures before publishing it. A day count, expiry date, or JAP subscription payload has no support in this row. Keep 1103 as a proposed selectable route.

[Builder capability snapshot](../../.ai/service-builder-capabilities.json) · [JAP types](../../.ai/JAP-SERVICE-TYPES.md) · [Local contract index](../../.ai/agent-search.json)

## Review and verification

Local checks covered all 21 mapped IDs and both fallback pairs for type, full quantity bounds, capabilities and raw-rate band. The proposed definition has not been authored or validated in Builder. Approval covers the 21-row mapped scope, route labels and choices, and the two backup pairs. Provider link formats, conflicting maxima, automatic quantity meaning and effective site fallback policy are open verification items. Treat a later added handler or changed route as a scope change for review.


## Approved implementation and verification

On 20 November 2026 the site owner approved creating the ProductDefinition. The [canonical JSON](../../products/instagram-stories.json) uses All Stories as the root tag and starting choice. The Story Views, Regional and Others tag bindings provide initial preview defaults. Each of those three tags requires a selection before submission on the local ordering path. The rollout scope is the product JSON, with the catalog status still recorded as `not_started`.

- DGP Validation 1.2.1 reported zero structural and semantic diagnostics against the installed DGP Spec 1.6.0 contract, 21 registry rows, the Builder capability snapshot and the local 5% fallback rate policy.
- DGP Core 1.1.0 resolved 19 unique primaries and the two approved node fallback pairs. Coverage matches all 21 mapped IDs.
- DGP Ordering 1.1.1 resolved one primary and the expected structured bounds per choice. The checks covered 19 choices, three required selectors, rejection of zero and fractional quantities, and drip feed on 10 routes. A drip-feed order required both dependent values, while ordinary orders omitted both even if stale values were present.
- DGP Ordering exposes the bounds in preview and snapshot data, but its snapshot builder accepted an All Stories quantity of 99 against a minimum of 100. Enforcement by the intended site order path remains unverified.
- Builder UI validation and provider fulfillment were not run. The open provider checks in this analysis still apply, including accepted link formats, conflicting maxima and what quantity means for automatic delivery.
