# Protocol 03: Data Hygiene & Value Standardisation

## 3.1 String Trimming and Casing Clean-up
Raw manual entries or scraper drops introduce subtle text contamination that breaks database queries or triggers platform messaging syntax bugs. The raw compilation runs yielded three discrete mutations for a single channel:
1. `LinkedIn` (Standard)
2. `Linkedin` (Lower-case mutation)
3. `LinkedIn ` (Trailing space white noise)

## 3.2 Normalization Protocol
Prior to database committing, all structural categorical headers must pass through a normalization pass:
* **Trailing Spaces:** Stripped via systematic whitespace regex trimming (`Text.Trim`).
* **Enforced Categorization:** Evaluated against an uppercase comparison matrix to enforce strict string conformity matching `[LinkedIn, Instagram, Facebook]`.
* **Null Value Handling:** Missing category cells are identified and enriched manually via deep profile bio inspection before file sign-off.
