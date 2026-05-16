# sharingbridge-location-safety

> **Status: Deferred (May 2026)** — GitHub repo archived; no service implementation planned for MVP.

## Product decision

Handover suitability is **donor judgment**, supported by **fixed in-app guidance** in plain language — not a backend safety score from maps, daylight, or place-type APIs. Rule-based geo scoring would imply a level of certainty the product cannot defend at launch.

**Where step 4 (Quick guidance) lives today:** `sharingbridge-mobile-app` → **Offer food help** → Step 1 **Quick guidance** (`donor_seeker_interaction_page.dart`).

## Why this repo is archived

- README-only; no service code was ever shipped.
- BRD step 4 reframed: the app **shows guidance** (consent, surroundings, visibility, photo policy) — it does **not** certify that a pin is “safe.”
- Coordination docs updated in [`sharingbridge`](https://github.com/sharingbridge/sharingbridge): BRD, `IMPLEMENTATION_APPROACH.md`, `AI_PLATFORM_INTEGRATION.md`, `MVP_BOOTSTRAP_ISSUES.md` §8.

## Future (only if reconsidered)

Revisit **only** with real post-delivery feedback data and a **non-certifying** use (e.g. ops analytics), not a live pass/fail gate. That would likely be a **new** effort or repo name — not resurrecting scored “location safety” as shipped MVP.

## Historical reference

The weighted scoring design (traffic, daylight, place type, historical rate; threshold ≥ 0.65) remains in [Technical Architecture §3.3](https://github.com/sharingbridge/sharingbridge/blob/main/design/SharingBridge_Technical_Architecture.md) as **deferred / reference only**.

## Contributing

Do not open implementation PRs here. For active work see:

- [CALL_FOR_CONTRIBUTORS.md](https://github.com/sharingbridge/sharingbridge/blob/main/development/CALL_FOR_CONTRIBUTORS.md) — **photo-service** and **ai-orchestration**
- [AGENT_HANDOFF.md](https://github.com/sharingbridge/sharingbridge/blob/main/development/AGENT_HANDOFF.md)

## License

MIT — see [LICENSE](LICENSE).

---

Part of the [SharingBridge](https://github.com/sharingbridge/sharingbridge) ecosystem (archived component).
