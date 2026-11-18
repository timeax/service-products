# Instagram Comments — full payload, option and fallback reanalysis

2026-11-18. Applies to the mapped Instagram Comments product and supersedes the earlier treatment of count wording on Default rows.

## Implemented against the local Builder policy

The product and Builder seed consolidate the fixed-quantity choices and preserve their delivery distinctions where the selector sells delivery. The Countries/regions selector has nine options. Its USA/UK Power chain is 38 → 965 → 1327 at 5.52, Brazil Power is 972 → 1377 at 6.60, and South Korea Power is 976 → 1428 at 6.60. These use equal-rate mapped rows from other paths because the lower tiers exceed the 5% tolerance.

The definition now has 278 service options, 35 option fallback lists, and nine tag fallback lists. All installed fallback entries cover the primary's full quantity range and capabilities, and their rates stay within the local 5% band. The 38 fixed-quantity IDs without a current routing reference are recorded in `meta.deferred_fixed_quantity_handler_ids` and remain in the Builder service seed. The following inventory is the pre-change analysis. ProductDefinition validation passed against the seeded handler catalog and the local fallback policy.

## Scope and rules

All 233 mapped root handler IDs resolve in the project registry. All are enabled and unlocked in this export. The current definition has 52 tags, 34 service selectors and 379 service options. All 233 handlers use JAP, so they can share provider outages. We use 50–80% failure as a planning scenario. No live fulfillment was checked. Only mapped rows are considered.

A Default adapter request sends link and quantity. A count in the provider name has no effect on the submitted quantity. Use the payload bounds for availability and the count field. Every fixed-1,000 row below receives quantity 1,000. The name is evidence of the conflict, and actual delivery of 1,000 remains unverified. Preserve package counts for Package and Custom Comments Package because these are different request types. Poll and Replies keep their own inputs. Keep the root input visibility and supported drip feed behavior.

Retain the tag tree. Tags pick defaults and options expose useful choices within that path. Combine variants with the same order inputs, target, meaningful qualifiers, supported features, and compatible bounds. Prefer a close backup and allow a broader backup when the choice permits it. A narrower backup can serve an order only when the actual quantity is within its bounds. The proposal for static lists requires every backup to cover the primary’s full range. A partial overlap belongs in the candidate inventory until fulfillment is shown to check the actual quantity and active capabilities before retry.

Sort each mutually compatible pool by the effective handler rate, highest first, then ascending root handler ID for a stable tie. Preserve that order when writing fallback IDs and use priority selection. The local Builder’s clear-service promotion takes the first enabled fallback and removes it from that list. Recheck the rate against the new primary after any promotion, skipped row or rate change. Use the rate that the active Builder registry exposes. All mapped source rows have zero markup and no rate adjustment in the supplied export.

The Builder source default is strict priority with rate policy lte_primary at 5%. In the local Core implementation it requires 95% of primary rate ≤ fallback rate ≤ primary rate. Cheapest-first routing would change the intended priority. Even descending chains can fail the current policy, and it evaluates every candidate against the current primary. A cost ceiling that accepts every lower rate requires a broader lower-side tolerance, for example lte_primary at 100% for positive rates. Confirm the actual host policy before implementation. This review does not change publication policies.

The existing definition has 15 option lists and 5 tag lists. The local 5% default would reject 13 of their 22 individual entries on price alone. 3 entries cost more than the primary. These are comparisons against the default in code, with the active host policy still unconfirmed.

## Default → Countries/regions

The 17 existing options reduce to nine useful choices using payload bounds. Keep the 5–50 and 5–500 USA rows separately and the ordinary Brazil choice separately from 1,000-quantity Brazil Power comments. The three fixed-quantity rows below show chains using the current selector entries. The full product pools in the next section also include compatible mapped rows from other paths.

| Choice | Payload range | Current dropdown handlers in proposed rate order |
| --- | --- | --- |
| USA/UK · Power comments | 1,000 | 1327 (5.52) → 1326 (3.60) → 1325 (2.04) |
| Brazil · Power comments | 1,000 | 1377 (6.60) → 1376 (5.10) → 1374 (3.24) → 1373 (1.80) |
| South Korea · Power comments | 1,000 | 1428 (6.60) → 1427 (5.10) → 1426 (3.24) → 1425 (1.80) |
| USA | 5–500 | 1337 (550.00) |
| USA | 5–50 | 1359 (60.00) → 880 (37.05) → 57 (37.05) |
| Brazil | 5–200 | 1421 (100.00) |
| France | 5–300 | 1371 (600.00) |
| Nigeria | 50–2,500 | 1431 (65.00) |
| Italy | 10–3,000 | 1435 (56.25) |

USA 880 and 57 are existing backups from elsewhere in the mapping. They cover 1359’s 5–50 range and fit a no-increase ceiling, with the default 5% window rejecting both. USA 911 covers 10–500, so it cannot back up 1337 at 5–9. Keep tag default 1337 while its wider range has no full-coverage backup. Brazil 1421 has a different quantity range and supports drip feed and cancellation. Option 888 appears on the Standard audience, language/region, and delivery paths. It belongs to the Arabic Power pool for the first two paths. A delivery-specific option must retain the delivery it advertises.

## All 74 fixed-1,000 Default rows

The name counts no longer split any of these nine groups. This yields 65 possible alternate positions before applying the rate policy and the constraints of specific selectors. All these groups use the same quantity and have the same capability flags within each group. The pairs column identifies adjacent promotion steps that the local 5% rule rejects. It is also possible for a non-adjacent candidate to fall outside the band.

| Choice | High-to-low rate chain | Adjacent pairs outside the local 5% band |
| --- | --- | --- |
| South Korea · Power comments | 976 (6.60) → 1428 (6.60) → 33 (5.10) → 975 (5.10) → 1427 (5.10) → 974 (3.24) → 1426 (3.24) → 973 (1.80) → 1425 (1.80) | 1428→33, 1427→974, 1426→973 |
| Brazil · Power comments | 972 (6.60) → 1377 (6.60) → 34 (5.10) → 971 (5.10) → 1376 (5.10) → 970 (3.24) → 1374 (3.24) → 969 (1.80) → 1373 (1.80) | 1377→34, 1376→970, 1374→969 |
| Worldwide · Power comments | 37 (12.00) → 962 (12.00) → 961 (9.00) → 36 (7.20) → 960 (7.20) → 959 (6.00) → 35 (4.80) → 958 (4.80) → 957 (3.00) → 956 (1.80) | 962→961, 961→36, 960→959, 959→35, 958→957, 957→956 |
| USA/UK · Power comments | 40 (10.80) → 968 (10.80) → 967 (9.00) → 39 (6.60) → 966 (6.60) → 38 (5.52) → 965 (5.52) → 1327 (5.52) → 964 (3.60) → 1326 (3.60) → 963 (2.04) → 1325 (2.04) | 968→967, 967→39, 966→38, 1327→964, 1326→963 |
| Arabic · Power comments | 982 (10.20) → 981 (8.40) → 980 (6.00) → 41 (4.80) → 979 (4.80) → 888 (3.30) → 978 (3.30) → 887 (1.80) → 977 (1.80) | 982→981, 981→980, 980→41, 979→888, 978→887 |
| Unspecified region · Power comments | 886 (12.00) → 885 (9.00) → 884 (6.00) → 42 (4.80) → 985 (4.80) → 984 (3.30) → 883 (3.00) → 882 (1.80) → 983 (1.80) | 886→885, 885→884, 884→42, 985→984, 984→883, 883→882 |
| Female accounts | 950 (12.00) → 949 (9.00) → 948 (7.20) → 947 (6.00) → 946 (4.80) → 945 (3.00) → 944 (1.80) | 950→949, 949→948, 948→947, 947→946, 946→945, 945→944 |
| Female accounts · 10K+ followers | 955 (9.00) → 954 (6.00) → 953 (4.80) → 987 (3.75) → 952 (3.00) → 986 (2.25) → 951 (1.80) | 955→954, 954→953, 953→987, 987→952, 952→986, 986→951 |
| Top tier | 997 (20.00) → 996 (17.00) | 997→996 |

