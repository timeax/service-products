# Instagram Reach

21 November 2026 · Deployed lab review

Instagram → Reach → Instagram Reach. TygerBooster lab 234, service 234, initial draft 54. The user authorized construction and publication without a separate approval pause. The live lab defines the connected scope and the workspace map agrees exactly.

## Scope and source evidence

All listed handlers are enabled, unlocked, use JAP configuration 1, have null descriptions and no rate adjustments or markup. The deployed catalog synchronization reported 12:00:15 UTC on 21 November 2026. The local snapshot agrees on external ID, type, bounds, rate and capability flags. Root IDs are distinct from JAP external IDs. No attached row is excluded.

| Root ID | JAP external ID | Type | Structured range | Raw rate | Enabled capabilities | Raw category | Raw name |
| ---: | --- | --- | ---: | ---: | --- | --- | --- |
| 1145 | jap:7702 | Default | 10–1,000,000 | 0.0945 | cancel, dripfeed | Instagram Reach | Instagram Profile Reach [Max: 12K] [Start Time: 0 to 1 Hour] [Speed: 12K/Day] ⛔️💧 |
| 1147 | jap:866 | Default | 10–1,000,000 | 0.36 | cancel, dripfeed | Instagram Reach | Instagram Video Reach [Max: 30K] [Start Time: 0-1 Hour] [Speed: 30K/Day] 💧 |

1141–1144, 1146, 1148 and 1150 bundle impressions and are assigned to Impressions. 1149 includes profile visits and belongs to Profile Visits. The labels give the named daily pace and do not advertise the conflicting maxima.

[Roadmap](../../catalog.json) · [Catalog mapping](../../catalog-handler-service-ids.json) · [Local handler export](../../handler%20services.json)

## Routing

1145 and 1147 are separate direct choices because profile and video links differ and the rates do not fit the fallback band. Both have cancellation and drip feed. Both structured maxima are 1,000,000 while the names say 12K and 30K.

| Tag | Primary | Ordered backups |
| --- | ---: | --- |
| Profile Reach · 12K/day | 1145 | — |
| Profile Reach · Drip feed | 1145 | — |
| Video Reach · 30K/day | 1147 | — |
| Video Reach · Drip feed | 1147 | — |

## Builder and checkout

Required Instagram link and positive whole-number quantity. Structured bounds appear on the quantity field and deployed checkout enforces them. Drip-feed tags require runs and interval together. They bind both fields directly to the scheduled tag so checkout accepts the field set without a DGP trigger. Other tags omit both fields.

The installed local DGP contract is Spec 1.6.0 with the registered text/default and number/default scalar controls and generic placeholders. Production checkout accepts the handler on the selected tag and rejects snapshots with trigger IDs. The numeric ProductDefinition ID matches the deployed storefront service ID because checkout verifies that identity. Publication uses the deployed workspace service and the existing main branch revision.

[ProductDefinition](../../products/instagram-reach.json) · [Builder capabilities](../../.ai/service-builder-capabilities.json) · [JAP order inputs](../../.ai/JAP-SERVICE-TYPES.md)

## Deployed verification

Published version 1 through the deployed Service Lab workspace using its existing Root Account owner. The stored version, main commit and active storefront definition all match the saved JSON. Production checkout preparation accepted all 4 tag route(s) after publication. The checkout checks did not create orders, charge customers or call the provider. The checks exercised each primary. Live fallback execution and fulfillment remain outside this verification.

## Version 2 fulfillment correction

The deployed gateway sends the target and quantity, and drops runs and interval even when checkout receives them. Published and activated version 2 (ID 235) with standard delivery routes only. All handler placements and applicable fallback coverage are preserved. Deployed checkout preparation accepted all 2 remaining routes. The saved JSON matches the current live version. [JAP order fields](https://justanotherpanel.com/api)
