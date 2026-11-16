# Instagram Comments — reanalysis (review only; not approved for definition)

Reanalyzed 2026-11-16 after rereading the current `.ai` workflow and host-specific guides, against the refreshed project handler snapshot and current service-ID mapping. This document is specifically about the catalog service **Instagram → Comments → Instagram Comments**. Adjacent services are mentioned only to state scope boundaries or mapping omissions. No ProductDefinition, catalog status, or mapping file has been changed.

## Recommendation summary

Treat **Instagram Comments** as the one-time service family for comments placed on an Instagram content target. The current map has 233 handler rows, but only **215** are of the two order types that fit the ordinary/random or customer-written comment fulfillment shapes: `Default` (154) and `Custom Comments` (61). These rows span ordinary posts, Reels, source-labeled audiences/geographies, and other target/style variants; they are not 215 interchangeable fulfillers.

Start the eventual design with two fulfillment modes: **Random comments** (`Default`) and **Custom comments** (`Custom Comments`). Keep audience/language claims as explicit variants only when intentionally customer-facing and supported by a suitable handler. Decide whether Reels share the product’s target field or need a separate work item. Keep channel comments, comment likes, comment replies, poll votes, recurring auto comments, and fixed or multi-engagement packages outside this one-time Instagram Comments scope unless the catalog owner deliberately expands the service definition.

A plausible general random candidate is row **895**; row **868** is a narrower alternative candidate. Neither is selected yet. Their targets and bounds overlap, but row 895 supports drip-feed and row 868 does not, and their maxima differ. Any fallback must preserve the chosen mode, target, audience promise, quantity range, and drip-feed selection.

## Scope and source evidence

- Catalog entry: `instagram-comments-comments`, **Instagram Comments**, under Instagram → Comments; currently `not_started`, with no ProductDefinition file.
- Current `products/` contains `instagram-likes.json` only. It is reference/method context, not evidence for comment rows or fields.
- Handler source is the project-root `handler services.json`, a 5,734-row bare JSON array. It has no top-level site, tenant, or project identity. Every mapped row has `payload.panel_key: jap`, `dgp_handler_id: 1`, and a JAP-prefixed `external_id`; those fields do not identify the intended site/tenant. All 233 mapped rows currently show `payload.catalog_sync.last_seen_at: 2026-11-16T12:00:16+00:00`.
- Mapping source is `catalog-handler-service-ids.json`, key `instagram-comments-comments`: 233 IDs, 233 unique, all resolved against the current registry; no stale IDs or duplicates.
- Every mapped row currently has `is_enabled: true`, `is_locked: false`, and `state_reason: null`. This describes the snapshot, not live health or storefront availability.
- Mapped `payload.type` counts: `Default` 154; `Custom Comments` 61; `Package` 7; `Custom Comments Package` 9; `Poll` 1; `Comment Replies` 1. Therefore the map has 215 rows in the two one-time comment modes proposed above; 18 are other order shapes and are not automatically part of this product.
- Mapped source capability counts: drip-feed 36/233; cancel 15/233; refill 0/233; contract 0/233. All mapped rows report refill disabled, including names containing refill/non-drop wording. Do not expose refill based on a name. For an eventual drip-feed control, follow the user-approved rule from Instagram Likes: show runs/interval only where the selected service advertises drip-feed support.
- The contract distinction is important: root registry `id`, `dgp_handler_id`, and provider `external_id` are separate. The mapping contains root row IDs. In product work, keep those identifiers distinct and scoped to this registry.
- The current local `@elqora/dgp-spec` package (installed 1.6.0) supplies the generic HandlerService contract. It does not define JAP `payload.type` as a customer input schema. The `.ai/JAP-SERVICE-TYPES.md` guide supplies the host-specific order-field rules used below.
- Builder capability snapshot: `.ai/service-builder-capabilities.json`, dated 2026-11-13 with no Builder version specified. It registers `text/default`, `textarea/default`, `number/default`, and single-choice `select/default` relevant here. `textarea/default` is scalar. A scalar textarea can collect newline-separated text; it is not a multi-value control. Use only registered variants and properties if definition work is approved. Policies in that snapshot are context only and must not be edited or generated.

## Handler-ID reconciliation

### Every mapped ID, grouped by the source category

