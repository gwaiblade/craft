# AGENTS.md — craft

## 1. Build identity

- **craft.** Personal track. Reusable personal skills (`skills/<name>/SKILL.md`) and workflow protocols (`protocols/<name>/PROTOCOL.md`).
- Repo: `gwaiblade/craft` (**public**), local `/Users/mujiri/Code/craft`. Everything committed here is on public URLs.
- No SPEC. Governing canons: `/Users/mujiri/Code/context-brain/governance/CANON_SKILL.md` and `/Users/mujiri/Code/context-brain/governance/CANON_PROTOCOL.md` — read the relevant one before adding or restructuring any entry.

## 2. Local conventions

- **Folder convention.** One kebab-case folder per entry; the file inside is always `SKILL.md` or `PROTOCOL.md`. Optional companions (`VERIFICATION.md`, `TEMPLATE_*.md`, `EXAMPLE_*.md`) only when the entry needs them.
- **Adoption discipline.** Adopting an existing document = canonical header block + version history appended; content otherwise intact. Chat-run protocols keep the run document execution-only (run-surface rule); off-run tooling, scoring infrastructure, and rationale go in a companion `VERIFICATION.md` marked never-paste.
- **Version hygiene.** Every content change gets a version bump and a 1–2 line version-history entry. Never edit entry content as a side effect of unrelated commits.

## 3. Deployment guardrails

None. There is no deploy; a push publishes to public URLs, so ask Henry before every push.

## 4. Repository conventions

- **Public-only content.** No secrets, no references to private repos' contents, nothing identity-adjacent (test: would publishing this expose reasoning, edge, or positioning?).
- gitleaks pre-commit hook (`.pre-commit-config.yaml`, pinned v8.30.1). If a commit is blocked, stop and tell Henry. Never use `--no-verify`.
- **Registry rule.** Any protocol added, re-versioned, superseded, or deprecated here also needs `/Users/mujiri/Code/context-brain/governance/INDEX_Protocols.md` updated (separate commit in context-brain). Ask Henry before editing it from here; without a yes, list the needed INDEX change in your report. Skills are not indexed.

## 5. Known footguns

None.

## 6. Escalate-to-Henry triggers

- Anything that might not pass the public-only test.
- Editing context-brain from this repo (see Registry rule).
