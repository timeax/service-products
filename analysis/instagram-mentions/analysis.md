# Instagram Mentions

20 November 2026 · Proposed routing for site-owner approval

The roadmap entry is Instagram → Mentions → Instagram Mentions (`instagram-mentions-mentions`). It is `not_started` and has no canonical ProductDefinition. The product orders mentions on destination Instagram media using an explicit audience source. I propose 19 selectable choices for all 20 mapped handlers, including eight under **Others** and one fallback-only row. Use **Custom List** as the starting mode, with an explicit delivery choice before submission.

## Source and coverage

The workspace map contains root row IDs 829–848. All 20 resolve in the 5,717-row root registry and are the complete set in its original `Instagram Mentions` category. The registry is a row array without embedded site or account identity. The analysis uses the local snapshot only. All 20 are enabled and unlocked with a null state reason, `dgp_handler_id: 1`, JAP panel key `jap`, last seen 2026-11-18 at 08:02:54 UTC with zero missing streak, zero markup and no rate adjustment. Refill, cancellation, drip feed and contract capability flags are false for all 20. External IDs are distinct from the root row IDs used by ProductDefinition bindings.

A full registry search by name, original category and payload type found no omitted Instagram Mentions handlers. Row **1102** (`jap:7577`) is the only adjacent Instagram match. It delivers Story Tag Taps with the `Default` payload type, a different outcome on a story. The wider scan matched X Mentions 3500–3507, Telegram Members 3988 and Google Visitors 4376 and 4378–4381. Those rows belong to their respective platforms and service families. No mapped row was stale, unavailable or locked.

[Roadmap](../../catalog.json) · [ID map](../../catalog-handler-service-ids.json) · [Registry](../../handler%20services.json)

## Customer choices and routing

Group on customer intent first. Custom List supplies the exact list, Account Followers uses an audience drawn from an account, Reels identifies an explicit destination, Hashtags uses one or multiple audience sources, and Post Likers uses a separate source post. Others preserves explicitly different sources, targeting or provider-listed formats. Offer one required choice per tag, with unique option IDs and one resolved primary. Delivery copy reflects listed estimates. The five-person and single-person qualifiers describe provider offerings with unresolved fulfillment details. They do not establish a limit of five or one entries in the input.

| Tag | Proposed choice | Primary | Ordered backups |
| --- | --- | ---: | --- |
| Custom List | 50K/day · starts within 24 hours | 830 | — |
| Custom List | 10K/day · starts within 24 hours · higher order limit | 831 | — |
| Custom List | 10K/day · starts within 24 hours | 834 | — |
| Account Followers | 50K/day · starts within 24 hours | 829 | — |
| Account Followers | Delivery pace varies · starts within 24 hours | 836 | 833 |
| Reels | Custom username list | 832 | — |
| Reels | Followers of an account | 835 | — |
| Hashtags | One hashtag | 837 | — |
| Hashtags | Multiple hashtags and usernames | 842 | — |
| Post Likers | 1K/day · starts in 24–72 hours | 838 | — |
| Post Likers | 5K/day · provider lists support for all post types | 839 | — |
| Others | Location audience | 840 | — |
| Others | Post commenters | 841 | — |
| Others | Female followers of an account | 843 | — |
| Others | Custom list · five-person format | 844 | — |
| Others | Account followers · five-person format | 845 | — |
| Others | Custom list · single-person format | 846 | — |
| Others | Account followers · provider lists 0–1 hour start | 847 | — |
| Others | Account followers · single-person format | 848 | — |

## Fallback decisions

The local Builder default is strict, priority-ordered and checks capability fit. The rate band is 95%–100% of the primary rate. An alternate must cover the primary's full structured range and match its payload type. I screened all ordered pairs, then compared target, audience and timing.

