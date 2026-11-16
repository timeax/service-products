# Catalog data model

`catalog.json` is the service build roadmap. It shows what the team intends to define, not which ProductDefinitions already exist.

## Structure

```json
{
  "platforms": [
    {
      "name": "Instagram",
      "categories": [
        {
          "name": "Likes",
          "services": [
            {
              "id": "instagram-likes",
              "name": "Instagram Likes",
              "status": "not_started",
              "product_definition_file": null
            }
          ]
        }
      ]
    }
  ],
  "product_definitions": []
}
```

## Catalog rules

- Organize the roadmap as platform → general service category → customer-facing service.
- Derive platform names and service families from the project-root `handler services.json`. Do not add platforms or categories based on general knowledge.
- For a specific catalog service, read its key in `catalog-handler-service-ids.json`, resolve all listed row IDs in `handler services.json`, and find relevant current rows absent from the mapping. The ID map defines lookup candidates, not handler facts or guaranteed complete coverage.
- Normalize provider-specific variants into a service family. For example, quality, geography, speed, refill, and account-type variants can belong to one service family rather than becoming separate product definitions.
- A handler record is a provider fulfillment option. It is not automatically a separate service to build.
- Every service entry has a stable `id`, a readable `name`, `status`, and `product_definition_file`.
- Use `not_started` for every catalog service until definition work actually begins. Leave `product_definition_file` as `null` until the canonical file exists.
- Keep `product_definitions` empty while there are no ProductDefinitions. Do not put example or historical definitions in this list.
- Do not include provider IDs, rates, state, or capability snapshots in the customer-facing worklist. Those belong in source analysis and later handler mapping.

## Status values

- `not_started`: planned in the catalog; no ProductDefinition has been started.
- `in_progress`: the user has started definition work and it is actively being prepared.
- `definition_created`: a canonical JSON exists but has not completed required validation.
- `validation_pending`: definition is ready for Builder validation.
- `validated`: the intended Builder validator accepted the exact definition.
- `blocked`: a specific missing decision or source prevents progress.
- `retired`: the user has removed the service from the work plan.

Changing a catalog status is a progress update, not proof of storefront availability. A catalog item remains a planned service until the user confirms it is offered or a separate source establishes that fact. Analyze each service in chat and save the analysis under `analysis/<service-slug>/`; wait for explicit approval before creating its ProductDefinition or changing related catalog status. See `WORKFLOW.md` for the approval gate.
