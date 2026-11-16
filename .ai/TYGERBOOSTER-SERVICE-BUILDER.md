# TygerBooster Service Builder guide

This is user-provided, host-specific context for building services in TygerBooster. Use it alongside the current Service Builder and DGP contracts. It describes how TygerBooster normalizes JAP's raw provider services; it is not a substitute for the active handler registry or the canonical ProductDefinition contract.

## About JustAnotherPanel

JustAnotherPanel (JAP) is an SMM panel platform where providers expose services such as followers, likes, views, comments, subscribers, website traffic, SEO, and other digital engagement products. A raw JAP service can include a name, category, type, minimum and maximum order quantities, rate, refill support, cancellation support, drip-feed support, and service-specific requirements. JAP exposes services through an API for retrieving the provider list and placing orders.

## Raw provider services and normalized services

A raw provider service is an individual service returned by the provider API. Examples might include Instagram Likes Fast, Premium, Refill, Worldwide, USA, or HQ. The provider stores and sells these as separate rows; TygerBooster Service Builder organizes compatible rows into a clearer administrator and customer ordering experience.

A normalized service may combine multiple provider rows, meaningful options, reusable input fields, conditional fields, compatibility constraints, fallbacks, and mappings from customer selections to provider services. The goal is to represent how an order should work, rather than reproduce provider category names or list every raw row as a storefront service.

## Analysis viewpoints

For each service, analyze:

- Service intent: what outcome is being ordered and what object it affects.
- Service behavior: single delivery, ongoing/automatic delivery, packages, pacing, or another distinct flow.
- Variations: quality/source claims, geography, audience, account type, refill/retention, speed, or bundled outcomes.
- Inputs: exact provider order type, required and optional API fields, target shape, and Builder control support.
- Relationships: which fields or options select/require/exclude a handler, and which handlers can safely fall back to one another.
- Evidence boundaries: source category text is organizational input, not automatically a customer tag; names and marketing claims do not establish guarantees.

Do not assume every provider row must be mapped. Group only rows whose customer promise, order inputs, and fulfillment behavior are compatible. Keep bundles, ongoing services, and different target objects distinct when combining them would misrepresent what the customer receives.

## Options, fields, mappings, and compatibility

Create customer choices only when the source evidence supports them and each option can be mapped to compatible provider rows. Define reusable fields from the actual required order inputs. Map selections to tags, options, or service selections only using semantics supported by the current Builder contract.

Use compatibility constraints where the current, authorized Builder workflow supports them, so incompatible selections cannot be combined. Fallbacks are alternatives for the same customer promise and input shape; compare service type, target, bounds, bundle contents, capability flags, and other relevant behavior before choosing one. Do not use a fallback to silently change a plain service into a bundle or a different target.

## Policy restriction for this workspace

This host guide describes compatibility policies as a possible Service Builder tool. The user's current Builder capability snapshot separately states that policies are context only and must not be changed or generated. Follow that workspace-specific restriction: note any compatibility issue in the analysis, but do not author, alter, or invent policy requirements unless the user explicitly changes the restriction.

## Source precedence

For actual work, use `catalog-handler-service-ids.json` to find candidate handler row IDs, then resolve and reconcile them against `handler services.json`. The current scoped registry supplies provider facts. The JAP service-type guide supplies host-specific order-input semantics. The live applicable Service Builder/DGP contract supplies ProductDefinition shape and supported controls. This guide supplies normalization principles only. Examples are process references, not current service facts.
