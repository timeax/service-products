# Historical Instagram Likes source analysis

## Scope

This is a record of how an earlier conversation examined a 202-handler Instagram Likes fixture. It demonstrates the analysis process only; it does not represent the current handler evidence or the actual service definition. Current actual work is tracked separately under `analysis/` and `products/`.

The old source files are in `source/`. They came from a local Service Builder lab fixture and are different from the current project-root `handler services.json`. The current file is the authority for building today's catalog.

## View 1 — How the supplied handlers were grouped

The 202-row example fixture had four provider categories:

| Provider category | Rows |
| --- | ---: |
| Instagram Likes | 91 |
| Instagram Likes [BOTS] | 48 |
| Instagram Likes [Targeted] | 51 |
| Instagram Likes Per Minute | 12 |

Those are backend groupings, not four independent storefront products and not a complete service inventory. The names exposed different characteristics that needed separate analysis.

## View 2 — Customer-facing characteristics

| Characteristic | Examples found in the old handler names | What the analysis needed to distinguish |
| --- | --- | --- |
| Quality | Basic, Medium, High, Premium | A stated tier is a choice within a service family; it is not proof of a guarantee. |
| Account type | Bot, profile picture, refill wording | Account type is separate from quality and targeting. |
| Geography | Country, region, and mixed-region labels | Keep distinct targets distinct; do not treat a regional service as a worldwide one. |
| Audience | Female/male and demographic labels | Audience targeting is separate from geography; a combined label can carry both constraints. |
| Refill | Refill capability and advertised duration | Capability and advertised duration are separate facts. |
| Retention | Non-drop, low drops, estimated drop ranges | Preserve the source claim without strengthening it. |
| Delivery | Instant, Emergency, Fast, per-minute rates | Priority and controlled rate describe different service dimensions. |
| Combined outcomes | Likes with Impressions and/or Reach | A handler that includes another outcome cannot be replaced by a plain-likes handler. |
| Unusual variants | Single delivery, Natural Increase, From App, RAU, RAL, and regional bundles | Keep unusual, evidenced choices visible for review rather than forcing them into a misleading common group. |

The purpose of this breakdown was to understand what a future customer-facing service might need to distinguish. It did not establish that any ProductDefinition had been started in this project.

## View 3 — Operational characteristics

Each row also carried order bounds, rate, state, and feature flags for refill, cancel, drip-feed, and contract. In that older fixture, all 202 rows were marked enabled; 15 had refill enabled, 112 cancel, 124 drip-feed, and 0 contract. These are counts from that fixture only. A capability being disabled does not mean the handler itself is disabled, and an enabled handler does not prove a storefront product is available.

Missing numeric IDs were not evidence of disabled or locked records. Handler IDs, rates, bounds, and capabilities were site-specific and unsuitable for transfer into another registry.

## View 4 — From analysis to a catalog entry

The main taxonomy lesson was to group provider variants into a customer-facing service family, then keep general categories such as Likes, Followers, Views, and Visits separate across platforms. Variants like geography, quality, refill, and delivery speed are then analyzed for a future definition rather than each becoming its own product by default.

Combined outcomes and different target objects may need separate service families when they change what is delivered or what the customer must provide. The exact choice belongs in the catalog only after reviewing the current `handler services.json` source.

## View 5 — What this example does not establish

- It does not define current platforms or current catalog entries.
- It does not establish live storefront availability.
- It does not supply current handler IDs or capabilities.
- It does not create or validate a ProductDefinition.
- It does not override the current project-root handler source.