## Other candidate pools

Every row below shows its actual range. The backup column considers cheaper or equal-rate rows sorted in descending rate order and requiring full bound and capability coverage. A dagger (†) marks a candidate outside the local 5% band. Evaluate stable ties in the listed direction to avoid registering cycles. These pools apply to general choices. A delivery-specific, retention-specific, or otherwise narrower choice uses only rows that preserve its stated qualifier.

| Choice | Handler rates and bounds | Full-coverage no-increase routes |
| --- | --- | --- |
| Plain random comments | 895 (5.625, 10–100,000); 868 (0.75, 10–50,000); 871 (0.75, 10–50,000) | 868 → 871 |
| Plain random Live comments | 1048 (6.00, 50–2,000); 1044 (5.50, 50–2,000) | 1048 → 1044† |
| Random comments from verified accounts | 993 (1125.00, 1–16); 994 (1125.00, 1–16) | 993 → 994 |
| Plain custom comments | 863 (75.00, 1–2,000); 862 (12.50, 1–50,000); 860 (11.25, 1–20,000); 896 (5.625, 20–100,000); 861 (0.75, 50–50,000); 873 (0.75, 50–50,000) | 863 → 862†, 860†; 861 → 873 |
| AI-relevant comments | 865 (100.00, 1–2,000); 864 (18.75, 1–20,000) | 865 → 864† |
| Positive emoji | 858 (5.625, 5–20,000); 856 (3.90, 10–200,000) | None with full coverage and descending rates |
| Negative emoji | 859 (5.625, 10–20,000); 857 (3.90, 10–200,000) | 859 → 857† |
| Generic emoji | 897 (5.625, 10–100,000); 872 (0.75, 10–50,000) | None with full coverage and descending rates |
| Random comments from female accounts | 917 (50.00, 10–500); 889 (12.525, 10–200) | None with full coverage and descending rates |
| USA comments | 1337 (550.00, 5–500); 1359 (60.00, 5–50); 911 (50.00, 10–500); 57 (37.05, 5–150); 880 (37.05, 5–300) | 1359 → 57†, 880†; 57 → 880 |
| USA custom comments | 1338 (550.00, 5–500); 924 (62.50, 10–500); 56 (43.225, 5–150); 881 (43.225, 5–300) | 56 → 881 |
| India comments | 907 (50.40, 5–20); 919 (50.00, 10–250); 894 (8.125, 1–1,000) | 907 → 894†; 919 → 894† |
| Brazil custom comments | 934 (62.50, 10–250); 908 (44.80, 1–10,000) | 934 → 908† |
| Generic Russian comments, retention flexible | 921 (50.00, 10–250); 891 (11.25, 10–200,000) | 921 → 891† |

### Keep distinct or confirm scope

- Preserve Reels and Live target requirements. A post-only service is not a matching backup. Country names, comment languages and audience terms can carry different promises. France versus French, Brazil multi-target versus post-only, and similar language or country overlaps need source confirmation. Separate named genders and tone unless the customer-facing choice allows that preference to vary.
- Fixed package counts, auto-order rows, Poll and Comment Replies stay distinct. No matching mapped alternative is established for Poll or Replies. Auto rows retain the unresolved scheduling issue from the original analysis.
- Root 895 currently covers 10–100,000 with drip feed. 871 covers only up to 50,000 and 868 also lacks drip feed. Keep root coverage and treat both as order-specific candidates until retry checks are verified.
- The two generic Live rows have equal bounds. Make 1048 (6.00) primary and 1044 (5.50) its backup for the generic Live choice under a no-increase ceiling. The 8.33% gap exceeds the local default tolerance. Keep male/female choices separate, and review the existing Random tag default 1045 because its source says male. The same generic pool can serve the instant-delivery path since both rows have the same delivery wording.

## Node audit

Each tag is listed with its current default. A regional or preference-specific leaf uses the pool only where its tag promise fits. Delivery tags retain their delivery scope. The Tags column records existing fallback IDs, and candidate labels refer to the tables above.

| Tag | Current handler and bounds | Current fallbacks | Routing review |
| --- | --- | --- | --- |
| t:root | 895, 10–100,000 | — | Review Plain random comments pool for this path |
| t:default | 871, 10–50,000 | — | Review Plain random comments pool for this path |
| t:custom-comments | 862, 1–50,000 | — | Review Plain custom comments pool for this path |
| t:package | 1446, 1–1 | — | Keep this default. No reviewed pool for this row. |
| t:custom-comments-package | 1455, 1–1 | — | Keep this default. No reviewed pool for this row. |
| t:default-standard | 868, 10–50,000 | 871 | Review Plain random comments pool for this path |
| t:default-exclusive | 64, 5–2,500 | — | Keep this default. No reviewed pool for this row. |
| t:default-reels | 803, 10–200 | — | Keep this default. No reviewed pool for this row. |
| t:default-verified | 993, 1–16 | 994 | Review Random comments from verified accounts pool for this path |
| t:default-regions | 1337, 5–500 | — | Review USA comments pool for this path |
| t:default-live | 1044, 50–2,000 | 1048 | Review Plain random Live comments pool for this path |
| t:default-channel | 1156, 10–5,000 | — | Keep this default. No reviewed pool for this row. |
| t:custom-standard | 860, 1–20,000 | — | Review Plain custom comments pool for this path |
| t:custom-reels | 816, 10–200 | — | Keep this default. No reviewed pool for this row. |
| t:custom-verified | 995, 1–16 | — | Keep this default. No reviewed pool for this row. |
| t:custom-super | 1039, 4–500 | — | Keep this default. No reviewed pool for this row. |
| t:custom-exclusive | 56, 5–150 | 881 | Review USA custom comments pool for this path |
| t:custom-regions | 1338, 5–500 | — | Review USA custom comments pool for this path |
| t:package-fixed | 1445, 1–1 | — | Keep this default. No reviewed pool for this row. |
| t:package-auto | 1504, 1–1 | — | Keep this default. No reviewed pool for this row. |
| t:custom-package-fixed | 1454, 1–1 | — | Keep this default. No reviewed pool for this row. |
| t:custom-package-auto | 1505, 1–1 | — | Keep this default. No reviewed pool for this row. |
| t:poll | 936, 50–5,000 | — | Keep this default. No reviewed pool for this row. |
| t:replies | 943, 5–1,000 | — | Keep this default. No reviewed pool for this row. |
| t:default-standard-style-or-tone | 855, 1–100,000 | — | Keep this default. No reviewed pool for this row. |
| t:default-standard-relevance-or-context | 864, 1–20,000 | — | Review AI-relevant comments pool for this path |
| t:default-standard-audience | 867, 1–2,000 | — | Keep this default. No reviewed pool for this row. |
| t:default-standard-language-or-region | 874, 20–50,000 | — | Keep this default. No reviewed pool for this row. |
| t:default-exclusive-power-or-explore | 33, 1,000–1,000 | — | Review South Korea · Power comments pool for this path |
| t:default-exclusive-audience | 34, 1,000–1,000 | — | Review Brazil · Power comments pool for this path |
| t:default-exclusive-language-or-region | 38, 1,000–1,000 | — | Review USA/UK · Power comments pool for this path |
| t:default-reels-audience | 804, 10–200 | — | Keep this default. No reviewed pool for this row. |
| t:default-reels-language-or-region | 807, 10–100 | — | Keep this default. No reviewed pool for this row. |
| t:default-reels-hq-wording | 806, 10–100 | — | Keep this default. No reviewed pool for this row. |
| t:default-verified-power-or-explore | 951, 1,000–1,000 | — | Review Female accounts · 10K+ followers pool for this path |
| t:default-verified-audience | 944, 1,000–1,000 | — | Review Female accounts pool for this path |
| t:default-verified-language-or-region | 963, 1,000–1,000 | — | Review USA/UK · Power comments pool for this path |
| t:default-live-random | 1045, 50–2,000 | — | Keep this default. No reviewed pool for this row. |
| t:default-live-audience | 1046, 50–2,000 | — | Keep this default. No reviewed pool for this row. |
| t:custom-standard-general-custom-comments | 861, 50–50,000 | 873 | Review Plain custom comments pool for this path |
| t:custom-standard-language-or-region | 853, 5–200,000 | — | Keep this default. No reviewed pool for this row. |
| t:custom-standard-gender | 909, 1–10,000 | — | Keep this default. No reviewed pool for this row. |
| t:custom-standard-relevance | 866, 1–2,000 | — | Keep this default. No reviewed pool for this row. |
| t:custom-standard-premium-or-high-end | 903, 1–200 | — | Keep this default. No reviewed pool for this row. |
| t:custom-reels-gender | 818, 10–200 | — | Keep this default. No reviewed pool for this row. |
| t:custom-reels-language-or-region | 822, 10–100 | — | Keep this default. No reviewed pool for this row. |
| t:custom-reels-hq-wording | 819, 10–100 | — | Keep this default. No reviewed pool for this row. |
| t:default-standard-general-random | 869, 10–500,000 | — | Keep this default. No reviewed pool for this row. |
| t:default-standard-delivery | 856, 10–200,000 | — | Keep the delivery qualification. Match any backup to that promise. |
| t:default-exclusive-delivery | 35, 1,000–1,000 | — | Keep the delivery qualification. Match any backup to that promise. |
| t:default-live-instant-delivery | 1048, 50–2,000 | — | Review Plain random Live comments pool for this path |
| t:default-channel-positive | 1156, 10–5,000 | — | Keep this default. No reviewed pool for this row. |

