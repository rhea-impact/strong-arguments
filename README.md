# strong-arguments

A framework for AI systems to make and evaluate arguments. Truth-seeking, not persuasion.

> **Start here:** [PHILOSOPHY.md](PHILOSOPHY.md) — The epistemic foundations. Why truth-seeking matters, what can go wrong, and how AI should approach argumentation.

## Why This Exists

AI systems have asymmetric persuasion capabilities. An AI optimizing for "winning" arguments will exploit human cognitive biases. That's bad even when the conclusions are correct.

This framework optimizes for **truth-seeking**: arguments should be strong because they're *true*, not because they're *persuasive*.

## Approach

Two-layer evaluation:

1. **Engagement scoring** — First, assess if the argument is worth engaging with. Steelman the position. Is this person arguing in good faith?
2. **Fallacy detection** — Only if engagement score passes, analyze for specific logical fallacies.

Rather than a sprawling taxonomy of 100+ fallacies, we hard-code detection for **12 high-value patterns** that appear constantly in real debates.

## Layer 1: Engagement Scoring

Before investing effort in detailed analysis, assess whether the argument is worth engaging with.

**Positive signals** (add points):
- Steelmanable position — can you reconstruct it as something smart people might believe?
- Specific, falsifiable claims
- Acknowledges tradeoffs
- Responds to actual points made
- Asks clarifying questions
- Willing to update on evidence

**Negative signals** (subtract points):
- Motte-and-bailey (retreating to weaker claims when pressed)
- Moving goalposts
- Sealioning (bad-faith question loops)
- Emotional escalation
- Gish gallop (quantity over quality)
- Kafka traps ("your denial proves guilt")
- Pure signaling (performing for an audience)

**Score interpretation:**
| Range | Action |
|-------|--------|
| 0-3 | Don't engage. Trolling, venting, or signaling. |
| 4-5 | Borderline. Clarify intent first. |
| 6-7 | Worth substantive response. |
| 8-10 | Strong good-faith argument. Prioritize. |

## Layer 2: The Core 12 Fallacies

| ID | Fallacy | One-liner |
|----|---------|-----------|
| `straw-man` | Straw Man | Misrepresenting a position to attack it |
| `hasty-generalization` | Hasty Generalization | Broad conclusion from few examples |
| `appeal-to-ignorance` | Appeal to Ignorance | "No proof" ≠ "disproven" |
| `false-analogy` | False Analogy | Comparison where key features differ |
| `false-dilemma` | False Dilemma | Only two options when more exist |
| `circular-reasoning` | Circular Reasoning | Conclusion assumed in premises |
| `appeal-to-authority` | Appeal to Authority | Expert said it, so it's true |
| `ad-hominem` | Ad Hominem | Attacking the person, not the argument |
| `red-herring` | Red Herring | Distracting from the main point |
| `correlation-causation` | Correlation ≠ Causation | Co-occurrence treated as cause |
| `appeal-to-tradition` | Appeal to Tradition | "We've always done it this way" |
| `equivocation` | Equivocation | Shifting word meanings mid-argument |

## Usage

### Load the ruleset

```python
import json

with open("fallacies.json") as f:
    ruleset = json.load(f)

for fallacy in ruleset["fallacies"]:
    print(f"{fallacy['id']}: {fallacy['name']}")
```

### Agent integration

For each argument your agent handles:

1. **Extract** the main claim(s) and premises
2. **Pattern match** against `patterns` for candidate fallacies
3. **Verify** using `detection_hints` to reduce false positives
4. **Report** with a diagnostic using `rewrite_hint`

Example output:
> ⚠️ **Possible hasty generalization**: Concluding about *all* AI coding agents from a single team's experience. Consider scoping the claim to match the evidence.

## Files

- `PHILOSOPHY.md` — **Read first.** Epistemic foundations for AI argumentation
- `engagement.json` — Engagement scoring signals and workflow
- `engagement-schema.json` — JSON Schema for engagement scoring
- `fallacies.json` — The 12 fallacy definitions with patterns, hints, and examples
- `fallacy-schema.json` — JSON Schema for fallacy definitions

## Contributing

PRs welcome for:
- Better detection patterns
- More representative examples
- Additional languages (translations of patterns)

Keep the core set at 12. If you want to add a fallacy, make the case for removing one.

## License

MIT

## References

- [Scribbr: Logical Fallacies](https://www.scribbr.com/fallacies/logical-fallacy/)
- [Philosophy A Level: Informal Fallacies](https://philosophyalevel.com/posts/informal-fallacies-examples/)
- [IEP: Fallacies](https://iep.utm.edu/fallacy/)
- [SynthCog: Logical Fallacies](https://www.synthcog.blog/p/logical-fallacies)

---

*A [Rhea Impact](https://rheaimpact.com) open-source project.*
