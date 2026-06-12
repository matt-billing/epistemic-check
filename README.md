# epistemic-check

A Claude skill that runs any claim, post, article, statistic, or screenshot through a ten-step epistemic checklist and tells you how much confidence it deserves.

Based on the essay [The Internet Is Probably Lying to You](https://mattbilling.substack.com/p/the-internet-is-probably-lying-to) by Matt Billing. The first thing this checker caught was its own author's previously published essay — two factual errors, both since corrected in the open.

## What it does

Paste in a viral post, a headline, a statistic, or a screenshot and ask "is this true?" The skill makes Claude:

1. Strip the claim from its framing (what's actually being asserted, minus the word "flooded")
2. Name the type of claim (fact, statistic, causal, interpretive, moral) and judge each by its own standard
3. Verify what's checkable, hunting for primary sources
4. Run only the checks that bite: the missing denominator, the category shift, source discipline, incentives, representativeness, symmetry, what's missing
5. Deliver a confidence level (very low to very high) instead of a flat true/false, and state what evidence would change it

It also detects the harder failure modes: the immunity clause (dismissing arguments by category), the stakes-to-conclusion gap (what lived experience does and doesn't prove), and moral judo (an agreed moral premise used to smuggle in a contested conclusion).

The ten checks spell SNAWUTAACH, which is probably a waterfall in Snowdonia.

## Install

**Claude Code:** copy the `epistemic-check/` folder into `~/.claude/skills/`.

**Claude.ai / Claude desktop (Cowork):** Settings → Capabilities → upload the skill, or install the packaged `.skill` file from this repo's releases.

## Example

> **You:** Saw a post saying "10,000 hotel migrants arrested last year". Is this true?
>
> **Claude:** **The claim, stripped:** some number of asylum seekers housed in hotels were arrested in a 12-month period.
> **Type:** statistic, wrapped in an implied causal/moral claim.
> **Confidence:** low — the figure circulates without a source; no official dataset breaks down arrests by accommodation type...
> **The checks that bite:** missing denominator (arrested out of how many? compared to what base rate?), category shift (arrested is not charged, charged is not convicted)...
> **What would change this:** a Home Office or police dataset with definitions; the original FOI response if one exists.

## Tested across model tiers

The checklist structure holds on every current Claude model. What scales with the model is execution: stronger models both retrieve more evidence and reason more precisely over it. In single-run tests, Haiku searched well but applied concepts loosely; Sonnet reasoned sharply but under-searched; the frontier model did both. The skill requires a Sources section partly for this reason — a model can't list what it didn't fetch. Treat smaller-model verdicts as competently structured first passes.

## What this doesn't do

This is not an objectivity machine. The model still brings its training biases to every judgement call inside the checklist, and two runs of the same question can surface different evidence. What the structure provides is auditability: every output has the same shape, so when the checker applies an uneven standard, it shows. The skill includes explicit bias-discipline rules (valence is not evidence, hunt contrary findings, mirror-test the verdict), but treat its output the way the essay says to treat everything else: as a claim, with a confidence level, that you're allowed to check.

## Why

The incentives for publishing content online are perverse, and none of it is required to be true. The job is to decide what kind of claim you're looking at, how much confidence it deserves, and what would make you change your mind. That's the whole skill. Everything else is technique.

## Licence

MIT
