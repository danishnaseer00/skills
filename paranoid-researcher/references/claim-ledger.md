# The Claim Ledger

The ledger is the research. The report is a rendering of it. If the ledger is
thin, the report is decoration.

Open this when you start recording claims, when two sources disagree, or when
you need to decide whether a claim is load-bearing.

## Contents

1. What earns a row
2. Columns
3. Status vocabulary
4. Provenance rules
5. The independence test
6. Contradiction protocol
7. Ledger hygiene
8. Worked ledger

## 1. What earns a row

Split the answer into **atomic claims**: one assertion each, phrased so it could
be true or false on its own.

> "Vitest is faster than Jest and supports ESM natively" = two rows, not one.

A claim is **load-bearing** when the answer would change if it were false. Only
load-bearing claims need full provenance. The others are decoration, and
decoration is not allowed to sound load-bearing in the final text.

Test: *if I removed this sentence, would the conclusion still stand?* If yes, it
is not load-bearing — keep it short or cut it.

## 2. Columns

| Column | What goes in it |
|--------|-----------------|
| Claim | One testable assertion, no hedging |
| Status | From the vocabulary below |
| Source | Who owns the claim — name, identifier/URL, version or date |
| Provenance | How you know: what you read, where in it, when |
| Confidence | High / medium / low / unknown |
| Last challenged | The disconfirmation attempt, or `none` |

| Weak | Strong |
|------|--------|
| "Docs say it supports X" | "Docs v2.4, §Auth → tokens, read 2026-11-08" |
| "Stack Overflow says it's fast" | "Author benchmark, repo commit a1b2c3, 10k rows" |
| "I remember it being removed" | "Changelog v3.0: 'Removed X'" |

## 3. Status vocabulary

| Status | Means | Exit condition |
|--------|-------|----------------|
| `open` | Recorded, not yet checked | Traced or killed |
| `supported` | Primary source confirms it, provenance recorded | A falsification attempt can still move it |
| `contested` | Credible sources disagree, unresolved | Resolution or declared gap |
| `dead` | Disconfirmed | Stays dead unless new evidence revives it |
| `secondary-only` | Only summaries exist; no primary artifact found | Upgrade or report the limitation |
| `unknown` | No reliable basis either way | Say so in the output |

`dead` and `unknown` are results, not failures. A ledger with only `supported`
rows usually means the falsification stage was skipped.

## 4. Provenance rules

1. End at the artifact: spec, official docs at the relevant version, source
   code, the paper's own data, the first-party changelog, a maintainer's own
   issue comment.
2. A secondary source is a lead. Use it to find the primary; never cite it as
   the primary when the primary exists.
3. Anything that moves gets a version or date. "Supports X" is meaningless
   without which version of what.
4. Quote the exact sentence or number. Paraphrase is where drift enters, and
   drift is how a caveat silently disappears.
5. "I read it" is not provenance. Location plus date is.
6. Memory is `unknown` with a hypothesis attached, until checked.

## 5. The independence test

Two sources are independent only when none of these are shared: origin (one
derives from the other), underlying data, author, funder, or incentive.

Procedure:

1. Follow citations to the origin. Most "multiple sources" collapse to one.
2. Check author and organization overlap.
3. Check who benefits from the claim being true.
4. Prefer a different *method* for the second line: docs plus source code plus
   observed behavior beats three doc pages.

Two summaries of one press release are one source with two URLs.

## 6. Contradiction protocol

Work in order; most conflicts die at step 1.

1. **Same question?** One source may be answering a nearby question. Compare the
   exact claim wording.
2. **Same version, same date?** Behavior changes between versions; check which
   one each source describes.
3. **Who owns it?** The spec owns what the protocol says; a blog owns only what
   the blogger observed.
4. **Measure or repeat?** A measured result outranks a restatement.
5. **Independent?** If one derives from the other, they are not two data points.

Then resolve, and record the reason next to the row. If unresolved: mark
`contested`, state both positions with their provenance, and say what
observation would settle it. Never average two contradictory facts into a safe
middle — the middle is usually false.

## 7. Ledger hygiene

- Update a row's status; do not append a second row for the same claim.
- Keep `dead` rows. They are the record of what you ruled out and why.
- Number the rows, and reference those numbers in the draft. Every concluding
  sentence maps to at least one.
- Keep the ledger in view while drafting. A ledger written after the report is a
  rationalization, not a check.
- Cover every sub-question from the Frame stage. An unmapped sub-question is an
  invisible gap.

## 8. Worked ledger

Question: *Should our Node service migrate from Jest to Vitest?*

| # | Claim | Status | Source | Provenance | Conf. | Last challenged |
|---|-------|--------|--------|------------|-------|-----------------|
| 1 | Vitest supports native ESM without flags | supported | Vitest docs, guide/features | Read 2026-11-08, ESM section | high | Searched GitHub issues for ESM breakage; #4121 is about a plugin, not core |
| 2 | Jest requires `--experimental-vm-modules` for ESM | supported | Jest docs, ECMAScript Modules | Read 2026-11-08 | high | Checked Jest 30 changelog: still required |
| 3 | Vitest runs our suite 2× faster | secondary-only | One blog benchmark | Blog post, no repo, no hardware detail | low | Tried to find the benchmark repo: not published |
| 4 | `jest-to-vitest` codemod handles our custom matchers | contested | Codemod README | README claims "most matchers"; issues report gaps | medium | Issue #88 shows custom matchers unsupported |
| 5 | Migrating is low risk for a 400-test suite | dead | Two postmortems + issue tracker | Read 2026-11-08 | high | Found three reports of silent snapshot format changes |

Consequences for the report: claim 3 cannot be stated as a speedup (blog-only,
unpublished data). Claim 4 is contested and must be reported as such with the
matcher gap named. Claim 5 is dead, so "low risk" comes out of the draft
entirely. The recommendation becomes conditional on matcher inventory, not on
speed — which is the opposite of the prior written before research began. That
inversion is the ledger doing its job.
