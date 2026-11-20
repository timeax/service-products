# Instagram Views routing reanalysis

2026-11-19 · Proposed routing changes for review

The saved ProductDefinition has five tag defaults and nine option bindings. Repeated handler IDs reduce those 14 references to **10 distinct primary handlers**. Its fallback configuration is null. The previously verified lab catalog contained **70** handlers (65 mapped plus five Reel rows), so **60** had no routing role. The previous implementation validated the approved preview's bindings and left the rest of the inventory without a routing disposition. This report fills that gap at the analysis level. [ProductDefinition](../../products/instagram-views.json) · [Lab](https://tygerbooster.com/labs/226)

## Sources and reconciliation

The 2026-11-18 handler export has 5,717 rows. All 70 IDs from the last verified lab catalog resolve in it. They are enabled and unlocked, have `payload.type: Default`, and were last seen at 08:02:54 UTC. The live lab catalog and active fallback policy could not be refreshed in this review because the available TygerBooster browser session was signed out. IDs below are root row IDs. Each row's `dgp_handler_id` is the handler configuration, and `external_id` identifies the separate JAP service. [Handler registry](../../handler%20services.json) · [Catalog ID map](../../catalog-handler-service-ids.json)

| Role in reviewed inventory | Count | Root row IDs or treatment |
| --- | ---: | --- |
| Primary | 10 | 706, 722, 728, 739, 751, 780, 781, 783, 786, 790 |
| Unbound with All Videos wording | 6 | 708, 720, 727, 732, 737, 748. Review for delivery choices and generic video pools. |
| Unbound with generic target wording | 27 | 704, 705, 707, 710, 711, 713, 714, 715, 718, 719, 724, 729, 730, 731, 733, 734, 738, 742, 743, 746, 747, 749, 750, 752, 753, 756, 759. Confirm accepted URLs before cross-routing. |
| Unbound with broad-link wording | 5 | 717, 726, 735, 741, 755. Confirm what “All” and “All Links” cover for each target. |
| Unbound Emergency rows | 6 | 709, 712, 736, 740, 758, 760. Review advertised start and speed as separate characteristics. Hold the row with undefined “Auto On / Off” wording. |
| Ambiguous private-video row | 1 | 761. “PRVT” needs clarification before routing. |
| Unbound legacy IGTV | 15 | 763, 764, 765, 767, 768, 769, 770, 771, 772, 773, 774, 775, 777, 778, 779. Confirm current accepted URLs before enabling a standalone tag or alternate route. |

The updated registry scan confirms the same 25 additional one-time media candidates outside the 65-row map. Five are already in the 70-row baseline: 780, 781, 783, 786 and 790. The remaining 20 are 716, 725, 744, 754, 757, 762, 766, 782, 784, 785, 787, 788, 789, 791, 793, 795, 796, 799, 800 and 801. These are potential extensions, subject to scope and lab membership. Story, Highlights, profile traffic, subscriptions and bundled outcomes remain outside this proposal. [Initial source and scope reconciliation](analysis.md)

## Why the existing options have no fallback

The preview began with a small set of primary choices. Its original generic Reel alternative was removed when 780 and 781 were exposed as separate 5M/day and 500K/day options. That decision preserved the chosen delivery wording. It left the generic tags, other speed tiers, and remaining 60 lab rows without a completed routing pass.

The checked local Builder default is strict `lte_primary` at 5%. A fallback's raw rate must be at most the primary's rate and at least 95% of it. For this review I also required a full match or superset of the primary's structured quantity range and enabled capabilities. These mechanical checks still leave target and delivery requirements to review.

| Existing primary | Candidates passing rate, range and capability checks within the 70 | Reason to hold |
| ---: | --- | --- |
| 706 | None | Its 0.0062 rate and full payload range leave no eligible candidate on these checks. |
| 722 | 707, 764, 773 | The available evidence establishes a photo target only for 722. |
| 728 | 726, 732, 734, 772, 774 | These rows lack the same Emergency video delivery description. |
| 739 | 740 | 740 lists Emergency, instant start and 50K/day. 739 lists 5M/hour. |
| 751 | 746, 747, 748, 749 | These alternatives list a one-hour start or window. 751 lists Instant start. |
| 780 | 705, 706, 763, 781 | 781 explicitly targets Reels and lists 500K/day. Keep it outside the 5M/day option. Confirm the other rows' target descriptions. |
| 781 | 705, 706, 763, 780 | 780 explicitly targets Reels and lists 5M/day. It fits a generic Reel choice if the higher speed is acceptable. |
| 783 | 708 | 708 says All Videos and lists 1M/day. 783 says Emergency Reel and lists 5M/day. |
| 786 | 712, 735 | Their broad-link descriptions and delivery differ. 782 is an explicit Reel row with 1M/day outside the lab baseline, but its 0.01 rate falls below the local band for 786 at 0.20. |
| 790 | 717, 718, 770, 771 | These have differing target or delivery descriptions and none lists 100M/day. |

## Proposed expansion

Use a distinct generic delivery choice for customers who are flexible about speed, alongside options that explicitly select a provider-listed speed. Put fallbacks on the option that actually receives the binding as well as on applicable tag defaults. The current delivery fields are required, so adding only a tag-default fallback would leave the selected options without backup routes.

| Proposed candidate | Evidence and condition |
| --- | --- |
| **General Reel delivery** `780 → 781` | Both are explicitly Reel, start in 0–1 hour by name, have rate 0.0063, cover 100–2,147,483,647, and support cancellation and drip feed. The generic option would omit the 5M/day and 500K/day commitments. Keep each existing speed-specific choice if it remains useful. |
| **Video, up to a one-hour start window and 500K/day** `715 → 714` | Both list 500K/day with compatible start wording for that window. Both cover 100–2,147,483,647 with the same capabilities. Rates 0.2088 → 0.2063 pass. Confirm the same video URL scope for these generic provider names. |
| **Video, 0–1 hour and 5M/day** `748 → 747` | Same listed start and speed, full range and the same capabilities. Rates 1.23 → 1.225 pass. 748 explicitly says All Videos. Verify that 747 accepts the same links. |
| **Video, Instant start and 5M/day** `752 → 751` | Same listed start and rate of delivery, bounds and capabilities. Rates 1.30 → 1.26 pass. This would change the primary. Verify 752 accepts the same video URLs, then compare against keeping 751 as the sole lower-rate primary. The reverse chain fails the current rate ceiling. |
| **General legacy IGTV delivery** `771 → 770` | Both explicitly say IGTV and list a 0–1 hour start. Bounds and capabilities match. Rates 0.2338 → 0.2313 pass. Delivery figures differ, so leave speed unspecific in this choice. Hold until current IGTV URL acceptance is established. |

For deliberate new options, review explicit All Videos row 720 (0–1 hour, 10M/day), Emergency video row 760 (0–1 hour, 500K/day), and the Reel candidates 782, 793 and 800 if expanding the connected catalog. The last three advertise distinct speeds or start windows. Keep Photo Post Views on 722 pending a second photo-only route. Shared JAP configuration offers no evidence of independent outage coverage.

Keep the existing fields: target-specific `select/default` options, required `text/default` link, `number/default` quantity based on the payload, and capability-gated `toggle/default` drip feed with Runs and Interval. The structured payload governs quantity and capability, including when names and icons disagree. The local ProductDefinition contract supports fallback references on tags and options. Host retry behavior and accepted URL equivalence remain to be verified before any routing change. Builder validation of the proposed changes has not run. [Builder capabilities](../../.ai/service-builder-capabilities.json) · [JAP input guide](../../.ai/JAP-SERVICE-TYPES.md)
