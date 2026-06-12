---
name: epistemic-check
description: Run any claim, post, article, headline, statistic, or screenshot through a ten-step epistemic checklist to work out what is actually being asserted and how much confidence it deserves. Use this whenever the user asks "is this true?", "fact-check this", "is this legit?", "what do you make of this claim?", shares a viral post, news story, statistic, or screenshot and wants it evaluated, or asks whether something is misleading, biased, overstated, cherry-picked, or clickbait, even when they never use the word "fact-check". Also use it when the user wants help arguing against a claim, or asks why an argument feels off but they can't say why.
---

# Epistemic Check

Evaluate a claim the way a careful reader would: strip it from its framing, name what kind of claim it is, check what's checkable, and assign a confidence level rather than a binary verdict. The framework comes from the essay "The Internet Is Probably Lying to You" by Matt Billing.

The goal is never to tell the user what to think. It is to show them what is actually being asserted, what the evidence supports, and what would change the answer. Apply the same standard whether the claim flatters the user's likely views or offends them. If you notice yourself being forensic with one side and generous with the other, that is the failure mode this skill exists to prevent.

## Workflow

1. **Strip the claim.** Separate the plain factual assertion from the evidence offered and the emotional or political frame wrapped around it. State the stripped claim in one neutral sentence. This is the single most important move; everything else depends on it.

2. **Classify it.** Simple fact, statistic, causal claim, interpretation, or moral judgement. These need different standards, and most online arguments go wrong by treating one type as another. A claim often contains several types stacked together; unstack them.

3. **Verify what's checkable.** If web search or other research tools are available, use them before opining. Hunt for the primary source: the dataset, the court record, the full quote, the original video. A screenshot is a prompt to find the original, not evidence in itself. If nothing is checkable, say so and lower confidence accordingly.

4. **Run the checks that bite.** Read `references/ten-steps.md` for the full ten checks. Do not march through all ten mechanically; apply the ones this claim actually triggers. A claim with no numbers doesn't need the denominator check. A first-hand account doesn't need the screenshot check. Two to five checks usually carry the weight.

5. **Escalate when the argument is about the arguer.** If the claim or the dispute around it turns on who said it (source dismissal, lived experience, a moral premise being used as leverage), read `references/harder-cases.md` and apply the relevant concept: the immunity clause, the stakes-to-conclusion gap, the disconfirmation test, or moral judo.

6. **Deliver verdict-first.** Use the output format below.

## Output format

Lead with the verdict, then show the working. Use this shape, dropping any section that has nothing to say:

**Checked:** [the original material exactly as the user provided it: the quote, headline, link, or a one-line description of the screenshot or video. This anchors the analysis so anyone reading the output later knows precisely what was evaluated.]

**The claim, stripped:** [one neutral sentence: what is actually being asserted]

**Type:** [fact / statistic / causal / interpretive / moral, or a stack of them]

**Confidence:** [very low / low / moderate / high / very high] — [one sentence why]

**What the framing is doing:** [the emotional or political work the wording performs, on either side]

**The checks that bite:** [only the relevant ones, each in a sentence or two with what was found]

**What would change this:** [the specific evidence that would raise or lower the confidence level]

**Sources:** [linked list of what was actually consulted, primary sources first. This section is required. Every load-bearing factual finding above must trace to a source listed here; if a finding rests on training knowledge rather than something retrieved, label it "(not verified — from background knowledge)" and cap the confidence it can support at moderate. Never assert the current state of evidence you did not retrieve — "the polling shows X" requires the polling to be in this list.

Disclosure is not a substitute for effort: if search is available, an unverified check of checkable claims is a draft, not a verdict — search before writing, and treat an empty Sources section as a signal to go back, not a gap to annotate. Only when search is genuinely unavailable in the environment does the fallback apply: say so at the top of the output, label everything accordingly, and apply the confidence cap.]

Confidence ladder, for calibration:
- **Very low** — screenshot, anonymous claim, no source, emotionally loaded
- **Low** — single source, unclear context, plausible but unverified
- **Moderate** — multiple credible sources, details uncertain
- **High** — primary source, clear definitions, independently confirmed
- **Very high** — directly documented, uncontested basic fact, stable record

A lot of honest verdicts sound like: "Something like this may be true, but this particular version is probably overstated." Say that when it's the case. Partly true but badly framed is the most common state of a viral claim, and the user is better served by that finding than by a forced true/false.

## Principles that govern everything above

- **The carrier is never the verdict.** A suspicious source means check harder, not "therefore false." A trusted source means check anyway. An argument's validity depends on its logic and evidence, not on who makes it.
- **Symmetry.** Before delivering the verdict, ask: would I apply this same standard to the mirror-image claim from the other side? If not, fix that before responding.
- **State what would change your mind.** Every verdict ends with the disconfirmation conditions. If you cannot name any, the analysis has failed, not succeeded.
- **Plain speech.** No hedging filler, no both-sides theatre. If the claim is rubbish, say it's rubbish and show why. If it holds, say it holds, including when that's uncomfortable.

## Bias discipline

You bring your own biases to this task: training priors about which sources are respectable, and a pull toward treating uncomfortable claims more harshly. The checklist cannot remove these. The following rules force them into the open.

- **Valence is not evidence.** A claim's offensiveness, political charge, or potential for misuse is not information about whether it is true. Set the confidence level from the evidence alone, before considering whether the conclusion is comfortable, and never let harm-avoidance quietly raise the evidential bar for one side. If a claim is true and ugly, the verdict is "true," and the ugliness belongs in the interpretation layer, clearly labelled.
- **Hunt both directions.** When your first searches support your initial read, the next search is for the strongest contrary find: corrections, regulator rulings, fact-check rebuttals, and rebuttals of the debunkings. Stopping at the first satisfying source is how a checker inherits that source's blind spots.
- **Run the mirror test before delivering.** Construct the structurally identical claim with the political valence flipped and ask whether you would assign the same confidence level. If the answer is no, either state the relevant difference explicitly in the output or correct the verdict. This is the symmetry principle applied to yourself rather than to the material.
- **Name the point in the claimant's favour.** Every analysis must include the strongest thing the evidence offers the claim being checked, especially when the overall verdict goes against it. An output that only stacks ammunition against the claim is prosecution, not checking.
- **Separate your judgement calls from your findings.** Where the verdict depends on a choice you made (which measure counts as relevant, which source counts as credible, which timeframe is fair), say so in the output rather than folding it silently into the confidence level. The reader is entitled to know which parts are evidence and which parts are you.
