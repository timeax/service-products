# Instagram Subscriptions

21 November 2026 · Proposed routing for site-owner approval

The roadmap is Instagram → Subscriptions → Instagram Subscriptions (instagram-subscriptions-subscriptions). It is not_started and has no canonical definition or catalog ID mapping. The local registry supports **165 candidates**. Cover them through **149 selectable handlers and 16 fallback-only handlers in 13 chains**. Target Builder registry membership remains unverified.

## Scope and omissions

The 165 are all Instagram rows with structured JAP type Subscriptions. Counts by original category are 83 Auto Likes, 28 Auto Views, 51 Auto Comments / Impressions / Saves / Reach, two Brazil rows and one Profile Visits / Highlights / Shares row. None is mapped elsewhere. A scan of the remaining Subscriptions rows by Instagram, IG and Reels names and categories found no further matches. The 5,717-row export has no embedded tenant or provider-account identity.

All 165 use JAP handler configuration 1 and were last seen at 08:02:54 UTC on 18 November 2026, with zero missing streak and markup and no rate adjustment. All are enabled and unlocked, with no state reason or description. Cancellation is enabled on 96. Refill, drip feed and contract are disabled throughout, despite some name qualifiers and emojis. Use root IDs for routing and keep external IDs as evidence.

The type boundary keeps time-labeled Package and Custom Comments Package rows 22–24, 43–44, 55, 103–111 and 121–126 in Instagram Packages. Automatic Story Views 1103 uses Default and stays in Stories. Auto Comments rows 1504 and 1505 are already assigned to Comments with package types. The recurring Saves and Profile Visits candidates from prior analyses are covered here.

[Catalog](../../catalog.json) · [Handler map](../../catalog-handler-service-ids.json) · [Registry](../../handler%20services.json)

## Customer choices

Use Automatic Likes as the starting mode, with 1214 as its preview default. Use one required searchable service choice per mode. Distinguish customer outcomes, eligible media, geographic targets, comment style, and bundle contents. Use source-backed pace and start estimates only where they distinguish a choice. Keep unsupported retention, quality and marketing claims out of the labels. Compare displayed price or structured limits where similar choices require a useful distinction.

| Mode | Direct count | Primary root IDs |
| --- | ---: | --- |
| Automatic Comments | 26 | 1476, 1486, 1488, 1489, 1490, 1491, 1492, 1493, 1494, 1495, 1496, 1497, 1498, 1499, 1500, 1501, 1503, 1507, 1508, 1513, 1514, 1519, 1520, 1521, 1522, 1523 |
| Automatic Impressions | 5 | 1475, 1479, 1481, 1482, 1483 |
| Automatic Likes | 68 | 1206, 1207, 1208, 1209, 1210, 1211, 1213, 1214, 1215, 1216, 1217, 1218, 1219, 1220, 1221, 1222, 1223, 1225, 1227, 1228, 1229, 1231, 1232, 1233, 1234, 1235, 1236, 1239, 1240, 1241, 1242, 1245, 1246, 1247, 1248, 1249, 1250, 1253, 1255, 1256, 1257, 1259, 1260, 1261, 1263, 1264, 1265, 1266, 1267, 1268, 1269, 1270, 1271, 1272, 1275, 1277, 1279, 1281, 1282, 1283, 1284, 1285, 1286, 1287, 1288, 1289, 1391, 1404 |
| Automatic Profile Visits | 2 | 1473, 1518 |
| Automatic Reach | 1 | 1487 |
| Automatic Saves | 3 | 1477, 1478, 1485 |
| Automatic Shares and Reposts | 5 | 1179, 1506, 1510, 1511, 1512 |
| Automatic Views | 20 | 1290, 1292, 1293, 1294, 1295, 1298, 1299, 1300, 1301, 1302, 1303, 1304, 1305, 1306, 1307, 1309, 1310, 1314, 1315, 1316 |
| Bundles | 14 | 1230, 1243, 1244, 1273, 1274, 1276, 1280, 1297, 1308, 1472, 1474, 1480, 1515, 1517 |
| Others | 5 | 1254, 1278, 1317, 1509, 1524 |

The bundle choices name the included metrics. Others preserves 1254 (USA Likes · 5K/day), 1278 (Ads Likes · 5K/day), 1317 (Views · All video types), 1509 (Impressions from Tags), 1524 (Comments · Delivery pace varies). The source does not define the claimed mechanisms for 1254, 1317 and 1524. Keep those claims out of customer copy. Structured quantity is an order input, while the provider's comment count can describe delivered results.

## Fallback decisions

The local strict 5% band requires comparable raw rates of 95%–100% of the primary, identical payload type, full range coverage and enabled capability fit. The ordered chains below passed those checks. The larger pool of 153 mechanically eligible pairs includes switches in audience, target or bundle outcome. For example, 1244 → 1222 would lose reach and impressions, 1298 → 1303 would change All Videos to All Posts, and 1475 has an impressions outcome instead of saves. 1497 and 1498 remain separate for random text versus emoji comments. 1482 retains its own faster, wider-range impressions option. Fallbacks are node-scoped. The host needs safe recurring-order retry semantics to avoid creating a duplicate subscription if a prior creation result is uncertain.

| Primary → backups | Compatibility and customer wording |
| --- | --- |
| 1207 → 1238 | Generic likes, within-hour start. Both names mention 30 days and the refill flag is off. Delivery pace varies. |
| 1214 → 1224 | Generic likes, no refill, within-hour start. Delivery pace varies. |
| 1221 → 1258 | Generic likes, 5K–8K/day. No retention promise. |
| 1222 → 1252 → 1251 | Generic likes, same start window and no refill promise. Both backups list 5K/day. The explicit mix listing goes last. |
| 1231 → 1237 | Generic likes with a within-hour start. Delivery pace varies. No quality or refill promise. |
| 1236 → 1226 | Generic likes, 20K–50K/day, with full capability and range fit. |
| 1246 → 1212 | Generic likes with within-hour start and no refill. Pace varies, and the backup covers wider bounds. |
| 1301 → 1291 | Generic views, within-hour start and 500K–2M/day. |
| 1306 → 1296 | Generic views, 15-minute or within-hour start wording. Pace varies. |
| 1314 → 1313 → 1312 → 1311 | Generic views, equal bounds. Closest numeric daily pace first, then the faster numeric pace, then the unquantified pace. |
| 1474 → 1516 | Same reach and impressions bundle, equal rate and bounds. 100K–250K/day. |
| 1477 → 1484 | Automatic saves, equal rate and bounds. 5K–20K/day. |
| 1501 → 1502 | Random comments, same rate, bounds and delivery. Audience varies between the male and female account listings. |

## Builder fields and quantities

Installed versions are DGP Spec 1.6.0, Core 1.1.0, Validation 1.2.1 and Ordering 1.1.1. The capability snapshot registers single-choice select/default, scalar text/default, and scalar number/default. Use placeholders. These routes need no newline-list control.

