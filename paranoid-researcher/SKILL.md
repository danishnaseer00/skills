---
name: paranoid-researcher
description: >
  Research a question until the answer cannot be broken. Keeps a claim ledger,
  traces every load-bearing claim to the primary source that owns it, actively
  tries to falsify it, audits its own bias, and keeps researching until a full
  round changes nothing. Use when the user asks to research, investigate,
  deep-dive, or "find the real story" on a topic; to verify or fact-check
  claims; to run due diligence on a tool, company, market, or decision; to
  compare competing claims; or when they say "don't trust the first answer",
  "be thorough", "keep researching until you're sure", "paranoid", "properly
  research this", or "I need to be sure". Do NOT fire for a single stable
  lookup (just answer it) or for questions with no factual component.
argument-hint: "[question | claim | topic]"
license: MIT
compatibility: any-agent
---

# Paranoid Researcher

Research is the deliberate attempt to prove yourself wrong until nothing you
try works. The first answer you find is a rumor wearing a citation.

The dangerous failure is not the answer that is obviously wrong. It is the one
that is plausible, sourced to something, and wrong by one detail — the version,
the caveat, the sample size, the condition that was left out. Paranoia exists
to catch that one detail.

Paranoia here is aimed at claims, never at people, and it is budgeted: spend it
where the conclusion would change if the claim turned out to be false.

## Persistence

Active for the whole research session. It ends when the satisfaction test
passes, not when the answer starts to feel good — "feeling satisfied" is what a
bias feels like from the inside. If you cannot name the test you passed, you are
not done.

## Write the prior first

Before searching, write down: your current best answer, your confidence, and
what you expect the sources to say. Then spend the first round attacking that
prior. An unwritten prior is a bias you cannot audit; a written one is a
hypothesis with a target on it.

## The loop

Run the stages in order, but expect to loop: a falsification that lands sends
you back to the map, and a bias audit that finds monogamy sends you back to the
sources. Each stage ends on a completion criterion, not on a feeling.

### 1. Frame

Write the question as one sentence. Split it into atomic sub-questions, name the
decision it feeds, and for each sub-question name the evidence that would settle
it. Define every ambiguous term before researching it — half of all disputed
answers are two people researching different questions.

Done when: each sub-question is answerable by evidence, and answering all of
them answers the original question.

### 2. Map the owners

For each sub-question, name the source that owns the answer: the spec, the
source code, the dataset, the paper's own results, the vendor's changelog, the
person who ran the experiment. A summary is a pointer to evidence, never
evidence. When a summary is all that exists, the ledger says so.

Done when: every sub-question has a named owner source and you know where its
primary artifact lives.

### 3. Trace to primary

Read the artifact itself: the doc page at the version in question, the code at
the commit, the table in the paper, the actual API response. Record what it
says, where, and when you read it.

Done when: every load-bearing claim has a provenance chain ending at a primary
source, or carries the `secondary-only` flag.

### 4. Falsify

For each load-bearing claim, ask "what would make this false?" and then go look
for exactly that: the failure reports, the issue tracker, the retraction, the
negative result, the team that migrated back, the benchmark that disagrees.
Search in the negative voice. A claim you only searched support for is a claim
you have not tested.

Done when: each load-bearing claim is either killed (`dead`) or has survived a
named disconfirmation attempt you can describe in one line.

### 5. Audit the bias

Run `references/bias-audit.md`. The three that end most research: confirmation
(you found what you looked for), selection (every source from one camp), and
availability (the first three results — best-SEO'd, not best).

For anything decisive, require two independent lines of evidence. Independence
means not copying the same origin; two summaries of one press release are one
source with two URLs.

Done when: every bias in the audit has a countermeasure you actually applied,
not one you acknowledged.

### 6. Saturate

A round is one full pass over every open sub-question. A round that produces no
new claim, no new contradiction, and no source that changes the ledger is
saturation. Until then, keep going: unanswered sub-questions first, then the
strongest challenge to the current answer.

Done when: a full round changed nothing. If your budget runs out first, stop
anyway and write the gap register — a declared gap is honest, an invented
answer is not.

### 7. Kill the report

Read your own draft as a hostile reviewer whose only goal is to find the
sentence that makes the whole conclusion wrong. Re-check every number, quote,
version, and citation against the ledger. Then check the inference: does the
evidence support the claim, or merely sit next to it?

Done when: no attack remains that would change the verdict. Any attack you
cannot answer goes into the report, not out of it.

## The claim ledger

Every conclusion in the final answer traces to a row: claim, status, source,
provenance, confidence, last challenged. Statuses are `open`, `supported`,
`contested`, `dead`, `secondary-only`, `unknown`. A conclusion with no row is a
guess in a suit.

Schema, independence test, and a worked ledger: `references/claim-ledger.md`.

## Contradictions resolve by rank, never by average

Order of precedence: directness (did the source measure it, or repeat someone
who did) → ownership (does this source own the claim) → recency (only for
moving targets) → independence (two copies of one origin are one source).
Record the reason. If it still will not resolve, mark it `contested`, say what
would settle it, and do not pick a winner just to look decisive.

## The satisfaction test

Fully satisfied means all six are true:

- every sub-question is answered, or declared unanswerable with the reason;
- every load-bearing claim is `supported` by a primary source, or flagged;
- a complete round produced nothing new;
- the strongest opposing case is stated and addressed on the merits;
- every contradiction is resolved with a reason, or marked `contested`;
- the draft survived the kill pass.

Passing all six cheaply is the failure mode. A thin ledger does not pass this
test — you are just tired.

## Output

Answer first. Then why it holds, what would change it, what is still contested,
and the gaps. The reader should be able to check you without redoing you.
Templates: `references/report-formats.md`.

## Anti-patterns

| Pattern | Looks like | Reality |
|---------|-----------|---------|
| Paranoia theater | Three more clarifying questions, one source read | Reading is the work, not asking |
| Contrarianism | "Actually, the consensus is wrong" | Breaking a claim takes a primary source, not a mood |
| Citation stuffing | Ten links, none read | One read primary beats ten summaries |
| Infinite research | No ledger, so no stop condition | Saturation is the stop, not interest |
| Source monogamy | Every source from one vendor or community | One origin is one source, however many URLs |
| Summary laundering | Citing a blog citing a tweet citing a changelog | Trace it or flag it |
| Timeline worship | Newest is correct | Newest is only newest |
| Confidence laundering | "Studies show" | Name it or drop it |
| False completeness | Gaps papered over | A gap register is a deliverable |

## Boundaries

- A single stable fact: answer it directly. Ceremony scales with the cost of
  being wrong.
- Research about people: public sources only, and never motive attribution
  presented as fact.
- Medical, legal, financial: this produces research, not advice. Name the
  primary sources and the professional who owns the decision.
- "Unanswerable with available sources" is a result. Report it as one, with what
  would settle it.
- Paranoia is for claims. Never for the user.

## References

| Open when you need to... | Read |
|--------------------------|------|
| track claims, judge independence, resolve contradictions | `references/claim-ledger.md` |
| find and counter the bias in your own research | `references/bias-audit.md` |
| choose an output shape: brief, deep dive, fact-check, contested, gap register | `references/report-formats.md` |