## Every service selector

Each selector lists its current options and how to read them against the proposals. A repeated group within a general selector can share one option if its routing covers the same customer order. The same choice can remain accessible from more than one tag. The 1,000-quantity groups can draw on the compatible mapped pool across paths. Keep the delivery-specific option set tied to the source delivery wording.

### f:service-default-regions · Language or region

| Current option | Handler | Proposed treatment |
| --- | --- | --- |
| USA/UK · 5 comments (source label) | 1325 | Use USA/UK · Power comments at quantity 1,000 |
| USA/UK · 10 comments (source label) | 1326 | Use USA/UK · Power comments at quantity 1,000 |
| USA/UK · 20 comments (source label) | 1327 | Use USA/UK · Power comments at quantity 1,000 |
| USA · 5–500 comments | 1337 | Review USA comments pool and preserve payload ranges |
| USA · 5–50 comments | 1359 | Review USA comments pool and preserve payload ranges |
| France | 1371 | Keep the customer distinction |
| Brazil · 5 comments (source label) | 1373 | Use Brazil · Power comments at quantity 1,000 |
| Brazil · 10 comments (source label) | 1374 | Use Brazil · Power comments at quantity 1,000 |
| Brazil · 20 comments (source label) | 1376 | Use Brazil · Power comments at quantity 1,000 |
| Brazil · 40 comments (source label) | 1377 | Use Brazil · Power comments at quantity 1,000 |
| Brazil | 1421 | Keep the customer distinction |
| South Korea · 5 comments (source label) | 1425 | Use South Korea · Power comments at quantity 1,000 |
| South Korea · 10 comments (source label) | 1426 | Use South Korea · Power comments at quantity 1,000 |
| South Korea · 20 comments (source label) | 1427 | Use South Korea · Power comments at quantity 1,000 |
| South Korea · 40 comments (source label) | 1428 | Use South Korea · Power comments at quantity 1,000 |
| Nigeria | 1431 | Keep the customer distinction |
| Italy | 1435 | Keep the customer distinction |

### f:service-custom-verified · Targeting

| Current option | Handler | Proposed treatment |
| --- | --- | --- |
| Arab/Gulf | 989 | Keep the customer distinction |
| 10K+ followers · 5 comments (source label) | 991 | Keep the customer distinction |
| 10K+ followers · 10 comments (source label) | 992 | Keep the customer distinction |
| Verified | 995 | Keep the customer distinction |

### f:service-custom-super · Region

| Current option | Handler | Proposed treatment |
| --- | --- | --- |
| USA/UK | 1039 | Keep the customer distinction |
| Germany | 1040 | Keep the customer distinction |
| Sweden | 1041 | Keep the customer distinction |
| Spain | 1042 | Keep the customer distinction |

### f:service-custom-exclusive · Region

| Current option | Handler | Proposed treatment |
| --- | --- | --- |
| USA | 56 | Review USA custom comments pool and preserve payload ranges |
| USA/Europe | 63 | Keep the customer distinction |
| USA · African American audience | 100 | Keep the customer distinction |

### f:service-custom-regions · Language or region

| Current option | Handler | Proposed treatment |
| --- | --- | --- |
| USA | 1338 | Review USA custom comments pool and preserve payload ranges |
| Brazil | 1420 | Keep the customer distinction |
| Italy | 1436 | Keep the customer distinction |
| Turkey | 1444 | Keep the customer distinction |

### f:service-package-fixed · Package size

| Current option | Handler | Proposed treatment |
| --- | --- | --- |
| 1 comment · Verified · Artist | 1445 | Keep the customer distinction |
| 2 comments · Verified · Artist | 1446 | Keep the customer distinction |
| 3 comments · Verified · Artist | 1447 | Keep the customer distinction |
| 4 comments · Verified · Artist | 1448 | Keep the customer distinction |
| 5 comments · Verified · Artist | 1449 | Keep the customer distinction |
| 6 comments · Verified · Artist | 1450 | Keep the customer distinction |

### f:service-custom-package-fixed · Package size

| Current option | Handler | Proposed treatment |
| --- | --- | --- |
| 1 comment · Verified · Egypt | 1454 | Keep the customer distinction |
| 2 comments · Verified · Egypt | 1455 | Keep the customer distinction |
| 3 comments · Verified · Egypt | 1456 | Keep the customer distinction |
| 4 comments · Verified · Egypt | 1457 | Keep the customer distinction |
| 5 comments · Verified · Egypt | 1458 | Keep the customer distinction |
| 10 comments · Verified · Egypt | 1459 | Keep the customer distinction |
| 15 comments · Verified · Egypt | 1460 | Keep the customer distinction |
| 20 comments · Verified · Egypt | 1461 | Keep the customer distinction |

