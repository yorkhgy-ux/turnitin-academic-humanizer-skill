---
name: turnitin-academic-humanizer
description: >-
  Rewrites, polishes, and humanizes academic texts to reduce Turnitin similarity scores
  and bypass AI writing detection (AIGC detection). Use this skill whenever the user asks
  to lower plagiarism/similarity rates (降重), reduce AI detection scores (降AI率 / 去AI味),
  humanize AI-generated drafts, or paraphrase academic papers while preserving scholarly rigor.
---

# Turnitin Academic Humanizer & De-AI Skill

This skill guides the agent to systematically rewrite academic text so that it passes both **Turnitin Similarity Detection (传统查重)** and **Turnitin AI Writing Detection (AIGC检测)** while maintaining rigorous academic tone and original meaning.

---

## 1. How Turnitin Detects Text (Core Principles)

### A. Similarity Detection (查重机制)
* **N-gram & Fingerprint Matching**: Flags 5–8+ consecutive identical words or shared phrase skeletons.
* **Thesaurus-Swap Detection**: Modern Turnitin detects "synonym stuffing" (keeping sentence structure identical while only swapping individual words).
* **Rule**: You must change **syntactic structure and information flow**, never swap technical terminology.

### B. AI Writing Detection (AIGC检测机制)
Turnitin's AI classifier evaluates statistical patterns across two primary metrics:
1. **Perplexity (困惑度 — Word Predictability)**:
   * LLMs consistently choose the highest-probability next token, resulting in low perplexity.
   * Human academic writers use unexpected yet precise collocations, discipline-specific verbs, and varied qualifiers (high perplexity).
2. **Burstiness (突发性 — Structural & Length Variance)**:
   * LLMs produce sentences of uniform length (typically 18–24 words) and uniform complexity (e.g., `Subject + Verb + Object + ", which/thereby V-ing..."`).
   * Human writing exhibits high burstiness: a 32-word complex analytical sentence followed immediately by an 8-word direct conclusion.

---

## 2. Step-by-Step Rewriting Workflow

Follow these four steps sequentially for every paragraph you rewrite:

### Step 1: Structural Reconstruction (破除句式骨架 — 降重核心)
* **Reorder Logic Chains**: Flip `Cause → Effect` into `Effect ← Cause` or `Observation → Mechanism → Implication`.
* **Merge & Split**: Combine two short, choppy sentences into one subordinate clause, or split a bloated compound sentence into two distinct statements.
* **De-nominalization / Verb Shifting**: Convert noun-heavy abstractions (*"The implementation of the algorithm led to an improvement in accuracy"*) into concrete verb-driven clauses (*"Once deployed, the algorithm classified edge cases more accurately"*).
* **Zero 6-Word Overlap**: Ensure no sequence of 6 or more consecutive words matches the source text, **except** fixed technical terms, proper nouns, formulas, or direct quotes.

### Step 2: Inject Burstiness (打破均匀节奏 — 降AI率核心)
* **Enforce Sentence Length Variance**: Within any 4–5 sentence paragraph, include:
  * At least one **short sentence (6–11 words)** for emphasis, transition, or critique.
  * At least one **long, multi-clause sentence (26–38 words)** unpacking complex evidence or methodology.
  * Medium sentences (14–22 words) with varied internal punctuation (parentheses, colons, semicolons—avoid overusing em-dashes `—`).
* **Vary Sentence Openings**: Never start two consecutive sentences with the same grammatical pattern (e.g., avoid `The study...` / `The results...` or `This suggests...` / `This indicates...`).
* **Break Paragraph Symmetry**: Avoid the classic AI paragraph template (`Topic Sentence → Point 1 → Point 2 → "Overall/Thus" Summary Sentence`). End paragraphs on a specific finding, a limitation, or a direct bridge to the next empirical question.

### Step 3: Eliminate AI Vocabulary & Formulaic Patterns (去AI高频词与句型)