| Raw handler category | Rows | Mapped root row IDs |
| --- | ---: | --- |
| Instagram Comments | 88 | 853, 855, 856, 857, 858, 859, 860, 861, 862, 863, 864, 865, 866, 867, 868, 869, 870, 871, 872, 873, 874, 875, 876, 877, 878, 879, 880, 881, 882, 883, 884, 885, 886, 887, 888, 889, 890, 891, 892, 893, 894, 895, 896, 897, 899, 900, 902, 903, 904, 905, 906, 907, 908, 909, 910, 911, 912, 913, 914, 915, 916, 917, 918, 919, 920, 921, 922, 923, 924, 925, 926, 927, 928, 929, 930, 931, 932, 933, 934, 935, 936, 937, 938, 939, 940, 941, 942, 943 |
| Instagram Comments [VERIFIED/TOP ACCOUNTS] | 54 | 944, 945, 946, 947, 948, 949, 950, 951, 952, 953, 954, 955, 956, 957, 958, 959, 960, 961, 962, 963, 964, 965, 966, 967, 968, 969, 970, 971, 972, 973, 974, 975, 976, 977, 978, 979, 980, 981, 982, 983, 984, 985, 986, 987, 988, 989, 990, 991, 992, 993, 994, 995, 996, 997 |
| Instagram Reel | 26 | 803, 804, 805, 806, 807, 808, 809, 810, 811, 812, 813, 814, 815, 816, 817, 818, 819, 820, 821, 822, 823, 824, 825, 826, 827, 828 |
| Instagram TOP Services [EXCLUSIVE] | 19 | 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 56, 57, 63, 64, 87, 88, 89, 100, 101 |
| Instagram EGYPT - VERIFIED Services 🇪🇬 | 8 | 1454, 1455, 1456, 1457, 1458, 1459, 1460, 1461 |
| Instagram Western Europe + USA Services 🇪🇺 🇬🇧 🇺🇸 | 7 | 1325, 1326, 1327, 1337, 1338, 1359, 1371 |
| Instagram BRAZIL Services 🇧🇷 | 6 | 1373, 1374, 1376, 1377, 1420, 1421 |
| Instagram TURKEY - VERIFIED Services 🇹🇷 | 6 | 1445, 1446, 1447, 1448, 1449, 1450 |
| Instagram Live Video | 4 | 1044, 1045, 1046, 1048 |
| Instagram SOUTH KOREA Services 🇰🇷 | 4 | 1425, 1426, 1427, 1428 |
| Instagram Super Services | 4 | 1039, 1040, 1041, 1042 |
| Instagram Auto Comments / Impressions / Saves / Reach | 2 | 1504, 1505 |
| Instagram ITALY Services 🇮🇹 | 2 | 1435, 1436 |
| Instagram Channel Members | 1 | 1156 |
| Instagram NIGERIA Services 🇳🇬 | 1 | 1431 |
| Instagram TURKEY Services 🇹🇷 | 1 | 1444 |
| **Total** | **233** | **All rows resolve; none stale or duplicated.** |

### Mapped IDs by actual order type (current snapshot)

This cross-check makes the 215-row core candidate set explicit without treating all candidates as compatible. IDs come from the root `id` values in this scoped registry.

- `Default` (154 candidate rows): 33–42, 57, 64, 87–89, 101, 803–815, 855–859, 864–865, 867–872, 874–877, 879–880, 882–889, 891–895, 897, 900, 902, 905–907, 911–923, 941–942, 944–988, 990, 993–994, 996–997, 1044–1046, 1048, 1156, 1325–1327, 1337, 1359, 1371, 1373–1374, 1376–1377, 1421, 1425–1428, 1431, 1435.
- `Custom Comments` (61 candidate rows): 56, 63, 100, 816–828, 853, 860–863, 866, 873, 878, 881, 890, 896, 899, 903–904, 908–910, 924–935, 937–940, 989, 991–992, 995, 1039–1042, 1338, 1420, 1436, 1444.
- Excluded mapped types: `Package` 1445–1450,1504; `Custom Comments Package` 1454–1461,1505; `Poll` 936; `Comment Replies` 943. The recurring monthly Auto Comments names on 1504–1505 do not make them one-time comments: retain their actual package types and keep them outside this scope.

The registry's enable/lock flags are only source-state evidence. No handler has been live-tested here, so none is claimed to work or be available in a storefront.

### Current rows omitted from the mapping that affect Instagram Comments scope

