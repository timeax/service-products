# Service analysis archive

This folder stores the source-backed analysis for each actual service before its ProductDefinition is created or changed.

## Review process

1. Analyze the requested service in the chat first. The chat is the primary place for the breakdown, discussion, and corrections.
2. Save the same readable analysis under `analysis/<service-slug>/` so the site owner can review the evidence and decisions later.
3. Include the current catalog entry, the service's complete handler-ID map, mapped IDs resolved against `handler services.json`, relevant rows missing from the map, variant viewpoints, field/capability plan, source conflicts, assumptions, and open decisions.
4. Wait for the user's explicit approval of that analysis before creating or editing `products/<service>.json` or making related catalog progress changes.
5. After implementation is approved and completed, update the analysis record with the decisions taken and validation actually performed.

Use dated files or revision sections to preserve material analysis changes and previous decisions. Mark unapproved analyses clearly. Do not store actual service analysis in `examples/`; that folder is for completed/reference work only.
