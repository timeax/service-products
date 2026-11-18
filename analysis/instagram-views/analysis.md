# Instagram Views

2026-11-18 · Approved ProductDefinition and source reconciliation

## Product scope

**Instagram → Views → Instagram Views** (`instagram-views-views`) covers one-time video post, Reel and photo post views. A separate Priority Delivery tag exposes the two provider-listed priority choices. The owner approved writing the canonical JSON after reviewing the local Service Builder preview. The saved definition matches that preview. The roadmap entry still records `not_started` with no definition path in the catalog. [ProductDefinition](../../products/instagram-views.json) · [Roadmap](../../catalog.json)

Target wording guides classification across provider categories. “All Videos,” “All Posts,” “All Links,” Reel and IGTV describe different or overlapping target claims. IGTV, all-post and mixed-target additions are pending confirmation of accepted links. “PRVT” on 761 remains ambiguous. Start and speed labels reproduce provider-listed figures in readable language, with the dropdown descriptions identifying their source. The registry supplies encoded capabilities. For example, 727 and 730 carry the droplet symbol with `dripfeed.enabled: false`.

Stories, Highlights, profile visits and multi-outcome bundles are outside this one-time media definition. All rows whose payload type is `Subscription` or `Subscriptions` are excluded. The local source has Live likes and comments. The search found no Instagram Live viewer handler.

## Source and reconciliation

- [Catalog](../../catalog.json), [catalog ID map](../../catalog-handler-service-ids.json) and [handler registry](../../handler%20services.json). The registry is a 5,726-row JSON array with no top-level site, tenant, or provider account identity. The 65 mapped rows and 25 omitted candidates are enabled and unlocked in the supplied registry. They were last seen on 2026-11-16 at 12:00:16 UTC and all use JAP, handler configuration `dgp_handler_id: 1` and `payload.type: Default`. These identify the snapshot's provider and configuration. Site and account identity still need confirmation.
- The local TygerBooster checkout exposes site-side `DgpService` and `DgpHandler` models and their relationship. A current deployment export with matching site/account identity was unavailable. The local Service Builder's memory seeds are development workspaces. The supplied export is the only row authority for this review.
- All 65 mapped IDs are unique and resolve. The map keys use root row `id`. The shared `dgp_handler_id` identifies a handler configuration and `external_id` (for example, `jap:6454` for row 706) identifies the provider service.

| Raw category | Count | Mapped root row IDs |
| --- | ---: | --- |
| Instagram Views | 50 | 704, 705, 706, 707, 708, 709, 710, 711, 712, 713, 714, 715, 717, 718, 719, 720, 722, 724, 726, 727, 728, 729, 730, 731, 732, 733, 734, 735, 736, 737, 738, 739, 740, 741, 742, 743, 746, 747, 748, 749, 750, 751, 752, 753, 755, 756, 758, 759, 760, 761 |
| Instagram IGTV | 15 | 763, 764, 765, 767, 768, 769, 770, 771, 772, 773, 774, 775, 777, 778, 779 |

The independent registry scan checked Instagram categories, names and descriptions for views, plays, watch-time and viewer wording, and reviewed the Live category. The 25 missed one-time views-only rows have no entries elsewhere in the map.

| Raw category | Count | Omitted one-time views-only IDs and classification |
| --- | ---: | --- |
| Instagram Views | 5 | 716 (Reel + IGTV + posts), 725 (Reel), 744 (Reel + IGTV), 754 and 757 (all posts) |
| Instagram IGTV | 2 | 762 (Reel + IGTV + posts), 766 (Reel + IGTV + normal) |
| Instagram Reel | 18 | 780, 781, 782, 783, 785, 786, 788, 789, 790, 791, 793, 795, 796, 799, 800, 801 (Reel), 784 (Reel + IGTV + posts), 787 (all links; accepted scope unconfirmed) |

| Related evidence outside the approved scope | Root row IDs and disposition |
| --- | --- |
| Views plus other metrics | 721, 723, 745, 776, 802 include impression or reach outcomes and are mapped under Impressions. |
| Story views | 52, 1049, 1051–1055, 1058–1063, 1065–1066, 1068–1069, 1072–1073, 1075, 1080 are Story-targeted. 1051 specifies “LAST POST” and is unmapped. 1103 advertises automatic Story views for 30 days but has the `Default` payload type, so its scheduling remains unconfirmed. |
| Story bundles | 1050, 1056–1057, 1064, 1067, 1070–1071, 1074, 1076–1079 add other metrics. 1064 is unmapped. The other rows are mapped under Impressions or Profile Visits. |
| Profile and Highlights | 1167–1168 are Profile Visits / Views. 1169 is Highlights Views. They have separate roadmap mappings. |
| Engagement packages | 55, 95 and 121–126 mention views as a package component. These rows are mapped under Packages. |

## Approved handler bindings

The five tags each bind a default handler. Selecting a delivery option replaces the current tag's default for the order preview. Video Post Views, Reel Views and Priority Delivery still require an explicit delivery or media selection. Photo Post Views uses its direct binding and the shared order fields.

| Tag | Default root row ID | Delivery field |
| --- | ---: | --- |
| Instagram Views | 706 | Shared order fields |
| Video Post Views | 706 | Video delivery |
| Reel Views | 780 | Reel delivery |
| Photo Post Views | 722 | Shared order fields |
| Priority Delivery | 728 | Priority media type |

