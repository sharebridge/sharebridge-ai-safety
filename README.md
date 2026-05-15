# sharingbridge-location-safety

> Locality safety assessment for donor–seeker field flow (rule-based MVP)

## Overview

This repository is the **Location Safety Service** for SharingBridge. It answers whether delivery at a given **lat/lng** is reasonably safe and practical (BRD step 4 — Quick Safety Check).

**Not an LLM service.** For LangChain / instruction generation, see `sharingbridge-ai-orchestration`. This repo uses **rule-based scoring** with external geo APIs (maps, places, daylight, historical signals) per the architecture doc.

**Planned public API:**

- `POST /v1/safety/assess` — body: `{ lat, lng, timestamp }` → `{ safety_score, is_safe, breakdown }` (threshold ≥ 0.65)

**Key responsibilities (MVP):**

- Traffic / congestion signals (e.g. Google Maps)
- Time-of-day / daylight scoring
- Location type (e.g. Places API)
- Historical delivery success rate at location (internal data)
- Caching and API cost guards

Custom ML training is **optional at scale**; MVP does not require TensorFlow/PyTorch.

**Technology direction:** Node.js or Python HTTP service; PostGIS or equivalent for geo history when wired to Postgres.

## Coordination docs

- Bootstrap checklist: [MVP_BOOTSTRAP_ISSUES.md §8](https://github.com/sharingbridge/sharingbridge/blob/main/development/MVP_BOOTSTRAP_ISSUES.md) (`sharingbridge-location-safety`)
- AI module map (vs orchestration / photo): [AI_PLATFORM_INTEGRATION.md](https://github.com/sharingbridge/sharingbridge/blob/main/development/AI_PLATFORM_INTEGRATION.md)
- End-to-end workflow: [SharingBridge_End_to_End_Workflow.md](https://github.com/sharingbridge/sharingbridge/blob/main/design/SharingBridge_End_to_End_Workflow.md)

For overall project context, see the [main SharingBridge repository](https://github.com/sharingbridge/sharingbridge).

## Repository status

🚧 **Status:** Initial setup (README + license; service code not started)  
📅 **Renamed:** `sharingbridge-ai-safety` → `sharingbridge-location-safety` (slug reflects rule-based geo safety, not LLM)

## Getting started

> Service bootstrap coming next — see coordination repo bootstrap §8.

## Contributing

See the [main repository's CALL_FOR_CONTRIBUTORS.md](https://github.com/sharingbridge/sharingbridge/blob/main/development/CALL_FOR_CONTRIBUTORS.md).

## License

MIT — see [LICENSE](LICENSE).

---

Part of the [SharingBridge](https://github.com/sharingbridge/sharingbridge) ecosystem