| Field | Configuration and remaining checks |
| --- | --- |
| Service choice | Required searchable select/default by outcome and delivery. “Choose what to add to new posts”. |
| Instagram username | Required text/default, name username. “Enter the Instagram username”. Verify accepted handle syntax. |
| Minimum and maximum per post | Required number/default fields named min and max. Positive whole numbers and distinct placeholders. The host must enforce min ≤ max and both selected-service bounds. |
| Fixed-count routes | 1488, 1489, 1490, 1492, 1493, 1494, 1495, 1508, 1522, 1523. Their two JAP limits both need to be 1,000 per the structured bounds. Prefill or enforce the pair and confirm the discrepancy with the comment counts in names. |
| Post delay | Required single select/default named delay. Options in minutes are 0, 5, 10, 15, 20, 30, 40, 50, 60, 90, 120, 150, 180, 210, 240, 270, 300, 360 and 600. Verify numeric zero and distinguish the per-post delay from listed service start timing. |
| Future posts | Optional number/default named posts, positive whole number when supplied. Omitting it gives an unlimited future-post count per the JAP guide. Verify empty-value omission. |
| Expiry | Optional text/default with DD/MM/YYYY and calendar validation, subject to verifying omission and date transport. JAP expects d/m/Y. |
| Existing posts | The old_posts field is conditional in the JAP guide. The export gives no support evidence for these rows, so omit it initially. |

DGP's snapshot has one pricing quantity, while JAP takes a per-post range and can process an unbounded number of future posts. The workspace has no verified host rule for billing that combination. An authored definition remains a draft until the host's pricing, cross-field limits, scheduling and subscription lifecycle work. No customer pricing formula is inferred.

The original names and structured limits disagree on at least 107 explicitly labeled maxima. Actual accepted links and quantities, live Builder acceptance and fulfillment are unverified.