- **836 → 833.** Both use `Mentions User Followers` with generic account-follower wording. The backup's 100–1,000,000 covers the primary's 1,000–100,000. Its 3.125 rate is within the 3.0875–3.25 band, with identical capability flags. The choice allows up to 24 hours to start and leaves speed flexible to accommodate 833's slower start and different pace wording. 833 is fallback-only. Orders outside the primary's range work through the separate 829 choice at its own rate.
- **832 ↔ 834 and 835 → 833.** These meet the numerical screen. The generic rows lack evidence that they accept the same explicit Reel destination, and 832's longer start window differs from 834's. Keep each selectable. Reassess if the provider confirms shared targets and suitable delivery wording.
- **836 → 835.** This also passes the numerical screen. 835 explicitly targets Reels, whereas 836 is generic. Keep 835 on the Reel route.
- **841 → 839.** Both use `Mentions Media Likers` and have equal rates, but 841 explicitly targets commenters and 839 targets likers. Keep distinct choices. All other pairs fail the payload type, rates or bounds screen.

Attach the approved backup to the 836 choice through DGP `fallbacks.nodes`. Site-effective policy, link compatibility and provider retry behavior remain unverified.

## Complete handler inventory

The table records the original provider name, structured bounds and raw catalog rate. **12 of 20** rows advertise a name maximum that differs from the structured maximum. For example, the two Reel handlers say 5K and have a structured maximum of 500K. Row 841 says 1K and has structured bounds of 1K–5K. The structured values drive local service metadata, while the differing provider limits need verification before publication. The registry contains no handler descriptions that explain these differences. Do not use guarantee language from 847 in customer copy.

