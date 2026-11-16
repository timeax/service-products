# Analysis lessons from the Instagram Likes example

This is historical process guidance only. It does not approve or define the actual current service; see `analysis/` for current service analysis and `products/` for canonical ProductDefinitions.

## Useful analysis distinctions

- One provider category can contain many handler variants; do not copy each row into the catalog as a separate service.
- Keep the platform, general category (Likes, Followers, Views, etc.), and customer-facing service family clear.
- Analyze quality, account type, audience, geography, refill, retention, speed, and bundled outcomes as separate viewpoints. They may be options within one service family or may reveal a genuinely distinct service.
- Keep combined outcomes separate from plain outcomes when they change what is fulfilled.
- Compare quantity limits and capability flags before treating two handlers as substitutes.
- Preserve source wording in analysis; keep future customer-facing names understandable.
- Treat “Other” as a deliberate place for identified unusual service families, not as an unreviewed dumping ground.

## Pitfalls from the earlier design discussion

1. A stale relationship remained after an earlier hierarchy edit. Any future ProductDefinition must resolve references after changes.
2. A parent and its child tags both had service bindings. Check the Builder's selection behavior before using parent and child bindings together.
3. Quality, geographic targeting, audience targeting, speed, retention, and refill are different dimensions. Do not choose fallbacks based on name similarity alone.
4. Promotional labels such as Popular, Recommended, Hot, or Fast are editorial unless supported by actual evidence.
5. The later Builder discussion proposed capability-aware visibility for drip-feed inputs. That is future implementation guidance, not a feature implemented by a current project ProductDefinition.
6. JSON parsing or source review does not equal Builder validation.

Use the root `handler services.json` for all current catalog work. The older 202-row fixture in this folder is not the current registry.