### f:service-default-standard-style-or-tone · Comment style

| Current option | Handler | Proposed treatment |
| --- | --- | --- |
| Hype | 855 | Keep the customer distinction |
| Positive emoji · 10–200,000 comments | 856 | Review Positive emoji pool and preserve payload ranges |
| Negative emoji · 10–200,000 comments | 857 | Review Negative emoji pool and preserve payload ranges |
| Positive emoji · 5–20,000 comments | 858 | Review Positive emoji pool and preserve payload ranges |
| Negative emoji · 10–20,000 comments | 859 | Review Negative emoji pool and preserve payload ranges |
| HQ emoji · 10–500,000 comments | 870 | Keep the customer distinction |
| Emoji · 10–50,000 comments | 872 | Review Generic emoji pool and preserve payload ranges |
| HQ emoji · 20–50,000 comments | 877 | Keep the customer distinction |
| Russian · positive | 892 | Keep the customer distinction |
| Russian · neutral | 893 | Keep the customer distinction |
| Emoji · 10–100,000 comments | 897 | Review Generic emoji pool and preserve payload ranges |

### f:service-default-standard-relevance-or-context · Relevance

| Current option | Handler | Proposed treatment |
| --- | --- | --- |
| AI-relevant · 1–20,000 comments | 864 | Review AI-relevant comments pool and preserve payload ranges |
| AI-relevant · 1–2,000 comments | 865 | Review AI-relevant comments pool and preserve payload ranges |
| Relevant · 10K+ followers | 867 | Keep the customer distinction |
| Post-related | 879 | Keep the customer distinction |

### f:service-default-standard-audience · Audience

| Current option | Handler | Proposed treatment |
| --- | --- | --- |
| Relevant · 10K+ followers | 867 | Keep the customer distinction |
| Male · HQ | 875 | Keep the customer distinction |
| Female · HQ | 876 | Keep the customer distinction |
| 5 comments (source label) | 882 | Use Unspecified region · Power comments at quantity 1,000 |
| 10 comments (source label) | 883 | Use Unspecified region · Power comments at quantity 1,000 |
| 40 comments (source label) | 884 | Use Unspecified region · Power comments at quantity 1,000 |
| 100 comments (source label) | 885 | Use Unspecified region · Power comments at quantity 1,000 |
| 200 comments (source label) | 886 | Use Unspecified region · Power comments at quantity 1,000 |
| Arabic · 5 comments (source label) | 887 | Use Arabic · Power comments at quantity 1,000 |
| Arabic · 10 comments (source label) | 888 | Use Arabic · Power comments at quantity 1,000 |
| Female · 10–200 comments | 889 | Review Random comments from female accounts pool and preserve payload ranges |
| Male | 915 | Keep the customer distinction |
| Female · 10–500 comments | 917 | Review Random comments from female accounts pool and preserve payload ranges |

### f:service-default-standard-language-or-region · Language or region

| Current option | Handler | Proposed treatment |
| --- | --- | --- |
| Worldwide · English | 874 | Keep the customer distinction |
| USA · 5–300 comments | 880 | Review USA comments pool and preserve payload ranges |
| Arabic · 5 comments (source label) | 887 | Use Arabic · Power comments at quantity 1,000 |
| Arabic · 10 comments (source label) | 888 | Use Arabic · Power comments at quantity 1,000 |
| Russian · random · non-drop wording | 891 | Review Generic Russian comments, retention flexible pool and preserve payload ranges |
| Russian · positive | 892 | Keep the customer distinction |
| Russian · neutral | 893 | Keep the customer distinction |
| India · 1–1,000 comments | 894 | Review India comments pool and preserve payload ranges |
| English · non-drop wording | 905 | Keep the customer distinction |
| Brazil | 906 | Keep the customer distinction |
| India · 5–20 comments | 907 | Review India comments pool and preserve payload ranges |
| USA · 10–500 comments | 911 | Review USA comments pool and preserve payload ranges |
| France | 912 | Keep the customer distinction |
| Italy | 913 | Keep the customer distinction |
| Germany | 914 | Keep the customer distinction |
| English · Iranian accounts | 916 | Keep the customer distinction |
| India · 10–250 comments | 919 | Review India comments pool and preserve payload ranges |
| Turkey | 920 | Keep the customer distinction |
| Thailand | 922 | Keep the customer distinction |
| Japan | 923 | Keep the customer distinction |
| Indonesia | 941 | Keep the customer distinction |
| Arab | 942 | Keep the customer distinction |

### f:service-default-exclusive-power-or-explore · Audience

| Current option | Handler | Proposed treatment |
| --- | --- | --- |
| South Korea · 20 comments (source label) | 33 | Use South Korea · Power comments at quantity 1,000 |
| Brazil · 20 comments (source label) | 34 | Use Brazil · Power comments at quantity 1,000 |
| Worldwide · 20 comments (source label) | 35 | Use Worldwide · Power comments at quantity 1,000 |
| Worldwide · 80 comments (source label) | 36 | Use Worldwide · Power comments at quantity 1,000 |
| Worldwide · 200 comments (source label) | 37 | Use Worldwide · Power comments at quantity 1,000 |
| USA/UK · 20 comments (source label) | 38 | Use USA/UK · Power comments at quantity 1,000 |
| USA/UK · 40 comments (source label) | 39 | Use USA/UK · Power comments at quantity 1,000 |
| USA/UK · 100 comments (source label) | 40 | Use USA/UK · Power comments at quantity 1,000 |
| Arabic · 20 comments (source label) | 41 | Use Arabic · Power comments at quantity 1,000 |
| 20 comments (source label) | 42 | Use Unspecified region · Power comments at quantity 1,000 |

### f:service-default-exclusive-audience · Audience

| Current option | Handler | Proposed treatment |
| --- | --- | --- |
| South Korea · 20 comments (source label) | 33 | Use South Korea · Power comments at quantity 1,000 |
| Brazil · 20 comments (source label) | 34 | Use Brazil · Power comments at quantity 1,000 |
| Worldwide · 20 comments (source label) | 35 | Use Worldwide · Power comments at quantity 1,000 |
| Worldwide · 80 comments (source label) | 36 | Use Worldwide · Power comments at quantity 1,000 |
| Worldwide · 200 comments (source label) | 37 | Use Worldwide · Power comments at quantity 1,000 |
| USA/UK · 20 comments (source label) | 38 | Use USA/UK · Power comments at quantity 1,000 |
| USA/UK · 40 comments (source label) | 39 | Use USA/UK · Power comments at quantity 1,000 |
| USA/UK · 100 comments (source label) | 40 | Use USA/UK · Power comments at quantity 1,000 |
| Arabic · 20 comments (source label) | 41 | Use Arabic · Power comments at quantity 1,000 |
| 20 comments (source label) | 42 | Use Unspecified region · Power comments at quantity 1,000 |
| Female | 88 | Keep the customer distinction |
| Male | 89 | Keep the customer distinction |

### f:service-default-exclusive-language-or-region · Language or region

| Current option | Handler | Proposed treatment |
| --- | --- | --- |
| USA/UK · 20 comments (source label) | 38 | Use USA/UK · Power comments at quantity 1,000 |
| USA/UK · 40 comments (source label) | 39 | Use USA/UK · Power comments at quantity 1,000 |
| USA/UK · 100 comments (source label) | 40 | Use USA/UK · Power comments at quantity 1,000 |
| Arabic · 20 comments (source label) | 41 | Use Arabic · Power comments at quantity 1,000 |
| USA | 57 | Review USA comments pool and preserve payload ranges |
| USA/Europe | 64 | Keep the customer distinction |
| USA · African American audience | 101 | Keep the customer distinction |