- **Direct omission:** row **898**, in raw category `Instagram Comments`, is enabled/unlocked and has `payload.type: Custom Comments`, bounds 50–10,000. Its name describes custom Instagram comments. It belongs in the candidate comparison for this product; the mapping itself has not been edited.
- **Separate adjacent action:** omitted rows **849, 850, 901** are named Instagram Comment Likes. The guide says `Comment Likes` needs `link`, `quantity`, and `username` (comment owner). They operate on an existing comment and should remain a separate service, despite sharing the raw category label `Instagram Comments`.
- **Separate recurring order family:** 28 omitted rows explicitly named Auto Comments are IDs **1476, 1486, 1488–1503, 1507–1508, 1513–1514, 1519–1524**. Their `payload.type` is `Subscriptions`, whose guide shape is `username`, `min`, `max`, `delay`, with optional post/expiry controls. The mapping omits them, and their recurring subscription behavior differs from a one-time post-comment order. Do not add them to this ProductDefinition based on their names.
- **Separate platform qualifier:** row **32** is `Threads Real Nigerian Comments` in category `Instagram THREADS Shares / Comments`; it is Threads-related and is not an Instagram Comments handler. The map for this catalog item does not include it.
- Other omitted rows mentioning comments are bundled engagement/subscription packages or other actions; their names alone do not make them standalone Instagram Comments fulfillers. They are not proposed for this service.

## Normalize and group the Instagram Comments variants

The provider category labels organize records; they are not customer tags. Normalize on customer-visible service behavior and compatible order inputs, then use a select option only where the variation is real and the mapping is known. Do not turn the raw categories into a deep tree or advertise provider claims as verified facts.

| Customer-facing viewpoint | Current evidence | Proposed treatment |
| --- | --- | --- |
| Random/default one-time comments | 154 mapped `Default` rows; examples include generic random comments, emoji/sentiment, relevant/hype-style, and audience or regional labels. | One fulfillment mode. Audience, language, or style may become explicit choices if the team intends to promise them and can bind each choice to compatible rows. Treat “high quality,” “verified,” “power,” or similar terms as provider wording, not independently verified quality. |
| Customer-written comments | 61 mapped `Custom Comments` rows, including 33 in raw `Instagram Comments`; omitted row 898 is another direct candidate. | Separate fulfillment mode because the order sends customer text. JAP guide: required `link` and `comments`; one comment per line (`\n` or `\r\n`); no separate JAP `quantity`, which the Builder derives from line count. |
| Target: post versus Reel | 26 mapped `Instagram Reel` rows (13 `Default`, 13 `Custom Comments`). Other rows occur in the generic `Instagram Comments` and audience/category groups. | Decide whether one Instagram Comments product accepts both post and Reel URLs, or whether Reel comments need a separate service. Source category and handler name indicate Reel targeting, but the exact accepted URL validation is not described in the local contract. Never fall back across targets unless both accept the submitted target. |
| Target: Live/Channel | Four rows in `Instagram Live Video`; one `Instagram Channel Comments` row in `Instagram Channel Members`. | Do not include by default in ordinary post/Reel comments. These labels indicate distinct target context; ask whether they belong here only if the owner wants those placements included. |
| Audience, geography, language, account labels | Rows include USA/UK, Brazil, Korea, Arabic, Italy, other regional/language labels, gender labels, and “verified/top/power” wording across categories. | These are candidate variants, not separate products by default. Show only deliberate choices backed by specific rows. A fallback must keep the same audience and language promise. Do not assert the named account characteristics were independently verified. |
| Fixed package-like counts | 74 `Default` rows have registry `min=max=1000` even though names commonly enumerate fixed comments (often 5–400). | This is a real mismatch between the JAP `Default` quantity shape and the registry row bounds/name. Do not use as ordinary variable-quantity handlers until the adapter/provider meaning of 1000 is clarified. Preserve the snapshot as-is in analysis. |
| Other mapped JAP types | One `Poll` row (936), one `Comment Replies` row (943), seven `Package`, nine `Custom Comments Package`. | Exclude from the ordinary one-time comments mode. Polls require `answer_number`; replies require the comment owner's `username`; packages have fixed package quantity and may bundle other engagement. Their order shapes/promises differ. |
| Refill, retention, speed, delivery wording | Several names claim refill/non-drop or delivery speed; mapped refill capability is false for all rows. | Keep as source notes only. Do not promise refill/retention or delivery guarantees from names. Drip-feed can be offered only on rows with `capabilities.dripfeed.enabled: true`. |

### Exact input shapes and Builder implications

