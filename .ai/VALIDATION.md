# Validation and QA checklist

## Static checks

1. Parse JSON with a standards-compliant parser; preserve UTF-8.
2. Check the expected top-level ProductDefinition shape against the exact contract version.
3. Ensure all IDs are unique in their relevant namespaces.
4. Resolve all tag, field, option, button, trigger, relationship, and visibility references.
5. Ensure every referenced handler ID exists in the intended site-specific registry. Confirm its state permits use.
6. Check option bindings and fallbacks for semantic compatibility, valid bounds, required capabilities, and target/package match.
7. Check quantity template fields and root binding against the contract and source evidence.
8. Check that hidden/conditional fields and dependent fields follow the Builder's documented submission behavior.
9. Check catalog paths and status values, and ensure the catalog does not assert more than the evidence.
10. Review a diff against the prior version, particularly removed relationships, handler mappings, and customer-facing claims.
11. Check every field against `.ai/service-builder-capabilities.json`: registered type and variant, cardinality, defaults, allowed UI properties, option support, and multi-value support. A UI `options` property alone does not prove option behavior.
12. If using the saved Quantity template, verify its values and bindings against the target registry and ProductDefinition contract; the template's limits are not universal service limits.
13. For JAP-backed services, reconcile the final order inputs with the selected handler's `payload.type` and `.ai/JAP-SERVICE-TYPES.md`. Confirm required, optional, and conditional fields, list formatting, package quantity behavior, and any TygerBooster control-to-JAP-field translation.

## Builder and runtime checks

- Only mark `builder_validated` after running the intended Service Builder validator on the saved definition. Record the result, date, Builder/schema version, and any errors.
- If the Builder cannot be accessed, write `Builder validation: not run`; do not imply that a JSON parse or local static scan is equivalent.
- Renderer behavior, UI appearance, live availability, provider behavior, and fulfillment must each be claimed only after their corresponding test or evidence.
- For capability visibility, verify a handler with the capability exposes the field and one without it hides the field, and confirm hidden fields are omitted from submission only if the Builder contract promises this behavior.
- The pasted publication-policy snapshot is context only. Do not modify or generate policies. An empty policy array means no policy entries were included in that snapshot; it does not authorize policy creation.

## Reporting

Save the analysis and final validation record under `analysis/<service-slug>/`. Present the analysis in chat before ProductDefinition work and wait for explicit user approval.

State: (a) source snapshot and scope; (b) mapped, stale, and omitted handler IDs; (c) checks actually executed; (d) checks not executed; (e) unresolved mapping/capability questions; (f) current catalog statuses. Never use “fully validated” without naming the validation layers performed.
