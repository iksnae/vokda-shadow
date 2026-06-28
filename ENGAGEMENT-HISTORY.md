# Engagement history

Account-manager record of what we delivered and discussed, in order.
- **issues/35-36** — Delivered two SSML tag registry improvements:

1. **Case-insensitive tag lookup** (#35) — `getTagDef()` now matches tag names regardless of casing, so `getTagDef('PROSODY')` and `getTagDef('Break')` both resolve correctly. `isTagSupportedByProvider()` benefits automatically.

2. **Attribute definition lookup** (#36) — New `getAttrDef(tagName, attrName)` helper resolves a single attribute definition from a tag, case-insensitive on both axes. Lets the toolbar and validator fetch an attribute's metadata without scanning `def.attributes` at each call site.

Both shipped with tests and are up for review as PRs #37 and #38.
- **#24** — Delivered per-provider capabilities + JobStatus enum to the public catalog contract (#24). Each provider in `/providers.json` and the OpenAPI spec now exposes `maxTextLength`, `outputFormats`, and `supportsStreaming` — plus a canonical `JobStatus` enum (`completed | pending | failed`). All 24 providers have capability data, the SDK types are updated, and both build and 259 tests pass. PR #39 is up for review.