#### 🚫 Banned AI Words (Never Use)
| Category | Banned Words / Phrases | Human Academic Alternatives |
| :--- | :--- | :--- |
| **Verbs** | `delve into`, `underscore`, `highlight`, `foster`, `leverage`, `navigate`, `spearhead`, `illuminate`, `unveil`, `bolster`, `harnesses`, `bridging the gap` | `examine`, `test`, `show`, `indicate`, `use`, `apply`, `address`, `measure`, `isolate`, `confirm`, `challenge` |
| **Adjectives** | `pivotal`, `crucial`, `vital`, `paramount`, `multifaceted`, `nuanced`, `intricate`, `comprehensive`, `groundbreaking`, `seamlessly`, `robust` (when overused) | `central`, `key`, `specific`, `complex`, `detailed`, `consistent`, `measurable`, `distinct`, `partial` |
| **Nouns** | `tapestry`, `landscape`, `realm`, `testament`, `beacon`, `catalyst`, `paradigm shift`, `cornerstone`, `interplay`, `synergy` | `field`, `context`, `domain`, `evidence`, `driver`, `change`, `basis`, `interaction`, `relationship` |
| **Connectors** | `Furthermore`, `Moreover`, `Additionally`, `Consequently`, `Nevertheless`, `In conclusion`, `Ultimately`, `Notably`, `Importantly` | Use content-based transitions (*"Building on this threshold..."*, *"Yet these gains disappear when..."*, *"In practice..."*) |
| **Filler Openers** | `It is worth noting that`, `It is important to consider`, `In the rapidly evolving field of`, `Has garnered significant attention` | Delete the filler entirely and state the claim or empirical fact directly. |

#### 🚫 Banned AI Syntactic Templates
1. **Participial Tail Clauses**: Delete trailing `..., thereby V-ing...`, `..., ultimately fostering...`, or `..., highlighting the need for...` at the end of sentences. Replace with a separate clause or a direct active verb.
2. **Symmetric Triads**: Avoid listing three parallel adjectives or nouns in a row (*"efficient, scalable, and reliable"*). Use two specific terms or unpack the actual metric.
3. **"Not only... but also..." / "While X..., Y..." Overuse**: Limit contrastive `"While/Although [Clause A], [Clause B]"` openings to at most once per 300 words.
4. **Em-Dash Summaries**: Avoid `... — a testament to / a clear indicator of ...`.

### Step 4: Inject Human Scholarly Nuance (注入真人学术语感)
* **Semantic Bridging Instead of Mechanical Conjunctions**: Instead of starting a sentence with `"Furthermore,"`, echo a concept from the previous sentence (*"That latency bottleneck becomes even more pronounced under concurrent loads."*).
* **Precise Hedging**: Replace vague AI hedging (*"may potentially have a significant impact"*) with specific academic qualifiers (*"tends to skew estimates upward when sample sizes fall below n = 50"*).
* **Protect Technical Terminology**: Never replace standard domain terms (e.g., *heteroskedasticity*, *transformer attention heads*, *Michaelis-Menten kinetics*) with awkward synonyms. Keep technical nouns intact and rewrite the verbs and logical framing around them.

---

## 3. Before & After Example

### ❌ Original (High AI Rate & High Similarity Risk)
> In the rapidly evolving landscape of renewable energy, solar power has garnered significant attention as a pivotal solution for reducing carbon emissions. Furthermore, the integration of machine learning algorithms into photovoltaic systems underscores the potential for optimizing energy output. While traditional forecasting models offer basic predictions, they often fail to capture the intricate interplay between meteorological variables, thereby limiting grid stability. Consequently, leveraging deep learning frameworks is crucial for fostering a more resilient and sustainable energy infrastructure.

### ✅ Rewritten (Humanized, Low Similarity, High Burstiness)
> Utility-scale solar deployment has expanded rapidly over the past decade, yet grid operators still struggle with the intermittent nature of photovoltaic generation. Conventional statistical forecasters handle clear-sky intervals reasonably well. Under volatile cloud cover, however, linear models miss non-linear interactions among irradiance, humidity, and panel temperature. Deep learning architectures address this gap by learning spatiotemporal dependencies directly from historical sensor logs. When forecasting errors drop, dispatchers can schedule spinning reserves more accurately without overbuilding backup capacity.

---

## 4. Pre-Output Verification Checklist

Before returning the rewritten text to the user, verify every item below:
- [ ] **Zero Banned Vocabulary**: Are words like *delve, underscore, pivotal, tapestry, furthermore, moreover, crucial, intricate* completely removed?
- [ ] **No Trailing `-ing` Clauses**: Have all `..., thereby/ultimately/highlighting V-ing...` sentence endings been rewritten?
- [ ] **Sentence Length Contrast**: Is there at least one short sentence (<12 words) and one complex sentence (>25 words) per paragraph?
- [ ] **No Paragraph-End Mini-Summaries**: Does each paragraph end on a concrete detail rather than a generic `"Thus, X plays a vital role in Y"` wrap-up?
- [ ] **Terminology Preserved**: Are all core technical terms, citations, and quantitative data 100% accurate and unaltered?
