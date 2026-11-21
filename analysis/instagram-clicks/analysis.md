# Instagram Clicks

21 November 2026 · Deployed lab review

Instagram → Clicks → Instagram Clicks. TygerBooster lab 239, service 239, initial draft 59. The user authorized construction and publication without a separate approval pause. The live lab defines the connected scope and the workspace map agrees exactly.

## Scope and source evidence

All listed handlers are enabled, unlocked, use JAP configuration 1, have null descriptions and no rate adjustments or markup. The deployed catalog synchronization reported 12:00:15 UTC on 21 November 2026. The local snapshot agrees on external ID, type, bounds, rate and capability flags. Root IDs are distinct from JAP external IDs. No attached row is excluded.

| Root ID | JAP external ID | Type | Structured range | Raw rate | Enabled capabilities | Raw category | Raw name |
| ---: | --- | --- | ---: | ---: | --- | --- | --- |
| 1094 | jap:8465 | Default | 100–1,000 | 0.9375 | dripfeed | Instagram Story | Instagram Story Link Click [Start Time: 0 - 1 Hour] [Speed: 1K/Day] |

1100 is Story Sticker Link Press and 1102 is Story Tag Taps. Both are distinct unconnected interaction types. 1099 is Swipe Up, also unconnected. None is used as a substitute.

[Roadmap](../../catalog.json) · [Catalog mapping](../../catalog-handler-service-ids.json) · [Local handler export](../../handler%20services.json)

## Routing

1094 is the one connected Story Link Click handler, with bounds 100–1,000 and drip feed. The form collects the Instagram story target and quantity.

| Tag | Primary | Ordered backups |
| --- | ---: | --- |
| Story Link Clicks | 1094 | — |
| Story Link Clicks · Drip feed | 1094 | — |

## Builder and checkout

Required Instagram link and positive whole-number quantity. Structured bounds appear on the quantity field and deployed checkout enforces them. Drip-feed tags require runs and interval together. They bind both fields directly to the scheduled tag so checkout accepts the field set without a DGP trigger. Other tags omit both fields.

The installed local DGP contract is Spec 1.6.0 with the registered text/default and number/default scalar controls and generic placeholders. Production checkout accepts the handler on the selected tag and rejects snapshots with trigger IDs. The numeric ProductDefinition ID matches the deployed storefront service ID because checkout verifies that identity. Publication uses the deployed workspace service and the existing main branch revision.

[ProductDefinition](../../products/instagram-clicks.json) · [Builder capabilities](../../.ai/service-builder-capabilities.json) · [JAP order inputs](../../.ai/JAP-SERVICE-TYPES.md)

## Deployed verification

Published version 1 through the deployed Service Lab workspace using its existing Root Account owner. The stored version, main commit and active storefront definition all match the saved JSON. Production checkout preparation accepted all 2 tag route(s) after publication. The checkout checks did not create orders, charge customers or call the provider. The checks exercised each primary. Live fallback execution and fulfillment remain outside this verification.

## Version 2 fulfillment correction

The deployed gateway sends the target and quantity, and drops runs and interval even when checkout receives them. Published and activated version 2 (ID 237) with standard delivery routes only. All handler placements and applicable fallback coverage are preserved. Deployed checkout preparation accepted all 1 remaining routes. The saved JSON matches the current live version. [JAP order fields](https://justanotherpanel.com/api)
