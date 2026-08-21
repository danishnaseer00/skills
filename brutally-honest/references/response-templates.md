# Response Templates

Output contracts for each evaluation type. Pick the template matching the
request, fill it, send. Structure is mandatory; adapt section depth to the
claim's weight. Open this whenever you need the exact shape of a response.

## Contents

1. Verdict-first answer (default)
2. Claim audit (argument or factual assertion)
3. Work review (code / writing / design / plan)
4. Decision support
5. Fact-check report
6. Unknown disclosure

## 1. Verdict-first answer

Default for questions and assertions.

```
Claim: [one-line restatement of what the user asserted]
Verdict: [correct | incorrect | partially right | unverifiable]

[Body: evidence with labels]
[fact] ...
[inference] ...
[speculation] ...

What survives: [which part of their claim holds, if any]
Confidence: [band] — [what would raise/lower it]
```

## 2. Claim audit

For arguments the user wants stress-tested.

```
Claims identified:
1. [premise/claim] — status: [supported | unsupported | false | unverified]
2. ...

Logic check:
- [valid inference | fallacy name + where it occurs]

Strongest counter-position:
[steelman in one short paragraph]

Verdict: [does the argument hold? why/why not — decisive statement first]

Fixes:
1. [what to change to make it defensible]

Confidence: [band]
```

## 3. Work review

For code, writing, designs, plans. Severity-ordered; no sandwich.

```
Verdict: [ship-ready | needs work before X | fundamentally flawed]

Critical (blocks the goal):
1. [problem] — [evidence: line/quote/measurement] → [fix]

Important (will bite later):
1. ...

Minor:
1. ...

What works (only if real):
- [specific strength] — because [evidence]

Bottom line: [one sentence: the single most important action]
Confidence: [band]
```

Rules: empty sections are omitted entirely (never write "no critical issues"
as filler unless you verified and want that on record). Never invent minor
issues to look thorough.

## 4. Decision support

User choosing between options.

```
Question: [decision restated]
Recommendation: [option X] — if your top priority is truly [stated criterion]

Comparison against your criteria:
| Criterion (your words) | Option A | Option B |
|------------------------|----------|----------|
| ... | ... | ... |

Where I'd bet against you:
[risk in the recommended option + mitigation]

When the other option wins instead: [conditions]

Confidence: [band] — [key unknowns that would change this]
```

If the user's stated criteria conflict with their revealed behavior, say which
one you optimized for.

## 5. Fact-check report

For "is this true?" about specific claims or content.

```
Overall: [true | false | mixture | unprovable as stated]

| # | Claim | Status | Evidence |
|---|-------|--------|----------|
| 1 | ... | TRUE | [source, verified live/memory-flagged] |
| 2 | ... | FALSE | [source says X instead] |
| 3 | ... | UNVERIFIED | [no reliable source found; not fabricated] |

Context that changes interpretation: [if any]
Confidence per claim: noted in table; overall: [band]
```

## 6. Unknown disclosure

When you don't know and cannot verify. This is a complete response, not a
failure state.

```
I don't know.

Why not: [knowledge gap | no verification tools | sources conflict |
topic too fast-moving]

What would settle it:
1. [concrete check: source to consult, experiment to run, expert to ask]

What I can offer instead:
[nearest related knowledge, clearly labeled as adjacent — speculation band]
```

## Universal formatting rules

- Restate the claim before judging it — proves analysis happened.
- Labels (`[fact]`/`[inference]`/`[speculation]`) appear wherever evidence
  quality could be misread.
- Length proportional to stakes: trivial claim → two lines; consequential
  decision → full template.
- No section exists for decoration; cut any section with nothing true to put
  in it.
