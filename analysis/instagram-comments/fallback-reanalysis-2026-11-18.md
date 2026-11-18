# Instagram Comments — option and fallback reanalysis (2026-11-18)

The implementation keeps meaningful options and merges clear duplicates where they repeat within a selector. The Comments definition now has 15 option fallback lists and five tag fallback lists, using 15 distinct alternate handlers. The approved proposals below include additional partial-coverage candidates that remain under review. The implemented chains preserve the primary's full quantity range and supported capabilities. The old root 895 → 871 route was removed because 871 cannot cover orders above 50,000. Three fixed-quantity duplicate rows (982, 986, 987) remain in the mapped registry and conflict metadata after their redundant options were removed.

## 2. Analyze and normalize variants

The current mapping contains 233 unique rows, all resolved in the supplied registry and all marked enabled and unlocked. It uses root handler IDs and one JAP provider panel. The bare export gives no tenant identity. The working assumption is that 50–80% of rows may fail at fulfillment time. That is a planning assumption, and alternatives within one panel can fail together.

Comments has 390 option bindings across 34 service selectors for 228 distinct option handlers, plus 52 tag bindings. Every mapped ID is represented. There are 56 repeated label groups within individual selectors. The current fallback map has five tag lists, six entries counting reuse, five distinct alternate IDs and zero option lists.

Instagram Likes provides the pattern to follow. Its current definition has one tag fallback list and nine option fallback lists. The broad tag chooses a default, a customer option chooses a specific outcome, and its extra compatible rows sit behind that selection. The historical Likes example provides the methodology. All IDs here come from the Comments mapping.

Keep the approved tag tree and leaf selectors. Within each selector, show the actual distinction once. A service may support several browsing paths where the choices mean the same thing. The 162 option bindings above the distinct option-handler count are repeated placements across selectors, so they should be reviewed separately from the repeated labels. Restore qualifiers omitted by previous copy, such as region, language, tone, exact package size or account audience. Only offer delivery as a choice where the wording is deliberately part of what the customer selects. Keep ordinary provider speed differences as routing details.

## 3. Choose primary handlers and fallbacks

### What a fallback can relax

The primary represents the preferred delivery. Use a close substitute first, then allow a broader backup where the tag or option makes that acceptable. Decide this per choice. A broad Comments tag can absorb more variation than a choice that explicitly requests a country, tone, account type, or delivery rate. If a selected attribute is a preference, describe that flexibility before the customer orders.

Every attempt still needs to accept the submitted inputs, fulfill the same order type and target, and support the requested quantity and enabled controls. A Custom Comments order must keep the customer’s text. A Live link stays with Live handlers. Drip feed, when selected, remains required for that order. Provider speed estimates and unused capabilities can vary when the choice does not promise them.

| Choice | Close replacement or broader backup to review |
| --- | --- |
| General random comments | Prefer 871 after 895. Allow 868 as a later backup when drip feed is off and the order is within 10–50,000. |
| General Russia comments | Review 891 → 921 where the order is 10–250 and retention wording is outside the promise. An explicitly positive or neutral selection needs its own compatible route or clearly stated permission to relax tone. |
| General random comments with a preferred tier | Review 869 → 895 or 871 when HQ is a preference and the order fits the backup bounds and capabilities. An explicitly HQ-only choice retains that requirement. |
| General custom comments | Try handlers with different speed estimates if they can post the same supplied text within the order bounds. A delivery-specific option needs its own chain. |

The 13 pools below cover the original review. The Russia and HQ examples expand the review to broader backups and are outside the 24 counted slots. Confirm the retry rules and customer-facing wording before encoding those examples.

The first pass identifies **13 service pools with 24 alternate slots**, counting each proposed pool once and including the existing alternates where they fit. These are review candidates. Some need an order-level eligibility check before they can be encoded, and the listed ordering is provisional. Under a tag, keep its default and add compatible fallback IDs to that node. On each surviving option, attach the corresponding ordered list to its option ID. Reuse a full-service chain only where the same promise holds in every context. A deliberate delivery choice needs a separate compatibility check.

