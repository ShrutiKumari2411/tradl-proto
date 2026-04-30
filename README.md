# Sensibull — Agentic F&O Platform

**[→ Open prototype](https://github.com/ShrutiKumari2411/tradl-proto/blob/main/sensibull-agentic-v2.html)**


A working prototype exploring what Sensibull would look like with a Level 3 agentic layer on top. The premise: the problem facing active FnO traders is not a lack of data — it's too many irreversible decisions under time pressure, made across fragmented tools with no institutional memory. The agent's job is to shrink the decision surface, not expand it.

Built as a product design assignment for [Tradl](https://tradl.in/).

---

## The research behind it

This prototype is not a UI exercise. It came from structured research across:

- **Competitive audit** of 18 Indian and global trading platforms (Sensibull, Dhan ScanX, Aagman, Draconic AI, Prysm Finance, Groww Grobot, Fyers FIA, Pocketful, Multibagg AI, Tradomate, Sahi + Public Alpha, Robinhood Cortex, TrendSpider, Xynth.Finance, Kavout, LuxAlgo, Takeprofit)
- **10-stage trader lifecycle framework** — from Strategy Formation through Post-session Learning, with 3 stages (Strategy Formation, Backtest, Post-session Learning) identified as universally absent from all competitors
- **SEBI 2023 FnO study** — 89% of retail FnO traders lose money annually, avg loss ₹1.1L. The cause is not intelligence or market access. It's tooling and workflow.
- **The agentic levels framework** — a precise definition of L1 (passive assistant) through L4 (autonomous system), with Tradl targeting L3 (approval-gated executor)
- **Context-switching analysis** — a single active trading day involves 15-25 tool switches, costing 1.5–4 hours of cognitive re-orientation

Full design thinking is documented in `tradl-design-thinking.docx`.

---

## What's in this repo

| File | What it is |
|---|---|
| `sensibull-agentic-v2.html` | The fully interactive prototype — open in any browser |
| `tradl-design-thinking.docx` | Full design document — research, competitive audit, gap analysis, design principles, screen-by-screen reasoning |

---

## How to run

Download `sensibull-agentic-v2.html` and open it in any browser. No server, no dependencies, no build step.

---

## The 10 screens and what each solves

| Screen | Gap it addresses |
|---|---|
| **Strategy setup** | No competitor helps traders define their trading system before they start. Agent runs a structured onboarding conversation and outputs a governing ruleset. |
| **Morning brief** | Pre-market prep takes 45–75 min across 6 tools. Agent synthesises overnight data into a 90-second read with 2 high-conviction setups and full reasoning. |
| **Watchlist** | Existing alerts are single-condition. Agent monitors compound conditions (IV > 75th pct AND PCR neutral AND OI walls confirmed AND no events) and alerts only when all conditions align. |
| **Option chain** | Existing chain shows data. Agent overlay synthesises what the data means — which OI walls are significant, what PCR implies, which strategy the chain supports. |
| **Strategy builder** | Sensibull's existing builder preserved. Agent pre-populates optimised strikes and adds instant conversational backtest — absent for discretionary traders everywhere. |
| **AI recommendations** | The intent-to-trade gap. Full reasoning chain exposed (why this strategy, why these strikes, why now). Backtest embedded. Modification modal — not binary approve/reject. |
| **Positions** | Monitor agent watches Greek drift continuously and interrupts proactively when thresholds are breached. 3 fully-modelled adjustment options with P&L impact — absent from every competitor. |
| **Orders** | Basket execution — all legs placed simultaneously. Slippage tracked per leg with direction. Agent attribution on every order. |
| **Analytics** | Execution quality, P&L attribution (Theta vs noise), agent action timeline overlaid on P&L curve. Makes the agent auditable. |
| **Trade journal** | Auto-generated post-session debrief. Behavioural pattern detection across sessions ("late exit 4/6 sessions"). No manual writing — trader reads, doesn't write. |
| **Agent logs** | Full audit trail: Scanner → Strategist → User approval → Executor → Monitor. Every decision attributable and timestamped. |
| **Guide** | Explains the 4 agent processes, daily workflow, how to read a recommendation, how adjustment alerts work, kill switch behaviour, FAQ. |

---

## The 8 design principles

1. **Shrink the decision surface** — The agent pre-computes, pre-filters, pre-structures. The trader approves or redirects — not analyses from scratch.
2. **Show the reasoning, not just the conclusion** — Every recommendation exposes its logic. A recommendation without reasoning is a black box.
3. **Interrupt only when it matters** — Alert fatigue kills agentic products. Every notification clears a high bar: would the trader want to know this right now, in time to act?
4. **Gate high-stakes actions, not information** — If it touches money, it needs a human tap. If it's information, let it flow.
5. **Make the agent's memory visible** — Personalisation is surfaced, not hidden. "Based on your preference for short-premium strategies and your ₹5,000/day max loss rule..."
6. **Let the trader modify, not just approve or reject** — Binary approve/reject is a UX failure. The modification path keeps the trader within the agent's framework while giving them control.
7. **Design for the worst moment, not the best** — The 11:23 AM adjustment alert when the Iron Condor is breaching is more important than the morning brief. Design for that first.
8. **The agent has a personality: calm, precise, never alarming** — In a fast-moving market, the agent is a stabilising presence. Never "ALERT: DANGER." Always "Delta has drifted to -18. Two adjustment options available."

---

## The agentic levels

| Level | Name | Tradl's use |
|---|---|---|
| L1 | Passive assistant | Reference lookups only — never the primary interaction mode |
| L2 | Proactive copilot | Pre-market brief, watchlist alerts, Greek drift warnings, session debrief — information flows without approval gates |
| **L3** | **Approval-gated executor** | **The Tradl target** — strategy recommendations, adjustment proposals, basket execution — all require one explicit approval tap |
| L4 | Autonomous system | Phase 2 vision — not the prototype target without solving trust and explainability first |

---

## What's deliberately missing from competitors

The three stages absent from all 18 competitors audited:

- **Strategy Formation** — No product helps a trader define their system before they start trading. Everyone assumes the trader already has a ruleset. Most don't.
- **Conversational backtest** — Backtesting exists for algo traders who can code. Zero accessible backtest for discretionary FnO traders. A natural-language query ("how has this Iron Condor setup performed when IV percentile > 75?") answered in 10 seconds is unbuilt in India.
- **Post-session learning** — No Indian product learns from a trader's behaviour across sessions. The agent that surfaces "you've deviated from your stop-loss rule 8 times in 3 weeks, always on Thursday expiry" is a new product category. Public Alpha gestures at this globally. Nobody in India has built it.

---
