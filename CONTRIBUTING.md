# Contributing to strong-arguments

Thanks for your interest in improving this framework. Here's how to contribute effectively.

## Philosophy First

Before contributing, read [PHILOSOPHY.md](PHILOSOPHY.md). This project optimizes for **truth-seeking**, not persuasion. Contributions should align with that goal.

## What We Welcome

### Better Detection Patterns

The fallacy patterns in `fallacies.json` are starting points. If you've found better linguistic markers or detection hints:

1. Open an issue with examples of the pattern in the wild
2. Show how the new pattern reduces false positives/negatives
3. Submit a PR with updated `patterns` or `detection_hints`

### More Representative Examples

The examples in `fallacies.json` and `examples/argument-domains.json` should feel real. If you have:

- Better example arguments (more realistic, clearer illustration)
- New argument domains we haven't covered
- Real-world cases that demonstrate the concepts

Open a PR. Include the source if it's from an actual debate.

### Translations

The linguistic patterns are English-centric. PRs welcome for:

- Translated pattern sets for other languages
- Culture-specific argumentation patterns
- Non-English examples

### Bug Fixes

If JSON doesn't validate, links are broken, or something is factually wrong—fix it.

## What We're Careful About

### The Core 12 Fallacies

We intentionally limit to 12 high-value fallacies rather than a sprawling taxonomy.

**To add a fallacy, you must make the case for removing one.**

This isn't arbitrary gatekeeping—it's a design constraint. A focused toolkit is more useful than a comprehensive one that's too complex to apply.

If you believe a fallacy should be added:

1. Open an issue (not a PR) first
2. Argue why the new fallacy is higher-value than one of the existing 12
3. Show evidence it appears frequently in real debates
4. Propose which fallacy it should replace and why

### Engagement Scoring Weights

The weights in `engagement.json` affect how arguments get scored. Changes here need justification:

- Why is the current weight wrong?
- What evidence supports the new weight?
- Have you tested it against real examples?

### Philosophy Changes

The epistemic foundations in `PHILOSOPHY.md` are load-bearing. Changes need discussion first. Open an issue.

## How to Submit

### For Small Changes (typos, broken links, formatting)

1. Fork the repo
2. Make your change
3. Submit a PR with a clear description

### For Larger Changes (new patterns, examples, features)

1. Open an issue first to discuss
2. Get agreement on the approach
3. Fork and implement
4. Submit a PR referencing the issue

### PR Expectations

- **Clear description** of what changed and why
- **Test your changes** — JSON should validate, links should work
- **One concern per PR** — don't bundle unrelated changes
- **Match existing style** — look at how similar content is formatted

## Code of Conduct

This is a truth-seeking project. In discussions:

- Steelman opposing views before critiquing
- Distinguish facts from opinions
- Update when presented with good evidence
- Attack arguments, not people

If you find yourself in a heated debate about a contribution, that's a sign to slow down and check if you're in performance mode or learning mode.

## Questions?

Open an issue with the "question" label. We'll do our best to respond thoughtfully.

---

*Remember: the goal is not to win arguments about the argument framework. The goal is to make the framework better at helping people think clearly.*
