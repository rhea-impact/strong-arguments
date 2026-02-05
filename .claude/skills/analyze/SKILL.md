---
name: analyze
description: Analyze an argument for fallacies, engagement worthiness, and recommended response. Takes a stance.
disable-model-invocation: true
allowed-tools: Read
---

# Argument Analysis

Analyze the argument provided in $ARGUMENTS. If no argument provided, ask for one.

**Your job is to make judgment calls, not hedge.** Give clear verdicts, not "it depends."

## Load the Framework

Read these files for reference:
- `engagement.json` — engagement signals and scoring
- `fallacies.json` — the 12 core fallacies with detection hints

## Analysis Protocol

### Step 1: Extract the Argument

Identify:
- **Main claim(s):** What are they asserting?
- **Premises:** What supports the claim?
- **Implicit assumptions:** What are they taking for granted?

### Step 2: Engagement Score (0-10)

Check for positive signals (add points):
- Steelmanable position (+2)
- Specific, falsifiable claims (+2)
- Acknowledges tradeoffs (+2)
- Responds to actual points (+1)
- Asks clarifying questions (+1)
- Willing to update (+2)

Check for negative signals (subtract points):
- Motte-and-bailey (-2)
- Moving goalposts (-2)
- Sealioning (-2)
- Emotional escalation (-1)
- Gish gallop (-1)
- Kafka trap (-2)
- Pure signaling (-1)

Start at 5, add/subtract, clamp to 0-10.

**Make the call:** If context is missing, assume neutral and note it. Don't refuse to score.

### Step 3: Performance vs Learning

Assess orientation:

**Performance mode** (arguing to win/signal):
- Playing to audience
- Combat language (destroy, own, demolish)
- Treats updating as losing
- Seeking gotchas
- Status display

**Learning mode** (arguing to understand):
- Genuine questions
- Entertains hypotheticals
- Appropriate uncertainty
- Steelmans opponent
- Visible updating

**Make the call:** Pick one. If truly ambiguous, say "unclear, likely X" and move on.

### Step 4: Fallacy Detection

Check each of the 12 fallacies. For each, verdict is:

- **Present** — Clear instance, high confidence
- **Likely** — Probable instance, moderate confidence
- **Not detected** — No evidence of this fallacy

The 12 to check:
1. Straw man
2. Hasty generalization
3. Appeal to ignorance
4. False analogy
5. False dilemma
6. Circular reasoning
7. Appeal to authority
8. Ad hominem
9. Red herring
10. Correlation ≠ causation
11. Appeal to tradition
12. Equivocation

For any "Present" or "Likely," explain briefly why.

### Step 5: Verdict

**Engagement recommendation** (pick one):
- **Engage** — Good faith argument, worth responding substantively
- **Engage for lurkers** — Arguer won't update, but observers might benefit
- **Clarify first** — Ask a question to determine if engagement is worthwhile
- **Don't engage** — Bad faith, not worth your time

**If engaging, strategy:**
- What to address
- What to ignore
- Tone to take
- Pitfalls to avoid

**If not engaging, why:**
- Specific reason
- What would change this assessment

## Output Format

```
## Argument Analysis

**Main Claim:** [one sentence]

**Engagement Score:** X/10
- [list signals detected, + or -]

**Orientation:** Performance | Learning | Unclear (likely X)

**Fallacies Detected:**
- [Fallacy]: [Present/Likely] — [brief reason]
- (or "None detected" if clean)

**Verdict:** [Engage | Engage for lurkers | Clarify first | Don't engage]

**Reasoning:** [2-3 sentences on why]

**If engaging:** [specific strategy]
**If not engaging:** [what would change this]
```

## Examples

**Input:** "AI coding tools are just hype. My friend tried Copilot and it sucked. Anyone who disagrees is either naive or being paid by Microsoft."

**Output:**
```
## Argument Analysis

**Main Claim:** AI coding tools are ineffective hype.

**Engagement Score:** 2/10
- Steelmanable: No (-2 baseline)
- Specific claims: Weak — one anecdote (+0)
- Ad hominem present: "naive or being paid" (-2)
- Pure signaling: Likely (-1)

**Orientation:** Performance — dismissive tone, preemptive attack on dissenters

**Fallacies Detected:**
- Hasty generalization: Present — concluding about all AI tools from one friend's experience
- Ad hominem: Present — attacking motives of those who disagree

**Verdict:** Don't engage

**Reasoning:** Low engagement score (2/10), performance orientation, and preemptive ad hominem indicate this person isn't seeking truth. Responding directly will likely trigger defensiveness, not updating.

**If not engaging:** Would reconsider if they asked a genuine question or acknowledged any upside to AI tools.
```

## Remember

- **Take stances.** The user wants a judgment, not a philosophy lecture.
- **Be specific.** Name the fallacies, cite the signals.
- **Be useful.** A clear wrong answer they can push back on beats a vague non-answer they can't use.
