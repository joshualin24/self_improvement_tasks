# Self-Improvement Roadmap: Becoming a Natural Scientist in the Deep Learning Era

> The best scientists of the next decade will be those who can think like a biologist,
> code like an engineer, and reason like a statistician — all at once.

---

## The Core Thesis

Deep learning has not replaced scientific intuition. It has raised the bar for it.
Models can now fit any dataset; the bottleneck is asking the right question, designing
the right experiment, and knowing when a result is real versus an artifact. That is
irreducibly human work — but it now requires fluency with the tools that generate the
data and the models that interpret it.

The goal of this roadmap is **scientific taste + technical depth**, not one or the other.

---

## Phase 1 — Sharpen the Scientific Foundation

**You cannot outsource intuition you never built.**

### What to do

- **Read primary literature obsessively.** Pick one problem (e.g. protein-ligand binding,
  gene regulation, drug resistance) and read every landmark paper in that area from the
  last 10 years. Understand *why* each paper mattered, not just what it found.
- **Reproduce a classic result from scratch.** Take a canonical experiment — a binding
  assay, a mutational scan, a CRISPR screen — and re-derive the analysis from raw data.
  You will find at least one thing the paper glossed over. That gap is where intuition lives.
- **Keep an experiment journal.** Write down predictions *before* you look at results.
  Track how often you are right and why you were wrong. This is the fastest way to
  calibrate scientific judgment.
- **Learn one wet-lab domain deeply.** Even as a computational scientist, understanding
  what an SPR trace looks like, what a gel artifact looks like, or what a failed sort
  looks like makes you dramatically better at interpreting data others generate.

### Metrics for this phase
- Can you explain *why* a published result is surprising, not just *that* it is?
- Can you design a control experiment without being told to?
- Can you spot when a figure is cherry-picked?

---

## Phase 2 — Build Real Deep Learning Fluency

**"I can use the API" is not fluency. Fluency means you know what is happening inside.**

### What to do

- **Implement foundational architectures from scratch.**
  In order: MLP → CNN → RNN → Transformer → Diffusion model.
  Use only NumPy/PyTorch, no high-level wrappers. Train each on a toy dataset until
  you understand every gradient that flows through it.

- **Work through the math.** You need a working knowledge of:
  - Linear algebra (SVD, eigendecomposition, matrix calculus)
  - Probability and statistics (Bayes, KL divergence, variational inference)
  - Optimization (SGD, Adam, learning rate schedules, loss landscapes)
  - Information theory (entropy, mutual information, channel capacity)

  Resources: *The Matrix Cookbook*, Bishop's *PRML*, Goodfellow et al. *Deep Learning*.

- **Read model papers mechanistically.** For every architecture you use (ESM-2,
  AlphaFold, Diffusion, etc.), read the original paper and understand each design
  choice. Why attention and not convolution? Why this loss and not that one?
  Write a one-page summary of what you would change and why.

- **Build something end-to-end.** Train a small model on a real biological dataset —
  not a benchmark, a dataset you care about. Go from raw data to a deployed prediction.
  You will encounter every practical problem: data leakage, overfitting, evaluation
  choices, distribution shift. No tutorial will teach you these.

### Metrics for this phase
- Can you debug a training run that has stalled, exploded, or collapsed?
- Can you explain why a model generalises (or doesn't) to a new distribution?
- Can you read a new architecture paper and implement the key idea in an afternoon?

---

## Phase 3 — Integrate: Become a Model-Informed Experimentalist

**The rarest skill: designing experiments that are informed by models and that
also generate the data models need.**

### What to do

- **Learn the design-build-test-learn loop in depth.** Study active learning,
  Bayesian optimisation, and experimental design (D-optimal, space-filling).
  Know when to exploit a current model and when to explore to improve it.

- **Study a real campaign end-to-end.**
  A directed evolution campaign, a drug optimisation programme, a CRISPR screen.
  Trace how computational predictions influenced experimental choices and how
  experimental results fed back into the models. What was the cycle time?
  What was the bottleneck? What would you automate?

- **Develop a personal evaluation philosophy.** For every model you build, ask:
  - What does this model *not* know that it should?
  - What is the worst way this model could be wrong?
  - What single experiment would most update my belief in it?

- **Collaborate across the boundary.** Work directly with experimentalists.
  Sit in on an assay. Help design a plate layout. Write the analysis before the
  data arrives. The friction at the computational/experimental interface is where
  the most value is created and where most people fail.

### Metrics for this phase
- Have you predicted something that was then confirmed experimentally?
- Have you caught an error in an experimental protocol by looking at the data?
- Can you write a one-page brief for an experimentalist that leads to a good decision?

---

## Ongoing Habits

| Habit | Cadence | Why |
|---|---|---|
| Read 2 papers deeply | Weekly | Stay at the frontier; build a mental model of what is known |
| Reproduce one result | Monthly | Forces honest engagement with methods |
| Write a technical note on something you learned | Weekly | Writing exposes gaps in understanding |
| Contribute to an open-source scientific tool | Ongoing | Forces code quality and collaboration |
| Talk to someone outside your field | Monthly | The best ideas come from analogies |
| Re-read your old predictions and be honest about the failures | Quarterly | Calibration is a skill, not a trait |

---

## Key Mindset Shifts

**From consumer to builder.** Use tools, but build them too. The scientists who shaped
the last decade (Jumper, Altman, Woese, Church) built instruments — conceptual or
physical — that others then used.

**From fitting to explaining.** A model that fits is cheap. A model that explains why
is what moves a field. Always ask: what mechanism does this model encode, even implicitly?

**From individual expertise to integrative reasoning.** The biggest questions now
require connecting genomics, structural biology, pharmacology, and computation. Be
deliberately uncomfortable in fields adjacent to your own.

**From avoiding failure to seeking informative failure.** The most useful experiment
is often the one that rules something out. Design experiments to be wrong efficiently.

---

## Resources

### Foundational texts
- *The Art of Doing Science and Engineering* — Richard Hamming
- *What Is Life?* — Erwin Schrödinger
- *A Mathematician's Apology* — G.H. Hardy (on taste and beauty in reasoning)
- *Thinking, Fast and Slow* — Kahneman (on where scientific intuition goes wrong)

### Technical
- Goodfellow, Bengio, Courville — *Deep Learning*
- Bishop — *Pattern Recognition and Machine Learning*
- MacKay — *Information Theory, Inference, and Learning Algorithms* (free online)
- fast.ai courses (practical fluency before theory)

### Staying current
- bioRxiv / arXiv daily digest in your area
- Papers with Code
- Twitter/X: follow the labs, not the takes
- Attend one conference a year and actually talk to people

---

## A Note on AI Tools

Use them. Use them heavily. But maintain the ability to reason without them.
The scientist who cannot evaluate whether an AI-generated hypothesis is plausible
is not a scientist augmented by AI — they are a scientist replaced by it.

The test: *can you explain, defend, and extend every result you produce?*
If yes, the tool made you faster. If no, the tool made you fragile.

---

*This document is a living roadmap. Update it as you learn what works and what doesn't.*
