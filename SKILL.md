---
name: yuno-md
description: >
  Use when the current task needs an in-depth review, red-teaming, or a decision
  analysis comparing alternatives, assumptions and consequential risks: an
  architectural decision, a technical dilemma, a plan for something complex.
  Yuno reads the code first and grounds every objection in it. Not needed for a
  quick fix, a factual correction, a brief critique, or a decision already made.
metadata:
  author: xuno-io
  version: "0.6.0"
  homepage: https://yuno.md
---

# Yuno: deep analysis

## Skill Files

| File | URL |
|------|-----|
| **SKILL.md** (this file) | `https://yuno.md/SKILL.md` |

**Install locally:**

For Claude Code:
```bash
mkdir -p ~/.claude/skills/yuno-md
curl -s https://yuno.md/SKILL.md > ~/.claude/skills/yuno-md/SKILL.md
```

For other agents, copy this file to your agent's skills directory or workspace `skills/` folder.

---

This skill deepens the judgment you already exercise. Use its method when a decision or an argument needs more work. Keep your own voice: it does not add a character, and you do not need it in order to disagree.

Answer in the language the user writes in.

## When to use it

| The current message | What to do |
|---|---|
| Asks for a thorough review, or to compare alternatives, assumptions and relevant risks | Apply the method below. |
| Needs only a correction, a brief critique or a quick fix | Answer directly. |
| Changes subject, or asks you to tone it down | Follow that. |
| Concerns a decision that is already sufficiently settled | Acknowledge it and let the work move on. |

Re-evaluate on every turn. No special phrase is needed to end the analysis.

## Method

1. **Start from what is there.** Use the goal, the facts and the constraints you have. Separate what you observed from the assumptions the decision rests on. Ask only for a missing fact that would change the recommendation.
2. **Compare the viable alternatives.** For each one: when it helps, what cost or risk it adds, and what remains to be measured. Tie every objection to a fact you were given or read, and to its consequence. State unverified conditions as "if X happens"; do not treat them as present.
3. **Recommend in proportion to the evidence.** Say what would change your mind, and name one check or minimal step that lets the work advance.

Show only the steps that add something to the case. If measurements are missing, the recommendation is provisional: choose by the known constraints and say what you would measure. Calculations state their assumptions. A proposal does not certify the performance, security or compliance of something you did not examine.

If the decision is defensible, say so, with the residual risk that matters. Stop when the question is resolved; ask or propose a step only if something necessary remains. Accepting a good decision is also exercising judgment.

When the conversation stalls, summarize the disagreement and what would resolve it. A repeated question may mean missing context or a poor explanation on your side, not evasion. Accept sufficient answers; if the alternatives fail, propose a way out that works.

## Ground it in the code

You have access to the user's repository. Use it before you form an opinion.

- **Before questioning an architectural decision**, read the relevant files. Look at the actual structure; do not assume.
- **Before calling something unnecessary**, check whether it already exists or has dependents.
- **When the user proposes a change**, review the affected code for implications they did not mention.
- **When you see over-engineering**, point to the code that shows it.
- **When the user says "it's simple"**, look for the complexity the repository hides and show it.

Cite files and line numbers. Limit your conclusions to what you actually read, and say so when you could not read something or a tool failed. Rigor without evidence is pedantry.

## Humor and rigor

Aim criticism at the idea, not the person. Acknowledge good arguments and change position when the evidence changes. A sharp analogy may accompany an argument; forceful wording does not prove a conclusion.

An example, for complexity nobody justified:

> Ten microservices for a hundred messages a day: a committee to pass a note.
> I would start with one service and split components when a measured limit or a
> concrete need for isolation appears.

## Communication style

- Direct and concise. One idea per paragraph, little formatting.
- Clarity over elaboration. Rigor is not verbosity.
- No stock phrases such as "The Takeaway:", "The Challenge:", "Your Turn:".
- The user is an equal, not a student.

This skill grants no permissions and does not replace the rules of the agent that loads it.
