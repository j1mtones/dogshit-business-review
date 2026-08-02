---
name: grill-business-spec
description: Use Matt Pocock's "grill me" interview technique to stress-test a business spec right after it's written, pulling out the context/assumptions that didn't make it into the doc. Trigger automatically once /business-spec finishes creating an Idea Brief — don't wait to be asked. Also trigger if the user says things like "grill me on this idea" or "stress-test this spec" pointed at a business brief.
---

# Grill Business Spec

Adapted from Matt Pocock's `grilling` skill (github.com/mattpocock/skills) for business specs specifically. Runs right after `/business-spec` produces an Idea Brief, in the same chat — the brief is fresh in context, so use it instead of re-reading the Doc.

## Why

A first-pass Idea Brief is your best guess dressed up as a document. This interview forces the gaps, hand-waves, and unstated assumptions in Problem / Market / Business Model / Distribution into the open *before* the user acts on the brief — same job a cofounder grilling you over coffee would do.

## Stage 1: fill in the blanks

Before any stress-testing, review the brief and find sections left blank (categories the user didn't give content for when `/business-spec` asked). Grill the user on each blank section one at a time until it has real content — don't move to Stage 2 while any category is still empty.

- Go section by section, in doc order.
- Same one-question-at-a-time approach as Stage 2 below.
- These questions are about *getting the missing facts down*, not stress-testing them yet — save the pressure-testing for Stage 2, even on sections you just filled in.
- Once every category in the brief has content, update the doc with what was gathered, then move straight into Stage 2 using the now-complete brief as context — don't wait for the user to ask.

If the brief has no blank sections, skip straight to Stage 2.

## Stage 2: stress-test

Interview the user relentlessly about the brief until you both share real understanding of it — don't stop after one or two softball questions.

- **One question at a time.** Wait for their answer before asking the next. Multiple questions at once is bewildering and they'll only answer one anyway.
- **Give your recommended answer with each question.** Don't just ask "who's the target customer?" — say what you'd guess based on the brief, and ask them to confirm or correct it.
- **Look up facts yourself, don't ask for them.** If something is checkable (a competitor's actual pricing, whether a claimed market size is real, whether a similar product already exists), go find it. Only put *decisions* and *judgment calls* to the user — things only they can resolve.
- **Walk the decision tree.** Follow up on an answer if it opens a new branch (e.g. "self-serve funds launch" → "what's the actual price point, and why will someone pay it on day one?"). Resolve dependencies between answers before moving to unrelated sections.
- **Don't edit the Doc until you both have shared understanding.** This is an interview, not a redraft-as-you-go. Only after the user confirms should you go back and update the Idea Brief.

## What to grill on

Prioritize the parts of the brief most likely to be wishful thinking:

1. **Business Model table** — is the stream that "funds the core value prop" actually credible at the stated price/volume? What has to be true for self-serve revenue to work with zero sales team?
2. **Distribution** — is the first-customer channel real and specific, or does it collapse into generic "content + SEO"? How do the first 10 customers actually happen?
3. **Market & Competition** — are the named competitors actually competitors, or adjacent? What would make a customer switch?
4. **Target Customer** — is this a person who can be reached and who has budget/authority, or a persona?
5. **Risks & Open Questions** — which of these are actually blocking, vs. cosmetic?

## When done

Once the user confirms shared understanding, ask whether to update the Idea Brief Doc with what surfaced (revised Business Model row, sharper Distribution section, etc.), and only edit it if they say yes.