### f:service-default-reels-audience · Audience

| Current option | Handler | Proposed treatment |
| --- | --- | --- |
| Male | 803 | Keep the customer distinction |
| Female | 804 | Keep the customer distinction |
| India | 805 | Keep the customer distinction |
| Hispanic · HQ | 806 | Keep the customer distinction |
| Female · Brazil · HQ | 811 | Keep the customer distinction |
| Arab · HQ | 813 | Keep the customer distinction |

### f:service-default-reels-language-or-region · Language or region

| Current option | Handler | Proposed treatment |
| --- | --- | --- |
| Turkey | 807 | Keep the customer distinction |
| France | 808 | Keep the customer distinction |
| Japan/China mix | 809 | Keep the customer distinction |
| Germany | 810 | Keep the customer distinction |
| Brazil | 811 | Keep the customer distinction |
| Korea/Thailand mix | 812 | Keep the customer distinction |
| Arab · HQ | 813 | Keep the customer distinction |
| Russia | 814 | Keep the customer distinction |
| Italy | 815 | Keep the customer distinction |

### f:service-default-reels-hq-wording · Quality

| Current option | Handler | Proposed treatment |
| --- | --- | --- |
| Hispanic · HQ | 806 | Keep the customer distinction |
| Turkey · HQ | 807 | Keep the customer distinction |
| France · HQ | 808 | Keep the customer distinction |
| Japan/China mix | 809 | Keep the customer distinction |
| Germany · HQ | 810 | Keep the customer distinction |
| Brazil · Female · HQ | 811 | Keep the customer distinction |
| Korea/Thailand mix | 812 | Keep the customer distinction |
| Arab · HQ | 813 | Keep the customer distinction |
| Russia · HQ | 814 | Keep the customer distinction |
| Italy · HQ | 815 | Keep the customer distinction |

### f:service-default-verified-power-or-explore · Audience

| Current option | Handler | Proposed treatment |
| --- | --- | --- |
| Female · 10K+ followers · 5 comments | 951 | Use Female accounts · 10K+ followers at quantity 1,000 |
| Female · 10K+ followers · 10 comments | 952 | Use Female accounts · 10K+ followers at quantity 1,000 |
| Female · 10K+ followers · 20 comments | 953 | Use Female accounts · 10K+ followers at quantity 1,000 |
| Female · 10K+ followers · 40 comments | 954 | Use Female accounts · 10K+ followers at quantity 1,000 |
| Female · 10K+ followers · 100 comments | 955 | Use Female accounts · 10K+ followers at quantity 1,000 |
| Worldwide · 5 comments (source label) | 956 | Use Worldwide · Power comments at quantity 1,000 |
| Worldwide · 10 comments (source label) | 957 | Use Worldwide · Power comments at quantity 1,000 |
| Worldwide · 20 comments (source label) | 958 | Use Worldwide · Power comments at quantity 1,000 |
| Worldwide · 40 comments (source label) | 959 | Use Worldwide · Power comments at quantity 1,000 |
| Worldwide · 80 comments (source label) | 960 | Use Worldwide · Power comments at quantity 1,000 |
| Worldwide · 100 comments (source label) | 961 | Use Worldwide · Power comments at quantity 1,000 |
| Worldwide · 200 comments (source label) | 962 | Use Worldwide · Power comments at quantity 1,000 |
| USA/UK · 5 comments (source label) | 963 | Use USA/UK · Power comments at quantity 1,000 |
| USA/UK · 10 comments (source label) | 964 | Use USA/UK · Power comments at quantity 1,000 |
| USA/UK · 20 comments (source label) | 965 | Use USA/UK · Power comments at quantity 1,000 |
| USA/UK · 40 comments (source label) | 966 | Use USA/UK · Power comments at quantity 1,000 |
| USA/UK · 80 comments (source label) | 967 | Use USA/UK · Power comments at quantity 1,000 |
| USA/UK · 100 comments (source label) | 968 | Use USA/UK · Power comments at quantity 1,000 |
| Brazil · 5 comments (source label) | 969 | Use Brazil · Power comments at quantity 1,000 |
| Brazil · 10 comments (source label) | 970 | Use Brazil · Power comments at quantity 1,000 |
| Brazil · 20 comments (source label) | 971 | Use Brazil · Power comments at quantity 1,000 |
| Brazil · 40 comments (source label) | 972 | Use Brazil · Power comments at quantity 1,000 |
| South Korea · 5 comments (source label) | 973 | Use South Korea · Power comments at quantity 1,000 |
| South Korea · 10 comments (source label) | 974 | Use South Korea · Power comments at quantity 1,000 |
| South Korea · 20 comments (source label) | 975 | Use South Korea · Power comments at quantity 1,000 |
| South Korea · 40 comments (source label) | 976 | Use South Korea · Power comments at quantity 1,000 |
| Arabic · 5 comments (source label) | 977 | Use Arabic · Power comments at quantity 1,000 |
| Arabic · 10 comments (source label) | 978 | Use Arabic · Power comments at quantity 1,000 |
| Arabic · 20 comments (source label) | 979 | Use Arabic · Power comments at quantity 1,000 |
| Arabic · 40 comments (source label) | 980 | Use Arabic · Power comments at quantity 1,000 |
| Arabic · 80 comments (source label) | 981 | Use Arabic · Power comments at quantity 1,000 |
| 5 comments (source label) | 983 | Use Unspecified region · Power comments at quantity 1,000 |
| 10 comments (source label) | 984 | Use Unspecified region · Power comments at quantity 1,000 |
| 20 comments (source label) | 985 | Use Unspecified region · Power comments at quantity 1,000 |

### f:service-default-verified-audience · Audience

