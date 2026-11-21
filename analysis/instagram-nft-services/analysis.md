# Instagram NFT Services

21 November 2026 · Deployed lab review

Instagram → NFT Services → Instagram NFT Services. TygerBooster lab 378, service 378, initial draft 198. The user authorized construction and publication without a separate approval pause. The live lab defines the connected scope and the workspace map agrees exactly.

## Scope and source evidence

All listed handlers are enabled, unlocked, use JAP configuration 1, have null descriptions and no rate adjustments or markup. The deployed catalog synchronization reported 12:00:15 UTC on 21 November 2026. The local snapshot agrees on external ID, type, bounds, rate and capability flags. Root IDs are distinct from JAP external IDs. No attached row is excluded.

| Root ID | JAP external ID | Type | Structured range | Raw rate | Enabled capabilities | Raw category | Raw name |
| ---: | --- | --- | ---: | ---: | --- | --- | --- |
| 113 | jap:7159 | Package | 10–1,000 | 106.25 | — | Instagram NFT Services | Instagram Followers [NFT Accounts] [500 Package] [Refill: No] [Start Time: 0 - 12 Hours] [Speed: 50 - 100] |
| 115 | jap:7161 | Package | 1–1 | 300.00 | — | Instagram NFT Services | Instagram Followers [NFT Accounts] [2-3K Package] [Refill: No] [Start Time: 0 - 12 Hours] [Speed: 50 - 100] |

112 and 114 are enabled in the archive and belong to the same raw NFT family, but are unconnected to this lab and are both Default routes. Row 114 is the 1K follower package by name. Keep both as local candidates without adding them to the deployed lab.

[Roadmap](../../catalog.json) · [Catalog mapping](../../catalog-handler-service-ids.json) · [Local handler export](../../handler%20services.json)

## Routing

113 and 115 are distinct link-only packages with different advertised follower counts and rates. Each has internal package quantity one per the JAP guide. Row 113 reports bounds 10–1,000, conflicting with quantity one. Checkout needs verified package quantity semantics before live publication. Changing the quantity would also change the computed customer price.

| Tag | Primary | Ordered backups |
| --- | ---: | --- |
| 500 Followers | 113 | — |
| 2K–3K Followers | 115 | — |

## Builder and checkout

Link only with one package as internal quantity. Checkout rejects quantity one for 113 under the current raw bounds.

The installed local DGP contract is Spec 1.6.0 with the registered text/default and number/default scalar controls and generic placeholders. Production checkout accepts the handler on the selected tag and rejects snapshots with trigger IDs. The numeric ProductDefinition ID matches the deployed storefront service ID because checkout verifies that identity. Publication uses the deployed workspace service and the existing main branch revision.

[ProductDefinition](../../products/instagram-nft-services.json) · [Builder capabilities](../../.ai/service-builder-capabilities.json) · [JAP order inputs](../../.ai/JAP-SERVICE-TYPES.md)

## Deployed verification

Saved and verified the complete JSON as the main-branch draft in deployed lab 378 / version 198. Local and deployed structural validators returned zero diagnostics. A rolled-back publication preflight accepted the 2K–3K package (115) and rejected the 500-follower package (113) because its structured minimum of 10 is above its single-package quantity of one. The service remains inactive. No active published lab tag establishes a production precedent for Package rows with a minimum over one. The deployed checkout prices using its accepted quantity, so changing that value without confirming the intended package behavior would change the computed charge. The main draft and both handler bindings were preserved.

## Package transport follow-up

The deployed gateway uses its generic order request for all selected services and always sends quantity. The local JAP guide specifies a link-only Package request. Both checkout and fulfillment planning apply the catalog quantity bounds and use quantity in per-thousand price calculations. This means changing handler 113's internal quantity from one to 10 also changes the submitted provider quantity and computed charge. The deployed draft stays inactive pending confirmation of package semantics. [JAP API](https://justanotherpanel.com/api)


## Direct JAP catalog recheck

On 21 November 2026, a read-only request through TygerBooster's configured JAP catalog driver returned Package service 7159 with minimum 10, maximum 1,000, and raw rate 106.25. It returned Package service 7161 with minimum and maximum one and raw rate 300.00. Neither response carried a description. Both match the deployed handler rows. This confirms the 7159 minimum originates in the provider catalog. The deployed sync replaces stored type, limits and rate with the provider values, so a local bounds override would be transient. The lab's version 198 remains a draft and the storefront entry remains inactive. No provider order request was made.


## Historical precedent check

A read-only deployed order query found no orders for the NFT Services storefront entry or with either attached handler selected in the saved snapshot. The registry archived before the 16 November import already labels JAP 7159 as Package with bounds 10–1,000 and rate 106.25. The same values appear in the current export and direct JAP response. The minimum is therefore not explained by a recent catalog change, and there is no deployed order precedent for the intended package quantity or charge. Lab 378, version 198 remains an inactive draft.
