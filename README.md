# Claude Support Ticket Classifier

A Node.js + TypeScript app that classifies customer support tickets using Anthropic's Claude API, matching each ticket to the right model for its complexity.

## What it does

| Ticket type | Model | Task |
|---|---|---|
| Simple | Claude Haiku | Classifies priority (LOW / MEDIUM / HIGH / URGENT) |
| Moderate | Claude Sonnet | Extracts priority, category, key details, recommended action |
| Complex | Claude Opus | Senior-manager analysis: root causes, impact, action plan |

It also runs all three models on the same ticket and compares **latency, token usage and cost**.

## Results (example run)

| Model | Time | Cost |
|---|---|---|
| Haiku | ~1 s | $0.0001 |
| Sonnet | ~2.6 s | $0.0019 |
| Opus | ~24 s | $0.027 |

**Takeaway:** Opus costs ~270× more than Haiku. Routing each task to the cheapest model that can handle it keeps quality high and costs low.

## Skills

TypeScript · Node.js · Claude API · Prompt Engineering · Cost/Latency Benchmarking

## Run it

```bash
npm install
cp .env.example .env   # add your ANTHROPIC_API_KEY
npm start
```

## Credit

Based on an exercise from the Udacity course *Claude Code*. Starter code by Udacity; implementation by Zahra Borzoo.