- **`Default`:** JAP requires `link` and `quantity`. Optional `runs` and `interval` apply only when that selected handler supports drip-feed and the customer enables it. In TygerBooster, `Drip feed` is a Builder toggle; `drip_feed` is not a JAP request field. The linked runs/interval inputs should be included only when the toggle is on, and every candidate handler bound to the enabled option must support drip-feed.
- **`Custom Comments`:** JAP requires `link` and newline-separated `comments`; there is no separate API quantity. The Builder derives quantity from the number of lines. The registered scalar textarea is appropriate for collecting a newline-separated string, subject to the adapter’s documented field mapping. Do not add a quantity field for this type merely because the registry displays min/max values.
- **`Package` / `Custom Comments Package`:** the guide specifies fixed internal package quantity one; these rows are not plain countable comments. Custom comments packages still require `link` and newline-separated `comments`. Excluded from the proposed core service unless the owner wants a separately presented package mode and confirms fulfillment semantics.
- **`Poll` / `Comment Replies`:** distinct target/action inputs. Excluded from this product’s proposed scope.
- Quantity bounds in the registry are `payload.min`/`payload.max`. They are not the Builder Quantity Template’s validation bounds. For `Default`, use actual service bounds where those bounds are coherent; do not copy the template’s 10–10,000,000 limits. For `Custom Comments`, count of supplied lines determines quantity, but the 74 fixed-1000 `Default` anomalies remain unresolved.

## Primary and fallback candidates (provisional)

- Generic random candidate **895**: `Default`, name “Instagram Comments [RANDOM] …”, `payload.min=10`, `payload.max=100000`, drip-feed enabled, cancel enabled.
- Generic random candidate **868**: `Default`, name “Instagram Comments [Random] …”, `payload.min=10`, `payload.max=50000`, drip-feed disabled, cancel enabled.
- These are plausible candidates for the same random one-time promise for orders up to 50,000 when drip-feed is off. Row 868 cannot satisfy an order with drip-feed on; neither candidate is a fallback for custom text, a different target, or a customer-selected audience/language. Final root assignment and ordered fallback require the product choices and target/site scope to be confirmed.
- The mapped custom-comment candidates include 860–863 and many more exact category/audience/Reel variants. The omitted row 898 must be compared alongside them. No generic fallback is selected: a custom handler must preserve the entered comments, and fallback candidates must support the same target and bounds.

## Proposed customer field/tag direction (analysis only)

- Core one-time form requires a target `link` for both modes.
- `Random comments` uses `quantity` with the selected `Default` handler’s actual coherent bounds. `Custom comments` uses a scalar textarea containing one comment per line; quantity is derived from its line count, not submitted as a separate JAP `quantity` field.
- A single-choice `select/default` can express fulfillment mode or an intentionally supported variant; the saved Builder snapshot reports option support and single cardinality. Do not expose options that have no compatible handler mapping.
- Add drip-feed toggle plus `runs` and `interval` only for selected services whose capability is true. The 36 enabled row IDs remain an evidence set, not a blanket promise. The proposed generic candidates differ on this capability.
- Follow the previously stated Instagram Likes layout constraint for this future definition: each filter/tag needs a default bound service, and the root should bind a service not already bound elsewhere. This is a design constraint, not a reason to bind an unreviewed row now.

## Decisions needed before ProductDefinition work

1. **Target boundary:** should this product accept only standard post links, or both post and Reel links? Keep Live Video and Channel comments out unless you want them covered.
2. **Modes and variants:** should the customer choose Random versus Custom comments as the main modes? Which, if any, audience, language, emoji/sentiment, or source-labeled account variants are customer-facing?
3. **Fixed-1000 Default rows:** can the handler adapter/provider confirm how to order rows whose `payload.min=max=1000` while their names enumerate smaller fixed comment counts? Until clarified, exclude them from ordinary quantity-bound handlers.
4. **Mapping omission 898:** should row 898 be added to `instagram-comments-comments` mapping in a separate mapping refresh, or should it remain documented as an omitted candidate? It will remain unbound unless resolved.
5. **Registry scope:** what target site/tenant does this `jap` registry represent? The file itself does not identify it, so product-specific identity assumptions cannot be attached to the provider IDs yet.

## Status and approval gate

This is the reanalyzed **Instagram Comments** scope only. The catalog stays `not_started`, `products/` has no comments definition, and no mapping/catalog/product JSON was changed. I have saved the analysis for review. I will wait for explicit approval of this analysis scope before creating or editing `products/instagram-comments.json` or changing catalog progress.
