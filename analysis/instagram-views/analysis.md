# Instagram Views

2026-11-20 · Approved ProductDefinition and routing analysis

Instagram Views (`instagram-views-views`) covers one-time views on Instagram media. The accepted definition references all **70 enabled, unlocked handlers** in the last verified TygerBooster Views lab. It has **62 unique primary handlers** and **eight fallback-only handlers**. Across **65 selectable routes**, 10 have backups and 55 have a single handler. The root and every customer tag have a default binding. [Canonical ProductDefinition](../../products/instagram-views.json) · [Local Builder preview](http://localhost:5173/?workspace=instagram-views)

## How the handler set was established

I started with the **65 root row IDs** mapped to Instagram Views and resolved all of them against the project registry. An independent scan by Instagram category, name and description found **25 additional one-time views candidates**. Five of those were in the last verified lab inventory: **780, 781, 783, 786 and 790**. The lab scope is therefore 65 mapped rows plus those five additions. The remaining 20 candidates are documented with their provider IDs and exact payload data. Their lab membership remains unconfirmed. There were no stale mapped IDs or exclusions among the 70 lab rows. [Catalog mapping](../../catalog-handler-service-ids.json) · [Scope reconciliation](full-handler-routing-2026-11-19.md#source-and-scope) · [Complete source inventory](handler-inventory-2026-11-19.md#complete-handler-inventory)

The 5,717-row export supplies the handler facts. All 70 lab rows use JAP and `payload.type: Default`, were last seen on 2026-11-18 at 08:02:54 UTC, and share `dgp_handler_id: 1`. The ProductDefinition binds the **root row ID**. The provider `external_id` identifies the JAP service, such as `jap:6454` for row 706. The export has no embedded site or provider-account identifier, so lab membership was reconciled separately. Story, Highlight and profile targets, bundles that add reach or impressions, and all subscription payload types are outside this product scope. [Handler registry](../../handler%20services.json) · [Related service evidence](handler-inventory-2026-11-19.md#related-records-outside-this-one-time-media-scope)

## How the tags and choices were designed

I grouped the main routes by the customer’s media target. Delivery start and pace became field options, since they change how views arrive on the same media type. Priority Delivery is a separate tag for offers explicitly designated Emergency by the provider. **Others** holds named choices for legacy IGTV, generic views, broad-link wording and unusual offers. It also covers every available lab row that lacked a suitable main placement or a compatible fallback role. The coverage rule in `AGENTS.md` drove this step. Counting binding locations alone had hidden the gap in the intermediate definition, which reached just 12 distinct handlers across primaries and fallbacks. [Workspace coverage rule](../../AGENTS.md) · [Complete tag and option mapping](full-handler-routing-2026-11-19.md#tag-defaults-and-main-choices)

| Tag | Default and backup | How the choice was made |
| --- | --- | --- |
| Instagram Views root | 727 → 732 | Use the general Video route as the initial preview binding. |
| Video Post Views | 727 → 732 | Both rows explicitly say All Videos and list a start within one hour. The general route allows the pace to vary. The separate delivery options retain their listed speeds, including 739 at 5M views/hour. |
| Reel Views | 780 → 781 | Both explicitly target Reels. The general route can use either pace. The 5M/day and 500K/day choices keep their own bindings. |
| Photo Post Views | 722 | Photo has one explicit handler and can proceed directly to the shared Link and Quantity fields. |
| Priority Delivery | 728 | Starts with an explicit Emergency Video handler. The 500K/day Video and 5M/day Reel offers can be selected separately. |
| Others | 715 → 714 | Both rows use generic views wording, list 500K/day, and support the same range and capabilities. The field still requires an explicit offer selection. |

Structured payload values determine quantity limits, raw rate and capabilities. The provider name supplies target, start and delivery speed where the payload has no separate value. For example, handler 722 advertises a 10M maximum in its name, but the structured maximum is **1,000,000**. Handler 727’s name includes a droplet even though its payload disables drip feed. Labels retain the original speed units and separate the start window from the pace. Generic Views, All Links, legacy IGTV, `PRVT` and `Auto on/off` label what the provider supplied. Accepted media URLs and the meaning of the ambiguous terms still require confirmation. [Exact row evidence](handler-inventory-2026-11-19.md#complete-handler-inventory)

## How fallbacks were selected

I compared eligible backups with the primary's order type, complete quantity range, enabled capabilities and local rate band. The Builder’s local rule permits a fallback from **95% through 100%** of its primary’s rate and requires capability fit. I then compared media target and the option’s advertised start and pace. The closest match goes first. Each fallback list belongs to a specific tag or option, which allows a general route and a speed-specific route to use different backups even when they share a primary. [Fallback evidence and rate checks](full-handler-routing-2026-11-19.md#fallback-evidence)

- **General Reel** uses **780 → 781**. Both rows have the same rate, bounds and capabilities. The advertised pace differs, so the specific 5M/day Reel route keeps only 780.
- **Video within one hour at 5M/day** uses **751 → 748**. Both preserve the listed speed. Handler 748 allows a one-hour start window, so the separate Instant option for 751 has no backup.
- **Others, delivery speed varies** uses primary **750** and ordered backups **747 → 746 → 749**. Handler 747 preserves 5M/day, 746 lists 10M/day, and 749 lists up to 2M/day. The fixed 5M/day choice uses only **750 → 747**. All three backups for the flexible route fit the primary’s 1.1875–1.25 rate band and full quantity range. Their common accepted link scope still needs verification.
- **Photo and Priority** have single-handler defaults. The candidates that numerically fit 722 lack evidence of photo delivery. The other explicit Emergency All Videos handler, 760, remains selectable at its own rate of 1.50, outside the fallback band for 728 at 0.2556.

The 48 selectable entries under Others use 47 distinct primaries because its fixed and flexible options both use 750. Some rows also serve as backups for separate choices. The full mapping and fallback lists together account for every lab ID. [Others option table](full-handler-routing-2026-11-19.md#others-choices) · [Second-pass routing decisions](routing-review-2026-11-20.md)

## How the order fields follow the payload

Every scoped handler uses the JAP `Default` order type, which requires `link` and `quantity`. The shared Instagram media link is a required `text/default` field with “Paste an Instagram link”. Quantity is a required `number/default` field with “e.g. 1,000”. Preview min and max come from the resolved handler. The Video, Reel, Priority and Others fields are required single-choice `select/default` controls with placeholders. Photo uses its tag binding directly.

Drip feed uses a `toggle/default` control and appears when the resolved handler supports it. Its description explains how to schedule multiple deliveries. With the toggle active, Runs and Interval (minutes) appear as required positive whole numbers, with placeholders “e.g. 5” and “e.g. 60”. The JAP request uses `runs` and `interval` for those optional delivery settings. [Builder capability snapshot](../../.ai/service-builder-capabilities.json) · [JAP type guide](../../.ai/JAP-SERVICE-TYPES.md)

## Approval and validation

The owner approved the final mapping after reviewing the local Service Builder preview. The canonical JSON matches that seed. It passed DGP Spec 1.6.0 schema validation and DGP Validation 1.2.1 with the 70-row registry, field capability snapshot and local fallback policy. Ordering preview resolved all six defaults and all 64 selector options to their intended handlers and checked the selected payload bounds. DGP Core resolved both ordered 750 fallback lists. The flexible option worked in the local browser by scrolling to it. The search box lost keyboard focus during that check. [Approval and verification record](routing-review-2026-11-20.md#acceptance-and-verification)

The TygerBooster lab check on 2026-11-18 applied to an earlier revision. It initially reported six unknown-service diagnostics against 65 catalog rows. After the five Reel rows were added, the lab loaded with zero diagnostics. The approved 70-handler revision has local verification. Live import, currently active host policy, accepted URL formats and actual retry and fulfillment behavior remain unverified. [TygerBooster Views lab](https://tygerbooster.com/labs/226)