| Tag | Option or direct order | Root row ID | Provider external ID | Payload min–max | Payload rate |
| --- | --- | ---: | --- | --- | ---: |
| Video Post Views | Starts within 1 hour · 20M views/day | 706 | `jap:6454` | 100–2,147,483,647 | 0.0062 |
| Video Post Views | Instant start · 5M views/day | 751 | `jap:6549` | 100–2,147,483,647 | 1.26 |
| Video Post Views | Starts within 1 hour · 5M views/hour | 739 | `jap:3008` | 100–2,147,483,647 | 0.625 |
| Reel Views | Starts within 1 hour · 500K views/day | 781 | `jap:5997` | 100–2,147,483,647 | 0.0063 |
| Reel Views | Starts within 1 hour · 5M views/day | 780 | `jap:3528` | 100–2,147,483,647 | 0.0063 |
| Reel Views | Starts within 1 hour · 100M views/day | 790 | `jap:6691` | 1,000–2,147,483,647 | 0.24 |
| Reel Views | Starts within 3 hours · 1M views/day | 786 | `jap:5993` | 100–2,147,483,647 | 0.20 |
| Photo Post Views | Direct order | 722 | `jap:5998` | 100–1,000,000 | 0.01 |
| Priority Delivery | Video post · Starts within 1 hour · 400K views/day | 728 | `jap:2` | 100–2,147,483,647 | 0.2556 |
| Priority Delivery | Reel · Starts within 1 hour · 5M views/day | 783 | `jap:6459` | 100–2,147,483,647 | 0.07 |

The local seed contains the full 90-row candidate inventory. Ten distinct rows have bindings, with five drawn from the mapping and five from the separately reconciled Reel rows. The other 80 are available for review in the seed. The approved choices use an explicit video, Reel or photo target in the source name. The current scope leaves legacy IGTV, mixed-target, ambiguous-link and private-target variants unassigned.

All ten bound handlers support cancellation. Nine support drip feed. Row 786 has `dripfeed.enabled: false` despite the droplet in its name. The 65 mapped rows include 62 with cancellation and 56 with drip feed. No mapped row reports refill or contract support. Mapped minima are 100 for 63 rows, 50 for row 729, and 1,000 for row 778. Fifty-six mapped rows have a payload maximum of 2,147,483,647. Of the 63 mapped names with a numeric ceiling, 62 differ from the payload maximum. Row 704, for example, advertises 10M and has a structured maximum of 2,147,483,647. Rows 748 and 758 have no numeric ceiling in the name. Quantity bounds, rate and capabilities come from the structured payload.

**Fallbacks** are unconfigured at both tag and option level. The earlier 780 → 781 proposal applied to generic Reel delivery. The approved design exposes each as a separate choice because the provider lists 5M/day for 780 and 500K/day for 781. Any later fallback needs matching target and delivery wording, full offered quantity coverage, compatible capabilities and the host's applicable rate checks. The local Builder source defaults to strict `lte_primary` at 5%, which accepts rates from 95% to 100% of the primary.

## Builder fields

Local Service Builder consumes `dgp-spec` 1.6.0 (canonical schema v1), `dgp-core` 1.1.0, `dgp-validation` 1.2.1, `dgp-ordering` 1.1.1 and `dgp-ordering-form-palette` 1.1.5. The capability snapshot is dated 2026-11-13. The local Form Palette adapter renders the approved placeholders from field defaults. [Builder capability snapshot](../../.ai/service-builder-capabilities.json) · [JAP type guide](../../.ai/JAP-SERVICE-TYPES.md)

| Field | Registered control | Behavior |
| --- | --- | --- |
| Video delivery, Reel delivery, Priority media type | Three `select/default` fields, each single-choice with options | Required on the associated tag. Each option has one handler binding and a provider-listed delivery label. |
| Instagram media link | `text/default`, scalar | Required `link`. Checks for an HTTP or HTTPS Instagram URL with a path. Per-target provider acceptance remains unverified. |
| Quantity | `number/default`, scalar | Required `quantity`. Uses the entered positive whole number for base quantity, with step 1. Preview bounds reflect the resolved handler payload. |
| Drip feed | `toggle/default`, scalar | Optional Builder button visible when the effective handler has `dripfeed.enabled: true`. |
| Runs and interval | Two `number/default` scalar fields | Visible and required while drip feed is active. Both accept positive whole numbers. The order snapshot includes `runs` and `interval` (minutes) only while displayed. |

`Default` requires link and quantity. The toggle is a Builder control. The JAP request uses runs and interval when drip feed is active.

## Validation and open questions

- Parsed the saved JSON, checked it against the installed DGP Spec ProductDefinition JSON Schema, and compared it to the approved local seed. The schema check passed and the definitions match exactly.
- Ran `dgp-validation` 1.2.1 against the saved JSON with the scoped service catalog and the field capability registry. Result was valid with zero diagnostics.
- Exercised the saved JSON in `dgp-ordering` 1.1.1. Verified all five tag defaults, all nine option overrides, selected payload bounds, link and integer validation, and drip-feed visibility and order snapshot omission. The local preview displayed the approved placeholders and default routing.
- TygerBooster Builder validation on 2026-11-18 for [Instagram Views Lab, version 1](https://tygerbooster.com/labs/226). The imported definition initially showed six unknown-service diagnostics because the lab catalog held the 65 originally mapped rows. Adding the five referenced Reel rows (780, 781, 783, 786 and 790) brought the lab catalog to 70. On a fresh Builder load, the console showed zero diagnostics and all ten bound services resolved.
- Live fulfillment, production quantity enforcement and host-to-JAP submission were outside this verification. The five Reel additions were made to an unpublished lab. Provider account identity and accepted IGTV, all-post and mixed-target link shapes remain open.