| Current option | Handler | Proposed treatment |
| --- | --- | --- |
| Female · 5 comments | 944 | Use Female accounts at quantity 1,000 |
| Female · 10 comments | 945 | Use Female accounts at quantity 1,000 |
| Female · 20 comments | 946 | Use Female accounts at quantity 1,000 |
| Female · 40 comments | 947 | Use Female accounts at quantity 1,000 |
| Female · 80 comments | 948 | Use Female accounts at quantity 1,000 |
| Female · 100 comments | 949 | Use Female accounts at quantity 1,000 |
| Female · 200 comments | 950 | Use Female accounts at quantity 1,000 |
| Female · 10K+ followers · 5 comments | 951 | Use Female accounts · 10K+ followers at quantity 1,000 |
| Female · 10K+ followers · 10 comments | 952 | Use Female accounts · 10K+ followers at quantity 1,000 |
| Female · 10K+ followers · 20 comments | 953 | Use Female accounts · 10K+ followers at quantity 1,000 |
| Female · 10K+ followers · 40 comments | 954 | Use Female accounts · 10K+ followers at quantity 1,000 |
| Female · 10K+ followers · 100 comments | 955 | Use Female accounts · 10K+ followers at quantity 1,000 |
| Worldwide · 5 comments (source label) | 956 | Use Worldwide · Power comments at quantity 1,000 |
| Worldwide · 10 comments (source label) | 957 | Use Worldwide · Power comments at quantity 1,000 |
| Worldwide · 20 comments (source label) | 958 | Use Worldwide · Power comments at quantity 1,000 |
| Worldwide · 40 comments (source label) | 959 | Use Worldwide · Power comments at quantity 1,000 |
| Worldwide · 80 comments (source label) | 960 | Use Worldwide · Power comments at quantity 1,000 |
| Worldwide · 100 comments (source label) | 961 | Use Worldwide · Power comments at quantity 1,000 |
| Worldwide · 200 comments (source label) | 962 | Use Worldwide · Power comments at quantity 1,000 |
| USA/UK · 5 comments (source label) | 963 | Use USA/UK · Power comments at quantity 1,000 |
| USA/UK · 10 comments (source label) | 964 | Use USA/UK · Power comments at quantity 1,000 |
| USA/UK · 20 comments (source label) | 965 | Use USA/UK · Power comments at quantity 1,000 |
| USA/UK · 40 comments (source label) | 966 | Use USA/UK · Power comments at quantity 1,000 |
| USA/UK · 80 comments (source label) | 967 | Use USA/UK · Power comments at quantity 1,000 |
| USA/UK · 100 comments (source label) | 968 | Use USA/UK · Power comments at quantity 1,000 |
| Brazil · 5 comments (source label) | 969 | Use Brazil · Power comments at quantity 1,000 |
| Brazil · 10 comments (source label) | 970 | Use Brazil · Power comments at quantity 1,000 |
| Brazil · 20 comments (source label) | 971 | Use Brazil · Power comments at quantity 1,000 |
| Brazil · 40 comments (source label) | 972 | Use Brazil · Power comments at quantity 1,000 |
| South Korea · 5 comments (source label) | 973 | Use South Korea · Power comments at quantity 1,000 |
| South Korea · 10 comments (source label) | 974 | Use South Korea · Power comments at quantity 1,000 |
| South Korea · 20 comments (source label) | 975 | Use South Korea · Power comments at quantity 1,000 |
| South Korea · 40 comments (source label) | 976 | Use South Korea · Power comments at quantity 1,000 |
| Arabic · 5 comments (source label) | 977 | Use Arabic · Power comments at quantity 1,000 |
| Arabic · 10 comments (source label) | 978 | Use Arabic · Power comments at quantity 1,000 |
| Arabic · 20 comments (source label) | 979 | Use Arabic · Power comments at quantity 1,000 |
| Arabic · 40 comments (source label) | 980 | Use Arabic · Power comments at quantity 1,000 |
| Arabic · 80 comments (source label) | 981 | Use Arabic · Power comments at quantity 1,000 |
| 5 comments (source label) | 983 | Use Unspecified region · Power comments at quantity 1,000 |
| 10 comments (source label) | 984 | Use Unspecified region · Power comments at quantity 1,000 |
| 20 comments (source label) | 985 | Use Unspecified region · Power comments at quantity 1,000 |
| Verified accounts | 993 | Review Random comments from verified accounts pool and preserve payload ranges |
| Top tier · 300 (source label) | 996 | Use Top tier at quantity 1,000 |
| Top tier · 400 (source label) | 997 | Use Top tier at quantity 1,000 |

### f:service-default-verified-language-or-region · Language or region

| Current option | Handler | Proposed treatment |
| --- | --- | --- |
| USA/UK · 5 comments (source label) | 963 | Use USA/UK · Power comments at quantity 1,000 |
| USA/UK · 10 comments (source label) | 964 | Use USA/UK · Power comments at quantity 1,000 |
| USA/UK · 20 comments (source label) | 965 | Use USA/UK · Power comments at quantity 1,000 |
| USA/UK · 40 comments (source label) | 966 | Use USA/UK · Power comments at quantity 1,000 |
| USA/UK · 80 comments (source label) | 967 | Use USA/UK · Power comments at quantity 1,000 |
| USA/UK · 100 comments (source label) | 968 | Use USA/UK · Power comments at quantity 1,000 |
| Arabic · 5 comments (source label) | 977 | Use Arabic · Power comments at quantity 1,000 |
| Arabic · 10 comments (source label) | 978 | Use Arabic · Power comments at quantity 1,000 |
| Arabic · 20 comments (source label) | 979 | Use Arabic · Power comments at quantity 1,000 |
| Arabic · 40 comments (source label) | 980 | Use Arabic · Power comments at quantity 1,000 |
| Arabic · 80 comments (source label) | 981 | Use Arabic · Power comments at quantity 1,000 |
| Arab/Gulf · random | 988 | Keep the customer distinction |
| Arab/Gulf · emoji | 990 | Keep the customer distinction |

### f:service-default-live-random · Comment style

| Current option | Handler | Proposed treatment |
| --- | --- | --- |
| Random | 1044 | Review Plain random Live comments pool and preserve payload ranges |
| Male | 1045 | Keep the customer distinction |
| Female | 1046 | Keep the customer distinction |

### f:service-default-live-audience · Audience

| Current option | Handler | Proposed treatment |
| --- | --- | --- |
| Male | 1045 | Keep the customer distinction |
| Female | 1046 | Keep the customer distinction |

### f:service-custom-standard-general-custom-comments · Custom comments

| Current option | Handler | Proposed treatment |
| --- | --- | --- |
| 1–20,000 comments | 860 | Review Plain custom comments pool and preserve payload ranges |
| 50–50,000 comments | 861 | Review Plain custom comments pool and preserve payload ranges |
| 1–50,000 comments | 862 | Review Plain custom comments pool and preserve payload ranges |
| 1–2,000 comments | 863 | Review Plain custom comments pool and preserve payload ranges |
| Start 0 - 1 Hour · Speed 5K/Day | 878 | Keep the customer distinction |
| 20–100,000 comments | 896 | Review Plain custom comments pool and preserve payload ranges |
| Start 0-1 Hr · Speed Up to 1K/D | 904 | Keep the customer distinction |
| Start 1 Hour · Speed 300/Day | 890 | Keep the customer distinction |

### f:service-custom-standard-language-or-region · Language or region

| Current option | Handler | Proposed treatment |
| --- | --- | --- |
| Ukrainian | 853 | Keep the customer distinction |
| USA · 5–300 comments | 881 | Review USA custom comments pool and preserve payload ranges |
| United Kingdom | 899 | Keep the customer distinction |
| Brazil · 1–10,000 comments | 908 | Review Brazil custom comments pool and preserve payload ranges |
| USA · 10–500 comments | 924 | Review USA custom comments pool and preserve payload ranges |
| Italy | 925 | Keep the customer distinction |
| India | 928 | Keep the customer distinction |
| Turkey | 929 | Keep the customer distinction |
| Russia | 930 | Keep the customer distinction |
| Thailand | 931 | Keep the customer distinction |
| Japan | 932 | Keep the customer distinction |
| Hispanic | 933 | Keep the customer distinction |
| Brazil · 10–250 comments | 934 | Review Brazil custom comments pool and preserve payload ranges |
| Arab | 935 | Keep the customer distinction |
| France | 937 | Keep the customer distinction |
| Germany | 938 | Keep the customer distinction |
| Indonesia | 940 | Keep the customer distinction |

### f:service-custom-standard-gender · Audience

| Current option | Handler | Proposed treatment |
| --- | --- | --- |
| Female · Brazil | 909 | Keep the customer distinction |
| Male · Brazil | 910 | Keep the customer distinction |
| Male | 926 | Keep the customer distinction |
| Female | 927 | Keep the customer distinction |

### f:service-custom-standard-relevance · Relevance

| Current option | Handler | Proposed treatment |
| --- | --- | --- |
| Relevant | 866 | Keep the customer distinction |