| Customer choice | Proposed primary → candidates | Eligibility and decision |
| --- | --- | --- |
| Random comments | 895 → 871, 868 | 895 is the current root. Try 871 from 10–50,000. Try 868 only when drip feed is off and within 10–50,000. Keep 868 as the existing Standard tag primary if that path should continue to start without drip feed. |
| Random Live comments | 1044 → 1048 | Same target, delivery wording, bounds (50–2,000) and capabilities. Keep targeted Live choices 1045 and 1046 separate. |
| Random comments from verified accounts | 993 → 994 | Same 1–16 range. Merge under the general verified choice. Keep the different delivery wording out of the shared label. |
| Plain custom comments | 862 → 860, 861, 873, 863, 896 | 862 covers 1–50,000. Order candidates by eligible bounds and rate policy. 861 and 873 share 50–50,000 and the same rate. 896 extends coverage to 100,000 and applies from 20. All have refill disabled. |
| AI-relevant comments | 864 → 865 | Same source style and drip feed. 865 only through 2,000 and costs more. |
| Positive emoji | 856 → 858 | Same tone and drip feed. Fallback overlap 10–20,000. 858 alone covers 5–9. |
| Negative emoji | 857 → 859 | Same tone and drip feed. 859 only through 20,000. |
| Random emoji | 897 → 872 | Generic emoji wording and matching enabled capabilities. 872 only through 50,000. Keep explicitly HQ and positive/negative choices separate. |
| Random comments from female accounts | 889 → 917 | Same targeting and drip feed. Overlap 10–200. 917 extends to 500 and costs more. |
| USA comments | 1337 → 911, 880, 57, 1359 | Same country and Default shape. Use payload ranges 5–500, 10–500, 5–300, 5–150 and 5–50 respectively. Special USA audience 101 stays separate. |
| USA custom comments | 1338 → 924, 881, 56 | Same country and Custom Comments shape. Ranges 5–500, 10–500, 5–300 and 5–150. Special USA audience 100 stays separate. |
| India comments | 894 → 919, 907 | Only if the general India promise covers all three. 919 overlaps at 10–250 and lacks cancel. 907 overlaps at 5–20 and lacks cancel and drip feed. |
| Brazil custom comments | 908 → 934 | 934 overlaps at 10–250 and lacks cancel. Both support the general Brazil post choice if link scope matches. Exclude the explicitly gendered or multi-target rows from the generic pool until their scopes are reviewed. |

The current Core resolver returns the ordered node and service-level IDs and removes duplicates. Its eligibility helper checks state and can check filter capabilities and rate policy. Those paths by themselves do not check the ordered quantity or the actual order inputs. Before wiring bounds-dependent candidates, establish that the retry path checks payload type, target, requested quantity, selected drip feed and other required capabilities, and allowed cost. For example, the existing root chain 895 → 871 needs a 50,000 ceiling on the retry. If that eligibility check is unavailable, use only context-safe chains after rate review and leave partial-coverage candidates documented. Prioritize live results and policy-compliant rates once they are available. All rows use JAP, so multiple IDs represent more retry routes within that panel.

### Held because the payload and name disagree

The 74 Default rows with payload min=max=1,000 normalize to 46 source-described choices. **25 of those choices account for 28 additional alternate slots on paper**. They stay out of the proposed live chains until the provider contract explains why the payload requires 1,000 while the name commonly advertises a much smaller count. Same source wording and bounds are evidence of duplicate choices, and do not establish that the payload can deliver the advertised count. The remaining 21 rows in this bucket have no matching peer under this comparison.

