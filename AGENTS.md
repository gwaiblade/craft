# craft — agent rules

Public repo: reusable personal skills (`skills/<name>/SKILL.md`) and workflow protocols (`protocols/<name>/PROTOCOL.md`). Everything committed here is on public URLs.

## Rules

1. **Public-only content.** No secrets, no references to private repos' contents, nothing identity-adjacent (test: would publishing this expose reasoning, edge, or positioning?). Governing canons: `~/Code/context-brain/governance/CANON_SKILL.md` and `CANON_PROTOCOL.md` — read the relevant one before adding or restructuring any entry.
2. **Folder convention.** One kebab-case folder per entry; the file inside is always `SKILL.md` or `PROTOCOL.md`. Optional companions (`VERIFICATION.md`, `TEMPLATE_*.md`, `EXAMPLE_*.md`) only when the entry needs them.
3. **Adoption discipline.** Adopting an existing document = canonical header block + version history appended; content otherwise intact. Chat-run protocols keep the run document execution-only (run-surface rule); off-run tooling, scoring infrastructure, and rationale go in a companion `VERIFICATION.md` marked never-paste.
4. **Registry rule.** Any protocol added, re-versioned, superseded, or deprecated here also updates `~/Code/context-brain/governance/INDEX_Protocols.md` in the same working session (separate commit in context-brain). Skills are not indexed.
5. **Version hygiene.** Every content change gets a version bump and a 1–2 line version-history entry. Never edit entry content as a side effect of unrelated commits.
