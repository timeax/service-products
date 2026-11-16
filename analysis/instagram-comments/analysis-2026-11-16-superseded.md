# Instagram Comments — source-backed analysis (not approved for definition)

Analysis prepared 2026-11-16 from the current workspace sources. This is a review artifact only; no comments ProductDefinition or catalog progress change has been made.

## Recommendation summary

The catalog item is **Instagram → Comments → Instagram Comments**, currently `not_started`, with no ProductDefinition. The mapped set contains 233 rows but spans several distinct order/target shapes. I recommend treating the mapping as a candidate inventory, not as 233 interchangeable comment handlers.

A plausible initial product scope is one-time comments on Instagram posts, with distinct customer choices for randomized/default versus customer-supplied comments and a curated subset of evidenced audience/region and source-labeled comment styles. Reels can be considered as a separate media-target choice only after confirming accepted URL and handler input semantics. Do not combine comment likes, replies, poll votes, channel comments, or monthly auto-comment subscriptions into the ordinary post-comment order without an explicit product decision.

No primary/fallback set is finalized. The mapped rows differ in order type, media target, customer text requirement, geographic/audience claims, quantity range, and drip-feed capability. Cross-variant fallback could change what the customer receives.

## Scope and source evidence

- Catalog service: `instagram-comments-comments` / **Instagram Comments** under Instagram’s **Comments** category; status `not_started`, `product_definition_file: null`.
- Current actual ProductDefinitions: `products/instagram-likes.json` only. It is method/reference context, not a source of comment IDs or comment behavior.
- Handler source: project-root `handler services.json`, 5,734 rows. It is a bare JSON array with no site/tenant/project metadata. Mapped rows all show `payload.panel_key: jap`, `dgp_handler_id: 1`, `external_id` prefixed `jap:`, and `payload.catalog_sync.last_seen_at: 2026-11-13T18:00:15+00:00` for all mapped rows. The panel key does not independently identify the intended site or tenant.
- Mapping source: `catalog-handler-service-ids.json`, key `instagram-comments-comments`, 233 unique row IDs. All resolve; zero stale IDs and zero duplicates.
- Registry states: all 233 mapped rows have `is_enabled: true`, `is_locked: false`, `state_reason: null`. This is the snapshot state only; it does not prove live health or storefront availability.
- Raw handler `payload.type` counts: `Default` 154, `Custom Comments` 61, `Custom Comments Package` 9, `Package` 7, `Comment Replies` 1, `Poll` 1. All mapped rows are under panel key `jap`.
- Capability counts: drip-feed enabled on 36/233, cancel enabled on 16/233, refill enabled on 0/233, contract enabled on 0/233. In particular, every mapped row reports refill disabled, including some names advertising a refill period; do not expose refill based on names alone.
- Exact capability cohorts: drip-feed enabled row IDs are `64, 855–859, 864–865, 869–872, 874–877, 879, 889, 891–895, 897, 902, 906, 915, 917–923, 1156, 1421`; cancel enabled IDs are `855, 868, 871–872, 891, 894–895, 897, 902, 908–910, 1156, 1421, 1435–1436`. These are source capabilities, not availability guarantees.
- The source keeps root registry `id`, `dgp_handler_id`, and provider `external_id` separate. The catalog map lists the root row IDs. The current local `@elqora/dgp-spec` HandlerService contract (installed 1.6.0) has generic service fields and does not define this provider-specific `payload.type` as a customer input schema.
- The saved Builder capability snapshot is dated 2026-11-13; Builder version is unspecified. It registers `text/default`, `textarea/default`, `number/default`, and single-choice `select/default`. `textarea/default` is scalar, not multi-value, and lists `rows`, `maxRows`, and `autoResize` UI properties. This establishes a control shape, not the provider’s required custom-comment encoding.

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

### Relevant current rows omitted from this mapping

