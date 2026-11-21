# Instagram Engagement

21 November 2026 · Deployed lab review

Instagram → Engagement → Instagram Engagement. TygerBooster lab 232, service 232, initial draft 52. The user authorized construction and publication without a separate approval pause. The live lab defines the connected scope and the workspace map agrees exactly.

## Scope and source evidence

All listed handlers are enabled, unlocked, use JAP configuration 1, have null descriptions and no rate adjustments or markup. The deployed catalog synchronization reported 12:00:15 UTC on 21 November 2026. The local snapshot agrees on external ID, type, bounds, rate and capability flags. Root IDs are distinct from JAP external IDs. No attached row is excluded.

| Root ID | JAP external ID | Type | Structured range | Raw rate | Enabled capabilities | Raw category | Raw name |
| ---: | --- | --- | ---: | ---: | --- | --- | --- |
| 182 | jap:5958 | Default | 10–300,000 | 0.2063 | refill, cancel, dripfeed | Instagram Likes | Instagram Likes + Reach + Impressions [Auto-Refill: 30 Days] [300K] [MQ] [Start Time: Instant] [Speed: 20K/Day] ♻️💧⛔️ |
| 267 | jap:5959 | Default | 10–300,000 | 0.2063 | refill, cancel, dripfeed | Instagram Likes [BOTS] | Instagram Likes + Reach + Impressions [Auto-Refill: 30 Days] [300K] [MQ] [Start Time: Instant] [Speed: 20K/Day] 💧♻️⛔️ |
| 1151 | jap:7526 | Default | 100–100,000 | 0.425 | — | Instagram Engagement | Instagram Engagement + Shares [Max: 100K] [Start Time: INSTANT] [Speed: 100k/Hr] |

1154 adds reach and impressions and is assigned to Impressions. 1155 also adds profile visits and is assigned to Profile Visits. 998–1012 are country-and-tier packages assigned to Packages. The bundle’s precise meaning for 1151 and accepted URLs remain unverified.

[Roadmap](../../catalog.json) · [Catalog mapping](../../catalog-handler-service-ids.json) · [Local handler export](../../handler%20services.json)

## Routing

182 and 267 list the same likes, reach and impressions bundle with 30-day refill. Both cover 10–300,000 and have identical rates and enabled capabilities. The choices disclose that bot accounts may be used. 1151 lists engagement and shares and has a separate route, since its listed outcomes and capabilities differ.

| Tag | Primary | Ordered backups |
| --- | ---: | --- |
| Likes + Reach + Impressions | 182 | 267 |
| Likes + Reach + Impressions · Drip feed | 182 | 267 |
| Engagement + Shares | 1151 | — |

## Builder and checkout

Required Instagram link and positive whole-number quantity. Structured bounds appear on the quantity field and deployed checkout enforces them. Drip-feed tags require runs and interval together. They bind both fields directly to the scheduled tag so checkout accepts the field set without a DGP trigger. Other tags omit both fields.

The installed local DGP contract is Spec 1.6.0 with the registered text/default and number/default scalar controls and generic placeholders. Production checkout accepts the handler on the selected tag and rejects snapshots with trigger IDs. The numeric ProductDefinition ID matches the deployed storefront service ID because checkout verifies that identity. Publication uses the deployed workspace service and the existing main branch revision.

[ProductDefinition](../../products/instagram-engagement.json) · [Builder capabilities](../../.ai/service-builder-capabilities.json) · [JAP order inputs](../../.ai/JAP-SERVICE-TYPES.md)

## Deployed verification

Published version 1 through the deployed Service Lab workspace using its existing Root Account owner. The stored version, main commit and active storefront definition all match the saved JSON. Production checkout preparation accepted all 3 tag route(s) after publication. The checkout checks did not create orders, charge customers or call the provider. The checks exercised each primary. Live fallback execution and fulfillment remain outside this verification.

## Version 2 fulfillment correction

The deployed gateway sends the target and quantity, and drops runs and interval even when checkout receives them. Published and activated version 2 (ID 234) with standard delivery routes only. All handler placements and applicable fallback coverage are preserved. Deployed checkout preparation accepted all 2 remaining routes. The saved JSON matches the current live version. [JAP order fields](https://justanotherpanel.com/api)
