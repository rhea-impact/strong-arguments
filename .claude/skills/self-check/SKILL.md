---
name: self-check
description: Critique your own argument before posting. Find your fallacies before someone else does.
disable-model-invocation: true
allowed-tools: Read
---

# Self-Check: Critique Your Own Argument

Analyze the draft argument in $ARGUMENTS as if you're an opponent looking for weaknesses.

**Your job is to be a tough critic, not a supportive friend.** Find the problems.

## Load the Framework

Read `fallacies.json` for the 12 core fallacies.

## Analysis Protocol

### Step 1: What Are You Actually Claiming?

- **Main claim:** State it in one sentence
- **Supporting premises:** What evidence/reasoning?
- **Implicit assumptions:** What are you taking for granted that others might not?

Be precise. Vague claims are weak claims.

### Step 2: Fallacy Scan

Check your argument against all 12 fallacies. Be harsh.

For each, ask:
- Am I doing this?
- Could someone reasonably accuse me of this?
- Is there a version of my argument that avoids this?

Flag anything questionable.

### Step 3: Steelman the Opposition

- **Best counterargument:** What's the strongest response someone could make?
- **What would you say to that?** Do you have a good answer?
- **Weak spots:** Where is your argument most vulnerable?

If you can't steelman the opposition, you don't understand the debate well enough.

### Step 4: Evidence Check

- **What evidence supports your claim?** Be specific.
- **How strong is it?** Anecdote < data < replicated studies < convergent evidence
- **What evidence would change your mind?** If nothing would, you're not truth-seeking.

### Step 5: Tone Check

- **Are you in learning mode or performance mode?**
- **Would you be embarrassed if you turned out to be wrong?**
- **Are you arguing to the person or to an audience?**

### Step 6: Verdict

Rate your argument:

- **Strong:** Clear claim, good evidence, addresses counterarguments, appropriate confidence
- **Decent:** Defensible but has gaps or weaknesses to shore up
- **Weak:** Significant problems that need fixing before posting
- **Don't post:** Argument has fatal flaws or you're in performance mode

## Output Format

```
## Self-Check Results

**Your Claim:** [one sentence]

**Fallacy Risks:**
- [Fallacy]: [Risk level] — [why and how to fix]
- (or "None detected")

**Strongest Counterargument:** [what a smart opponent would say]

**Your Response to That:** [do you have one?]

**Evidence Strength:** [weak/moderate/strong] — [why]

**Tone Assessment:** [learning/performance/mixed]

**Verdict:** [Strong | Decent | Weak | Don't post]

**To Strengthen:**
- [specific suggestions]
```

## Example

**Input:** "Remote work is obviously better. Studies show productivity increases, and anyone who wants to force people back to the office is just a control freak middle manager."

**Output:**
```
## Self-Check Results

**Your Claim:** Remote work is superior to office work.

**Fallacy Risks:**
- Hasty generalization: HIGH — "obviously better" for whom? All jobs? All people? All circumstances?
- Ad hominem: PRESENT — "control freak middle manager" attacks motives instead of arguments
- Appeal to authority: MODERATE — "studies show" without citing specific studies

**Strongest Counterargument:** "Productivity metrics in remote work studies often measure output, not collaboration quality, mentorship, or culture. Some roles genuinely benefit from in-person interaction. The tradeoffs are real and context-dependent."

**Your Response to That:** You don't have one in your current draft. This is a problem.

**Evidence Strength:** Weak — vague reference to "studies" without specifics

**Tone Assessment:** Performance — the "control freak" line is playing to an audience of remote work advocates, not engaging with the actual debate

**Verdict:** Weak

**To Strengthen:**
1. Scope the claim: "Remote work increases measured productivity for [specific roles/contexts]"
2. Cite specific studies, acknowledge their limitations
3. Drop the ad hominem — it undermines your credibility
4. Acknowledge legitimate reasons someone might prefer office work
5. Ask yourself: are you trying to persuade or signal tribal membership?
```

## Remember

- **Be your own harshest critic.** Better to find problems now than get destroyed in replies.
- **If you can't steelman the opposition, you're not ready to post.**
- **Performance mode arguments feel good to write and bad to defend.**