- Exact raw category `Instagram Comments`: **849, 850, 898, 901**. IDs 849, 850, and 901 are explicitly *Instagram Comment Likes* with a comment-link/specific-comment target, so they are a different service family. **898** is `Instagram Comments [CUSTOM] [Max: 5K]...`, `payload.type: Custom Comments`, bounds 50–10,000, enabled/unlocked, drip-feed false. It is a directly relevant custom-comments row missing from the mapping; review it before any final definition mapping or mapping refresh.
- The mixed raw category `Instagram Auto Comments / Impressions / Saves / Reach` contains **51 unmapped rows**: 1472, 1473, 1474, 1475, 1476, 1477, 1478, 1479, 1480, 1481, 1482, 1483, 1484, 1485, 1486, 1487, 1488, 1489, 1490, 1491, 1492, 1493, 1494, 1495, 1496, 1497, 1498, 1499, 1500, 1501, 1502, 1503, 1506, 1507, 1508, 1509, 1510, 1511, 1512, 1513, 1514, 1515, 1516, 1517, 1518, 1519, 1520, 1521, 1522, 1523, 1524. Of those, these 28 names explicitly describe auto comments: 1476, 1486, 1488, 1489, 1490, 1491, 1492, 1493, 1494, 1495, 1496, 1497, 1498, 1499, 1500, 1501, 1502, 1503, 1507, 1508, 1513, 1514, 1519, 1520, 1521, 1522, 1523, 1524. They are `Subscriptions`-type recurring/automatic offerings, often tied to monthly or ongoing posts; review as a distinct auto-comment order family, not as standard one-time comments. The other unmapped rows in the same mixed category include auto impressions, reach, saves, shares, and profile visits.
- The source contains rows 30–32 under raw category `Instagram THREADS Shares / Comments`: 30 is Threads Reshare, 31 Threads Shares, and 32 Threads Real Nigerian Comments. None is in this Instagram Comments map. The catalog has a separate `Threads Comments` work item under Instagram, but `catalog-handler-service-ids.json` currently has no `threads-comments-comments` key. Keep these distinct from Instagram comments and record the mapping gap for the Threads item.
- No current handler is inferred stale, locked, or disabled from absence in the mapping. Other social platforms’ comment handlers remain outside this Instagram scope.

## Normalize variants and boundaries

| Viewpoint | Evidence in mapped rows | Analysis / proposed handling |
| --- | --- | --- |
| Default / randomized comments | 154 rows have raw `payload.type: Default`; names include random, post-related, hype/thrill, AI-relevant, positive/negative emoji, and language-specific variants. | Separate random/default from custom-text fulfillment. Treat sentiment/emoji and promotional-sounding source labels as explicit variants, not verified quality. |
| Customer-supplied comments | 61 rows have raw `payload.type: Custom Comments`; 33 of these occur in exact category `Instagram Comments`, with more in regional, Reel, Super, TOP, and verified categories. | A textarea is available in the saved Builder snapshot, but the registry does not say what input field key or encoding the provider expects, whether one or many text lines are accepted, or how quantity is derived. Do not bind these rows until that adapter/order contract is established. |
| Region, language, and audience | Names include USA/UK, Brazil, India, Korea, Russia, Arab, Italy, France, Germany, Spain, Indonesia, Iran, Ukraine, Hispanic, male/female, and combinations. | Keep geography, language, and audience as separate dimensions where the rows support it. Preserve source claims and never use an incompatible region/audience row as fallback. |
| Verified / TOP / POWER labels | 54 rows are in `Instagram Comments [VERIFIED/TOP ACCOUNTS]`; other TOP/POWER/EXCLUSIVE groups are included in the map. Names mention verified/top accounts, follower thresholds, or Power/explore-page claims. | Treat the wording as source labels, not independently verified account quality. This may be a customer option only if the claim is intentionally shown and backed by the seller. |
| Media target | 26 `Instagram Reel` rows, 4 `Instagram Live Video` rows, and 1 `Instagram Channel Members` row named Channel Comments. | Reel, Live Video, and Channel targets may need different accepted URLs and fulfillment handling. Decide whether Reels belong as a target choice here; keep Live/Channel separate unless the same customer promise and input contract are established. |
| Fixed packages / suspicious quantity bounds | 7 `Package` and 9 `Custom Comments Package` rows have `min=max=1`. Another 74 mapped rows have `min=max=1000`, although names can describe 5–200 comments. | Do not assume the quantity field means individual comments for these rows. The fixed bounds conflict with name-level comment counts, and package counts appear encoded in the selected service. Exclude from generic quantity choices pending provider semantics. |
| Distinct order families | One `Poll` row (936), one `Comment Replies` row (943), and two mapped monthly Auto Comments package rows (1504–1505). | Poll votes, replies to a comment, and recurring Auto Comments have different outcomes, target objects, or order lifecycles. Keep them out of the one-time comment product unless the roadmap/product boundary is deliberately changed. |
| Refill / retention wording | Names advertise refill, non-drop, lifetime, or retention in multiple groups, but all 233 mapped rows report `capabilities.refill.enabled: false`. | No refill-capability tag or refill promise can be derived from this snapshot. Preserve any name claims as unresolved source conflicts. |
| Drip-feed / cancellation | Drip-feed is enabled on 36 rows; cancel on 16. | Capability-aware drip-feed visibility can be considered only for selected rows that explicitly enable it. Do not infer capability from icons, speeds, or name labels. Cancel is not automatically a customer input. |