| Row | Provider external ID | JAP payload type | Structured min–max | Raw rate | Original provider name |
| ---: | --- | --- | ---: | ---: | --- |
| 829 | jap:6 | Mentions User Followers | 100–2,500,000 | 3.9125 | Instagram Mentions [USER FOLLOWERS] [Max: 250K] [Start Time: 0 - 24 Hour] [Speed: 50K/Day] |
| 830 | jap:493 | Mentions Custom List | 100–2,500,000 | 3.60 | Instagram Mentions [CUSTOM LIST] [Max: 250K] [Start Time: 0 - 24 Hour] [Speed: 50K/Day] |
| 831 | jap:6718 | Mentions Custom List | 100–1,000,000 | 3.125 | Instagram Mentions [CUSTOM LIST] [Max: 500K] [Refill: No] [Start Time: 0 - 24 Hours] [Speed: 10K/Day] |
| 832 | jap:6715 | Mentions Custom List | 100–500,000 | 2.875 | Instagram Mentions [for REELS] [CUSTOM LIST] [Max: 5K] [Refill: No] [Start Time: 24 - 48 Hours] [Speed: 1K/Day] |
| 833 | jap:6717 | Mentions User Followers | 100–1,000,000 | 3.125 | Instagram Mentions [USER FOLLOWERS] [Max: 100K] [Refill: No] [Start Time: 0 - 24 Hours] [Speed: 10K/Day] |
| 834 | jap:6716 | Mentions Custom List | 100–500,000 | 2.875 | Instagram Mentions [CUSTOM LIST] [Max: 100K] [Refill: No] [Start Time: 0 - 24 Hours] [Speed: 10K/Day] |
| 835 | jap:6714 | Mentions User Followers | 100–500,000 | 3.125 | Instagram Mentions [for REELS] [USER FOLLOWERS] [Max: 5K] [Refill: No] [Start Time: 0 - 24 Hours] [Speed: 1K/Day] |
| 836 | jap:7174 | Mentions User Followers | 1,000–100,000 | 3.25 | Instagram Mentions [User Followers] [Refill: No] [Max: 20K] [Start Time: 0-12 Hours] [Speed: 6-48 Hours to Complete] |
| 837 | jap:6719 | Mentions Hashtag | 100–10,000 | 5.625 | Instagram Mentions [HASHTAG] [Max: 10K] [Refill: No] [Start Time: 24 - 48 Hours] [Speed: 1K/Day] |
| 838 | jap:6720 | Mentions Media Likers | 100–1,000 | 5.625 | Instagram Mentions [MEDIA LIKERS] [Max: 1K] [Refill: No] [Start Time: 24 - 72 Hours] [Speed: 1K/Day] |
| 839 | jap:6721 | Mentions Media Likers | 500–500,000 | 6.25 | Instagram Mentions [MEDIA LIKERS - Works for ALL type of posts] [Max: 30K] [Refill: No] [Start Time: 24 - 72 Hours] [Speed: 5K/Day] |
| 840 | jap:6723 | Mentions User Followers | 100–10,000 | 8.75 | Instagram Mentions [LOCATION] [Max: 10K] [Refill: No] [Start Time: 12 - 72 Hours] [Speed: 1K/Day] |
| 841 | jap:6725 | Mentions Media Likers | 1,000–5,000 | 6.25 | Instagram Mentions [MEDIA COMMENTERS] [Max: 1K] [Refill: No] [Start Time: 24 - 72 Hours] [Speed: 5K/Day] |
| 842 | jap:6724 | Mentions with Hashtags | 500–100,000 | 12.50 | Instagram Mentions [MULTIPLE HASHTAGS] [Max: 100K] [Refill: No] [Start Time: 24 - 48 Hours] [Speed: 3K/Day] |
| 843 | jap:6726 | Mentions User Followers | 100–5,000 | 18.75 | Instagram Mentions [USER FEMALES&#039; FOLLOWERS] [Max: 5K] [Refill: No] [Start Time: 12 - 72 Hours] [Speed: 1K/Day] |
| 844 | jap:7191 | Mentions Custom List | 20–100,000 | 30.00 | Instagram Mentions [Custom List] [Five Persons] [Refill: No] [Start Time: 0-10 Hours] [Speed: 10-20K/Day] |
| 845 | jap:7189 | Mentions User Followers | 20–100,000 | 31.25 | Instagram Mentions [Five Persons] [Username] [Refill: No] [Max: 20K] [Start Time: 0-24 Hours] [Speed: 10K/Day] |
| 846 | jap:7190 | Mentions Custom List | 5–100,000 | 36.25 | Instagram Mentions [Custom List] [Single Person] [Refill: No] [Start Time: 0-10 Hours] [Speed: 10-20K/Day] |
| 847 | jap:6722 | Mentions User Followers | 100–5,000 | 25.00 | Instagram Mentions [SUPER] [Lifetime Guaranteed] [Max: 5K] [Start Time: 0-1 Hour] [Speed: 500-1K/Day] |
| 848 | jap:7188 | Mentions User Followers | 5–100,000 | 36.25 | Instagram Mentions [Single Person] [Username] [Refill: No] [Max: 20K] [Start Time: 0-24 Hours] [Speed: 10K/Day] |

## Builder fields and order contract

The installed consumer uses DGP Spec 1.6.0, Core 1.1.0, Validation 1.2.1 and Ordering 1.1.1. The capability snapshot registers `text/default`, `textarea/default`, and `number/default` as scalar controls and `select/default` as single-choice with options and search. Multiline inputs are scalar strings. Builder's generic `defaults.placeholder` property is available separately from the palette's variant-specific UI list. Keep the destination link common and reveal audience and quantity fields from the selected option. DGP Core supports including unbound fields through `includes_for_buttons` on an option trigger. Check preview and snapshot behavior on mixed-type tags, including required selectors and omission of stale fields after switching routes.

| JAP payload type | Required order fields | Customer inputs and placeholders |
| --- | --- | --- |
| All routes | `link` | Required scalar text, **Destination Instagram link**, “Paste the destination Instagram link”. The Reel choice identifies the destination as a Reel. |
| Mentions Custom List · 830–832, 834, 844, 846 | `usernames` in addition to link | Required textarea, “Enter one username per line”. Derive internal billable quantity from trimmed, non-empty lines using an evaluated base quantity rule. Send the newline-separated list. There is no separate JAP quantity input. |
| Mentions User Followers · 829, 833, 835, 836, 840, 843, 845, 847, 848 | `quantity`, `username` in addition to link | Required whole-number quantity, “Enter the number of mentions”, and source account text, “Paste the source Instagram profile URL”. This is the guide's default interpretation of `username`. Row 840 needs separate confirmation below. |
| Mentions Hashtag · 837 | `quantity`, `hashtag` in addition to link | Required quantity and scalar text, “Enter one hashtag”. Confirm accepted leading hash syntax before enforcing it. |
| Mentions with Hashtags · 842 | `quantity`, `usernames`, `hashtags` in addition to link | Required quantity and two textareas, “Enter one username per line” and “Enter one hashtag per line”. Use a newline-per-item authoring format. Quantity is entered explicitly for this route. |
| Mentions Media Likers · 838, 839, 841 | `quantity`, `media` in addition to link | Required quantity and a separate source-post text input, “Paste the source Instagram post link”. The 841 label describes commenters and keeps the same media key. |
| Mode delivery selector | Builder routing only | Required `select/default`, “Choose a delivery option” or “Choose an audience source”. Searchable Others selector. Do not submit routing metadata as JAP fields. |

Use structured service bounds for preview, and verify host-side enforcement for both explicit quantity and derived list length. DGP Ordering exposes catalog bounds but the prior local test showed that snapshot construction alone can accept out-of-range counts. For custom lists, the line count and actual submitted list must agree. The textarea can request one item per line. Test whitespace and blank-line handling in the host path before publication. No drip-feed controls are planned.

[Builder capability snapshot](../../.ai/service-builder-capabilities.json) · [JAP types](../../.ai/JAP-SERVICE-TYPES.md) · [Local contract index](../../.ai/agent-search.json)

## Open provider questions and verification

- **840 Location.** The row says Location while its type requires `username`. Keep the selectable placement under Others. Verify what value JAP expects in `username` for this route before finalizing its field wording or treating it as ready to order. The source provides no separate location key.
- **841 Post commenters.** The row's structured type takes `media`. Confirm accepted source-media formats and its listed order maximum. The same key serves different audience choices.
- **844, 845, 846 and 848.** Confirm what the single-person and five-person labels describe. The structured ranges start at 5 or 20, and the JAP types still use a list or one source account respectively. These labels alone do not establish exact input cardinality.
- Confirm generic destinations, accepted profile URL or handle shape, and provider limits for the rows with conflicting maximums. Use the explicit Reel routes until wider support is understood.

The static review reconciled the exact 20 mapped IDs and the omitted-candidate scan, and screened all fallback pairs. Builder validation and provider fulfillment checks have not run. This proposal is awaiting approval before creating `products/instagram-mentions.json`.


## Approved implementation and verification

On 20 November 2026 the site owner approved the proposed routing and creation of the [canonical ProductDefinition](../../products/instagram-mentions.json). Custom List is the starting tag. Each tag requires a route choice before submission. The catalog status remains `not_started`.

- Local DGP validation reported zero structural and semantic diagnostics against the installed contract, the 20 mapped registry rows, the Builder field capability snapshot and the local strict 5% fallback rate band. DGP Core resolved the single approved fallback, 836 → 833.
- Local ordering tests passed all 19 choices across five payload types. Each choice selects one primary and submits only its required JAP field keys, even with stale values from another choice. All 13 controls have placeholders.
- A shared usernames textarea supports custom lists and the multiple-hashtag choice. Custom lists derive quantity from username lines. The multi-hashtag choice requires a separate numeric quantity, which takes precedence over the shared list. Lists accept one item per line, with blank lines, whitespace within entries and comma or semicolon separators rejected so the submitted list and derived count agree.
- The shared `username` field uses neutral wording for Location and explains the profile URL expected for account-follower choices. The correct value for 840 remains unverified.
- Builder UI validation, site-side range enforcement and live provider fulfillment were not run. The provider questions above remain open.


### Username chips

The shared usernames field now uses the registered `chips/default` control. Enter commits one username per chip. Custom List quantity is the number of chips. The multiple-hashtag route still requires an explicit quantity.

DGP Ordering writes the chip values to the `usernames` snapshot field as an array. JAP expects newline-separated text, so the host's JAP adapter must join those entries with newlines. That host conversion remains unverified. Local DGP validation reported zero diagnostics, and focused ordering checks passed for all seven routes that use the field, including rejection of malformed entries.

The multiple-hashtag route now uses chips with textarea mode for both usernames and hashtags. The focused local ordering check verified both arrays and the explicit quantity. The single-hashtag route uses a text field for its single value.
