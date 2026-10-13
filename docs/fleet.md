# Fleet operating policy (this fork)

This fork stays close to upstream. Personal operating policy lives in
user-local config (`setup-pstack` sheet) and in this note, not in forked
code, until a divergence earns a code change. Rationale is recorded per
decision so a future sync can re-evaluate it.

## Reviewer lineup (`interrogate reviewers`)

- Reviewer A: `opus` family at medium thinking. Resolves to
  `openai/gpt-6.1-sol` on the OpenAI table. Verified dispatching.
- Reviewer B: `inherit-parent` (whatever model the session runs,
  currently `muse-spark-1.3-contributor` at xhigh). Family diversity
  with A is what makes the agreement signal real.
- Reserve: `haiku` family (`openai/gpt-6-luna`, high and up) as third
  reviewer or for follow-up probes.

Set via the `setup-pstack` sheet (user-local), not `models.json`:
the generator rejects aliases in role lists, and expressing this in
`models.json` would need an `explicit` tier carried through the Copilot
setup tables. Revisit if a third runtime needs the default in-repo.
Proven by the trial below.

## Evidence

`interrogate` trial on the Maxun `ci/pr-checks-gate` branch, nine
commits, briefed with exact diff range plus six task briefs as
requirement snapshots: 25 findings across two reviewers, agreement on
the three biggest clusters, five Act-ons all confirmed against the
code on re-read. Two-model panel sufficient; nothing wanted a third
reviewer.

## Open

- Routing posture toward house skills (superpowers set): untried.
  Default stays as upstream ships it until a collision is observed.
- Install scope (full extension vs borrowed procedures): undecided.
  No install has been done from any address yet.
- Sync: follow upstream releases; re-run `bun tools/generate.mjs`
  and `bun test` after every sync before pushing.