| Source-described choice | Matching root handler IDs |
| --- | --- |
| instagram power comments [10k+ followers] [south korea] [random 20 comments] [explore page] | 33, 975, 1427 |
| instagram power comments [10k+ followers] [br] [random 20 comments] [explore page] | 34, 971, 1376 |
| instagram power comments [10k+ followers] [ww] [random 20 comments] [explore page] | 35, 958 |
| instagram power comments [10k+ followers] [ww] [random 80 comments] [explore page] | 36, 960 |
| instagram power comments [10k+ followers] [ww] [random 200 comments] [explore page] | 37, 962 |
| / usa - uk instagram power comments [10k+ followers] [random 20 comments] [explore page] | 38, 965, 1327 |
| / usa - uk instagram power comments [10k+ followers] [random 40 comments] [explore page] | 39, 966 |
| / usa - uk instagram power comments [10k+ followers] [random 100 comments] [explore page] | 40, 968 |
| instagram power comments [10k+ followers] [random arabic 20 comments] [explore page] | 41, 979 |
| instagram power comments [10k+ followers] [random 20 comments] [explore page] | 42, 985 |
| instagram power comments [10k+ followers] [random 5 comments] [explore page] | 882, 983 |
| instagram power comments [10k+ followers] [random 10 comments] [explore page] | 883, 984 |
| instagram power comments [10k+ followers] [random arabic 5 comments] [explore page] | 887, 977 |
| instagram power comments [10k+ followers] [random arabic 10 comments] [explore page] | 888, 978 |
| instagram female comments [10k+ followers] [random 20 comments] | 953, 986 |
| instagram female comments [10k+ followers] [random 40 comments] | 954, 987 |
| / usa - uk instagram power comments [10k+ followers] [random 5 comments] [explore page] | 963, 1325 |
| / usa - uk instagram power comments [10k+ followers] [random 10 comments] [explore page] | 964, 1326 |
| instagram power comments [10k+ followers] [br] [random 5 comments] [explore page] | 969, 1373 |
| instagram power comments [10k+ followers] [br] [random 10 comments] [explore page] | 970, 1374 |
| instagram power comments [10k+ followers] [br] [random 40 comments] [explore page] | 972, 1377 |
| instagram power comments [10k+ followers] [south korea] [random 5 comments] [explore page] | 973, 1425 |
| instagram power comments [10k+ followers] [south korea] [random 10 comments] [explore page] | 974, 1426 |
| instagram power comments [10k+ followers] [south korea] [random 40 comments] [explore page] | 976, 1428 |
| instagram power comments [10k+ followers] [random arabic 80 comments] [explore page] | 981, 982 |

### Repeated labels that still need distinct choices

- “Random” in the Standard selector includes general, HQ, English, Hispanic and Russian rows. Plain random rows 868/871/895 form a pool. Premium, retention wording and targeted rows keep their own meaning.
- “Russia” includes random, positive and neutral variants (891–893). “Arab/Gulf” 988/990 hides random text versus emoji. “USA” 56/100 or 57/101 hides general versus a named audience. Preserve the source qualifier with appropriate customer copy.
- “20 comments” can hide Brazil, worldwide or unspecified targeting. “10K+ followers” 991/992 hides the stated 5 versus 10 custom comments and both payloads allow 1–40. Keep these separate for review. Restore the explicit geography on Power choices, and keep South Korea, Brazil and worldwide separate.
- Equal delivery wording is insufficient. Positive versus negative emoji, male versus female targeting, and languages still differ. Do not attach the general fallback pool to a choice that promises specific speed or delivery timing.
- Keep fixed package counts distinct. The mapped Poll (936), Reply (943), and Auto rows (1504/1505) have no confirmed like-for-like alternates. Keep each provider input shape and root field visibility rule. Package scheduling is still unresolved.

### Complete repeated-label inventory

