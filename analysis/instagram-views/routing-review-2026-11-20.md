# Instagram Views routing review

2026-11-20 · Approved in the local Service Builder review

The approved definition accounts for **70 of 70** lab handlers. It has 15 unique primaries in the main tags, 47 unique primaries under Others, and eight fallback-only handlers. This revision retains the source-backed label for handler 739 and adds a speed-flexible Others choice with three ordered fallbacks. [Canonical ProductDefinition](../../products/instagram-views.json) · [Complete ID and placement tables](full-handler-routing-2026-11-19.md) · [Exact source rows](handler-inventory-2026-11-19.md#complete-handler-inventory)

## Corrected Video option

Use **Starts within 1 hour · 5M views/hour** for 739. Its provider name explicitly contains `[Start Time: 0-1 Hour] [Speed: 5M/Hour]`. The 19 November proposal incorrectly described its start as unspecified. The label in the saved JSON already reflects the source, so retain its existing option ID and wording.

## Additional backup route

Keep the existing Others choice **General views · Within 1 hour · 5M/day · Cancellation available, no drip feed**, with **750 → 747**. Add **General views · Within 1 hour · Delivery speed varies · Cancellation available, no drip feed**, with **750 → 747 → 746 → 749**. The arrows show the configured order under the same primary, and each alternate is compared with 750.

| Handler | Role in the new choice | Provider-listed start | Provider-listed speed | Raw rate |
| ---: | --- | --- | --- | ---: |
| 750 | Primary | 1 hour | 5M/day | 1.25 |
| 747 | First fallback | 0–1 hour | 5M/day | 1.225 |
| 746 | Second fallback | 1 hour | 10M/day | 1.2125 |
| 749 | Third fallback | 0–1 hour | Up to 2M/day | 1.25 |

747 is the closest match on speed. 746 preserves the one-hour start and has a higher listed pace. 749 has a lower listed pace and sits last. All four rows use `Default`, cover 100–2,147,483,647 and support cancellation. Only the primary's capabilities are offered on this choice, so drip feed stays hidden. The allowed local rate band for all three alternates is 1.1875–1.25. Keep the separate speed-specific options for 746 and 749. Both the new chain and the earlier generic chains rely on a common accepted link scope, which the generic names alone cannot establish.

## Default routes

I checked every in-scope row as a possible fallback against the structured type, bounds, capability and local rate rules for each tag default, then compared the provider's target and delivery wording.

| Tag | Default | Fallback decision |
| --- | --- | --- |
| Root and Video Post Views | 727 | 732 is the explicit All Videos match. Other numerical matches say All, generic Views, or IGTV. |
| Reel Views | 780 | 781 is the explicit Reel match. Other numerical matches say generic Views, All Videos, or IGTV. |
| Photo Post Views | 722 | Rows 707, 764 and 773 pass the numerical checks. Their wording is generic Views or IGTV, so none has evidence of photo delivery. |
| Priority Delivery | 728 | The numerical matches lack the explicit Emergency Video combination. The other confirmed Emergency All Videos row, 760, remains selectable at its own rate of 1.50 versus 0.2556 for 728. |
| Others | 715 | 714 matches generic wording, listed 500K/day, bounds and capabilities. Keep the explicit Others selection required. |

The reconciled export contains the same 65 mapped rows and five lab additions, with 20 relevant candidates whose lab membership remains unconfirmed. All 70 lab rows are enabled, unlocked, and `Default`. The 20 candidates and the adjacent subscription, bundle and other target exclusions are documented in the previous analysis. [Scope reconciliation](full-handler-routing-2026-11-19.md#source-and-scope)

## Coverage versus fallback availability

The definition has **65 selectable routes**, including the Photo tag itself and the added speed-flexible option. **10** have configured backups and **55** have a single handler. The other tag and root defaults are preview bindings outside this route count. The fallback lists are attached to the relevant tag and option nodes so a speed-specific choice can keep its own delivery terms. DGP Core resolves the ordered candidate list for a node. Actual retry behavior and fulfillment require site verification.

## Acceptance and verification

The canonical JSON matches the accepted local Builder seed. It retains the field placeholders, the search-enabled single-choice Others field, and the Drip feed description. The local Builder showed all 70 services and displayed the speed-flexible choice at a catalog rate of 1.25 per 1,000. The preview dropdown's search box lost keyboard focus during that check, so the choice was selected by scrolling.

The saved JSON passed the installed DGP Spec 1.6.0 schema and DGP Validation 1.2.1 with the exact 70-row lab registry, the Builder field capability snapshot, and the local 5% fallback rate policy. Ordering preview resolved all six default bindings and all 64 selector options to their intended primaries, with the expected quantity bounds for every option. DGP Core resolved **747 → 746 → 749** for the flexible choice and **747** for the fixed 5M/day choice. Live TygerBooster import, current policy, accepted link scopes and provider fulfillment remain unverified.
