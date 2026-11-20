# Instagram Comments handler coverage review

2026-11-20 · Approved and implemented in the canonical JSON and local Builder

The accepted JSON and local Comments seed now reach all **233 mapped handlers** through 211 distinct primaries and 22 fallback-only handlers. The prior revision reached 195 despite loading all 233 rows in the Builder. The 38 restored handlers are enabled, unlocked `Default` rows with a fixed payload quantity of **1,000**. Eight are used exclusively as backups and 30 are selectable primaries under Others. [Saved ProductDefinition](../../products/instagram-comments.json) · [Local Comments Builder](http://localhost:5173/?workspace=instagram-comments)

## Scope and source evidence

The roadmap lists **Instagram → Comments → Instagram Comments** (`instagram-comments-comments`, status `definition_created`). The map has 233 unique root row IDs with no stale IDs. All are enabled and unlocked in the 5,717-row export, use JAP panel configuration `dgp_handler_id: 1`, and were last seen on 2026-11-18 at 08:02:54 UTC. The export has no embedded tenant or provider-account identity. The local Comments seed establishes the test context. Current live TygerBooster membership and policy remain unverified. [Roadmap](../../catalog.json) · [ID map](../../catalog-handler-service-ids.json) · [Registry](../../handler%20services.json)

The independent scan checked Instagram category, provider name, description and comment-shaped payload types. It found no additional confirmed rows for this mapped product. Related records include Threads row 32, Mentions row 841, Comment Likes rows 849/850/901, Story reply and poll rows 1085–1092, and engagement bundles already mapped under Packages. Ignore true subscription payload types, including the Auto Comments subscription rows. Rows 1504 and 1505 use `Package` and `Custom Comments Package`. Keep their current package placements and treat the “MONTHLY UNLIMITED POST” wording as unverified provider copy. [Prior source category reconciliation](analysis.md#handler-id-reconciliation)

## Variant tree and field plan

| JAP payload type | Handlers | Customer choice and input shape |
| --- | ---: | --- |
| `Default` | 154 | Provider-written comments. Keep post, Reel, Live and Channel targets distinct. Use options for language/region, audience, tone, emoji, relevance and delivery. Collect link and quantity. Show drip feed and its help text only where supported. |
| `Custom Comments` | 61 | Customer-written comments. Choose target and evidenced audience attributes, then collect the link and comment lines. Derive quantity from the line count. |
| `Package` | 7 | Fixed comment packs. Collect the link and use one internal package unit. |
| `Custom Comments Package` | 9 | Collect the link and comment lines. Track comment-list length separately from the fixed package unit. |
| `Poll` | 1 | Row 936. Collect link, answer number and vote quantity. |
| `Comment Replies` | 1 | Row 943. Collect link, username and reply text lines. Derive quantity from the line count. |

The existing tag and option identifiers stay in place. **Others** has **36 → 960** as its default and a required searchable `select/default` field with “Choose a fixed-quantity comment option” as its placeholder. The tag supplies a fixed **1,000** quantity directly to the snapshot. The description and preview summary display the fixed amount. The editable quantity field is hidden on this branch because the Ordering preview only displays the handler bounds. Provider-listed comment counts remain qualified in the choice labels. Comment lists use the registered `chips/default` control, and the definition retains its Link and Drip feed controls. [JAP input guide](../../.ai/JAP-SERVICE-TYPES.md) · [Builder capabilities](../../.ai/service-builder-capabilities.json)

## Where the 38 missing handlers go

All rows below have a structured quantity of 1,000 and no enabled capabilities. For a listed backup, the primary and alternate both use `Default`, have equal rates, and cover the same fixed quantity. The first seven pairs share the target, listed audience and source-described count. The eighth pair uses an additional pace-flexible Arabic choice because row 887's existing selector advertises 5/hour. The rate policy is the local Builder default `lte_primary` at 5%, with capability fit.

| Proposed routing | Primary → backup | Raw rate | Source-described variant |
| --- | --- | ---: | --- |
| Others default and selectable choice | 36 → 960 | 7.20 | Worldwide Power comments, provider lists 80 |
| Others selectable | 39 → 966 | 6.60 | USA/UK Power comments, provider lists 40 |
| Others selectable | 964 → 1326 | 3.60 | USA/UK Power comments, provider lists 10 |
| Others selectable | 969 → 1373 | 1.80 | Brazil Power comments, provider lists 5 |
| Others selectable | 970 → 1374 | 3.24 | Brazil Power comments, provider lists 10 |
| Others selectable | 973 → 1425 | 1.80 | South Korea Power comments, provider lists 5 |
| Others selectable | 974 → 1426 | 3.24 | South Korea Power comments, provider lists 10 |
| Others pace-flexible choice, existing primary | 887 → 977 | 1.80 | Arabic Power comments, provider lists 5. Retain the separate existing 887 selection at 5/hour. |

Each remaining handler gets its own Others option. The figures below are provider label qualifiers. Every option uses the same payload order constraint of 1,000.

| Root row IDs | Distinguishing option wording in matching ID order |
| --- | --- |
| 883, 884, 885 | Power comments, region unspecified, provider lists 10, 40, or 100 |
| 945, 946, 947, 948, 949 | Comments from female accounts, provider lists 10, 20, 40, 80, or 100 |
| 952, 953, 954 | Comments from female accounts with 10K+ followers, provider lists 10, 20, or 40 |
| 956, 957, 959, 961 | Worldwide Power comments, provider lists 5, 10, 40, or 100 |
| 967 | USA/UK Power comments, provider lists 80 |
| 980, 982 | Arabic Power comments, provider lists 40 or 80 |
| 983, 984 | Power comments with a French flag in the provider label, provider lists 5 or 10. The flag's targeting meaning remains unconfirmed. |
| 986, 987 | Alternate options for female accounts with 10K+ followers, provider lists 20 or 40. Their rates differ too much to pair with 953 or 954. |
| 996 | Top tier comments, provider lists 300 |

The rate rule explains why some similar rows still need their own choices. For example, 953 and 986 list the same audience and count, but rates of 4.80 and 2.25 are outside the 5% band in either direction. Row 982 at 10.20 likewise cannot share a fallback with 981 at 8.40. Row 983's flag and delivery wording differ from the existing unspecified-region, 5/hour route for 882. Across the restored rows, the proposed coverage is **30 primaries and eight backups**, plus reuse of existing primary 887 on the flexible Arabic route.

## Existing coverage and order preview findings

The prior definition had 52 tag defaults, 278 direct option bindings, and 44 node fallback lists. Those referenced 181 unique primaries and 20 distinct fallback IDs, including 14 used exclusively as fallbacks. The existing edges passed the local type, full quantity range, capability and 5% rate checks. The coverage repair retains their placements. The register below shows the exact nodes for each retained ID and the placement of each restored row.

The local seed matches the saved definition and passed DGP Validation against its 233-row catalog and local fallback rules. Two payload-specific problems appeared in the local ordering preview.

- **Poll.** Entering 125 votes on row 936 preserved `poll_quantity: 125` in the form but produced a preview quantity of **1** for a service with a 50–5,000 range. Bind the Poll quantity field as the snapshot quantity source and verify its host-to-JAP mapping to `quantity`.
- **Custom comment package.** Three submitted lines on row 1505 produced a preview quantity of **3**, while the handler allows exactly **one package unit**. Preserve all three lines as the comments list and verify a separate internal package quantity of one.

The same Ordering preview also reported required errors on fields hidden for the active Poll path. The revision scopes type-specific inputs to their branches and exposes Runs and Interval through the Drip feed trigger. This lets local Ordering snapshots omit fields from other order types.

## Implementation verification

The canonical JSON matches the local seed and passed DGP Spec 1.6.0 schema validation and DGP Validation 1.2.1 with the 233-row registry, field capability snapshot, and the local rate and capability policy. The JSX Builder and canonical seed passed TypeScript checking.

Local Ordering verified all **53** tag defaults and all **31** Others choices. Each Others snapshot resolved a quantity of **1,000** even with a stale quantity from another branch. DGP Core resolved the eight new option fallback lists and the Others tag fallback in their configured order. The local Builder displayed **233 All Services** and **211 Active Services**. Stock comments, custom text, fixed packages, custom packages, polls and replies were exercised through their order snapshots. The Poll snapshot produced **125** votes from the entered quantity. The custom-package snapshot preserved three submitted lines with an internal quantity of **one**. Runs and interval appeared in a Default snapshot only when the test activated drip feed.

The definition keeps unique form names for `poll_quantity`, `package_comments`, and `reply_comments`, as required by DGP validation. The production host's translation of those values into JAP request fields and provider fulfillment remain unverified.

## Handler placement register

For mapped handlers already covered, retain the exact listed nodes. For the 38 missing rows, the proposed entries refer to the Others choices and fallback order above. All rows in this register are enabled and unlocked.

| Root row | Order type | Placement |
| ---: | --- | --- |
| 33 | Default | Keep primary on `t:default-exclusive-power-or-explore`, `t:default-exclusive-power-or-explore:33`, `t:default-exclusive-audience:33`, `t:default-exclusive-delivery:33` |
| 34 | Default | Keep primary on `t:default-exclusive-audience`, `t:default-exclusive-power-or-explore:34`, `t:default-exclusive-audience:34`, `t:default-exclusive-delivery:34` |
| 35 | Default | Keep primary on `t:default-exclusive-delivery` |
| 36 | Default | Others selectable primary and tag default, with backup 960 |
| 37 | Default | Keep primary on `t:default-exclusive-power-or-explore:37`, `t:default-exclusive-audience:37`, `t:default-exclusive-delivery:37` |
| 38 | Default | Keep primary on `t:default-exclusive-language-or-region`, `o:default-regions:1327` |
| 39 | Default | Others selectable primary, with backup 966 |
| 40 | Default | Keep primary on `t:default-exclusive-power-or-explore:40`, `t:default-exclusive-audience:40`, `t:default-exclusive-language-or-region:40`, `t:default-exclusive-delivery:40` |
| 41 | Default | Keep primary on `t:default-exclusive-power-or-explore:41`, `t:default-exclusive-audience:41`, `t:default-exclusive-language-or-region:41`, `t:default-exclusive-delivery:41` |
| 42 | Default | Keep primary on `t:default-exclusive-power-or-explore:42`, `t:default-exclusive-audience:42`, `t:default-exclusive-delivery:42` |
| 56 | Custom Comments | Keep primary on `t:custom-exclusive`, `o:custom-exclusive:56` |
| 57 | Default | Keep primary on `t:default-exclusive-language-or-region:57`, `t:default-exclusive-delivery:57` |
| 63 | Custom Comments | Keep primary on `o:custom-exclusive:63` |
| 64 | Default | Keep primary on `t:default-exclusive`, `t:default-exclusive-language-or-region:64` |
| 87 | Default | Keep primary on `t:default-exclusive-delivery:87` |
| 88 | Default | Keep primary on `t:default-exclusive-audience:88`, `t:default-exclusive-delivery:88` |
| 89 | Default | Keep primary on `t:default-exclusive-audience:89`, `t:default-exclusive-delivery:89` |
| 100 | Custom Comments | Keep primary on `o:custom-exclusive:100` |
| 101 | Default | Keep primary on `t:default-exclusive-language-or-region:101` |
| 803 | Default | Keep primary on `t:default-reels`, `t:default-reels-audience:803` |
| 804 | Default | Keep primary on `t:default-reels-audience`, `t:default-reels-audience:804` |
| 805 | Default | Keep primary on `t:default-reels-audience:805` |
| 806 | Default | Keep primary on `t:default-reels-hq-wording`, `t:default-reels-audience:806`, `t:default-reels-hq-wording:806` |
| 807 | Default | Keep primary on `t:default-reels-language-or-region`, `t:default-reels-language-or-region:807`, `t:default-reels-hq-wording:807` |
| 808 | Default | Keep primary on `t:default-reels-language-or-region:808`, `t:default-reels-hq-wording:808` |
| 809 | Default | Keep primary on `t:default-reels-language-or-region:809`, `t:default-reels-hq-wording:809` |
| 810 | Default | Keep primary on `t:default-reels-language-or-region:810`, `t:default-reels-hq-wording:810` |
| 811 | Default | Keep primary on `t:default-reels-audience:811`, `t:default-reels-language-or-region:811`, `t:default-reels-hq-wording:811` |
| 812 | Default | Keep primary on `t:default-reels-language-or-region:812`, `t:default-reels-hq-wording:812` |
| 813 | Default | Keep primary on `t:default-reels-audience:813`, `t:default-reels-language-or-region:813`, `t:default-reels-hq-wording:813` |
| 814 | Default | Keep primary on `t:default-reels-language-or-region:814`, `t:default-reels-hq-wording:814` |
| 815 | Default | Keep primary on `t:default-reels-language-or-region:815`, `t:default-reels-hq-wording:815` |
| 816 | Custom Comments | Keep primary on `t:custom-reels`, `t:custom-reels-gender:816` |
| 817 | Custom Comments | Keep primary on `t:custom-reels-language-or-region:817` |
| 818 | Custom Comments | Keep primary on `t:custom-reels-gender`, `t:custom-reels-gender:818` |
| 819 | Custom Comments | Keep primary on `t:custom-reels-hq-wording`, `t:custom-reels-hq-wording:819` |
| 820 | Custom Comments | Keep primary on `t:custom-reels-hq-wording:820` |
| 821 | Custom Comments | Keep primary on `t:custom-reels-hq-wording:821` |
| 822 | Custom Comments | Keep primary on `t:custom-reels-language-or-region`, `t:custom-reels-language-or-region:822`, `t:custom-reels-hq-wording:822` |
| 823 | Custom Comments | Keep primary on `t:custom-reels-language-or-region:823`, `t:custom-reels-hq-wording:823` |
| 824 | Custom Comments | Keep primary on `t:custom-reels-language-or-region:824`, `t:custom-reels-hq-wording:824` |
| 825 | Custom Comments | Keep primary on `t:custom-reels-gender:825`, `t:custom-reels-language-or-region:825`, `t:custom-reels-hq-wording:825` |
| 826 | Custom Comments | Keep primary on `t:custom-reels-language-or-region:826`, `t:custom-reels-hq-wording:826` |
| 827 | Custom Comments | Keep primary on `t:custom-reels-language-or-region:827`, `t:custom-reels-hq-wording:827` |
| 828 | Custom Comments | Keep primary on `t:custom-reels-language-or-region:828`, `t:custom-reels-hq-wording:828` |
| 853 | Custom Comments | Keep primary on `t:custom-standard-language-or-region`, `t:custom-standard-language-or-region:853` |
| 855 | Default | Keep primary on `t:default-standard-style-or-tone`, `t:default-standard-style-or-tone:855`, `t:default-standard-delivery:855` |
| 856 | Default | Keep primary on `t:default-standard-delivery`, `t:default-standard-style-or-tone:856`, `t:default-standard-delivery:856` |
| 857 | Default | Keep primary on `t:default-standard-style-or-tone:857`, `t:default-standard-delivery:857` |
| 858 | Default | Keep primary on `t:default-standard-style-or-tone:858`, `t:default-standard-delivery:858` |
| 859 | Default | Keep primary on `t:default-standard-style-or-tone:859`, `t:default-standard-delivery:859` |
| 860 | Custom Comments | Keep primary on `t:custom-standard`, `t:custom-standard-general-custom-comments:860` |
| 861 | Custom Comments | Keep primary on `t:custom-standard-general-custom-comments`, `t:custom-standard-general-custom-comments:861` |
| 862 | Custom Comments | Keep primary on `t:custom-comments`, `t:custom-standard-general-custom-comments:862` |
| 863 | Custom Comments | Keep primary on `t:custom-standard-general-custom-comments:863` |
| 864 | Default | Keep primary on `t:default-standard-relevance-or-context`, `t:default-standard-relevance-or-context:864`, `t:default-standard-delivery:864` |
| 865 | Default | Keep primary on `t:default-standard-relevance-or-context:865`, `t:default-standard-delivery:865` |
| 866 | Custom Comments | Keep primary on `t:custom-standard-relevance`, `t:custom-standard-relevance:866` |
| 867 | Default | Keep primary on `t:default-standard-audience`, `t:default-standard-relevance-or-context:867`, `t:default-standard-audience:867`, `t:default-standard-delivery:867` |
| 868 | Default | Keep primary on `t:default-standard`, `t:default-standard-general-random:868`, `t:default-standard-delivery:868` |
| 869 | Default | Keep primary on `t:default-standard-general-random`, `t:default-standard-general-random:869`, `t:default-standard-delivery:869` |
| 870 | Default | Keep primary on `t:default-standard-style-or-tone:870`, `t:default-standard-delivery:870` |
| 871 | Default | Keep primary on `t:default`, `t:default-standard-general-random:871`, `t:default-standard-delivery:871`<br>Keep backup on `t:default-standard` (#1), `t:default-standard-general-random:868` (#1) |
| 872 | Default | Keep primary on `t:default-standard-style-or-tone:872`, `t:default-standard-delivery:872` |
| 873 | Custom Comments | Keep backup on `t:custom-standard-general-custom-comments` (#1), `t:custom-standard-general-custom-comments:861` (#1) |
| 874 | Default | Keep primary on `t:default-standard-language-or-region`, `t:default-standard-language-or-region:874`, `t:default-standard-general-random:874`, `t:default-standard-delivery:874` |
| 875 | Default | Keep primary on `t:default-standard-audience:875`, `t:default-standard-delivery:875` |
| 876 | Default | Keep primary on `t:default-standard-audience:876`, `t:default-standard-delivery:876` |
| 877 | Default | Keep primary on `t:default-standard-style-or-tone:877`, `t:default-standard-delivery:877` |
| 878 | Custom Comments | Keep primary on `t:custom-standard-general-custom-comments:878` |
| 879 | Default | Keep primary on `t:default-standard-relevance-or-context:879`, `t:default-standard-general-random:879`, `t:default-standard-delivery:879` |
| 880 | Default | Keep primary on `t:default-standard-language-or-region:880`, `t:default-standard-delivery:880`<br>Keep backup on `t:default-exclusive-language-or-region:57` (#1), `t:default-exclusive-delivery:57` (#1) |
| 881 | Custom Comments | Keep primary on `t:custom-standard-language-or-region:881`<br>Keep backup on `t:custom-exclusive` (#1), `o:custom-exclusive:56` (#1) |
| 882 | Default | Keep primary on `t:default-standard-delivery:882` |
| 883 | Default | Others selectable primary |
| 884 | Default | Others selectable primary |
| 885 | Default | Others selectable primary |
| 886 | Default | Keep primary on `t:default-standard-audience:886`, `t:default-standard-delivery:886` |
| 887 | Default | Keep primary on `t:default-standard-delivery:887`<br>Also use as the pace-flexible Arabic primary under Others with backup 977 |
| 888 | Default | Keep primary on `t:default-standard-audience:888`, `t:default-standard-language-or-region:888`, `t:default-standard-delivery:888` |
| 889 | Default | Keep primary on `t:default-standard-audience:889`, `t:default-standard-delivery:889` |
| 890 | Custom Comments | Keep primary on `t:custom-standard-general-custom-comments:890` |
| 891 | Default | Keep primary on `t:default-standard-language-or-region:891`, `t:default-standard-delivery:891` |
| 892 | Default | Keep primary on `t:default-standard-style-or-tone:892`, `t:default-standard-language-or-region:892`, `t:default-standard-delivery:892` |
| 893 | Default | Keep primary on `t:default-standard-style-or-tone:893`, `t:default-standard-language-or-region:893`, `t:default-standard-delivery:893` |
| 894 | Default | Keep primary on `t:default-standard-language-or-region:894`, `t:default-standard-delivery:894` |
| 895 | Default | Keep primary on `t:root`, `t:default-standard-general-random:895`, `t:default-standard-delivery:895` |
| 896 | Custom Comments | Keep primary on `t:custom-standard-general-custom-comments:896` |
| 897 | Default | Keep primary on `t:default-standard-style-or-tone:897`, `t:default-standard-delivery:897` |
| 899 | Custom Comments | Keep primary on `t:custom-standard-language-or-region:899` |
| 900 | Default | Keep primary on `t:default-standard-general-random:900`, `t:default-standard-delivery:900` |
| 902 | Default | Keep primary on `t:default-standard-general-random:902`, `t:default-standard-delivery:902` |
| 903 | Custom Comments | Keep primary on `t:custom-standard-premium-or-high-end`, `t:custom-standard-premium-or-high-end:903` |
| 904 | Custom Comments | Keep primary on `t:custom-standard-general-custom-comments:904` |
| 905 | Default | Keep primary on `t:default-standard-language-or-region:905`, `t:default-standard-general-random:905`, `t:default-standard-delivery:905` |
| 906 | Default | Keep primary on `t:default-standard-language-or-region:906`, `t:default-standard-delivery:906` |
| 907 | Default | Keep primary on `t:default-standard-language-or-region:907`, `t:default-standard-delivery:907` |
| 908 | Custom Comments | Keep primary on `t:custom-standard-language-or-region:908` |
| 909 | Custom Comments | Keep primary on `t:custom-standard-gender`, `t:custom-standard-gender:909` |
| 910 | Custom Comments | Keep primary on `t:custom-standard-gender:910` |
| 911 | Default | Keep primary on `t:default-standard-language-or-region:911`, `t:default-standard-delivery:911` |
| 912 | Default | Keep primary on `t:default-standard-language-or-region:912`, `t:default-standard-delivery:912` |
| 913 | Default | Keep primary on `t:default-standard-language-or-region:913`, `t:default-standard-delivery:913` |
| 914 | Default | Keep primary on `t:default-standard-language-or-region:914`, `t:default-standard-delivery:914` |
| 915 | Default | Keep primary on `t:default-standard-audience:915`, `t:default-standard-delivery:915` |
| 916 | Default | Keep primary on `t:default-standard-language-or-region:916`, `t:default-standard-delivery:916` |
| 917 | Default | Keep primary on `t:default-standard-audience:917`, `t:default-standard-delivery:917` |
| 918 | Default | Keep primary on `t:default-standard-general-random:918`, `t:default-standard-delivery:918` |
| 919 | Default | Keep primary on `t:default-standard-language-or-region:919`, `t:default-standard-delivery:919` |
| 920 | Default | Keep primary on `t:default-standard-language-or-region:920`, `t:default-standard-delivery:920` |
| 921 | Default | Keep primary on `t:default-standard-general-random:921`, `t:default-standard-delivery:921` |
| 922 | Default | Keep primary on `t:default-standard-language-or-region:922`, `t:default-standard-delivery:922` |
| 923 | Default | Keep primary on `t:default-standard-language-or-region:923`, `t:default-standard-delivery:923` |
| 924 | Custom Comments | Keep primary on `t:custom-standard-language-or-region:924` |
| 925 | Custom Comments | Keep primary on `t:custom-standard-language-or-region:925` |
| 926 | Custom Comments | Keep primary on `t:custom-standard-gender:926` |
| 927 | Custom Comments | Keep primary on `t:custom-standard-gender:927` |
| 928 | Custom Comments | Keep primary on `t:custom-standard-language-or-region:928` |
| 929 | Custom Comments | Keep primary on `t:custom-standard-language-or-region:929` |
| 930 | Custom Comments | Keep primary on `t:custom-standard-language-or-region:930` |
| 931 | Custom Comments | Keep primary on `t:custom-standard-language-or-region:931` |
| 932 | Custom Comments | Keep primary on `t:custom-standard-language-or-region:932` |
| 933 | Custom Comments | Keep primary on `t:custom-standard-language-or-region:933` |
| 934 | Custom Comments | Keep primary on `t:custom-standard-language-or-region:934` |
| 935 | Custom Comments | Keep primary on `t:custom-standard-language-or-region:935` |
| 936 | Poll | Keep primary on `t:poll` |
| 937 | Custom Comments | Keep primary on `t:custom-standard-language-or-region:937` |
| 938 | Custom Comments | Keep primary on `t:custom-standard-language-or-region:938` |
| 939 | Custom Comments | Keep primary on `t:custom-standard-premium-or-high-end:939` |
| 940 | Custom Comments | Keep primary on `t:custom-standard-language-or-region:940` |
| 941 | Default | Keep primary on `t:default-standard-language-or-region:941` |
| 942 | Default | Keep primary on `t:default-standard-language-or-region:942`, `t:default-standard-delivery:942` |
| 943 | Comment Replies | Keep primary on `t:replies` |
| 944 | Default | Keep primary on `t:default-verified-audience` |
| 945 | Default | Others selectable primary |
| 946 | Default | Others selectable primary |
| 947 | Default | Others selectable primary |
| 948 | Default | Others selectable primary |
| 949 | Default | Others selectable primary |
| 950 | Default | Keep primary on `t:default-verified-audience:950` |
| 951 | Default | Keep primary on `t:default-verified-power-or-explore` |
| 952 | Default | Others selectable primary |
| 953 | Default | Others selectable primary |
| 954 | Default | Others selectable primary |
| 955 | Default | Keep primary on `t:default-verified-power-or-explore:955`, `t:default-verified-audience:955` |
| 956 | Default | Others selectable primary |
| 957 | Default | Others selectable primary |
| 958 | Default | Keep backup on `t:default-exclusive-delivery` (#1) |
| 959 | Default | Others selectable primary |
| 960 | Default | Others backup for 36 |
| 961 | Default | Others selectable primary |
| 962 | Default | Keep primary on `t:default-verified-power-or-explore:962`, `t:default-verified-audience:962`<br>Keep backup on `t:default-exclusive-power-or-explore:37` (#1), `t:default-exclusive-audience:37` (#1), `t:default-exclusive-delivery:37` (#1) |
| 963 | Default | Keep primary on `t:default-verified-language-or-region` |
| 964 | Default | Others selectable primary, with backup 1326 |
| 965 | Default | Keep backup on `t:default-exclusive-language-or-region` (#1), `o:default-regions:1327` (#1) |
| 966 | Default | Others backup for 39 |
| 967 | Default | Others selectable primary |
| 968 | Default | Keep primary on `t:default-verified-power-or-explore:968`, `t:default-verified-audience:968`, `t:default-verified-language-or-region:968`<br>Keep backup on `t:default-exclusive-power-or-explore:40` (#1), `t:default-exclusive-audience:40` (#1), `t:default-exclusive-language-or-region:40` (#1), `t:default-exclusive-delivery:40` (#1) |
| 969 | Default | Others selectable primary, with backup 1373 |
| 970 | Default | Others selectable primary, with backup 1374 |
| 971 | Default | Keep backup on `t:default-exclusive-audience` (#1), `t:default-exclusive-power-or-explore:34` (#1), `t:default-exclusive-audience:34` (#1), `t:default-exclusive-delivery:34` (#1) |
| 972 | Default | Keep primary on `o:default-regions:1377`, `t:default-verified-power-or-explore:972`, `t:default-verified-audience:972` |
| 973 | Default | Others selectable primary, with backup 1425 |
| 974 | Default | Others selectable primary, with backup 1426 |
| 975 | Default | Keep backup on `t:default-exclusive-power-or-explore` (#1), `t:default-exclusive-power-or-explore:33` (#1), `t:default-exclusive-audience:33` (#1), `t:default-exclusive-delivery:33` (#1) |
| 976 | Default | Keep primary on `o:default-regions:1428`, `t:default-verified-power-or-explore:976`, `t:default-verified-audience:976` |
| 977 | Default | Others backup for 887 |
| 978 | Default | Keep backup on `t:default-standard-audience:888` (#1), `t:default-standard-language-or-region:888` (#1) |
| 979 | Default | Keep backup on `t:default-exclusive-power-or-explore:41` (#1), `t:default-exclusive-audience:41` (#1), `t:default-exclusive-language-or-region:41` (#1), `t:default-exclusive-delivery:41` (#1) |
| 980 | Default | Others selectable primary |
| 981 | Default | Keep primary on `t:default-verified-power-or-explore:981`, `t:default-verified-audience:981`, `t:default-verified-language-or-region:981` |
| 982 | Default | Others selectable primary |
| 983 | Default | Others selectable primary |
| 984 | Default | Others selectable primary |
| 985 | Default | Keep primary on `t:default-verified-power-or-explore:985`, `t:default-verified-audience:985`<br>Keep backup on `t:default-exclusive-power-or-explore:42` (#1), `t:default-exclusive-audience:42` (#1), `t:default-exclusive-delivery:42` (#1) |
| 986 | Default | Others selectable primary |
| 987 | Default | Others selectable primary |
| 988 | Default | Keep primary on `t:default-verified-language-or-region:988` |
| 989 | Custom Comments | Keep primary on `o:custom-verified:989` |
| 990 | Default | Keep primary on `t:default-verified-language-or-region:990` |
| 991 | Custom Comments | Keep primary on `o:custom-verified:991` |
| 992 | Custom Comments | Keep primary on `o:custom-verified:992` |
| 993 | Default | Keep primary on `t:default-verified`, `t:default-verified-audience:993` |
| 994 | Default | Keep backup on `t:default-verified` (#1), `t:default-verified-audience:993` (#1) |
| 995 | Custom Comments | Keep primary on `t:custom-verified`, `o:custom-verified:995` |
| 996 | Default | Others selectable primary |
| 997 | Default | Keep primary on `t:default-verified-audience:997` |
| 1039 | Custom Comments | Keep primary on `t:custom-super`, `o:custom-super:1039` |
| 1040 | Custom Comments | Keep primary on `o:custom-super:1040` |
| 1041 | Custom Comments | Keep primary on `o:custom-super:1041` |
| 1042 | Custom Comments | Keep primary on `o:custom-super:1042` |
| 1044 | Default | Keep primary on `t:default-live`, `t:default-live-random:1044`, `t:default-live-instant-delivery:1044` |
| 1045 | Default | Keep primary on `t:default-live-random`, `t:default-live-random:1045`, `t:default-live-audience:1045`, `t:default-live-instant-delivery:1045` |
| 1046 | Default | Keep primary on `t:default-live-audience`, `t:default-live-random:1046`, `t:default-live-audience:1046`, `t:default-live-instant-delivery:1046` |
| 1048 | Default | Keep primary on `t:default-live-instant-delivery` |
| 1156 | Default | Keep primary on `t:default-channel`, `t:default-channel-positive` |
| 1325 | Default | Keep backup on `t:default-verified-language-or-region` (#1) |
| 1326 | Default | Others backup for 964 |
| 1327 | Default | Keep backup on `t:default-exclusive-language-or-region` (#2), `o:default-regions:1327` (#2) |
| 1337 | Default | Keep primary on `t:default-regions`, `o:default-regions:1337` |
| 1338 | Custom Comments | Keep primary on `t:custom-regions`, `o:custom-regions:1338` |
| 1359 | Default | Keep primary on `o:default-regions:1359` |
| 1371 | Default | Keep primary on `o:default-regions:1371` |
| 1373 | Default | Others backup for 969 |
| 1374 | Default | Others backup for 970 |
| 1376 | Default | Keep backup on `t:default-exclusive-audience` (#2), `t:default-exclusive-power-or-explore:34` (#2), `t:default-exclusive-audience:34` (#2), `t:default-exclusive-delivery:34` (#2) |
| 1377 | Default | Keep backup on `t:default-verified-power-or-explore:972` (#1), `t:default-verified-audience:972` (#1), `o:default-regions:1377` (#1) |
| 1420 | Custom Comments | Keep primary on `o:custom-regions:1420` |
| 1421 | Default | Keep primary on `o:default-regions:1421` |
| 1425 | Default | Others backup for 973 |
| 1426 | Default | Others backup for 974 |
| 1427 | Default | Keep backup on `t:default-exclusive-power-or-explore` (#2), `t:default-exclusive-power-or-explore:33` (#2), `t:default-exclusive-audience:33` (#2), `t:default-exclusive-delivery:33` (#2) |
| 1428 | Default | Keep backup on `t:default-verified-power-or-explore:976` (#1), `t:default-verified-audience:976` (#1), `o:default-regions:1428` (#1) |
| 1431 | Default | Keep primary on `o:default-regions:1431` |
| 1435 | Default | Keep primary on `o:default-regions:1435` |
| 1436 | Custom Comments | Keep primary on `o:custom-regions:1436` |
| 1444 | Custom Comments | Keep primary on `o:custom-regions:1444` |
| 1445 | Package | Keep primary on `t:package-fixed`, `o:package-fixed:1445` |
| 1446 | Package | Keep primary on `t:package`, `o:package-fixed:1446` |
| 1447 | Package | Keep primary on `o:package-fixed:1447` |
| 1448 | Package | Keep primary on `o:package-fixed:1448` |
| 1449 | Package | Keep primary on `o:package-fixed:1449` |
| 1450 | Package | Keep primary on `o:package-fixed:1450` |
| 1454 | Custom Comments Package | Keep primary on `t:custom-package-fixed`, `o:custom-package-fixed:1454` |
| 1455 | Custom Comments Package | Keep primary on `t:custom-comments-package`, `o:custom-package-fixed:1455` |
| 1456 | Custom Comments Package | Keep primary on `o:custom-package-fixed:1456` |
| 1457 | Custom Comments Package | Keep primary on `o:custom-package-fixed:1457` |
| 1458 | Custom Comments Package | Keep primary on `o:custom-package-fixed:1458` |
| 1459 | Custom Comments Package | Keep primary on `o:custom-package-fixed:1459` |
| 1460 | Custom Comments Package | Keep primary on `o:custom-package-fixed:1460` |
| 1461 | Custom Comments Package | Keep primary on `o:custom-package-fixed:1461` |
| 1504 | Package | Keep primary on `t:package-auto` |
| 1505 | Custom Comments Package | Keep primary on `t:custom-package-auto` |