### f:service-custom-standard-premium-or-high-end · Service type

| Current option | Handler | Proposed treatment |
| --- | --- | --- |
| Premium | 903 | Keep the customer distinction |
| High-end | 939 | Keep the customer distinction |

### f:service-custom-reels-gender · Audience

| Current option | Handler | Proposed treatment |
| --- | --- | --- |
| Male | 816 | Keep the customer distinction |
| Female | 818 | Keep the customer distinction |
| Female · Brazil · HQ | 825 | Keep the customer distinction |

### f:service-custom-reels-language-or-region · Language or region

| Current option | Handler | Proposed treatment |
| --- | --- | --- |
| France | 822 | Keep the customer distinction |
| Germany | 823 | Keep the customer distinction |
| Korea/Thailand mix | 824 | Keep the customer distinction |
| Brazil | 825 | Keep the customer distinction |
| Arab · HQ | 826 | Keep the customer distinction |
| Russia | 827 | Keep the customer distinction |
| Italy | 828 | Keep the customer distinction |
| India | 817 | Keep the customer distinction |

### f:service-custom-reels-hq-wording · Quality

| Current option | Handler | Proposed treatment |
| --- | --- | --- |
| Turkey · HQ | 819 | Keep the customer distinction |
| Hispanic · HQ | 820 | Keep the customer distinction |
| Japan/China mix | 821 | Keep the customer distinction |
| France · HQ | 822 | Keep the customer distinction |
| Germany · HQ | 823 | Keep the customer distinction |
| Korea/Thailand mix | 824 | Keep the customer distinction |
| Brazil · Female · HQ | 825 | Keep the customer distinction |
| Arab · HQ | 826 | Keep the customer distinction |
| Russia · HQ | 827 | Keep the customer distinction |
| Italy · HQ | 828 | Keep the customer distinction |

### f:service-default-standard-general-random · Comment style

| Current option | Handler | Proposed treatment |
| --- | --- | --- |
| Random · no drip feed | 868 | Review Plain random comments pool and preserve payload ranges |
| HQ random | 869 | Keep the customer distinction |
| Random · 10–50,000 comments | 871 | Review Plain random comments pool and preserve payload ranges |
| Worldwide · English | 874 | Keep the customer distinction |
| Post-related | 879 | Keep the customer distinction |
| Random · 10–100,000 comments | 895 | Review Plain random comments pool and preserve payload ranges |
| Random · non-drop wording | 900 | Keep the customer distinction |
| Premium random | 902 | Keep the customer distinction |
| English · non-drop wording | 905 | Keep the customer distinction |
| Hispanic random | 918 | Keep the customer distinction |
| Russian random | 921 | Review Generic Russian comments, retention flexible pool and preserve payload ranges |

### f:service-default-standard-delivery · Delivery

| Current option | Handler | Proposed treatment |
| --- | --- | --- |
| Comments · HYPE/THRILL · Start 0-1 Hr · Up to 20k/D | 855 | Keep delivery scope. Remove Default count wording where it appears. |
| Comments · Positive EMOJI · Start 0 - 3 Hours · 2K/Day | 856 | Keep delivery scope. Remove Default count wording where it appears. |
| Comments · Negative EMOJI · Start 0 - 3 Hours · 2K/Day | 857 | Keep delivery scope. Remove Default count wording where it appears. |
| Comments · Random Positive Emoji · Start 0 - 2 Hrs · 20K/D | 858 | Keep delivery scope. Remove Default count wording where it appears. |
| Negative emoji · Start 0 - 2 Hrs · 20K/D | 859 | Keep delivery scope. Remove Default count wording where it appears. |
| AI-relevant · Start 0 - 2 Hrs · Up to 3K/D | 864 | Keep delivery scope. Remove Default count wording where it appears. |
| AI-relevant · Start 0 - 2 Hrs · Up to 2K/D | 865 | Keep delivery scope. Remove Default count wording where it appears. |
| Random Comments · RELEVENT COMMENT · From 10k+ Followers · Start 0-3 Hrs · 500/Day | 867 | Keep delivery scope. Remove Default count wording where it appears. |
| Random · no drip feed · Start 0 - 1 Hour · 5K/Day | 868 | Keep delivery scope. Remove Default count wording where it appears. |
| HQ random · Start 0 - 3 Hours · 20K/Day | 869 | Keep delivery scope. Remove Default count wording where it appears. |
| HQ emoji · Start 0 - 3 Hours · 20K/Day | 870 | Keep delivery scope. Remove Default count wording where it appears. |
| Random · Start 0 - 3 Hours · 25K/Day | 871 | Keep delivery scope. Remove Default count wording where it appears. |
| Emoji · Start 0 - 3 Hours · 25K/Day | 872 | Keep delivery scope. Remove Default count wording where it appears. |
| Worldwide · English · Start 6 Hours · 2.5K/Day | 874 | Keep delivery scope. Remove Default count wording where it appears. |
| Random Comments · Male · High quality  · Start 0-6 Hours · 1K/Day | 875 | Keep delivery scope. Remove Default count wording where it appears. |
| Random Comments · Female · High quality  · Start 0-6 Hours · 1K/Day | 876 | Keep delivery scope. Remove Default count wording where it appears. |
| HQ emoji · Start 0-6 Hours · 1K/Day | 877 | Keep delivery scope. Remove Default count wording where it appears. |
| Comments · RANDOM POST RELATED · Start 0 - 1 Hr · 2K/D | 879 | Keep delivery scope. Remove Default count wording where it appears. |
| Comments · RANDOM - USA · 300 · Start 0 - 1 Hour · 150/Day | 880 | Keep delivery scope. Remove Default count wording where it appears. |
| 5 comments (source label) · Start 0-1 Hour · 5/Hour | 882 | Keep delivery scope. Remove Default count wording where it appears. |
| 10 comments (source label) · Start 0-1 Hour · 10/Hour | 883 | Keep delivery scope. Remove Default count wording where it appears. |
| 40 comments (source label) · Start 0-1 Hour · 10/Hour | 884 | Keep delivery scope. Remove Default count wording where it appears. |
| 100 comments (source label) · Start 0-1 Hour · 10/Hour | 885 | Keep delivery scope. Remove Default count wording where it appears. |
| 200 comments (source label) · Start 0-1 Hour · 10/Hour | 886 | Keep delivery scope. Remove Default count wording where it appears. |
| Arabic · 5 comments (source label) · Start 0-1 Hour · 5/Hour | 887 | Keep delivery scope. Remove Default count wording where it appears. |
| Arabic · 10 comments (source label) · Start 0-1 Hour · 10/Hour | 888 | Keep delivery scope. Remove Default count wording where it appears. |
| Female · Start 0 - 1 Hr · 2K/D | 889 | Keep delivery scope. Remove Default count wording where it appears. |
| Russian · random · non-drop wording · Start 1 Hour · 300/Day | 891 | Keep delivery scope. Remove Default count wording where it appears. |
| Russian · positive · Start 1 Hour · 300/Day | 892 | Keep delivery scope. Remove Default count wording where it appears. |
| Russian · neutral · Start 1 Hour · 300/Day | 893 | Keep delivery scope. Remove Default count wording where it appears. |
| India · Start 1 Hour · 500/Day | 894 | Keep delivery scope. Remove Default count wording where it appears. |
| Random · Start 0-1 Hour · 10K/Day | 895 | Keep delivery scope. Remove Default count wording where it appears. |
| Emoji · Start 0-1 Hour · 10K/Day | 897 | Keep delivery scope. Remove Default count wording where it appears. |
| Random · non-drop wording · Start 0-1 Hour · INSTANT | 900 | Keep delivery scope. Remove Default count wording where it appears. |
| Premium random · Start 0 - 3 Hours · 250/Day | 902 | Keep delivery scope. Remove Default count wording where it appears. |
| English · non-drop wording · Start 0-1 Hour · 2K/Day | 905 | Keep delivery scope. Remove Default count wording where it appears. |
| BRAZIL Comments · RANDOM · Start 1 Hour · 500/Day | 906 | Keep delivery scope. Remove Default count wording where it appears. |
| India · Start 0 - 1 Hour · 500/Day | 907 | Keep delivery scope. Remove Default count wording where it appears. |
| Comments · RANDOM · USA · Start 0-1 Hour · Fast | 911 | Keep delivery scope. Remove Default count wording where it appears. |
| Comments · RANDOM · FRENCH · Start 0-1 Hour · Fast | 912 | Keep delivery scope. Remove Default count wording where it appears. |
| Comments · RANDOM · ITALIAN · Start 0-1 Hour · Fast | 913 | Keep delivery scope. Remove Default count wording where it appears. |
| Comments · RANDOM · GERMANY · Start 0-1 Hour · Fast | 914 | Keep delivery scope. Remove Default count wording where it appears. |
| Comments · RANDOM · MALE · Start 1 Hour · 500/Day | 915 | Keep delivery scope. Remove Default count wording where it appears. |
| English · Iranian accounts · Start 0 - 1 Hour · 500/Day | 916 | Keep delivery scope. Remove Default count wording where it appears. |
| Female · Start 1 Hour · 500/Day | 917 | Keep delivery scope. Remove Default count wording where it appears. |
| Hispanic random · Start 1 Hour · 100/Day | 918 | Keep delivery scope. Remove Default count wording where it appears. |
| India · Start 1 Hour · 100/Day | 919 | Keep delivery scope. Remove Default count wording where it appears. |
| Comments · RANDOM · TURKEY · Start 1 Hour · 100/Day | 920 | Keep delivery scope. Remove Default count wording where it appears. |
| Russian random · Start 1 Hour · 100/Day | 921 | Keep delivery scope. Remove Default count wording where it appears. |
| Comments · RANDOM · KOREAN THAILAND · Start 1 Hour · 100/Day | 922 | Keep delivery scope. Remove Default count wording where it appears. |
| Comments · RANDOM · JAPAN CHINA · Start 1 Hour · 100/Day | 923 | Keep delivery scope. Remove Default count wording where it appears. |
| Comments · RANDOM · ARAB · Start 0-1 Hour · FAST | 942 | Keep delivery scope. Remove Default count wording where it appears. |