[Builder capability snapshot](../../.ai/service-builder-capabilities.json) · [JAP order fields](../../.ai/JAP-SERVICE-TYPES.md#subscriptions) · [Local contract index](../../.ai/agent-search.json)

## Complete row-by-row placement

All rows have the Subscriptions type and are enabled and unlocked. Limits and rates are structured payload values.

| Root ID | JAP external ID | Mode | Placement | Structured min–max | Raw rate | Capability | Original category | Original name |
| ---: | --- | --- | --- | ---: | ---: | --- | --- | --- |
| 1179 | jap:10175 | Automatic Shares and Reposts | Selectable | 1–10,000 | 0.45 | Cancellation | Instagram Profile Visits / Highlights / Shares | Instagram Auto Reposts [10K] [Start Time : 0-1 Hour] [NO REFILL] |
| 1206 | jap:10320 | Automatic Likes | Selectable | 10–3,000,000 | 0.175 | Cancellation | Instagram Auto Likes | Instagram Auto Likes [Refill: No] [Max: 1M] [Start Time: 0 - 1 Hr] [Speed: 200K/D] 💧 |
| 1207 | jap:1773 | Automatic Likes | Selectable | 10–50,000 | 0.4125 | Cancellation | Instagram Auto Likes | Instagram Auto HQ Likes [Refill: 30D] [Max: 150K] [Start Time: 0-1 Hr] [Speed: 150K/Day] ⚡⛔ |
| 1208 | jap:10157 | Automatic Likes | Selectable | 10–500,000 | 0.1375 | — | Instagram Auto Likes | Instagram Auto Likes [Refill: No] [Max: 500K] [Start Time: 0 - 1 Hr] [Speed: Up to 100K/D] 💧⛔ |
| 1209 | jap:5716 | Automatic Likes | Selectable | 10–1,000,000 | 0.585 | Cancellation | Instagram Auto Likes | Instagram Auto Likes [80% FEMALE] [Refill: LIFETIME GUARANTEED] [Max: 25K] [Start Time: Instant] [Speed: 10K/Hour] |
| 1210 | jap:10332 | Automatic Likes | Selectable | 10–1,000,000 | 0.324 | Cancellation | Instagram Auto Likes | Instagram Auto Likes [NON DROP] [Refill: 1 Year] [Max: 10K] [Start Time: 1 Hour] [Speed: 5K/Day] ♻️ |
| 1211 | jap:1065 | Automatic Likes | Selectable | 50–100,000 | 0.1215 | Cancellation | Instagram Auto Likes | Instagram Auto Likes [Refill: No] [Max: 100K] [Start Time: 0-1 Hour] [Speed: 300K/Day] ⚡⛔💧 |
| 1212 | jap:9575 | Automatic Likes | Backup for 1246 | 10–1,000,000 | 0.10 | Cancellation | Instagram Auto Likes | Instagram Auto Likes [HQ] [Refill: No] [Max: 500K] [Start Time: 0-3 Hrs] [Speed: 100K/D] 💧⛔️ |
| 1213 | jap:8222 | Automatic Likes | Selectable | 10–300,000 | 0.35 | Cancellation | Instagram Auto Likes | Instagram Auto Likes [Refill: No] [Max: 300K] [Start Time: 0-1 Hour] [Speed: 300K/Day] ⚡⛔💧 |
| 1214 | jap:8233 | Automatic Likes | Selectable | 10–300,000 | 0.225 | Cancellation | Instagram Auto Likes | Instagram Auto Likes [Refill: No] [Max: 80K] [Start Time: 0 - 1 Hour] [Speed: 80K/Day] 💧 |
| 1215 | jap:1697 | Automatic Likes | Selectable | 10–100,000 | 0.1609 | — | Instagram Auto Likes | Instagram Auto Likes [Refill: 90D] [Max: 150K] [Start Time: 0-1 Hr] [Speed: 150K/Day] |
| 1216 | jap:984 | Automatic Likes | Selectable | 100–150,000 | 0.30 | Cancellation | Instagram Auto Likes | Instagram Auto Likes [FROM APP] [Refill: AR30] [Max: 100K] [Start Time: 0 - 1 Hour] [Speed: Up to 5K/Day] |
| 1217 | jap:10319 | Automatic Likes | Selectable | 10–10,000 | 0.6875 | — | Instagram Auto Likes | 🇺🇸 Instagram Auto Likes [USA] [Refill: 30D] [10K] [Start Time: 0 - 1 Hr] [Speed: 10K/D]💧 |
| 1218 | jap:10411 | Automatic Likes | Selectable | 20–15,000 | 1.375 | — | Instagram Auto Likes | Instagram Auto Likes [Max: 15K] [USA 🇺🇸 ] [Refill: 90 Days] [Speed: 10K/Day] [Start Time: 0 - 1 Hours] 💧 ⛔️ ♻️ |
| 1219 | jap:7550 | Automatic Likes | Selectable | 50–50,000 | 0.20 | Cancellation | Instagram Auto Likes | Instagram Auto Likes [Max: 50K] [BOTS] [Refill: No] [Start Time: 0 - 1 Hour] [Speed: 3K/Day] ⛔ |
| 1220 | jap:8530 | Automatic Likes | Selectable | 10–300,000 | 0.1875 | Cancellation | Instagram Auto Likes | Instagram Auto Likes [Max: 30K] [Refill: 30D] [Start Time: 0 - 1 Hour] [Speed: 3K/Day] ⛔ |
| 1221 | jap:2292 | Automatic Likes | Selectable | 10–100,000 | 0.1609 | — | Instagram Auto Likes | Instagram Auto Likes [Max: 300K] [Start Time: 0-1 Hr] [Speed: 5K/Day] 🔥 |
| 1222 | jap:8812 | Automatic Likes | Selectable | 10–150,000 | 0.2375 | Cancellation | Instagram Auto Likes | Instagram Auto Likes [Max: 150K] [Start Time: 0-1 Hour] [Speed: 2-5K/Day] 🔥 |
| 1223 | jap:8371 | Automatic Likes | Selectable | 10–250,000 | 0.2375 | Cancellation | Instagram Auto Likes | Instagram Auto Likes [Max: 100K] [Refill: 30] [Start Time: 0 - 1 Hour] [Speed: 30K/Hour] |
| 1224 | jap:7757 | Automatic Likes | Backup for 1214 | 10–500,000 | 0.225 | Cancellation | Instagram Auto Likes | Instagram Auto Likes [Max: 10K] [Refill: No] [Start Time: 0 - 1 Hour] [Speed: 10K/Hour] |
| 1225 | jap:7586 | Automatic Likes | Selectable | 10–300,000 | 0.225 | Cancellation | Instagram Auto Likes | Instagram Auto Likes [Refill: 30 Days] [10K] [Start Time: Instant] [Speed: 10K/Day] ⛔♻️ |
| 1226 | jap:10156 | Automatic Likes | Backup for 1236 | 10–1,000,000 | 0.495 | Cancellation | Instagram Auto Likes | Instagram Auto Likes [REAL LOOKING] [Max: 50K] [Start Time: 0-1 Hour] [Speed: 20K/Day] |
| 1227 | jap:8374 | Automatic Likes | Selectable | 20–10,000 | 1.35 | — | Instagram Auto Likes | Instagram Auto Likes [5 Likes Per Minute] [Max: 10K] [Start Time: 0-1 Hour] |
| 1228 | jap:5864 | Automatic Likes | Selectable | 10–250,000 | 0.225 | Cancellation | Instagram Auto Likes | Instagram Auto Likes [Refill: 180 Days] [Max: 50K] [Start Time: 1 Hour] [Speed: 5K/Day] ♻️ |
| 1229 | jap:8375 | Automatic Likes | Selectable | 20–10,000 | 1.35 | — | Instagram Auto Likes | Instagram Auto Likes [10 Likes Per Minute] [Max: 10K] [Start Time: 0-1 Hour] |
| 1230 | jap:1161 | Bundles | Selectable | 10–5,000 | 11.5875 | Cancellation | Instagram Auto Likes | 🇮🇹 Instagram Auto Likes + Impressions + Reach [ITALY] [NON DROP] [Max: 2.5K] [Start Time: 4 Hours] [Speed: 1K/Day] |
| 1231 | jap:5957 | Automatic Likes | Selectable | 10–50,000 | 0.30 | Cancellation | Instagram Auto Likes | Instagram Auto Likes [Max: 100K] [Start Time: 0-1 Hour] [Speed: 15K/Day] ⛔️ |
| 1232 | jap:6479 | Automatic Likes | Selectable | 50–50,000 | 0.25 | Cancellation | Instagram Auto Likes | Instagram Auto Likes [Refill: 30D] [Max: 200K] [Start Time: 0-1 Hour] [Speed: 15K/Day] ⛔ |
| 1233 | jap:8546 | Automatic Likes | Selectable | 50–30,000 | 0.225 | Cancellation | Instagram Auto Likes | Instagram Auto Likes [Refill: No Drop] [Max: 30K] [Start Time: Instant - 1 Hour] [Speed: 30K/Day] ⚡💧⛔️ |
| 1234 | jap:8389 | Automatic Likes | Selectable | 10–50,000 | 0.5625 | Cancellation | Instagram Auto Likes | Instagram Auto Likes [Refill: Auto-Refill 30 Days] [50K] [HQ] [Start Time: Instant] [Speed: 30K/Day] 💧⛔️♻️ |
| 1235 | jap:7703 | Automatic Likes | Selectable | 50–150,000 | 0.225 | Cancellation | Instagram Auto Likes | Instagram Auto Likes [Refill: Lifetime Guaranteed] [Max: 100K] [Start Time: 1 Hour] [Speed: 10K/Day] ♻️ |
| 1236 | jap:8547 | Automatic Likes | Selectable | 10–50,000 | 0.50 | Cancellation | Instagram Auto Likes | Instagram Auto Likes [Max: 50K] [Start Time: 0 - 1 Hours] [Speed: 50K Per Day] 💧⛔ |
| 1237 | jap:6213 | Automatic Likes | Backup for 1231 | 10–100,000 | 0.30 | Cancellation | Instagram Auto Likes | Instagram Auto Likes [HQ] [Refill: AR30] [Max: 100K] [Start Time: 0-1 Hour] [Speed: FAST] ⛔ |
| 1238 | jap:7783 | Automatic Likes | Backup for 1207 | 10–200,000 | 0.4125 | Cancellation | Instagram Auto Likes | Instagram Auto Likes [Refill: 30D] [Max: 200K] [Start Time: 0-1 Hour] [Speed: 200K/Day] ⚡⛔ |
| 1239 | jap:6091 | Automatic Likes | Selectable | 10–50,000 | 0.27 | Cancellation | Instagram Auto Likes | Instagram Auto Likes [Refill: AR30] [Max: 200K] [Start Time: 1 Hour] [Speed: 5K/D] ⛔️ |
| 1240 | jap:7099 | Automatic Likes | Selectable | 50–20,000 | 0.225 | Cancellation | Instagram Auto Likes | Instagram Auto Likes [Max: 5K] [Start Time: 0-1 Hour] [Speed: INSTANT] 💧⛔⚡🔥 |
| 1241 | jap:982 | Automatic Likes | Selectable | 50–15,000 | 6.875 | — | Instagram Auto Likes | Instagram Auto RAL™ Likes [Refill: No Drop] [Max: 15K] [Start Time: 0-8 Hours] [Speed: 2K/Day] ⚡💧 |
| 1242 | jap:10297 | Automatic Likes | Selectable | 50–10,000 | 6.75 | — | Instagram Auto Likes | Instagram Auto RAL™ Likes [Refill: No Drop] [Max: 10K] [Start Time: 0-8 Hrs] [Speed: Up to 5K/D] ⚡💧 |
| 1243 | jap:5960 | Bundles | Selectable | 10–300,000 | 0.2063 | Cancellation | Instagram Auto Likes | Instagram Auto Likes + Reach + Impressions [Auto-Refill: 30 Days] [300K] [MQ] [Start Time: Instant] [Speed: 20K/Day] ♻️⛔️ |
| 1244 | jap:1160 | Bundles | Selectable | 10–45,000 | 0.2375 | Cancellation | Instagram Auto Likes | Instagram Auto Likes + Impressions + Reach [Max: 45K] [Start Time: 0-1 Hour] [Speed: 1K/Day] |
| 1245 | jap:5733 | Automatic Likes | Selectable | 25–25,000 | 0.348 | Cancellation | Instagram Auto Likes | Instagram Auto Likes [Refill: No] [Max: 3K/order 30k/link] [Start Time: 0-1 Hour] |
| 1246 | jap:2995 | Automatic Likes | Selectable | 50–5,000 | 0.10 | Cancellation | Instagram Auto Likes | Instagram Auto Likes [EXCLUSIVE] [Refill: No] [Max: 5K] [Start Time: 0-1 Hour] [Speed: 500-1K/Hour] |
| 1247 | jap:6218 | Automatic Likes | Selectable | 50–10,000 | 0.1609 | — | Instagram Auto Likes | Instagram Auto Likes [LOW DROP] [Refill: No] [Max: 10K] [Start Time: 1 Hour] [Speed: 10K/Day] |
| 1248 | jap:2195 | Automatic Likes | Selectable | 10–100,000 | 0.275 | — | Instagram Auto Likes | Instagram Auto Likes [EXCLUSIVE] [WITH PP] [Max: 15K] [Start Time: 0-1 Hour] [Speed: 1.5K/Hour]⚡🔥💧⛔ |
| 1249 | jap:5660 | Automatic Likes | Selectable | 10–100,000 | 0.7375 | Cancellation | Instagram Auto Likes | Instagram Auto Likes [HQ] [NON DROP] [Max: 50K] [Start Time: 0-1 Hour] [Speed: 5K/Hour] |
| 1250 | jap:1923 | Automatic Likes | Selectable | 10–20,000 | 0.1609 | — | Instagram Auto Likes | Instagram Auto Likes [LQ] [EXCLUSIVE] [Refill: No] [Max: 100K] [Start Time: 1 Hour] [Speed: 5K/Day]🔥🔥🔥 |
| 1251 | jap:3853 | Automatic Likes | Backup for 1222 | 10–500,000 | 0.2375 | Cancellation | Instagram Auto Likes | Instagram Auto Likes [MIX] [NO REFILL] [Max: 150K] [Start Time: 0-1 Hour] [Speed: 5K/Day] 💧🔥 |
| 1252 | jap:1922 | Automatic Likes | Backup for 1222 | 10–500,000 | 0.2375 | Cancellation | Instagram Auto Likes | Instagram Auto Likes [HQ] [BEST QUALITY] [Refill: No] [Max:10K] [Start Time: 0-1 Hour] [Speed: 5K/Day] 🔥🔥🔥 |
| 1253 | jap:9134 | Automatic Likes | Selectable | 20–4,000 | 1.50 | — | Instagram Auto Likes | 🇺🇸 Instagram Auto Likes [USA] [Refill: 30D] [Max: 4K] [Start Time: 0 - 1 Hr] [Speed: 3K/D] |
| 1254 | jap:9585 | Others | Selectable | 10–20,000 | 4.00 | — | Instagram Auto Likes | 🇺🇸 Instagram Auto Likes [USA] [Algorithm Tricking] [Refill: Auto - 30D] [Max: 5K] [Start Time: 0 - 1 Hr] [Speed: 5K/D] |
| 1255 | jap:5671 | Automatic Likes | Selectable | 10–10,000 | 0.208 | Cancellation | Instagram Auto Likes | Instagram Auto Likes [Refill: No] [Max: 10K] [Start Time: 2 Hours] [Speed: 20K/Day] 🔥⛔ |
| 1256 | jap:6366 | Automatic Likes | Selectable | 10–20,000 | 2.80 | — | Instagram Auto Likes | Instagram RAU™ Auto Likes [Refill: No Drop] [Max: 7K] [Start Time: 0-1 Hour] [Speed: 2K/Hour] 💧 |
| 1257 | jap:7530 | Automatic Likes | Selectable | 100–2,500,000 | 0.13 | Cancellation | Instagram Auto Likes | Instagram Auto Likes [Refill: No] [Max: 10K] [Start Time: 0-1 Hours] [Speed: 20K/Day] 🔥⛔ |
| 1258 | jap:5717 | Automatic Likes | Backup for 1221 | 10–100,000 | 0.1609 | — | Instagram Auto Likes | Instagram Auto Likes [NON DROP] [Max: 8K] [Start Time: 0-1 Hour] [Speed: 8K/Day] 💧🔥🔥 |
| 1259 | jap:3812 | Automatic Likes | Selectable | 10–100,000 | 0.784 | — | Instagram Auto Likes | Instagram AUTO POWER Likes [TOP IN MARKET] [Refill: No] [Max: 10K] [Start Time: 1 Hour] [Speed: 5K/Day] 🔥 |
| 1260 | jap:6216 | Automatic Likes | Selectable | 100–2,500 | 31.25 | — | Instagram Auto Likes | 🇳🇬Instagram Auto Likes [NIGERIA] [Refill: No] [Max: 2K] [Start Time: 1 Hour] [Speed: 2K/Day] |
| 1261 | jap:8529 | Automatic Likes | Selectable | 20–50,000 | 2.925 | Cancellation | Instagram Auto Likes | Instagram Auto Likes [ARAB - عرب متفاعلين] [Refill: 30 Days] [Max: 500] [Start Time: 0 -12 Hours] [Speed: 500/Day] |
| 1263 | jap:8584 | Automatic Likes | Selectable | 10–1,000,000 | 0.1413 | Cancellation | Instagram Auto Likes | Instagram Auto Likes [R30] [Max: 100K] [Start Time: 0-1 Hours] [Speed: 20K/Day] |
| 1264 | jap:7992 | Automatic Likes | Selectable | 10–10,000,000 | 0.1788 | Cancellation | Instagram Auto Likes | Instagram Auto Likes [R365] [Max: 100K] [Start Time: 0-1 Hours] [Speed: 20K/Day] |
| 1265 | jap:3811 | Automatic Likes | Selectable | 10–100,000 | 0.4968 | — | Instagram Auto Likes | Instagram AUTO POWER Likes [TOP IN MARKET] [Refill: No] [Max: 50K] [Start Time: 1 Hour] [Speed: 5K/Day] 🔥 |
| 1266 | jap:232 | Automatic Likes | Selectable | 10–500,000 | 0.247 | Cancellation | Instagram Auto Likes | Instagram Auto Likes [SUPER HQ] [Max: 45K] [Start Time: 0-1 Hour] [Speed: 2-5K/Day] 🔥🔥🔥🔥 |
| 1267 | jap:6092 | Automatic Likes | Selectable | 10–500,000 | 0.4125 | Cancellation | Instagram Auto Likes | Instagram Auto Likes [SUPER HQ] [Max: 150K] [Start Time: 0-1 Hour] [Speed: 2-5K/Day] 🔥🔥🔥🔥 |
| 1268 | jap:3246 | Automatic Likes | Selectable | 20–10,000 | 1.35 | Cancellation | Instagram Auto Likes | Instagram Auto Likes [MIGHT DROP] [Max: 5K] [Start Time: 0-1 Hour] [Speed: 2K/Day] |
| 1269 | jap:831 | Automatic Likes | Selectable | 20–10,000 | 10.40 | — | Instagram Auto Likes | Instagram Auto Likes RAU™ [KOREA 🇰🇷 🇰🇵] [Max: 1.5K] [Refill: 60D] [Start Time: 0 - 1 Hr] [Speed: 1.5K/D] 💧 |
| 1270 | jap:1989 | Automatic Likes | Selectable | 50–5,000 | 1.10 | Cancellation | Instagram Auto Likes | Instagram Auto Likes [FAST] [Refill: No] [Max: 5K] [Start Time: 0-1 Hour] [Speed: 500/Hour] 🔥🔥 |
| 1271 | jap:1892 | Automatic Likes | Selectable | 25–1,000 | 8.148 | — | Instagram Auto Likes | 🇫🇷 Instagram Auto Likes [FRANCE] [Max: 1K] [Refill: Non Drop] [Start Time: 0 - 8 Hrs] [Speed: Up to 100/D] |
| 1272 | jap:6090 | Automatic Likes | Selectable | 10–300,000 | 0.3125 | Cancellation | Instagram Auto Likes | Instagram Auto Likes [Bots with PP] [Refill: AR30] [Max: 300K] [Start Time: 0-1 Hour] [Speed: FAST] |
| 1273 | jap:3335 | Bundles | Selectable | 5–50,000 | 2.00 | Cancellation | Instagram Auto Likes | Instagram Auto Likes + Impressions + Reach + Views [English Private Profiles] [Refill: No] [Max: 1.5K] [Start Time: 0-1 Hour] [Speed: 1 Hour] 🔥🔥🔥 |
| 1274 | jap:2146 | Bundles | Selectable | 10–500,000 | 1.625 | — | Instagram Auto Likes | 🔥🔥🔥 [EXCLUSIVE] Instagram AUTO Likes + Impressions [Refill: No] [Max: 2K] [Start Time: 0-1 Hour] [Speed: 400-800/Hour] 🔥🔥🔥 |
| 1275 | jap:176 | Automatic Likes | Selectable | 10–500,000 | 1.625 | — | Instagram Auto Likes | 🇮🇷Instagram Auto Likes [10K] [IRAN / ARAB] [Start Time: 1 Hour] [Speed: 10K/Day] |
| 1276 | jap:698 | Bundles | Selectable | 50–50,000 | 2.064 | — | Instagram Auto Likes | Instagram Auto Likes + Impressions + PV [Refill: No] [Max: 50K] [Start Time: 2 Hours] [Speed: 20K/Day] 🔥⛔ |
| 1277 | jap:1896 | Automatic Likes | Selectable | 50–50,000 | 2.064 | — | Instagram Auto Likes | Instagram Auto Likes [Max: 50K] [Start Time: 0-1 Hour] [Speed: INSTANT] 🔥 |
| 1278 | jap:4261 | Others | Selectable | 100–50,000 | 2.375 | Cancellation | Instagram Auto Likes | Instagram Auto Likes [ADS] [Refill: No] [Max: 50K] [Start Time: 1 Hour] [Speed: 5K/Day] |
| 1279 | jap:666 | Automatic Likes | Selectable | 50–50,000 | 2.3564 | — | Instagram Auto Likes | Instagram Auto Likes [Max: 50K] [Start Time: 0-1 Hour] [Speed: 50K/Day] |
| 1280 | jap:1772 | Bundles | Selectable | 50–50,000 | 2.408 | — | Instagram Auto Likes | Instagram Auto Likes + Impressions + PV [Refill: No] [Max: 50K] [Start Time: 0-1 Hour] [Speed: INSTANT] 🔥 |
| 1281 | jap:1920 | Automatic Likes | Selectable | 20–50,000 | 3.08 | — | Instagram Auto Likes | Instagram Auto Likes [SUPER FAST] [Refill: No] [Max: 50K] [Start Time: 0-1 Hour] [Speed: INSTANT] 🔥🔥 |
| 1282 | jap:8576 | Automatic Likes | Selectable | 20–10,000 | 2.75 | — | Instagram Auto Likes | Instagram Auto Likes [🇦🇪 🇸🇦 ARAB - GULF] [Refill: No] [Max: 3K] [Start Time: 0-1 Hour] [Speed: 3K/Day] |
| 1283 | jap:1003 | Automatic Likes | Selectable | 5–50,000 | 3.36 | Cancellation | Instagram Auto Likes | 🇺🇸 Instagram Auto Likes [USA] [Start Time: 0 - 1 Hour] [Speed: 5K/Day] |
| 1284 | jap:715 | Automatic Likes | Selectable | 10–20,000 | 4.00 | — | Instagram Auto Likes | Instagram Auto Likes [Max: 1K] [USA 🇺🇸 ] [Refill: No] [Speed: 1K/Day] [Start Time: 0 - 1 Hours] |
| 1285 | jap:1771 | Automatic Likes | Selectable | 20–2,000 | 4.125 | — | Instagram Auto Likes | Instagram Auto Likes [Max: 2K] [UK 🇬🇧 ] [Refill: No] [Speed: 2K/Day] [Start Time: 0 - 1 Hours] |
| 1286 | jap:6269 | Automatic Likes | Selectable | 50–15,000 | 14.00 | — | Instagram Auto Likes | ⚠️🔥🎇🇺🇸🇪🇺 Instagram Auto Likes USA / EUROPE [EXCLUSIVE - NON DROP] |
| 1287 | jap:5946 | Automatic Likes | Selectable | 50–9,050 | 11.40 | — | Instagram Auto Likes | Instagram Auto Female Likes [Premium] [NON DROP] [Max: 2K] [Start Time: 0-1 Hour] [Speed: 24 Hours Delivery] |
| 1288 | jap:9605 | Automatic Likes | Selectable | 20–200,000 | 1.6313 | Cancellation | Instagram Auto Likes | 🇰🇷 Instagram Auto Likes [KOREA] [Refill: No] [Max: 200K] [Start Time: 0-3 Hrs] [Speed: 2K/Day] |
| 1289 | jap:10076 | Automatic Likes | Selectable | 10–5,000 | 4.8125 | — | Instagram Auto Likes | 🇧🇷 Instagram Auto Likes [BRAZIL] [Refill: No] [Max: 40K] [Start Time: 0 - 1 Hours] [Speed: 10K/Day] 💧 |
| 1290 | jap:798 | Automatic Views | Selectable | 100–2,147,483,647 | 0.0063 | Cancellation | Instagram Auto Views | Instagram Auto Views [Max: 1M] [Start Time: Insatnt] [Speed: 1M/Day] 💧 |
| 1291 | jap:793 | Automatic Views | Backup for 1301 | 100–2,147,483,647 | 0.01 | Cancellation | Instagram Auto Views | Instagram Auto Views [Max: 500K] [Start Time: 0 - 1 Hr] [Speed: 500K/D] 💧 |
| 1292 | jap:731 | Automatic Views | Selectable | 100–2,147,483,647 | 0.03 | Cancellation | Instagram Auto Views | Instagram Auto Views [Max: 1M] [Start Time: 0-1 Hour] [Speed: 1M/Day] |
| 1293 | jap:8617 | Automatic Views | Selectable | 100–2,147,483,647 | 0.07 | Cancellation | Instagram Auto Views | Instagram Auto Views [Max: 10M] [Start Time: 0-1 Hour] [Speed: 500K/Day] |
| 1294 | jap:8577 | Automatic Views | Selectable | 100–2,147,483,647 | 0.0015 | Cancellation | Instagram Auto Views | Instagram Auto Views [Max: 5M] [Start Time: 0-3 Hours] [Speed: 500K/Day] |
| 1295 | jap:792 | Automatic Views | Selectable | 100–2,147,483,647 | 0.125 | Cancellation | Instagram Auto Views | Instagram Auto Views [ALL] [Max: 1M] [Start Time: 0 - 1 Hour] [Speed: 100K/Day] 💧 |
| 1296 | jap:7823 | Automatic Views | Backup for 1306 | 100–2,147,483,647 | 0.20 | Cancellation | Instagram Auto Views | Instagram Auto Views [Max: 1M] [Start Time: 15 Minutes] [Speed: 5M/Day] |
| 1297 | jap:794 | Bundles | Selectable | 100–2,147,483,647 | 0.2375 | Cancellation | Instagram Auto Views | Instagram Auto Views + Reach + Impressions [Max: 10M] [Start Time: 0-1 Hr] [Speed: 500K/D] 💧 |
| 1298 | jap:729 | Automatic Views | Selectable | 100–2,147,483,647 | 0.2556 | Cancellation | Instagram Auto Views | Instagram Auto Views [All Videos] [Max: 1M] [Start Time: 0-1 Hour] [Speed: 10K/Hour] 💧 |
| 1299 | jap:1792 | Automatic Views | Selectable | 100–2,147,483,647 | 0.25 | Cancellation | Instagram Auto Views | Instagram Auto Views [Max: 10M] [Start Time: 0-1 Hour] [Speed: 10M/Day] |
| 1300 | jap:795 | Automatic Views | Selectable | 100–217,545,811 | 0.0032 | — | Instagram Auto Views | Instagram Auto Views [Max: 9M] [Start Time: 0-1 Hour] [Speed: 100K/Day] |
| 1301 | jap:5939 | Automatic Views | Selectable | 100–100,000,000 | 0.01 | Cancellation | Instagram Auto Views | Instagram Auto Views [Max: 10M] [Start Time: 0 - 1 Hours] [Speed: 2M/Day] |
| 1302 | jap:6000 | Automatic Views | Selectable | 100–2,147,483,647 | 0.30 | Cancellation | Instagram Auto Views | Instagram Auto Views [Max: 10M] [Start Time: 0-1 Hour] [Speed: INSTANT] |
| 1303 | jap:791 | Automatic Views | Selectable | 100–2,147,483,647 | 0.248 | Cancellation | Instagram Auto Views | Instagram Auto Views [All Posts] [Max: 10M] [Start Time: 0-1 Hour] [Speed:1M/Day] 💧 |
| 1304 | jap:490 | Automatic Views | Selectable | 100–2,147,483,647 | 0.625 | Cancellation | Instagram Auto Views | Instagram Auto Views [Max: 50K] [Start Time: Instant] [Speed: 50K/Day] 💧 |
| 1305 | jap:340 | Automatic Views | Selectable | 100–2,147,483,647 | 1.00 | Cancellation | Instagram Auto Views | Instagram Auto HQ Views [ALL LINKS] [Max: 100K] [Start Time: 0 - 1 Hour] [Speed: 50K/Hour] ⚡💧 |
| 1306 | jap:5639 | Automatic Views | Selectable | 100–2,147,483,647 | 0.2088 | Cancellation | Instagram Auto Views | Instagram Auto Views [Max: 10M] [Start Time: 0-1 Hour] [Speed: INSTANT]⛔️ |
| 1307 | jap:8578 | Automatic Views | Selectable | 100–2,147,483,647 | 1.125 | Cancellation | Instagram Auto Views | Instagram Auto Reel Views [Max: 5M] [Start Time: 0-1 Hour] [Speed: 500K/Day] |
| 1308 | jap:2942 | Bundles | Selectable | 100–2,147,483,647 | 1.20 | Cancellation | Instagram Auto Views | Instagram Auto Views + Impressions [Max: 5M] [Start Time: 1 Hour] [Speed: 500K/Day] |
| 1309 | jap:797 | Automatic Views | Selectable | 100–2,147,483,647 | 1.2375 | Cancellation | Instagram Auto Views | Instagram Auto Views [REEL + IGTV + POSTS] [Max: 9M] [Start Time: 0-1 Hour] [Speed: 100K/Day] |
| 1310 | jap:2194 | Automatic Views | Selectable | 100–2,147,483,647 | 1.25 | Cancellation | Instagram Auto Views | Instagram Auto Views [Max: 10M] [Start Time:0 - 1 Hours] [Speed: Up to 2M / Day] ⚡ |
| 1311 | jap:529 | Automatic Views | Backup for 1314 | 100–2,147,483,647 | 1.26 | Cancellation | Instagram Auto Views | Instagram Auto Views [Max: 20M] [Start Time: 0-1 Hour] [Speed: Medium] |
| 1312 | jap:6093 | Automatic Views | Backup for 1314 | 100–2,147,483,647 | 1.308 | Cancellation | Instagram Auto Views | Instagram Auto Views [Max: 1M] [Start Time: 15 Minutes] [Speed: 5M/Day] ⚡💧 |
| 1313 | jap:6468 | Automatic Views | Backup for 1314 | 100–2,147,483,647 | 1.325 | Cancellation | Instagram Auto Views | Instagram Auto Views [Max: 1.5M] [Start Time: 0-1 Hour] [Speed: 1.5M/Day] |
| 1314 | jap:6392 | Automatic Views | Selectable | 100–2,147,483,647 | 1.326 | Cancellation | Instagram Auto Views | Instagram Auto Views [Max: 10M] [Start Time: 1 Hour] [Speed: 1M/Day] ⚡ |
| 1315 | jap:6375 | Automatic Views | Selectable | 100–2,147,483,647 | 1.3433 | Cancellation | Instagram Auto Views | Instagram Auto Views [All Posts] [Max: 10M] [Start Time: 0-5 Minutes] [Speed:100K/Hour] 💧 |
| 1316 | jap:7531 | Automatic Views | Selectable | 100–2,147,483,647 | 1.3516 | Cancellation | Instagram Auto Views | Instagram Auto Reel Views [Max: 1M] [Start Time: 15 Minutes] [Speed: 5M/Day] ⚡💧 |
| 1317 | jap:175 | Others | Selectable | 100–2,147,483,647 | 1.3886 | Cancellation | Instagram Auto Views | Instagram Auto Views [EMERGENCY - ALL TYPE OF VIDEOS - AUTO ON / OFF] |
| 1391 | jap:10063 | Automatic Likes | Selectable | 10–5,000 | 3.8375 | — | Instagram BRAZIL Services 🇧🇷 | 🇧🇷Instagram Auto Likes [BRAZIL] [Refill: No] [Max: 40K] [Start Time: 6 Hours] [Speed: 200/Hour] 💧 |
| 1404 | jap:6357 | Automatic Likes | Selectable | 10–10,000 | 0.8125 | — | Instagram BRAZIL Services 🇧🇷 | 🇧🇷 Instagram Auto Likes [BRAZIL][Max: 10K] [Start Time: 0 - 1 Hr] [Speed: 5K/Day] |
| 1472 | jap:8469 | Bundles | Selectable | 10–1,000,000 | 0.0249 | Cancellation | Instagram Auto Comments / Impressions / Saves / Reach | Instagram Auto Impressions + Reach [Max: 500K] [Start Time: 0 - 1 Hr] [Speed: 50K/D] |
| 1473 | jap:10016 | Automatic Profile Visits | Selectable | 10–1,000,000 | 0.025 | Cancellation | Instagram Auto Comments / Impressions / Saves / Reach | Instagram Auto Profile Visits [Max: 500K] [Start Time: 0 - 1 Hr] [Speed: 50K/Day]💧⛔ |
| 1474 | jap:8447 | Bundles | Selectable | 10–1,000,000 | 0.05 | Cancellation | Instagram Auto Comments / Impressions / Saves / Reach | Instagram Auto Reach + Impressions [1M] [Start Time: 0 - 1 Hour] [Speed: 250K/Day] ⛔💧 |
| 1475 | jap:800 | Automatic Impressions | Selectable | 10–1,000,000 | 0.0625 | Cancellation | Instagram Auto Comments / Impressions / Saves / Reach | Instagram Auto Impressions [Max: 500K] [Start Time: 0-1 Hour] [Speed: INSTANT] |
| 1476 | jap:3272 | Automatic Comments | Selectable | 20–50,000 | 7.20 | — | Instagram Auto Comments / Impressions / Saves / Reach | Instagram Auto Random Comments [Male] [High quality ] [Refill: LIFETIME] [Max: 5K] [Start Time: 0-6 Hours] [Speed: 1K/Day] ♻️ |
| 1477 | jap:805 | Automatic Saves | Selectable | 10–150,000 | 0.0625 | Cancellation | Instagram Auto Comments / Impressions / Saves / Reach | Instagram Auto Saves [Max: 20K] [Start Time: 0-1 Hour] [Speed: 20K/Day] |
| 1478 | jap:2941 | Automatic Saves | Selectable | 10–50,000 | 0.0625 | Cancellation | Instagram Auto Comments / Impressions / Saves / Reach | Instagram Auto Saves [Max: 50K] [Start Time: 1 Hour] [Speed: 50K/Day] |
| 1479 | jap:801 | Automatic Impressions | Selectable | 100–1,000,000 | 0.036 | — | Instagram Auto Comments / Impressions / Saves / Reach | Instagram Auto Impressions [Max: 100K] [Start Time: 1 Hour] [Speed: 100K/Day] |
| 1480 | jap:4425 | Bundles | Selectable | 10–1,000,000 | 0.27 | Cancellation | Instagram Auto Comments / Impressions / Saves / Reach | Instagram Auto Impressions + Reach + Profile Visits [Max: 1M] [Start Time: 0-1 Hour] [Speed: INSTANT] |
| 1481 | jap:355 | Automatic Impressions | Selectable | 100–1,000,000 | 0.10 | — | Instagram Auto Comments / Impressions / Saves / Reach | Instagram Auto Impressions [Max: 1M] [Start Time: 0-1 Hour] [Speed: 500K/Day] |
| 1482 | jap:618 | Automatic Impressions | Selectable | 100–10,000,000 | 0.10 | — | Instagram Auto Comments / Impressions / Saves / Reach | Instagram Auto Impressions [10M] [Speed: 1M / Day] [Start Time: Instant] |
| 1483 | jap:799 | Automatic Impressions | Selectable | 10–300,000 | 0.10 | — | Instagram Auto Comments / Impressions / Saves / Reach | Instagram Auto Impressions [Max: 100K] [Start Time: 1 Hour] [Speed: 20K/Day] |
| 1484 | jap:803 | Automatic Saves | Backup for 1477 | 10–150,000 | 0.0625 | Cancellation | Instagram Auto Comments / Impressions / Saves / Reach | Instagram Auto Saves [Max: 5K] [Start Time: 1 Hour] [Speed: 5K/Day] |
| 1485 | jap:804 | Automatic Saves | Selectable | 10–35,000 | 0.20 | — | Instagram Auto Comments / Impressions / Saves / Reach | Instagram Auto Saves [Max: 35K] [Start Time: 0-1 Hour] [Speed: 35K/Day] |
| 1486 | jap:802 | Automatic Comments | Selectable | 10–200,000 | 3.90 | — | Instagram Auto Comments / Impressions / Saves / Reach | Instagram Auto Comments [Positive EMOJI] [Refill: No Refill] [Max: 200K] [Start Time: 0 - 3 Hours] [Speed: 2K/Day] |
| 1487 | jap:867 | Automatic Reach | Selectable | 100–30,000 | 0.60 | — | Instagram Auto Comments / Impressions / Saves / Reach | Instagram Auto Photo Reach [Max: 30K] [Start Time: 0-1 Hour] [Speed: 30K/Day] |
| 1488 | jap:1007 | Automatic Comments | Selectable | 1,000–1,000 | 1.80 | — | Instagram Auto Comments / Impressions / Saves / Reach | Instagram Auto Power Comments [10K+ Followers] [Random 5 Comments] [EXPLORE PAGE] [Max: 5] [Speed: 1 Hour Delivery] |
| 1489 | jap:178 | Automatic Comments | Selectable | 1,000–1,000 | 1.80 | — | Instagram Auto Comments / Impressions / Saves / Reach | 🇸🇦Instagram Auto Power Comments [10K+ Followers] [Random ARABIC 5 Comments] [EXPLORE PAGE] [Max: 5] [Speed: 1 Hour Delivery] |
| 1490 | jap:981 | Automatic Comments | Selectable | 1,000–1,000 | 3.00 | — | Instagram Auto Comments / Impressions / Saves / Reach | Instagram Auto Power Comments [10K+ Followers] [Random 10 Comments] [EXPLORE PAGE] [Max: 10] [Speed: 1 Hour Delivery] |
| 1491 | jap:4411 | Automatic Comments | Selectable | 20–50,000 | 7.38 | — | Instagram Auto Comments / Impressions / Saves / Reach | Instagram Auto Comments [RANDOM] [90% MIDDLE EAST] [Refill: Lifetime] [Max: 5K] [Start Time: 6 Hours] [Speed: 2.5K/Day] ♻️ |
| 1492 | jap:230 | Automatic Comments | Selectable | 1,000–1,000 | 3.30 | — | Instagram Auto Comments / Impressions / Saves / Reach | 🇸🇦Instagram Power Comments [10K+ Followers] [Random ARABIC 10 Comments] [EXPLORE PAGE] [Max: 10] [Speed: 1 Hour Delivery] |
| 1493 | jap:6517 | Automatic Comments | Selectable | 1,000–1,000 | 6.00 | — | Instagram Auto Comments / Impressions / Saves / Reach | 🇸🇦Instagram Power Comments [10K+ Followers] [Random ARABIC 40 Comments] [EXPLORE PAGE] [Max: 40] [Speed: 1 Hour Delivery] |
| 1494 | jap:6819 | Automatic Comments | Selectable | 1,000–1,000 | 4.80 | — | Instagram Auto Comments / Impressions / Saves / Reach | Instagram Auto FEMALE Comments [Random 20 Comments] [Max: 20] [Start Time: 0-1 Hour] [Speed: 20/Hour] |
| 1495 | jap:5641 | Automatic Comments | Selectable | 1,000–1,000 | 6.00 | — | Instagram Auto Comments / Impressions / Saves / Reach | Instagram Auto FEMALE Comments [Random 40 Comments] [Max: 40] [Start Time: 0-1 Hour] [Speed: 40/Hour] |
| 1496 | jap:8405 | Automatic Comments | Selectable | 20–50,000 | 7.20 | — | Instagram Auto Comments / Impressions / Saves / Reach | Instagram Auto Random Comments [Emojis] [High quality ] [Refill: LIFETIME] [Max: 5K] [Start Time: 0-6 Hours] [Speed: 1K/Day] ♻️ |
| 1497 | jap:5726 | Automatic Comments | Selectable | 10–100,000 | 5.625 | Cancellation | Instagram Auto Comments / Impressions / Saves / Reach | Instagram Auto Comments [RANDOM] [Max: 75K] [Start Time: 0-1 Hour] [Speed: 10K/Day] |
| 1498 | jap:6311 | Automatic Comments | Selectable | 10–100,000 | 5.625 | Cancellation | Instagram Auto Comments / Impressions / Saves / Reach | Instagram Auto Emoji Comments [RANDOM] [Max: 100K] [Start Time: 0-1 Hour] [Speed: 10K/Day] |
| 1499 | jap:5640 | Automatic Comments | Selectable | 5–5,000 | 16.80 | — | Instagram Auto Comments / Impressions / Saves / Reach | Instagram Auto Comments [RANDOM] [NEVER DROP] [Max: 5K] [Start Time: 0-1 Hour] [Speed: INSTANT] |
| 1500 | jap:5734 | Automatic Comments | Selectable | 10–50 | 30.00 | — | Instagram Auto Comments / Impressions / Saves / Reach | Instagram Auto Comments [RANDOM] [90% ENGLISH] [NON DROP] [Max: 500] [Start Time: 0-1 Hour] [Speed: 2K/Day] |
| 1501 | jap:1711 | Automatic Comments | Selectable | 10–500 | 50.00 | — | Instagram Auto Comments / Impressions / Saves / Reach | Instagram Auto Comments [RANDOM] [MALE] [Max: 100] [Start Time: 1 Hour] [Speed: INSTANT] |
| 1502 | jap:1641 | Automatic Comments | Backup for 1501 | 10–500 | 50.00 | — | Instagram Auto Comments / Impressions / Saves / Reach | Instagram Auto Comments [FEMALE] [Max: 200] [Start Time: 1 Hour] [Speed: INSTANT] |
| 1503 | jap:5947 | Automatic Comments | Selectable | 5–2,500 | 251.20 | — | Instagram Auto Comments / Impressions / Saves / Reach | Instagram Auto Comments [NON DROP] [Max: 500] [Start Time: 0-1 Hour] [Speed: 24 Hours Delivery] |
| 1506 | jap:10118 | Automatic Shares and Reposts | Selectable | 10–100,000 | 9.875 | Cancellation | Instagram Auto Comments / Impressions / Saves / Reach | 🇺🇸 Instagram Auto REPOST [Max: 100K] [Start Time: 0 -1 Hr] [Speed: Up to 50K/D]💧⛔ |
| 1507 | jap:6002 | Automatic Comments | Selectable | 10–3,000 | 56.25 | Cancellation | Instagram Auto Comments / Impressions / Saves / Reach | 🇮🇹Instagram Auto Comments [ITALY - RANDOM] [NON DROP] [Max: 2.5K] [Start Time: 4 Hours] [Speed: 1K/Day] |
| 1508 | jap:6003 | Automatic Comments | Selectable | 1,000–1,000 | 7.20 | — | Instagram Auto Comments / Impressions / Saves / Reach | Instagram Auto FEMALE Comments [Random 80 Comments] [Max: 80] [Start Time: 0-1 Hour] [Speed: 1 Hour Delivery] |
| 1509 | jap:6118 | Others | Selectable | 10–100,000,000 | 0.0813 | Cancellation | Instagram Auto Comments / Impressions / Saves / Reach | Instagram Auto Impression [Tags] [Max: 10K] [Start Time: 0-1 Hour] [Speed: 10K/Day] |
| 1510 | jap:8470 | Automatic Shares and Reposts | Selectable | 10–5,000,000 | 0.0125 | Cancellation | Instagram Auto Comments / Impressions / Saves / Reach | Instagram Auto Shares [Max: 50K] [Start Time: 0 -1 Hr] [Speed: 20K/D] |
| 1511 | jap:9624 | Automatic Shares and Reposts | Selectable | 100–500,000 | 0.0375 | Cancellation | Instagram Auto Comments / Impressions / Saves / Reach | Instagram Auto Shares [Max: 500K] [Start Time: 0 - 24 Hrs] [Speed: Up to 20K/D]💧⛔ |
| 1512 | jap:6376 | Automatic Shares and Reposts | Selectable | 100–5,000,000 | 0.255 | — | Instagram Auto Comments / Impressions / Saves / Reach | Instagram Auto Shares [Max: 5M] [Start Time: 0 -1 Hr] [Speed: 5M/D] |
| 1513 | jap:6451 | Automatic Comments | Selectable | 5–1,000 | 171.60 | — | Instagram Auto Comments / Impressions / Saves / Reach | ⚠️🔥🎇🇺🇸🇪🇺 Instagram Auto Comments [RANDOM] USA / EUROPE [EXCLUSIVE - NON DROP] |
| 1514 | jap:6864 | Automatic Comments | Selectable | 20–50,000 | 7.50 | — | Instagram Auto Comments / Impressions / Saves / Reach | Instagram Auto Random Comments [Female] [High quality ] [Refill: LIFETIME] [Max: 5K] [Start Time: 0-6 Hours] [Speed: 1K/Day] ♻️ |
| 1515 | jap:7416 | Bundles | Selectable | 10–250,000 | 0.075 | Cancellation | Instagram Auto Comments / Impressions / Saves / Reach | Instagram Auto Reach + Impression [Max: 100K] [Start Time: 1 Hour] [Speed: 100K/Day] |
| 1516 | jap:10145 | Bundles | Backup for 1474 | 10–1,000,000 | 0.05 | Cancellation | Instagram Auto Comments / Impressions / Saves / Reach | Instagram Auto Reach + Impressions [Max: 300K] [Start Time: 0-1 Hour] [Speed: 100K/Day] |
| 1517 | jap:10144 | Bundles | Selectable | 10–1,000,000 | 0.0845 | Cancellation | Instagram Auto Comments / Impressions / Saves / Reach | Instagram Auto Reach + Impressions [Max: 5M] [Start Time: 0-1 Hour] [Speed: INSTANT] 💧 |
| 1518 | jap:7447 | Automatic Profile Visits | Selectable | 100–5,000,000 | 0.0816 | — | Instagram Auto Comments / Impressions / Saves / Reach | Instagram Auto Profile Visits [Max: 5M] [Start Time: 1 Hour] [Speed: 1M/Day] |
| 1519 | jap:6217 | Automatic Comments | Selectable | 50–2,500 | 65.00 | — | Instagram Auto Comments / Impressions / Saves / Reach | 🇳🇬 Instagram Auto Comments Nigeria [Max: 2K] [Start Time: 1 Hour] [Speed: 100/Day] |
| 1520 | jap:8471 | Automatic Comments | Selectable | 10–50,000 | 0.75 | Cancellation | Instagram Auto Comments / Impressions / Saves / Reach | Instagram Auto Comments [Random] [Refill: No] [Start Time: 0 - 1 Hour] [Speed: 5K/Day] |
| 1521 | jap:5922 | Automatic Comments | Selectable | 1–12 | 1125.00 | — | Instagram Auto Comments / Impressions / Saves / Reach | Instagram Auto Comments [from VERIFIED accounts] [Random - USA/EUROPE] [Max: 20] [Start Time: 0-12 Hours] [Speed: 24 Hours Delivery] |
| 1522 | jap:9055 | Automatic Comments | Selectable | 1,000–1,000 | 2.25 | — | Instagram Auto Comments / Impressions / Saves / Reach | Instagram Auto FEMALE Comments [10K+ Followers] [Random 20 Comments] [Max: 20] [Start Time: 0-1 Hour] [Speed: 1 Hour Delivery] |
| 1523 | jap:9056 | Automatic Comments | Selectable | 1,000–1,000 | 3.75 | — | Instagram Auto Comments / Impressions / Saves / Reach | Instagram Auto FEMALE Comments [10K+ Followers] [Random 40 Comments] [Max: 40] [Start Time: 0-1 Hour] [Speed: 1 Hour Delivery] |
| 1524 | jap:10119 | Others | Selectable | 1–20,000 | 18.75 | — | Instagram Auto Comments / Impressions / Saves / Reach | Instagram Auto Comments [AI Releveant] [Refill: No] [Max: 20K] [Start Time: 0 - 2 Hrs] [Speed: Up to 3K/D] |

## Approval

Static checks covered every matched row and all proposed fallback placements. Wait for approval before creating products/instagram-subscriptions.json.


## Approved implementation and verification

On 21 November 2026 the site owner approved both routing proposals. The [canonical Subscriptions draft](../../products/instagram-subscriptions.json) uses 1214 as the Automatic Likes preview default and requires a service choice under each of ten modes. All text, numeric and select fields have placeholders. The roadmap status remains `not_started` and there is no catalog mapping change.

Local DGP validation passed with zero diagnostics against all 165 candidates and the local strict fallback policy. All 149 selectable choices produced snapshots with exactly one primary and the approved bounds. The 16 backup IDs matched their 13 ordered lists. The checks confirmed numeric zero delay, positive integer entry checks, valid optional dates and post limits, and the required recurring field names. On the ten fixed-count routes, selecting the choice applies 1,000 to both limits. The ordering session clears those applied values on leaving the fixed route.

The snapshot includes optional inputs only when represented in form state. The host must omit blank values, enforce minimum and maximum together and against the selected service, and apply the recurring billing and retry contract. The local runtime's default pricing quantity is not a verified subscription billing rule. Builder membership, live acceptance and provider fulfillment remain unverified.
