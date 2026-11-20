# Instagram Views full handler routing

2026-11-19 · Proposal for approval

The saved ProductDefinition reaches **12 of the 70** handler rows in the last verified TygerBooster Views lab. Its 16 direct bindings reuse 11 unique handlers, and the fallback lists add one more unique handler. This proposal routes **all 70**: **15** distinct handlers directly under the main tags, **47** as selectable **Others** choices, and **8** exclusively through ordered fallbacks. Nine primary-to-fallback pairs are proposed. One fallback, 781, also has its own Reel choice. No in-scope row is excluded.

## Source and scope

The roadmap classifies this as Instagram → Views → Instagram Views (`instagram-views-views`, status `not_started`). The last verified [TygerBooster lab](https://tygerbooster.com/labs/226) contained the 65 mapped rows plus 780, 781, 783, 786 and 790. All 65 mapped IDs resolve, with no stale IDs. The local 5,717-row [registry export](../../handler%20services.json) supplies the current local state and payloads. All 70 lab IDs are enabled and unlocked, use JAP `payload.type: Default`, and were last seen by the catalog sync on 2026-11-18 at 08:02:54 UTC. The export carries no embedded site or account identifier. Lab membership comes from the previously verified site inventory. References below use root row IDs. The shared `dgp_handler_id` is 1, and each provider `external_id` is recorded separately in the [row evidence](handler-inventory-2026-11-19.md#complete-handler-inventory).

The independent registry scan gives 90 one-time media-view candidates in three provider categories, Instagram Views (55), Instagram Reel (18), and Instagram IGTV (17). The 20 additional registry rows outside the last verified lab are **716, 725, 744, 754, 757, 762, 766, 782, 784, 785, 787, 788, 789, 791, 793, 795, 796, 799, 800, 801**. Their lab membership is unconfirmed. If added or confirmed, each needs a documented placement in an expanded review before binding. Stories, profile/Highlights, and views bundled with impressions or other outcomes are separate offerings. Subscription types are outside scope. [Roadmap](../../catalog.json) · [ID mapping](../../catalog-handler-service-ids.json) · [Adjacent scope evidence](handler-inventory-2026-11-19.md#related-records-outside-this-one-time-media-scope)

## Rules and variant decisions

- `AGENTS.md` governs coverage. Its requirement to place every enabled, unlocked lab row overrides the selective-mapping guidance in the TygerBooster guide and the provisional holds in the prior Views report. The workflow and validation guidance still governs fallback compatibility, source reconciliation, and approval.
- Media target determines the main tags. Delivery start, speed, and the provider's Emergency designation become choices within a tag. **Others** provides named routes for legacy IGTV, unspecified media types, broadly advertised link scopes, and unusual wording. The source distinguishes start time from pace. When a name says “Instant” under Speed, its separate start window still applies.
- Structured payload values determine input type, quantity limits and capability flags. Use provider labels for target, start and speed evidence where the payload has no structured equivalent. For example, 722 has a structured maximum of 1,000,000 despite a name that says 10M, and 727 lacks drip feed despite the droplet symbol. Row 739 lists 5M/hour but no start time, so the proposal corrects its current start-time label and preserves its option ID.
- The local Builder default is `lte_primary` at 5% with capability fit. Each proposed alternate costs 95% to 100% of its primary and covers the primary's entire structured quantity range and enabled capabilities. Target and promised delivery wording also guided pairing. The local packages inspected were Builder's installed DGP Spec 1.6.0 and DGP Validation 1.2.1, along with the core service-filter logic and Builder's canonical fallback configuration. Publication policies are outside this proposal.

[AGENTS](../../AGENTS.md) · [AI index](../../.ai/README.md) · [Workflow](../../.ai/WORKFLOW.md) · [Data model](../../.ai/DATA-MODEL.md) · [Validation](../../.ai/VALIDATION.md) · [Local source index](../../.ai/agent-search.json) · [TygerBooster guide](../../.ai/TYGERBOOSTER-SERVICE-BUILDER.md) · [Historical method](../../examples/instagram-likes/decisions-and-pitfalls.md)

## Tag defaults and main choices

Root defaults to **727 → 732**. Video Post Views defaults to **727 → 732**, Reel Views to **780 → 781**, Photo Post Views to **722**, Priority Delivery to **728**, and Others to **715 → 714**. The Others default supports the initial preview. A required explicit choice prompts the customer to select the named offer before ordering. Photo and Priority have single-handler defaults because the available alternatives differ in target, delivery promise or price band.

| Tag | Customer-facing option | Primary | Ordered fallback |
| --- | --- | ---: | ---: |
| Video Post Views | General delivery · Starts within 1 hour | 727 | 732 |
| Video Post Views | Starts within 1 hour · 1M views/day | 708 | — |
| Video Post Views | Starts within 1 hour · 5M views/day | 751 | 748 |
| Video Post Views | Starts within 1 hour · 10M views/day | 720 | — |
| Video Post Views | Starts within 1 hour · 20M views/day | 706 | — |
| Video Post Views | Starts within 1 hour · 10K views/hour | 737 | — |
| Video Post Views | Instant start · 5M views/day | 751 | — |
| Video Post Views | 5M views/hour · Start time unspecified | 739 | — |
| Reel Views | General delivery · Starts within 1 hour | 780 | 781 |
| Reel Views | Starts within 1 hour · 500K views/day | 781 | — |
| Reel Views | Starts within 1 hour · 5M views/day | 780 | — |
| Reel Views | Starts within 1 hour · 100M views/day | 790 | — |
| Reel Views | Starts within 3 hours · 1M views/day | 786 | — |
| Photo Post Views | Tag selection · Starts within 1 hour · 500K views/day | 722 | — |
| Priority Delivery | Video post · Starts within 1 hour · 400K views/day | 728 | — |
| Priority Delivery | Video post · Starts within 1 hour · 500K views/day | 760 | — |
| Priority Delivery | Reel · Starts within 1 hour · 5M views/day | 783 | — |

Priority means the provider designated the row Emergency. Photo can go straight to Link and Quantity because it has one choice. General Video and General Reel use a one-hour start and leave delivery speed flexible. The Reel 5M/day choice keeps its own primary only. A 500K/day fallback is appropriate for General Reel, where no daily pace is advertised.

## Others choices

Each row below is a selectable option. Labels distinguish target wording, start, pace or a real quantity/capability difference. For otherwise identical offers, “Alternate” presents a second independently selectable route whose quote is shown by its actual selected handler. General Views means the provider gave no specific media format. “All Links” and “All” reproduce provider scope labels without claiming universal format coverage. IGTV means Instagram's legacy long-form video format. Supported link formats for generic, broad, legacy, `PRVT` and `Auto on/off` offerings still need site/provider checks. Their recorded placement is an explicit option, with qualifiers visible where they affect the choice.

| Customer-facing option | Primary | Ordered fallback |
| --- | ---: | ---: |
| General views · Within 1 hour · 200K/day | 704 | — |
| General views · Within 1 hour · 500K/day · Alternate | 705 | — |
| General views · Starts in 1–4 hours · 5M/day | 707 | — |
| Emergency views · Within 1 hour · 50K/day | 709 | — |
| General views · Within 1 hour · 100K/day | 710 | — |
| General views · Within 1 hour · 1M/day | 711 | — |
| All Links · Emergency · Within 3 hours · 500K/day | 712 | — |
| General views · Within 1 hour · 100K/day · Drip feed available, cancellation unavailable | 713 | — |
| General views · Within 1 hour · 500K/day | 715 | 714 |
| All Links · Within 1 hour · 500K/day | 717 | — |
| General views · Within 1 hour · 5M/day | 718 | — |
| General views · Instant start · 3K/minute | 719 | — |
| General views · Within 1 hour · 5M/day · Drip feed available, cancellation unavailable | 724 | — |
| All · Within 1 hour · 100K/day | 726 | — |
| General views · Starts around 1 hour · 500K/day · Minimum 50 | 729 | — |
| General views · Within 1 hour · 60K/day | 730 | — |
| General views · Instant start · 5M/day · Cancellation available | 731 | — |
| General views · Within 1 hour · 1M/day · Cancellation available, no drip feed | 733 | — |
| General views · Within 1 hour · 5M/day · Alternate | 734 | — |
| All Links · Within 1 hour · 1M/day | 735 | — |
| All · Emergency · Within 1 hour · 500K/day | 736 | — |
| General views · Starts around 1 hour · 1M/day | 738 | — |
| Emergency views · Instant start · 50K/day | 740 | — |
| All Links · Within 1 hour · 50K/hour | 741 | — |
| General views · Within 1 hour · Delivery listed as “Instant” | 742 | — |
| General views · Instant start · 10M/day | 743 | — |
| General views · Starts around 1 hour · 10M/day | 746 | — |
| General views · Within 1 hour · Up to 2M/day | 749 | — |
| General views · Within 1 hour · 5M/day · Cancellation available, no drip feed | 750 | 747 |
| General views · Within 15 minutes · 5M/day | 753 | 752 |
| All Links · Within 1 hour · 100K/day · Cancellation available, no drip feed | 755 | — |
| General views · 1M/day · Start wording unclear | 756 | — |
| Video views · Emergency · “Auto on/off” | 758 | — |
| General views · Within 1 hour · Delivery listed as “Instant” · Alternate | 759 | — |
| Video views · “PRVT” · Within 1 hour · 500K/day | 761 | — |
| Legacy IGTV · Within 1 hour · Delivery listed as “Instant” | 763 | — |
| Legacy IGTV · Within 1 hour · 50K/hour | 765 | — |
| Legacy IGTV · Within 1 hour · 10M/day | 767 | — |
| Legacy IGTV · Within 1 hour · 5M/day | 768 | — |
| Legacy IGTV · Within 1 hour · 1M/day | 769 | — |
| Legacy IGTV · General delivery · Within 1 hour | 771 | 770 |
| Legacy IGTV · General delivery · Within 6 hours · Up to 100M per order | 773 | 764 |
| Legacy IGTV · General delivery · Within 1 hour · Alternate | 774 | 772 |
| Legacy IGTV · Within 1 hour · 10K/hour | 775 | — |
| Legacy IGTV · Within 1 hour · 1M/day · Cancellation available, no drip feed | 777 | — |
| Legacy IGTV · Starts around 2 hours · 5M/day · Minimum 1,000 | 778 | — |
| Legacy IGTV · Starts around 15 minutes · 5M/day · Cancellation available, no drip feed | 779 | — |

Row 756 spells its start claim “Insatnt.” Row 758 has a `Default` payload and no evidence for subscription inputs or automatic ordering controls. Row 761's wording does not establish that access to private content is supported. Keep the ambiguous provider terms visible as labels.

## Fallback evidence

| Primary → fallback | Raw rate comparison | Why the fallback fits the proposed option |
| --- | --- | --- |
| 727 → 732 | 0.25 → 0.25 | All Videos, within 1 hour, speed-flexible. 732 covers 100–100M and adds drip feed. The option exposes cancellation only. |
| 780 → 781 | 0.0063 → 0.0063 | Same Reel target, start window, bounds and capabilities. Speed-flexible option only. |
| 751 → 748 | 1.26 → 1.23 | Both All Videos and 5M/day. 748 lists 0–1 hour, so attach it only to the one-hour choice. |
| 715 → 714 | 0.2088 → 0.2063 | Same generic target wording, 500K/day and capability profile. The alternate lists a 0–1 hour start. |
| 750 → 747 | 1.25 → 1.225 | Same generic target wording and 5M/day. The alternate is within 1 hour and adds drip feed. The option exposes cancellation only. |
| 753 → 752 | 1.31 → 1.30 | Same generic target wording and 5M/day. The alternate lists instant start and satisfies the 15-minute window. |
| 771 → 770 | 0.2338 → 0.2313 | Both explicit IGTV, within 1 hour, identical bounds and capabilities. Delivery pace is flexible. |
| 773 → 764 | 0.01 → 0.01 | Both explicit IGTV with full coverage of the primary's 100–100M range. The six-hour window covers both starts. Delivery pace is flexible. |
| 774 → 772 | 0.2556 → 0.25 | Both explicit IGTV, within 1 hour, identical bounds and capabilities. Delivery pace is flexible. |

The local rate rule rejects alternatives with the same listed delivery when the price gap is too large. Three examples are 770 → 768 (0.2313 → 0.125), 771 → 769 (0.2338 → 0.2063) and 734 → 718 (0.25 → 0.2338). These rows still have a placement above. Use the ordered lists on each applicable option node and on the named default nodes. A global fallback across different media targets would mix order promises.

## Builder fields and verification

Keep the required `text/default` media Link with “Paste an Instagram link”, and the required `number/default` Quantity with “e.g. 1,000” and the effective payload bounds. Each delivery selector uses the registered single-choice `select/default` control. Others uses the registered `searchable` property and placeholder “Choose a views option”. The `toggle/default` Drip feed keeps its description, “Schedule multiple deliveries by setting the number of runs and the minutes between them.” Gate it on the selected service's structured capability, and require the two `number/default` inputs when on, with “e.g. 5” for Runs and “e.g. 60” for Interval (minutes). JAP receives `link` and `quantity`, plus `runs` and `interval` when drip feed applies. [Builder capability snapshot](../../.ai/service-builder-capabilities.json) · [JAP input guide](../../.ai/JAP-SERVICE-TYPES.md)

The static coverage check matched the proposed bindings to all 70 locally documented lab IDs with zero missing or extra IDs. All nine fallback pairs passed the local checks for order type, quantity coverage, capability fit and rate. Live Builder validation of the proposal has not run. Current lab membership, active host rate policy, accepted URL formats and fulfillment behavior remain unverified. Multiple JAP external IDs provide routing alternatives within the same integration.

This mapping is pending approval before edits to the [ProductDefinition](../../products/instagram-views.json).