| Selector | Repeated option label | Root handler IDs | Disposition |
| --- | --- | --- | --- |
| default-regions | USA | 1337, 1359 | One general choice with fallback candidates |
| custom-verified | 10K+ followers | 991, 992 | Restore qualifiers. Merge only matching rows from the pools above |
| custom-exclusive | USA | 56, 100 | Restore qualifiers. Merge only matching rows from the pools above |
| default-standard-style-or-tone | Positive emoji | 856, 858 | One general choice with fallback candidates |
| default-standard-style-or-tone | Emoji | 859, 870, 872, 897 | Restore qualifiers. Merge only matching rows from the pools above |
| default-standard-style-or-tone | Random | 877, 892 | Restore qualifiers. Merge only matching rows from the pools above |
| default-standard-relevance-or-context | AI-relevant | 864, 865 | One general choice with fallback candidates |
| default-standard-audience | 10K+ followers · Power · Explore page · Arabic | 887, 888 | Restore qualifiers. Merge only matching rows from the pools above |
| default-standard-audience | Female | 889, 917 | One general choice with fallback candidates |
| default-standard-language-or-region | USA | 880, 911 | One general choice with fallback candidates |
| default-standard-language-or-region | Arabic | 887, 888 | Restore qualifiers. Merge only matching rows from the pools above |
| default-standard-language-or-region | Russia | 891, 892, 893 | Restore qualifiers. Merge only matching rows from the pools above |
| default-standard-language-or-region | India | 894, 907, 919 | One general choice with fallback candidates |
| default-standard-language-or-region | English | 905, 916 | Restore qualifiers. Merge only matching rows from the pools above |
| default-exclusive-power-or-explore | 20 comments | 34, 35, 42 | Restore qualifiers. Merge only matching rows from the pools above |
| default-exclusive-audience | 20 comments | 34, 35, 42 | Restore qualifiers. Merge only matching rows from the pools above |
| default-exclusive-language-or-region | USA | 57, 101 | Restore qualifiers. Merge only matching rows from the pools above |
| default-verified-power-or-explore | Female · 10K+ followers · 20 comments | 953, 986 | Same choice on paper. Hold for bounds conflict |
| default-verified-power-or-explore | Female · 10K+ followers · 40 comments | 954, 987 | Same choice on paper. Hold for bounds conflict |
| default-verified-power-or-explore | 10K+ followers · Power · Explore page · 5 comments | 956, 969, 983 | Restore qualifiers. Merge only matching rows from the pools above |
| default-verified-power-or-explore | 10K+ followers · Power · Explore page · 10 comments | 957, 970, 984 | Restore qualifiers. Merge only matching rows from the pools above |
| default-verified-power-or-explore | 10K+ followers · Power · Explore page · 20 comments | 958, 971, 985 | Restore qualifiers. Merge only matching rows from the pools above |
| default-verified-power-or-explore | 10K+ followers · Power · Explore page · 40 comments | 959, 972 | Restore qualifiers. Merge only matching rows from the pools above |
| default-verified-power-or-explore | 10K+ followers · Power · Explore page · Arabic | 977, 978, 979, 980, 981, 982 | Restore qualifiers. Merge only matching rows from the pools above |
| default-verified-audience | Female · 10K+ followers · 20 comments | 953, 986 | Same choice on paper. Hold for bounds conflict |
| default-verified-audience | Female · 10K+ followers · 40 comments | 954, 987 | Same choice on paper. Hold for bounds conflict |
| default-verified-audience | 10K+ followers · Power · Explore page · 5 comments | 956, 969, 983 | Restore qualifiers. Merge only matching rows from the pools above |
| default-verified-audience | 10K+ followers · Power · Explore page · 10 comments | 957, 970, 984 | Restore qualifiers. Merge only matching rows from the pools above |
| default-verified-audience | 10K+ followers · Power · Explore page · 20 comments | 958, 971, 985 | Restore qualifiers. Merge only matching rows from the pools above |
| default-verified-audience | 10K+ followers · Power · Explore page · 40 comments | 959, 972 | Restore qualifiers. Merge only matching rows from the pools above |
| default-verified-audience | 10K+ followers · Power · Explore page · Arabic | 977, 978, 979, 980, 981, 982 | Restore qualifiers. Merge only matching rows from the pools above |
| default-verified-audience | Verified | 993, 994 | One general choice with fallback candidates |
| default-verified-audience | Top tier | 996, 997 | Restore qualifiers. Merge only matching rows from the pools above |
| default-verified-language-or-region | Arabic | 977, 978, 979, 980, 981, 982 | Restore qualifiers. Merge only matching rows from the pools above |
| default-verified-language-or-region | Arab/Gulf | 988, 990 | Restore qualifiers. Merge only matching rows from the pools above |
| default-live-random | Random | 1044, 1045, 1046, 1048 | Restore qualifiers. Merge only matching rows from the pools above |
| custom-standard-general-custom-comments | Start 0 - 1 Hour · Speed 5K/Day | 861, 878 | Restore qualifiers. Merge only matching rows from the pools above |
| custom-standard-language-or-region | USA | 881, 924 | One general choice with fallback candidates |
| custom-standard-language-or-region | Brazil | 908, 934 | One general choice with fallback candidates |
| default-standard-general-random | Random | 868, 869, 871, 874, 895, 900, 902, 905, 918, 921 | Restore qualifiers. Merge only matching rows from the pools above |
| default-standard-delivery | Start 0 - 3 Hours · Speed 2K/Day | 856, 857 | Restore qualifiers. Merge only matching rows from the pools above |
| default-standard-delivery | Start 0 - 2 Hrs · Speed 20K/D | 858, 859 | Restore qualifiers. Merge only matching rows from the pools above |
| default-standard-delivery | AI-relevant | 864, 865 | One general choice with fallback candidates |
| default-standard-delivery | Start 0 - 3 Hours · Speed 20K/Day | 869, 870 | Restore qualifiers. Merge only matching rows from the pools above |
| default-standard-delivery | Start 0 - 3 Hours · Speed 25K/Day | 871, 872 | Restore qualifiers. Merge only matching rows from the pools above |
| default-standard-delivery | Start 0-6 Hours · Speed 1K/Day | 875, 876, 877 | Restore qualifiers. Merge only matching rows from the pools above |
| default-standard-delivery | Start 0-1 Hour · Speed 5/Hour | 882, 887 | Restore qualifiers. Merge only matching rows from the pools above |
| default-standard-delivery | Start 0-1 Hour · Speed 10/Hour | 883, 884, 885, 886, 888 | Restore qualifiers. Merge only matching rows from the pools above |
| default-standard-delivery | Start 1 Hour · Speed 300/Day | 891, 892, 893 | Restore qualifiers. Merge only matching rows from the pools above |
| default-standard-delivery | Start 1 Hour · Speed 500/Day | 894, 906, 915, 917 | Restore qualifiers. Merge only matching rows from the pools above |
| default-standard-delivery | Start 0-1 Hour · Speed 10K/Day | 895, 897 | Restore qualifiers. Merge only matching rows from the pools above |
| default-standard-delivery | Start 0 - 1 Hour · Speed 500/Day | 907, 916 | Restore qualifiers. Merge only matching rows from the pools above |
| default-standard-delivery | Start 0-1 Hour · Speed Fast | 911, 912, 913, 914 | Restore qualifiers. Merge only matching rows from the pools above |
| default-standard-delivery | Start 1 Hour · Speed 100/Day | 918, 919, 920, 921, 922, 923 | Restore qualifiers. Merge only matching rows from the pools above |
| default-exclusive-delivery | Start 0-1 Hour · Speed 1 Hour Delivery | 33, 34, 35, 36, 37, 38, 39, 40, 41, 42 | Restore qualifiers. Merge only matching rows from the pools above |
| default-live-instant-delivery | Start INSTANT · Speed INSTANT | 1044, 1045, 1046, 1048 | Restore qualifiers. Merge only matching rows from the pools above |

The existing analysis retains the full 233-ID reconciliation by provider category and payload type. IDs outside the proposed pools remain mapped for review. Being outside this first set of pools does not establish that a row has no alternative. Potential additional matches such as France versus French, or country names versus language labels, need target confirmation before collapse. No omitted rows were used.
