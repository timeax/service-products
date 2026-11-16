# Service ProductDefinition Workspace

This project is the roadmap for services that may later become ProductDefinitions. It is independent of the TygerBooster repository. Do not add this project to TygerBooster or change that repository's `.gitignore` for this workspace.

## Current project state

`catalog.json` is the service roadmap. Actual ProductDefinitions belong under `products/`; inspect the current contents at the start of each task instead of assuming the folder is empty. `examples/` contains completed/reference work for learning the method only. Never copy an example definition or its service IDs into the actual product workspace.

## Before generating or editing a product

1. Read `.ai/README.md`, `.ai/WORKFLOW.md`, `.ai/DATA-MODEL.md`, `.ai/VALIDATION.md`, and `.ai/agent-search.json`. For TygerBooster service normalization, read `.ai/TYGERBOOSTER-SERVICE-BUILDER.md`; for JAP input fields, read `.ai/JAP-SERVICE-TYPES.md`; for Builder controls, read `.ai/service-builder-capabilities.json`.
2. Inspect `catalog.json` and the target service's entry in `catalog-handler-service-ids.json`. Resolve every mapped row ID against `handler services.json`, and search the registry for relevant rows omitted from the mapping.
3. Read completed references in `examples/` for method only. Do not use their source rows or definitions as facts for the actual service.
4. Inspect the current target site's handler/service registry and its ProductDefinition contract. Treat each registry as scoped to its source site, project, provider account, and snapshot. Never mix service IDs or capabilities from different registries.
5. Analyze the requested service in chat and save the readable, source-backed analysis under `analysis/<service-slug>/`. Wait for the user's explicit approval before creating or editing its ProductDefinition JSON or making related catalog progress changes.
6. After approval, create or update the canonical service JSON under `products/`, preserving identifiers and relationships unless the user authorizes a change.

## Analysis approval gate

For each service, present the analysis in the chat as the primary review and save the same detailed analysis for the site owner under `analysis/<service-slug>/`. Include source evidence, full mapped and omitted handler-ID reconciliation, platform/category/service classification, variant viewpoints, proposed handler mappings, Builder capabilities and field plan, assumptions, conflicts, and unresolved questions. Stop for the user's explicit approval. Until then, do not create or edit that service's ProductDefinition JSON or mark it `in_progress`. Approval applies only to the presented service scope; material source or mapping changes require renewed analysis and approval. Reading sources and preparing analysis do not require approval.

## Handler services source

When the project-root file `handler services.json` is present, inspect it before analyzing or generating products. Treat it as the user's supplied handler-services source for the site/project it identifies, and use its actual records for handler IDs, names, categories, states, limits, rates, and capabilities. First verify the source scope and structure; if its site/project scope conflicts with the product being built or is unclear, preserve the distinction and record the uncertainty rather than mixing registries. Keep the input file unchanged. Do not use the Instagram Likes example or an older fixture to fill missing facts in this source.

`catalog-handler-service-ids.json` is a catalog-key-to-handler-row-ID mapping, not a replacement for handler records. Check each mapped ID against `handler services.json`, flag stale IDs, and independently find relevant current rows omitted from the mapping. Keep root row `id`, `dgp_handler_id`, and provider `external_id` distinct in analysis and ProductDefinitions.

## Source-of-truth order

For the roadmap, use the current project-root `handler services.json` to discover platform and service families. The catalog should show platforms, general categories such as Likes, Followers, Views, Visits, and other categories actually found, then the services to build under each category. It should not contain provider handler rows as if each were a product. For later ProductDefinitions, use the current registry for handler facts and the versioned contract for schema and Builder behavior. Examples teach the method and pitfalls; they do not supply facts for the current catalog.

If sources disagree, do not silently choose. Record the conflict in the product's analysis, preserve the conflicting evidence, and ask for clarification only when it blocks a safe canonical definition.

For Service Builder input types, variants, cardinalities, UI properties, defaults, option/multi support, and field templates, use the user-provided snapshot in `.ai/service-builder-capabilities.json` as authoritative for the represented Builder state. Do not invent support from general knowledge or another package. The publication-policy snapshot is context only: never change or generate policies. Recheck the open Builder if a later task may depend on capabilities changing after the snapshot.

## Local package lookup

Use `.ai/agent-search.json` as the local source index for the handler registry, DGP packages, and Builder repositories. Inspect the actual local manifests, source, declarations, schemas, and package-specific `AGENTS.md` files that apply to the question. Do not visit the online Gist by default; a local `GIST.md` may be used as a navigation overview only and never replaces direct inspection of local package interfaces. Keep package authority concern-specific and keep installed package versions distinct from any other checkout or site-specific handler registry.

## Required discipline

- Do not invent service availability, handler behavior, capabilities, ranges, pricing, provider promises, platform coverage, or Builder validation.
- Do not add unregistered input types, variants, UI properties, option behavior, or multi-value behavior. Check the exact capability entry, including its variant, cardinality, and support flags.
- Distinguish a customer-facing product from backend handler records. Many handlers can implement one product; their count does not prove product availability.
- Catalog status tracks build progress only. Do not imply that a planned service is already a ProductDefinition or a live storefront product.
- Keep provider names and opaque IDs out of customer labels unless that is the deliberate user-facing meaning.
- Treat disabled, locked, restricted, and enabled states exactly as encoded by the intended site's source. A locked handler is not usable or replaceable unless the site contract explicitly permits it. Never infer a lock from an ID, name, or missing record.
- When analyzing the handler source, separate product family from variations such as targeting, quality, speed, refill, and account type. Keep the catalog at the customer service-family level; analyze handler compatibility later during ProductDefinition work.

## Project map

- `handler services.json`: user-supplied source registry; leave it unchanged.
- `catalog.json`: build roadmap organized as platform → general category → service, with status per service.
- `products/`: actual canonical ProductDefinition JSON files; inspect current contents and only change a service after its analysis is approved.
- `analysis/`: per-service analysis presented in chat and saved for site-owner review before ProductDefinition work.
- `.ai/`: repeatable catalog analysis and future definition workflow.
- `examples/`: completed/reference work and method only; never treat it as the current product or handler source.

Keep source snapshots and decision notes with examples. Do not overwrite evidence to make it appear cleaner or newer; add dated/scope notes when refreshing a registry.

Do not turn a word inside a compound source category into a separate platform without explicit platform evidence. For example, `Instagram THREADS Likes` belongs under the Instagram platform's Likes category; retain `Threads` in the service name as the source's qualifier. Preserve the original category string in analysis.


