# Instagram Highlights

21 November 2026 · Deployed lab review

Instagram → Highlights → Instagram Highlights. TygerBooster lab 396, service 396, initial draft 216. The user authorized construction and publication without a separate approval pause. The live lab defines the connected scope and the workspace map agrees exactly.

## Scope and source evidence

All listed handlers are enabled, unlocked, use JAP configuration 1, have null descriptions and no rate adjustments or markup. The deployed catalog synchronization reported 12:00:15 UTC on 21 November 2026. The local snapshot agrees on external ID, type, bounds, rate and capability flags. Root IDs are distinct from JAP external IDs. No attached row is excluded.

| Root ID | JAP external ID | Type | Structured range | Raw rate | Enabled capabilities | Raw category | Raw name |
| ---: | --- | --- | ---: | ---: | --- | --- | --- |
| 1169 | jap:732 | Default | 20–300,000 | 1.00 | — | Instagram Profile Visits / Highlights / Shares | Instagram Highlights Views [Max: 300K] [Start Time: 0-1 Hour] [Speed: 100K/Day] |

Rows 1158–1168 and 1170–1179 in the compound source category are shares, reposts or profile visits. No other connected Highlight Views row is present.

[Roadmap](../../catalog.json) · [Catalog mapping](../../catalog-handler-service-ids.json) · [Local handler export](../../handler%20services.json)

## Routing

1169 is the only connected highlight-view handler, with 20–300,000 bounds and no enabled flags. Its category also contains Shares and Profile Visits, which are separate outcomes.

| Tag | Primary | Ordered backups |
| --- | ---: | --- |
| Highlight Views | 1169 | — |

## Builder and checkout

Required Instagram link and positive whole-number quantity. Structured bounds appear on the quantity field and deployed checkout enforces them.

The installed local DGP contract is Spec 1.6.0 with the registered text/default and number/default scalar controls and generic placeholders. Production checkout accepts the handler on the selected tag and rejects snapshots with trigger IDs. The numeric ProductDefinition ID matches the deployed storefront service ID because checkout verifies that identity. Publication uses the deployed workspace service and the existing main branch revision.

[ProductDefinition](../../products/instagram-highlights.json) · [Builder capabilities](../../.ai/service-builder-capabilities.json) · [JAP order inputs](../../.ai/JAP-SERVICE-TYPES.md)

## Deployed verification

Published version 1 through the deployed Service Lab workspace using its existing Root Account owner. The stored version, main commit and active storefront definition all match the saved JSON. Production checkout preparation accepted all 1 tag route(s) after publication. The checkout checks did not create orders, charge customers or call the provider. The checks exercised each primary. Live fallback execution and fulfillment remain outside this verification.
