# Service catalog and ProductDefinition workflow

Use `catalog.json` as the service roadmap and `products/` for actual ProductDefinitions. Inspect the current contents of both at the start of a task. For every actual service being created or redone, analyze the current catalog mapping and handler records first, present the analysis in chat, save it under `analysis/<service-slug>/`, and wait for explicit approval before product JSON changes.

## 0. Establish scope and evidence

- Read `.ai/agent-search.json` first when locating local registries, DGP contracts, or Builder behavior. Use its local paths and inspect the actual package interfaces, declarations, schemas, and source relevant to the task.
- Do not visit the online Gist by default. A local `GIST.md` is only a navigation overview; it cannot substitute for inspecting the local DGP packages or Builder code.
- Respect concern-specific authority: handler registry facts come from the scoped handler-services source; canonical ProductDefinition shape comes from the applicable local `dgp-spec`; product interpretation from `dgp-core`; validation behavior from `dgp-validation`; order runtime and Builder-specific behavior from their respective local packages and consumer source.
- For TygerBooster normalization, use `.ai/TYGERBOOSTER-SERVICE-BUILDER.md` as host-specific guidance for grouping raw JAP services into a customer ordering experience. Provider categories are organizational evidence, not automatic customer tags.
- For a JAP-backed handler, use its actual `payload.type` with `.ai/JAP-SERVICE-TYPES.md` to identify required, optional, and conditional API inputs. Keep JAP API fields distinct from TygerBooster Builder controls (for example, `drip_feed` is a Builder toggle; `runs` and `interval` are JAP request fields).
- For current Service Builder controls and templates, read `.ai/service-builder-capabilities.json`. Treat its registered input capabilities and field templates as the user's authoritative snapshot for the represented Builder state. It does not specify a Builder version; recheck the open Builder before relying on it if the Builder may have changed.
- Publication policies in that snapshot are context only. Do not edit, generate, or infer policy requirements from them.
- Confirm the target platform/product and intended site or tenant.
- Inspect the project-root `handler services.json` if present. Confirm its site/project scope, structure, and snapshot context; use its handler rows as source evidence for that scope, and never overwrite it or silently blend it with another registry.
- Inspect `catalog-handler-service-ids.json` for the exact catalog service key. Treat it as a row-ID mapping only: resolve every mapped ID in `handler services.json`, identify stale IDs, and search the registry for relevant rows omitted from the mapping. Do not treat the mapping as complete without reconciliation.
- Locate the current handler registry, existing ProductDefinition, schema/contract version, and Builder capability context.
- Record source paths, capture dates when known, registry scope, and whether each source is authoritative, historical, or illustrative.
- Keep each site's registry separate. IDs are opaque within their source and must never be joined across sites just because their numbers or names match.
- Identify explicit disabled/locked/restricted records and any site-specific constraints. Do not equate “not in snapshot” with disabled, unavailable, or locked.

## 1. Inventory without invention

- Parse the registry and count records. Preserve raw records in the example/source bundle when practical.
- Summarize platform/product category labels actually present. Separate provider category text from customer-facing product families.
- Parse compound category labels by their platform and general-service parts; do not promote an embedded qualifier into a new platform. For example, source category `Instagram THREADS Likes` maps under platform `Instagram` → category `Likes`, with `Threads Likes` as the service name. Keep the raw category label in the evidence notes and use a separate platform only when the source or corroborating evidence identifies one.
- Record each handler's ID, name, source category, state, min/max, rate, and capabilities exactly as supplied; do not normalize away the original.
- Identify duplicates and near-duplicates by comparing evidence (service behavior, category, limits, capability flags, delivery speed, audience, package contents), not name alone.
- Break the registry into analytical viewpoints to identify platforms, general categories, and service families to build. Treat quality, account type, targeting, refill, retention, speed, and bundles as possible variants within a service family unless the source shows they are separate customer-facing services.
- Propose the `catalog.json` structure as `platform → general category → services` in the analysis. After approval, write it with a progress `status` on each service, all new services `not_started`, and `product_definitions` empty. Do not put provider handler rows or evidence notes in the catalog.
- Normalize repeated provider variants into one service work item where they share the same customer-facing service family. Do not create one catalog service per handler ID.
- Keep source-category labels or uncertain classifications in analysis notes when needed; do not treat them as finished product names when their meaning is unclear.
- Mark ambiguous fields and conflicting source claims. Do not infer availability or behavior from marketing-like handler names.

## Approval gate before JSON changes

For each actual service, present the analysis in the chat as the primary review and save the same detailed report in `analysis/<service-slug>/` for the site owner. Include source evidence and scope, mapped/stale/omitted handler IDs, all relevant analytical viewpoints, service-family boundaries, proposed field and fallback mappings, Builder capability evidence, conflicts, and unresolved decisions. Then stop and wait for explicit user approval. Until approval, do not create or edit that service's ProductDefinition JSON or mark it `in_progress`. Approval applies only to the reviewed scope; material source or mapping changes need a revised analysis and approval. Source inspection and analysis preparation may proceed without approval.

## 2. Analyze and normalize variants

