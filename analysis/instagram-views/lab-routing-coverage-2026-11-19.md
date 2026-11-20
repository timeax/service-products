# Instagram Views lab routing coverage

2026-11-19 · Revised routing proposal for review

The saved revision has 16 primary-binding nodes, 11 distinct primaries and two distinct fallback IDs. One fallback ID is also a primary. The union is 12 distinct handlers, leaving 58 of the last verified 70-handler lab catalog outside routing. All 70 resolve as enabled and unlocked in the 2026-11-18 export. This proposal reconciles each lab row to a routing pool, a distinct offering or a specific hold. The 20 additional raw candidates outside that lab remain documented in the full source inventory. [Definition](../../products/instagram-views.json) · [Source inventory](handler-inventory-2026-11-19.md) · [TygerBooster lab](https://tygerbooster.com/labs/226)

## Proposed routing disposition for every lab row

| Pool | Count | Root row IDs | Proposed handling |
| --- | ---: | --- | --- |
| Explicit All Videos, regular | 9 | 706, 708, 720, 727, 732, 737, 739, 748, 751 | Use 751 → 748 as a speed-flexible, full-range, drip-feed route with a start within one hour. Both explicitly say All Videos. Use 727 → 732 as the lower-rate cancellation route for 100–100M orders, with speed flexibility. Review 706, 708, 720, 737 and 739 as distinct delivery options or alternatives if their promises and the host policy permit. |
| Explicit Reel, regular | 4 | 780, 781, 786, 790 | Use 780 → 781 for general Reel orders with speed flexibility. Preserve 786's listed 0–3 hour / 1M-day option without drip feed, and 790's 100M/day option with a 1,000 minimum, only if single-handler options are acceptable. |
| Explicit photo | 1 | 722 | Single photo-only route. Confirm another photo route before promising backup coverage. |
| Explicit IGTV | 15 | 763, 764, 765, 767, 768, 769, 770, 771, 772, 773, 774, 775, 777, 778, 779 | Pending legacy URL checks. Speed-flexible pools: 771 → 770 and 774 → 772 for a start within one hour, and 773 → 764 for a start within six hours within the 100–100M primary range. The other nine rows are potential start, speed or capability choices. Two matching-speed pairs have rate gaps, detailed below. |
| Unqualified, 500K/day | 4 | 705, 714, 715, 729 | Confirm links. 715 → 714 fits the strict band and an at-most-one-hour start. 705 starts within an hour with drip feed. 729 provides a minimum of 50 and lacks drip feed, which may warrant a separate option. |
| Unqualified, 5M/day | 8 | 707, 718, 724, 731, 734, 747, 750, 752 | Confirm links. Test 747 against All Videos 748 for the same 0–1 hour / 5M-day option. Test 752 → 751 for Instant start / 5M-day. The others offer distinct starts, capabilities or costs. Compare 718 and 734 for the same nominal 0–1 hour / 5M-day offer once the rate policy and target are verified. |
| Unqualified, other stated speeds | 12 | 704, 710, 711, 713, 719, 730, 733, 738, 743, 746, 749, 756 | Confirm links, then pool by the start, output and capabilities the customer selects. The set includes low raw rates, hourly starts and high daily tiers, with distinct capability and range restrictions. 756's “Insatnt” wording requires confirmation for a start-specific option. |
| Unqualified, other or ambiguous delivery | 3 | 742, 753, 759 | Confirm links. 753 lists a 15-minute start and 5M/day. 742 and 759 say “Instant” under Speed, with a 0–1 hour start window. Keep their delivery labels literal until clarified. |
| All / All Links | 5 | 717, 726, 735, 741, 755 | Verify whether “All” covers video, Reels and photos. No distinct pair passes the strict rate, bounds and capability checks within this group. 726 and 755 both list 100K/day, but their rates and drip-feed support differ. |
| Emergency, explicit All Videos | 2 | 728, 760 | Review as a speed-flexible priority pool only if Emergency means the same thing. Both cover the same bounds and capabilities, but the local rate rule rejects the pair. Preserve 400K/day and 500K/day as distinct claims if shown. |
| Emergency, explicit Reel | 1 | 783 | Only Reel Emergency row in the 70. Review the external candidate 788 separately. It lists 500K/day, a higher rate, and its drip-feed flag is disabled. |
| Emergency, target to verify | 4 | 709, 712, 736, 740 | Confirm accepted links and meaning of priority. 709 and 740 both list 50K/day, with 0–1 hour and instant starts respectively. 712 and 736 both list 500K/day, with 0–3 hour and 0–1 hour starts. Both pairs have rate gaps under the local rule. |
| Hold for wording | 2 | 758, 761 | 758 says “AUTO ON / OFF” under an Emergency video label, with no resolved operational meaning. 761 uses “PRVT.” Hold both until link and ordering behavior are clear. |

The count is 70 unique IDs. In the groups above, 17 already have explicit non-legacy targets and ordinary or Emergency wording (nine regular All Videos, four regular Reel, one photo and three explicit Emergency). The remaining 53 have legacy target, generic target, broad-link, priority-target or wording questions. The counts are evidence levels, independent of fulfillment health.

## Where candidate redundancy is lost

The local Builder comparison uses the strict `lte_primary` 5% setting from source. Both existing routes and the proposed 751 → 748 route pass. On 751 → 748, 751 lists Instant and 748 lists 0–1 hour. Offer a start within one hour on this route. Both list 5M/day, but this review treats General delivery as speed-flexible. The saved Instant-start option can retain its single primary until a separate instant-compatible fallback is approved.

Some useful same-delivery pairs fall outside the local price band even though the cheaper row has full structured quantity and capability coverage. Examples are 770 → 768 (IGTV, 0–1 hour / 5M/day; 0.2313 → 0.125), 771 → 769 (IGTV, 0–1 hour / 1M/day; 0.2338 → 0.2063), and 734 → 718 (unqualified target, 0–1 hour / 5M/day; 0.25 → 0.2338). The last pair is 6.48% lower. Verify the live policy and accepted target scopes before treating these as implementable. Structuring a pool in the analysis does not modify a host policy.

The two proposed tiers of General Video use different raw rates and capability sets. Selecting 751 → 748 as the primary General Video route would enable drip feed and expand the quantity range, while 727 → 732 could remain a distinct lower-rate option with fewer features. Favor real backups on options that a customer can select. Keep speed- and priority-specific choices explicit about their delivery, and account for untested or single-handler choices in the launch decision.

Direct bindings, fallback references, and membership in the lab are separate counts. The live browser session was signed out when the prior inventory was refreshed. Current host policy, actual accepted URLs and live fulfillment remain open. This is a new binding proposal. ProductDefinition edits for these additional routes await approval.