## Fixed-bound exception ID reconciliation

The 74 mapped rows with `min=max=1000` are grouped below. Their names often encode a lower comment count, so these bounds need the provider’s order interpretation before using a general quantity field.

| Raw handler category | IDs (`min=max=1000`) |
| --- | --- |
| Instagram Comments [VERIFIED/TOP ACCOUNTS] | 944–987, 996–997 |
| Instagram TOP Services [EXCLUSIVE] | 33–42 |
| Instagram Comments | 882–888 |
| Instagram BRAZIL Services 🇧🇷 | 1373–1374, 1376–1377 |
| Instagram SOUTH KOREA Services 🇰🇷 | 1425–1428 |
| Instagram Western Europe + USA Services 🇪🇺 🇬🇧 🇺🇸 | 1325–1327 |

The 16 rows with `min=max=1` are `1445–1450` (`Package`), `1454–1461` (`Custom Comments Package`), and `1504` (`Package`) plus `1505` (`Custom Comments Package`). The names of several encode one or more comments, whereas the registry quantity is one; they are package-shaped candidates, not ordinary comment counts.

## Candidate field and mapping plan (not final)

- Core ordinary order: target link (`text/default`) and quantity (`number/default`). Use each selected handler’s payload bounds; the saved Quantity template’s 10–10,000,000 numeric validation is not universal for this service.
- For `Custom Comments` rows, evaluate a `textarea/default` field only after the provider adapter contract identifies the form key, delimiter/line rules, and quantity relationship. Its registered cardinality is scalar; do not assume multi-value support.
- If target/media and variants are approved, use single-choice `select/default` fields with options bound to exact mapped handler IDs. The Builder snapshot says this variant supports options and single selection.
- Every future filter tag should have an intentional default `service_id`, following the user’s direction established during Instagram Likes work. The root should use a mapped service that is not already bound elsewhere. Avoid creating arbitrary generic catch-all tags.
- Primary candidate for a standard randomized comment order: row **895**, `Default`, general `Instagram Comments [RANDOM]`, bounds 10–100,000, drip-feed and cancel enabled. Row **868** is another general random candidate, bounds 10–50,000, drip-feed disabled, cancel enabled. These are review candidates, not selected primary/fallbacks; the differing bounds and drip-feed support prevent assuming they are fully interchangeable.
- Custom mode candidates include mapped rows 860–863 plus relevant country/audience rows; omitted row 898 is also directly relevant. Do not use a custom-comment handler as fallback for random/default or vice versa.
- No ordered fallback set is proposed until target scope, custom-text handling, capability promises, and the quantity scope are decided. Fallbacks must preserve target, comment mode, audience/region, package content, bounds for the customer’s requested quantity, and any enabled drip-feed behavior.

## Decisions needed before implementation

1. **Target scope:** should this product cover feed-post comments only, or also Reel comments? Keep Live Video and Channel comments separate? The mapped categories distinguish these targets.
2. **Comment style:** should random/default, emoji/sentiment, AI-relevant/hype, and customer-supplied text be separate choices? Which source-label claims should customers see?
3. **Custom text input:** does the provider expect one comment, one line per comment, a fixed list, or another format? What field key and quantity behavior does the active handler adapter require? Builder supports a scalar textarea, but that alone does not answer this.
4. **Package rows:** should the one-comment package entries be omitted from the first product, or modeled as discrete packages? What do the 74 `min=max=1000` rows represent despite names describing other comment counts?
5. **Omitted row 898:** should it be added to the Instagram Comments mapping as a candidate before definition work, since it is a current enabled custom-comments row in the exact category?
6. **Registry scope:** please confirm the intended target site/tenant for the supplied `jap` panel registry; the file itself does not identify it.

## Current status and approval gate

The catalog item remains `not_started`; no ProductDefinition exists for Instagram Comments and no catalog or mapping file was changed. This analysis is saved for review. I will wait for your approval and decisions before creating or editing `products/instagram-comments.json` or changing catalog progress.
