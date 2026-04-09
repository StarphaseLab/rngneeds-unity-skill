# RNGNeeds Unity Agent Skill

This repository contains the `rngneeds-unity` agent skill.

It helps compatible AI coding agents give better **RNGNeeds-specific** answers for gameplay randomness in Unity, especially when a prompt involves `ProbabilityList<T>`, `ProbabilityItem<T>`, `PLCollection<T>`, depletable lists, repeat prevention, probability influence, seeding, or debugging surprising pick behavior.

## What it helps with

The skill is designed to improve agent responses for tasks such as:

- choosing the right RNGNeeds mechanic for a gameplay problem
- implementing `ProbabilityList<T>`, `ProbabilityItem<T>`, and `PLCollection<T>`
- handling depletable lists, repeat prevention, and probability influence
- debugging surprising result counts and selection behavior
- explaining RNGNeeds concepts in a designer-friendly way

## Design goals

- favor the correct RNGNeeds mechanic before writing code
- stay grounded in real RNGNeeds API names and behaviors
- avoid generic Unity randomness advice when the problem is specifically about RNGNeeds
- highlight important gotchas such as disabled items still occupying probability space and `PickValue()` returning `default(T)` on failure

## Repository layout

```text
rngneeds-unity/
  SKILL.md
  references/
```

The actual skill lives in the `rngneeds-unity/` folder.

## Local packaging

If you want to build a `.skill` distributable archive locally, run:

```bash
python3 ~/.npm-global/lib/node_modules/openclaw/skills/skill-creator/scripts/package_skill.py ./rngneeds-unity ./dist
```

This creates a packaged artifact in `./dist/`.

## Notes

- This repository is the source of truth for the skill contents.
- The skill itself is intentionally lean: agent instructions in `SKILL.md`, with focused supporting material in `references/`.
- User-facing docs, release notes, and installation pages should live in GitHub Releases or the main RNGNeeds documentation site rather than inside the skill folder.
