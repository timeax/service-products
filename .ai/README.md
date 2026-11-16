# Catalog and ProductDefinition workflow

This project separates its service roadmap (`catalog.json`), actual ProductDefinitions (`products/`), service analyses (`analysis/`), and completed references (`examples/`). Inspect the current contents rather than assuming a folder is empty. Examples guide the method only; actual services must be analyzed from the current catalog mapping and handler registry.

Read these files for the relevant stage:

1. `agent-search.json` — local source paths and which files/packages are authoritative for each concern. Use local package interfaces directly; do not visit the online Gist by default.
2. `service-builder-capabilities.json` — authoritative user-provided Builder capability, field-template, and policy-context snapshot. Policies are context only and must not be changed or generated.
3. `TYGERBOOSTER-SERVICE-BUILDER.md` — host-specific service normalization guidance for raw JAP rows and normalized TygerBooster ordering experiences.
4. `JAP-SERVICE-TYPES.md` — host-specific JAP order fields by `payload.type`.
5. `DATA-MODEL.md` — platform/category/service roadmap and service statuses.
6. `WORKFLOW.md` — how to analyze handler services, create or update the catalog, then later generate a ProductDefinition when requested.
7. `VALIDATION.md` — checks and truthful validation reporting once a definition exists.
8. `../examples/instagram-likes/README.md` — historical analysis method only. Its source registry and definitions are not facts for current services.
9. `../analysis/README.md` — where each actual service analysis is presented in chat and saved for site-owner review before approval and ProductDefinition work.

## Required approval gate

For each actual service, analyze the `catalog-handler-service-ids.json` mapping against the full `handler services.json` registry. Present the detailed analysis in chat first and save it under `analysis/<service-slug>/` for the site owner. Wait for the user's explicit approval before creating or editing the service's ProductDefinition JSON or marking it `in_progress`. Examples are references, not actual service deliverables.
