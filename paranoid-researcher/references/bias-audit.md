# Bias Audit

A bias you have named is not a bias you have fixed. Each row pairs the bias with
the specific action that neutralizes it. Run this at least once mid-research and
once before the report leaves.

## Contents

1. The audit table
2. Search in the negative voice
3. The two-line rule
4. Source diversity check
5. Red-team prompts
6. Audit output block

## 1. The audit table

| Bias | How it shows up in research | Detection question | Countermeasure |
|------|----------------------------|--------------------|----------------|
| Confirmation | You searched the words that would prove you right | Did any search intend to disprove? | Run the Falsify stage on every load-bearing claim |
| Selection | Every source agrees; all from one community, vendor, or era | Who would disagree, and did I read them? | Deliberately fetch the strongest critic |
| Availability | The top three results become the answer | Are these ranked by quality or by SEO? | Search beyond page one; go to primary directly |
| Anchoring | The prior written first survives unchanged | Which claim did I abandon? | List every prior that died; zero is suspicious |
| Authority | "A senior engineer said so" | Does the source own the claim, or just have status? | Trace to the artifact, regardless of who said it |
| Publication bias | Only the successes are documented | Where are the failures? | Look for postmortems, retractions, "we reverted" |
| Survivorship | You studied the tools that lived | Which equivalent options died quietly? | Ask what failed and why, not just what worked |
| Recency / novelty | Newest version or newest hype wins | Is newer also better here, or just newer? | Check the older source for what the new one dropped |
| Vendor interest | The benchmark is from the company that sells it | Who paid for this evidence? | Seek a disinterested test, or label the interest |
| Fluency | Clear, confident writing reads as true | Would this convince me without the prose? | Judge the method, not the writing |
| Base-rate neglect | A vivid case overrides the general pattern | What usually happens? | State the base rate before the example |
| Sunk cost / ego | Your earlier answer is being defended | Am I researching or litigating? | Adopt the strongest counter-hypothesis and argue it |

## 2. Search in the negative voice

The single highest-yield habit. For any claim `X`, run the searches that would
surface its failure:

- `X problems` / `X limitations` / `X drawbacks`
- `X doesn't work` / `X not working`
- `X vs <alternative> benchmark`
- `X migrated away` / `we reverted X` / `X postmortem`
- `X issue tracker` + the exact feature
- `X retraction` / `X erratum` / `X was wrong`
- `site:github.com <repo> issues <feature>`
- `<X> 2026` when the topic moves

For every positive claim, at least one search must be phrased so that a true
negative would appear in the results.

## 3. The two-line rule

Anything decisive needs **two independent lines of evidence**.

A line is one of: primary documentation, source code, a measurement you ran, a
first-party dataset, a practitioner report from someone with no stake, or a
systematic study. Two lines are independent when they share no origin, author,
dataset, or incentive.

If you only have one line, say so, and downgrade the confidence in that claim.
Do not launder one line into two by finding another summary of it.

## 4. Source diversity check

Fill the left column before drafting. Empty rows are the audit's answer.

| Line of evidence | Present? | Origin | Stake |
|------------------|----------|--------|-------|
| Primary spec / docs (correct version) | | | |
| Source code or raw data | | | |
| Direct measurement or reproduction | | | |
| Practitioner account (unaffiliated) | | | |
| Credible critic / failure report | | | |
| Historical or base-rate view | | | |

Minimum for a decisive claim: primary + one independent line + one attempt to
find the critic. Missing the critic row is the most common audit failure.

## 5. Red-team prompts

Answer these in writing before the report, even briefly:

1. **The hostile reviewer:** "What is the single sentence here that a domain
   expert would call naive?" Fix it or cut it.
2. **The opposite conclusion:** "What evidence would a smart person cite to
   conclude the reverse?" If you cannot produce it, you have not read enough.
3. **The hidden condition:** "Under what condition is my answer false?" Put that
   condition in the report.
4. **The stale fact:** "Which of these was true eighteen months ago and might
   not be now?" Re-check it.
5. **The borrowed certainty:** "Which claim am I confident about only because a
   confident person wrote it?" Trace or demote it.
6. **The missing voice:** "Whose experience would contradict this and is absent
   from my sources?" Go find one.

## 6. Audit output block

Paste this into the research log, filled in. It is the evidence that the audit
happened rather than being announced.

```
Bias audit — round <n>
Prior at risk: <the belief research could have confirmed>
Negative searches run: <queries>
Strongest critic read: <source + what it argues>
Claims killed: <row numbers>
Claims demoted for single-line evidence: <row numbers>
Conditions under which the answer fails: <list>
Unaddressed: <what the audit found and you could not fix>
```