### f:service-default-exclusive-delivery · Delivery

| Current option | Handler | Proposed treatment |
| --- | --- | --- |
| South Korea · 20 comments (source label) · Start 0-1 Hour · 1 Hour Delivery | 33 | Keep delivery scope. Remove Default count wording where it appears. |
| Brazil · 20 comments (source label) · Start 0-1 Hour · 1 Hour Delivery | 34 | Keep delivery scope. Remove Default count wording where it appears. |
| Worldwide · 20 comments (source label) · Start 0-1 Hour · 1 Hour Delivery | 35 | Keep delivery scope. Remove Default count wording where it appears. |
| Worldwide · 80 comments (source label) · Start 0-1 Hour · 1 Hour Delivery | 36 | Keep delivery scope. Remove Default count wording where it appears. |
| Worldwide · 200 comments (source label) · Start 0-1 Hour · 1 Hour Delivery | 37 | Keep delivery scope. Remove Default count wording where it appears. |
| USA/UK · 20 comments (source label) · Start 0-1 Hour · 1 Hour Delivery | 38 | Keep delivery scope. Remove Default count wording where it appears. |
| USA/UK · 40 comments (source label) · Start 0-1 Hour · 1 Hour Delivery | 39 | Keep delivery scope. Remove Default count wording where it appears. |
| USA/UK · 100 comments (source label) · Start 0-1 Hour · 1 Hour Delivery | 40 | Keep delivery scope. Remove Default count wording where it appears. |
| Arabic · 20 comments (source label) · Start 0-1 Hour · 1 Hour Delivery | 41 | Keep delivery scope. Remove Default count wording where it appears. |
| 20 comments (source label) · Start 0-1 Hour · 1 Hour Delivery | 42 | Keep delivery scope. Remove Default count wording where it appears. |
| Comments · RANDOM - USA · 150 · Start 0 - 1 Hour · 150/Day | 57 | Keep delivery scope. Remove Default count wording where it appears. |
| Comments · NON DROP · Start 0-1 Hour · 24 Hours Delivery | 87 | Keep delivery scope. Remove Default count wording where it appears. |
| Female Comments · NON DROP · Start 0-1 Hour · 24 Hours Delivery | 88 | Keep delivery scope. Remove Default count wording where it appears. |
| Male Comments · NON DROP · Start 0-1 Hour · 24 Hours Delivery | 89 | Keep delivery scope. Remove Default count wording where it appears. |

### f:service-default-live-instant-delivery · Delivery

| Current option | Handler | Proposed treatment |
| --- | --- | --- |
| Random · Start INSTANT | 1044 | Review Plain random Live comments pool and preserve payload ranges |
| Male · Start INSTANT | 1045 | Keep delivery scope. Remove Default count wording where it appears. |
| Female · Start INSTANT | 1046 | Keep delivery scope. Remove Default count wording where it appears. |

## Current rate exceptions

| Node | Current primary → alternate | Reason under local default |
| --- | --- | --- |
| t:default-live | 1044 (5.50) → 1048 (6.00) | Costs more |
| o:default-regions:1359 | 1359 (60.00) → 880 (37.05) | More than 5% cheaper |
| o:default-regions:1359 | 1359 (60.00) → 57 (37.05) | More than 5% cheaper |
| t:default-standard-style-or-tone:859 | 859 (5.625) → 857 (3.90) | More than 5% cheaper |
| t:default-standard-relevance-or-context:865 | 865 (100.00) → 864 (18.75) | More than 5% cheaper |
| t:default-standard-language-or-region:907 | 907 (50.40) → 894 (8.125) | More than 5% cheaper |
| t:default-standard-language-or-region:919 | 919 (50.00) → 894 (8.125) | More than 5% cheaper |
| t:default-live-random:1044 | 1044 (5.50) → 1048 (6.00) | Costs more |
| t:custom-standard-general-custom-comments:863 | 863 (75.00) → 862 (12.50) | More than 5% cheaper |
| t:custom-standard-general-custom-comments:863 | 863 (75.00) → 860 (11.25) | More than 5% cheaper |
| t:custom-standard-language-or-region:934 | 934 (62.50) → 908 (44.80) | More than 5% cheaper |
| t:default-standard-general-random:921 | 921 (50.00) → 891 (11.25) | More than 5% cheaper |
| t:default-live-instant-delivery:1044 | 1044 (5.50) → 1048 (6.00) | Costs more |

The mapped registry IDs absent from current direct or fallback bindings are 982, 986, 987. They appear in the 1,000-quantity pools above. The earlier reconciliation lists all mapped categories and all payload types. No omitted handler is introduced. The ProductDefinition and Builder seed are unchanged in this analysis pass.