- Group handlers by meaningful customer choice: quality, audience/region, bot status, retention/refill, delivery timing/speed, and bundled outcomes when evidenced.
- Distinguish a distinct service family from a variation that belongs in a field option. Use hierarchy only when it improves navigation; avoid deep or redundant trees.
- Normalize customer language while preserving the provider's original label in evidence. Keep claims bounded to source wording.
- Map each normalized option to the exact handler ID(s) that support it. Maintain a traceable row/decision for every assigned handler and every intentionally excluded handler.
- Treat “Other” as an explicit catch-all only if its semantics are defined; it must not silently absorb unreviewed or incompatible handlers.

## 3. Choose primary handlers and fallbacks

- Select a primary handler using documented requirements and evidenced trade-offs such as relevant capability, limits, quality/target fit, speed, and state. Do not assume cheapest or highest numeric ID is best.
- A fallback must satisfy the same customer promise and input shape. Match capability, min/max constraints, target, package contents, and other relevant attributes.
- Keep fallbacks in an explicit ordered list only where contract semantics support that order. Explain why each fallback is compatible and when it can be used.
- Do not map locked, disabled, or out-of-scope handlers as primary or fallback. If no compatible active alternative exists, preserve the gap as unresolved.
- Ensure the root binding and quantity templating are intentional and supported by the current contract; do not copy an example root ID into a new product.

## 4. Design fields, tags, and visibility

- Define required order inputs and bind each to the correct tag or root. Preserve field IDs and names when updating an existing definition unless change is authorized.
- For JAP services, derive the order input shape from the selected row's `payload.type` and JAP type guide. Do not infer it from provider category or name; preserve distinctions where a service type has no `quantity` field or derives quantity from a list/package.
- Use Select options for variations within one family; use sub-tags only for genuinely distinct service families. Every option must map to an evidenced handler and have unique stable IDs/values.
- Before selecting a control, match its exact registered `type` and `variant` in `.ai/service-builder-capabilities.json`. Use only listed UI properties/defaults. Respect the declared cardinality and `optionCapability`/`multiCapability` flags; a control having an `options` UI property does not by itself prove that options or multiple values are supported. Note the separate `checkbox/default` and `checkbox/options` registrations.
- Treat the saved Quantity field template as a Builder authoring artifact, not a universal product rule or a ready-made ProductDefinition. Do not copy its minimum, maximum, placeholder, tags, pricing role, or quantity binding without checking the target service's evidence and contract. Do not copy template/editor metadata such as `published`, `branch_id`, template `id`, `updated_at`, or relationships into a ProductDefinition unless the applicable Builder workflow and contract explicitly require them.
- Keep customer copy short. If a field already has a useful description, do not duplicate it with help text. Use placeholder/help text only when it answers a real customer question.
- Add notices/promotional labels only when requested or supported by a deliberate merchandising decision. Do not present them as verified quality/popularity facts without evidence.
- Derive visibility conditions from explicit handler capabilities and supported expression syntax. For each conditional field, record the capability and handler set that makes it available.
- Tie dependent inputs (for example, drip-feed runs and interval) to the controlling toggle. Do not submit an order input when its visibility condition is false if the Builder contract says hidden fields are omitted.
- Avoid hard-coded handler exclusion lists when a reliable capability-aware rule exists. Keep exceptions only with documented evidence and a reason.
- Use compact controls and other Form Palette properties only when the exact registered capability lists them; do not claim exact font-size control unless the API provides it.

## 5. Generate the canonical ProductDefinition

- Do this only after the user starts work on a specific catalog service and explicitly approves the analysis for that service.
- Write one valid JSON file under `products/` named for the user-facing service.
- Follow the exact current ProductDefinition schema. Do not add policies, capabilities, template context, or properties absent from the contract.
- Preserve unrelated IDs, order, fallback mappings, quantity templates, field relationships, notices, and metadata when making a targeted edit.
- Keep per-service status in `catalog.json`; do not embed uncertain catalog claims into the product.
- Include any site-specific IDs only with an explicit source scope in the analysis.

## 6. Validate and reconcile

- Run JSON parsing first, then the smallest meaningful static checks: schema shape if available, unique IDs, all relationship targets exist, every handler reference belongs to the intended registry, fallback targets are compatible, required inputs exist, and capability visibility references are valid.
- Compare the generated definition against the raw source and the previous definition. Review every changed mapping and every removed handler.
- If the Builder validator is available and is actually run, record its exact result and version/context. Otherwise say `Builder validation: not run`.
- Fix validation errors by tracing them to a stale/missing reference or unsupported contract feature; do not delete the feature blindly. Update analysis and the catalog's statuses after repair.
- A product may be called validated only at the level actually completed. Static checks do not imply Builder acceptance, renderer correctness, or live service availability.

## 7. Close out

- Update catalog statuses and evidence links.
- Save the approved analysis, decisions, mapping reconciliation, and QA results in `analysis/<service-slug>/`. Keep `examples/` for completed references only; do not put current service work there.
- Summarize what changed, what evidence supports it, unresolved questions, and validation actually performed.



