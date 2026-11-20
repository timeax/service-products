# Instagram Shares

2026-11-18 · Approved ProductDefinition and source reconciliation

## Scope and source

The roadmap entry is **Instagram → Shares → Instagram Shares** (`instagram-shares-shares`, `not_started`). The owner approved the local preview for export as the canonical ProductDefinition. It covers one-time Instagram Shares, Reposts, Reposts by Region, and Reposts + Reach. Shares and Reposts carry different outcome labels in the source. The registry gives no descriptions or target subtype for these rows, so exact post and Reel link support and the share destination remain open. [ProductDefinition](../../products/instagram-shares.json) · [Catalog](../../catalog.json) · [Handler registry](../../handler%20services.json)

The current registry is a 5,717-row JSON array without embedded site or provider-account identity. All 14 mapped rows use JAP, `dgp_handler_id: 1`, and `payload.type: Default`. All were last seen at 08:02:54 UTC on 2026-11-18, with zero missing streak, enabled and unlocked, zero markup, and no rate adjustment. I matched all 14 provider external IDs and names to the 14 connected handlers that TygerBooster shows as **Available** in Instagram Shares Lab. This confirms the lab membership for the reviewed rows. The registry supplies the detailed payload values. The map uses root row IDs and the lab lists provider external IDs. [Catalog ID map](../../catalog-handler-service-ids.json) · [TygerBooster service labs](https://tygerbooster.com/admin/service-labs)

## Complete mapping

All 14 mapped root IDs are unique and resolve. Every mapped row has the raw category `Instagram Profile Visits / Highlights / Shares`. The rates below are raw handler rates. All 14 report cancellation, 11 report drip feed, and all report refill and contract disabled. Provider name figures are included as evidence. Structured payload values govern quantity and capability decisions.

| Root row ID | Provider external ID | Outcome / provider qualifier | Payload min–max | Rate | Drip feed | Name delivery claim | Name max |
| ---: | --- | --- | --- | ---: | --- | --- | ---: |
| 1158 | `jap:10058` | Shares | 100–100,000,000 | 0.01 | Yes | 0–1 hour · 200K/day | 10M |
| 1159 | `jap:9590` | Shares | 10–1,000,000 | 0.0125 | Yes | 0–1 hour · 100K/day | 1M |
| 1160 | `jap:584` | Shares | 10–1,000,000 | 0.1775 | Yes | 0–1 hour · 20K/day | 50K |
| 1161 | `jap:9428` | Shares | 100–500,000 | 0.0375 | Yes | 0–24 hours · up to 20K/day | 500K |
| 1162 | `jap:6318` | Shares | 10–1,000,000 | 0.25 | Yes | 0–1 hour · 5M/day | 5M |
| 1170 | `jap:10049` | Repost | 10–100,000 | 11.218 | No | 0–1 hour · up to 10K/day | 50K |
| 1171 | `jap:10050` | Repost | 10–100,000 | 12.482 | No | 0–1 hour · up to 5K/day | 5K |
| 1172 | `jap:10006` | Repost | 10–100,000 | 9.875 | Yes | 0–1 hour · up to 50K/day | 100K |
| 1173 | `jap:1847` | Repost · Brazil flag | 10–100,000 | 9.875 | Yes | 0–1 hour · up to 50K/day | 100K |
| 1174 | `jap:2257` | Repost · Spain flag | 10–100,000 | 9.875 | Yes | 0–1 hour · up to 50K/day | 100K |
| 1175 | `jap:10007` | Repost · UK flag | 10–100,000 | 9.875 | Yes | 0–1 hour · up to 50K/day | 100K |
| 1176 | `jap:2959` | Repost · US flag | 10–100,000 | 9.875 | Yes | 0–1 hour · up to 50K/day | 100K |
| 1177 | `jap:1398` | Reposts | 1–10,000 | 0.50 | Yes | 0–1 hour · speed unspecified | 10K |
| 1178 | `jap:2996` | Reposts + Reach | 10–10,000 | 0.5625 | No | Instant · 3K/day | 10K |

Five named ceilings differ from the payload (1158, 1160, 1162, 1170, 1171). Rows 1170 and 1171 carry a droplet despite `dripfeed.enabled: false`. The four flags provide country labels only. The source gives no definition of how accounts or audiences are classified by region.

## Registry search beyond the map

I scanned Instagram names, categories and descriptions for share, repost, reshare, forward and send variants, then inspected the combined source category. The search found no additional standalone one-time Instagram Shares or Reposts rows for the proposed scope.

| Related rows outside the proposed bindings | Disposition |
| --- | --- |
| 30 (`jap:6835`), 31 (`jap:2135`) | Omitted, one-time `Default` rows in `Instagram THREADS Shares / Comments`. Their names say Threads Reshare and Threads Shares. Both are enabled and unlocked with a 10–20,000 payload range and refill enabled. They belong to a separate **Threads Shares** review under Instagram → Shares, subject to the target link confirmation. |
| 32 | Same Threads compound category, with a comments outcome. |
| 95, 1151, 1154, 1155 | Shares form part of a package or engagement bundle. Existing mappings assign these rows to Packages, Engagement, Impressions or Profile Visits. The simpler mapped Reposts + Reach bundle has its own proposed tag. |
| 1163–1169 | The same combined provider category includes profile-visit handlers and a Highlights Views handler. These rows have existing Profile Visits or Highlights mappings. |
| 1179, 1506, 1510–1512 | `Subscriptions` payloads. Excluded under the one-time scope. |

## Approved tags and options

Every tag has an explicit default binding. Tags with multiple offerings use a single dropdown. Each option overrides its tag default. The option labels use provider-listed delivery figures and structured minima where a choice offers a lower minimum.

| Tag | Default row | Choices and rationale |
| --- | ---: | --- |
| Instagram Shares (root) | 1158 | General entry point, mirroring the Shares default. |
| Shares | 1158 | **Starts within 1 hour · 200K shares/day** (1158); **Starts within 1 hour · 100K shares/day · From 10** (1159); **Starts within 1 hour · 5M shares/day** (1162). 1158 has the broadest payload coverage and lowest rate. 1159 supports 10–99 shares. 1162 has the highest listed delivery rate. |
| Reposts | 1177 | **Starts within 1 hour · From 1 repost** (1177); **Starts within 1 hour · Up to 50K reposts/day** (1172). The default covers single reposts at a lower rate. 1172 extends structured quantity coverage and has an explicit daily speed claim. |
| Reposts by Region | 1173 | **Brazil** (1173), **Spain** (1174), **United Kingdom** (1175), **United States** (1176). Requires an explicit country selection. Brazil is the first-listed source option and the tag default. The precise meaning of the provider flags remains unconfirmed. |
| Reposts + Reach | 1178 | Direct binding. The provider lists instant start and 3K/day. The registry does not specify a separately orderable reach quantity or a reach-to-repost ratio. |

The definition binds ten of the fourteen lab handlers. Rows 1160, 1161, 1170 and 1171 are unassigned. Their advertised starts or speeds and their payload limits and rates provide no clear advantage over the selected choices. Rows 1170 and 1171 also lack drip feed.

Tag and option fallbacks are unconfigured. The Shares choices differ in offered ranges, delivery and rates. For example, 1158 cannot cover 1159's 10–99 orders, and 1159 cannot cover 1158 above 1M. The two generic Reposts choices trade low minimum and lower rate for wider coverage and a specified daily speed. The regional rows have equal rates and limits, with distinct country labels. Row 1178 is the only in-scope bundle. The local strict `lte_primary` default also checks a 95%–100% rate band. Any later fallback needs equivalent customer-facing outcomes, delivery and capability coverage and must pass the applicable host checks.

## Builder and JAP fields

The installed Service Builder contracts are `dgp-spec` 1.6.0 (schema v1), `dgp-core` 1.1.0, `dgp-validation` 1.2.1, `dgp-ordering` 1.1.1 and `dgp-ordering-form-palette` 1.1.5. The canonical contract supports direct tag bindings, per-option service IDs and optional fallback lists. [Builder capability snapshot](../../.ai/service-builder-capabilities.json) · [JAP field guide](../../.ai/JAP-SERVICE-TYPES.md)

| Field | Exact control | Behavior |
| --- | --- | --- |
| Share delivery, Repost delivery, Region | `select/default`, single choice with options | One required selector per relevant tag. Use prompts such as “Choose share delivery” and “Choose a region.” |
| Instagram media link | `text/default`, scalar | Required `link`, with “Paste an Instagram link.” Check general Instagram URL shape. Confirm supported media link subtypes with the site before claiming narrower coverage. |
| Quantity | `number/default`, scalar | Required positive whole-number `quantity`, used for base quantity. Display resolved payload bounds and use a valid example such as “e.g. 100.” |
| Drip feed | `toggle/default`, scalar | Optional Builder control visible when the effective handler's `dripfeed.enabled` is true. The description explains how to schedule deliveries using runs and minutes between them. Hidden on Reposts + Reach. |
| Runs and interval | Two `number/default` scalar fields | Reveal and require both when drip feed is on. Use positive whole numbers with examples such as “e.g. 5” and “e.g. 60.” The JAP parameters are `runs` and `interval` (minutes). |

The JAP `Default` submission uses link and quantity, plus runs and interval when eligible and selected. The toggle itself is a Builder control. The approved definition supplies seven placeholders through field defaults.

## Validation

- The saved JSON parses, matches the approved local seed exactly, and passes the installed DGP Spec ProductDefinition JSON Schema.
- DGP validation 1.2.1 passed with zero diagnostics using the same 14 catalog IDs reconciled against the lab and the documented field capability registry.
- The saved definition resolved five tag defaults and nine option overrides in the Ordering preview with payload-based quantity bounds. Drip feed exposed runs and interval on eligible services and omitted both from the snapshot when hidden, including on Reposts + Reach.
- The local Service Builder preview showed zero diagnostics. The TygerBooster lab was inspected read-only to verify handler membership. Validation of a TygerBooster import and live fulfillment remain unverified.
