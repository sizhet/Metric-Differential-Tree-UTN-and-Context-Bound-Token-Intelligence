# VALIDATION-003 — Context Density Policy Protocol

## A Validation Framework for Controlling the Amount, Placement, and Strength of Context-Bound Token Injection

**Repository:** Metric-Differential-Tree UTN and Context-Bound Token Intelligence (MDT-UTN-CBT)  
**Validation Document:** VALIDATION-003  
**Status:** v1.0.0 Validation Methodology  
**Related Documents:**  
- MDT-UTN-CBT-004 — Context-Bound Tokens for Structural Encoding  
- MDT-UTN-CBT-005 — Baseline-Preserved Context Injection  
- VALIDATION-001 — Baseline-Preserved Context Injection  
- VALIDATION-002 — Domain-Space-Time Context Matrix  

---

## 1. Purpose

Context-Bound Tokens introduce explicit structural evidence into token-based systems.

For example:

```text
rollback
+
rollback@DatabaseTransaction
````

But once a useful context has been identified, another question immediately appears:

> **How much context should be injected?**

Too little context may fail to resolve ambiguity.

Too much context may produce:

```text
token inflation
context dilution
repetition artifacts
anchoring
over-specialization
latency
cache fragmentation
reduced generalization
```

Therefore Context-Bound Token Intelligence requires not only:

```text
Context Selection Policy
```

but also:

```text
Context Density Policy
```

This document defines a validation protocol for determining:

```text
how many CBTs to inject,
which tokens should receive them,
where they should be placed,
how specific they should be,
how strongly context should be reinforced,
and when additional context should stop.
```

The central principle is:

> **Explicit context should be injected at the minimum density required to produce stable, validated structural gain.**

---

# 2. Context Selection and Context Density Are Different Problems

`VALIDATION-002` asks:

> Which context dimensions are useful?

For example:

```text
Domain
Space
Time
```

This document asks:

> Once useful context has been selected, how densely should it be represented?

For example:

```text
Sparse:
rollback@DatabaseTransaction
```

versus:

```text
Dense:
task@CodeRepair
rollback@DatabaseTransaction
transaction@DatabaseTransaction
manager@TransactionManager
retry@TransactionRecovery
version@Version42
```

These are separate policy decisions.

---

# 3. Two Policy Axes

The overall context policy therefore contains at least two axes:

```text
Axis 1 — Context Selection

Which context?
Domain?
Space?
Time?
UTN Type?
CCC Type?
```

and:

```text
Axis 2 — Context Density

How much of the selected context
should be injected?
```

Together:

```text
Context Policy
=
Selection Policy
+
Density Policy
```

---

# 4. Definition of Context Injection Density

Define **Context Injection Density (CID)** conceptually as:

```text
CID
=
Injected Context-Bound Units
/
Relevant Baseline Units
```

For example:

```text
Baseline:
Fix rollback after transaction failure.
```

Suppose there are three structurally relevant baseline units:

```text
rollback
transaction
failure
```

and one CBT is injected:

```text
rollback@DatabaseTransaction
```

then the relative context density is approximately:

```text
CID = 1 / 3
```

The exact denominator may vary by implementation.

The essential requirement is:

> **CID must be defined consistently within an experiment.**

---

# 5. CID Is a Policy Variable

CID is not intended as a universal fixed constant.

Different tasks may require different density.

For example:

```text
Simple lexical disambiguation
→ very low CID
```

while:

```text
complex AI coding localization
→ moderate CID
```

and:

```text
highly structured multi-object reasoning
→ potentially higher CID
```

Therefore:

```text
CID = f(Task, Context, Confidence, Consumer, Policy)
```

---

# 6. The Core Experimental Question

The primary question is:

> **At what Context Injection Density does additional structural evidence stop producing useful validated gain?**

The expected relationship may be:

```text
Performance
    ^
    |
    |             ●
    |          ●     ●
    |       ●           ●
    |    ●
    | ●
    +------------------------>
             CID
```

This implies an optimum rather than unlimited improvement.

---

# 7. The Context Density Hypothesis

A central hypothesis is:

> **Context Gain follows a saturation or inverted-U relationship with Context Injection Density.**

Conceptually:

```text
Too Little Context
        ↓
Insufficient Localization

Useful Context Region
        ↓
Improved Structural Focus

Too Much Context
        ↓
Dilution / Anchoring / Cost
```

This must be validated experimentally.

It should not be assumed to hold universally.

---

# 8. Canonical Density Levels

For v1.0.0 validation, use four primary regimes.

```text
CID-0
No explicit CBT

CID-L
Low / Sparse Context

CID-M
Medium / Selective Context

CID-H
High / Dense Context
```

Optionally:

```text
CID-XH
Very High / Stress-Test Context
```

can be added for robustness testing.

---

# 9. CID-0 — Baseline

Example:

```text
Fix the rollback behavior after transaction failure.
```

No explicit CBT is injected.

This establishes:

```text
Score(CID-0)
```

and preserves the canonical BPCI baseline.

---

# 10. CID-L — Sparse Context

Inject one high-value structural anchor.

Example:

```text
Fix the rollback behavior after transaction failure.

rollback@DatabaseTransaction
```

The purpose is to test whether one decisive structural cue is sufficient.

---

# 11. CID-M — Selective Context

Inject several context-bound units associated with distinct important concepts.

Example:

```text
Fix the rollback behavior after transaction failure.

rollback@DatabaseTransaction
transaction@Database
failure@TransactionRuntime
```

This provides multiple complementary structural anchors.

---

# 12. CID-H — Dense Context

Inject context for many relevant terms.

Example:

```text
Fix the rollback behavior after transaction failure.

fix@CodeRepair
rollback@DatabaseTransaction
behavior@TransactionManager
transaction@Database
failure@TransactionRuntime
```

This condition tests whether dense explicit structure provides further gain or starts causing interference.

---

# 13. CID-XH — Stress-Test Density

An intentionally dense condition may include:

```text
task@CodeRepair
fix@CodeRepair
rollback@DatabaseTransaction
behavior@TransactionManager
transaction@DatabaseTransaction
failure@TransactionRuntime
retry@TransactionRecovery
repository@PaymentService
version@Version42
```

CID-XH is not a recommended operating mode.

Its purpose is to detect:

```text
over-conditioning
repetition sensitivity
context dilution
token-cost explosion
```

---

# 14. Baseline Preservation Remains Mandatory

Every density condition must satisfy:

```text
Recover(CID-L) = Baseline

Recover(CID-M) = Baseline

Recover(CID-H) = Baseline

Recover(CID-XH) = Baseline
```

The only changing variable should be structural augmentation.

This preserves paired-control validity.

---

# 15. Context Density Is Not Just Token Count

Two prompts may inject the same number of CBTs but carry different structural density.

For example:

```text
rollback@Database
retry@Database
```

may provide two closely related cues.

Whereas:

```text
rollback@DatabaseTransaction
function@TransactionManager
```

covers two distinct structural dimensions.

Therefore density should distinguish:

```text
quantity
```

from:

```text
structural information content
```

---

# 16. Raw Density vs Effective Density

A useful distinction is:

```text
Raw Context Density
=
number of injected CBTs
```

and:

```text
Effective Context Density
=
number of non-redundant structural constraints
```

For example:

```text
rollback@Database
transaction@Database
database@Database
```

contains three CBTs but may provide little more effective information than one strong Domain cue.

---

# 17. Context Redundancy

Define **Context Redundancy** conceptually as the amount of injected structural evidence that duplicates information already supplied by other CBTs or by the baseline.

Examples:

```text
database@Database
transaction@Database
rollback@Database
```

may contain substantial redundancy.

A good density policy should prefer:

```text
complementary evidence
```

over:

```text
repeated equivalent evidence
```

---

# 18. Complementary Context

A higher-quality medium-density condition may use:

```text
rollback@DatabaseTransaction
function@TransactionManager
version@Version42
```

These represent:

```text
Domain
Space
Time
```

rather than repeating the same Domain evidence three times.

Thus:

> **Effective context density should increase through structural diversity, not blind repetition.**

---

# 19. Context Density and Domain-Space-Time

`VALIDATION-002` provides D/S/T context selection.

Density policy determines how extensively those selected dimensions are instantiated.

For example:

```text
Selected Context:
Domain + Space
```

could produce:

### Sparse

```text
rollback@DatabaseTransaction
```

### Medium

```text
rollback@DatabaseTransaction
function@TransactionManager
```

### Dense

```text
rollback@DatabaseTransaction
transaction@Database
function@TransactionManager
manager@TransactionManager
retry@TransactionRecovery
```

The selected dimensions remain the same.

Only density changes.

---

# 20. Context Depth and Context Density Are Different

Context Depth answers:

> How specific is the context?

Example:

```text
rollback@Database
        ↓
rollback@Transaction
        ↓
rollback@DatabaseTransaction
```

Context Density answers:

> How many contextual bindings are injected?

Example:

```text
rollback@DatabaseTransaction
transaction@Database
retry@TransactionRecovery
```

Therefore:

```text
Depth ≠ Density
```

Both should be separately controlled.

---

# 21. Context Breadth

A third concept is **Context Breadth**.

Breadth asks:

> How many distinct structural dimensions or objects are contextualized?

For example:

```text
rollback@DatabaseTransaction
```

has narrow breadth.

While:

```text
rollback@DatabaseTransaction
function@TransactionManager
version@Version42
policy@SafeRetry
```

has broader structural coverage.

Thus a fuller policy eventually considers:

```text
Depth
Density
Breadth
```

---

# 22. The DDB Model

A useful conceptual trio is:

```text
D — Depth
D — Density
B — Breadth
```

or:

> **Context Depth-Density-Breadth Policy**

v1.0.0 focuses primarily on Density while recording Depth and Breadth as control variables.

---

# 23. Global Context Injection

Context may be injected globally.

Example:

```text
Context:
DatabaseTransaction
TransactionManager
Version42

Fix the rollback behavior.
```

This provides context for the entire input.

It has relatively low local binding.

---

# 24. Local Context Injection

Context may be attached directly to individual tokens.

Example:

```text
Fix rollback@DatabaseTransaction behavior
inside function@TransactionManager.
```

This provides stronger token-to-context association.

---

# 25. Dual-Track Local Injection

To maximize baseline recoverability:

```text
Fix rollback rollback@DatabaseTransaction behavior
inside function function@TransactionManager.
```

The raw units remain explicitly present.

This is the canonical BPCI form.

---

# 26. Hybrid Context Injection

A hybrid representation combines:

```text
Global Context
+
Local CBT
```

Example:

```text
Context:
DatabaseTransaction / Version42

Fix the rollback rollback@DatabaseTransaction behavior
inside the transaction manager.
```

This may provide broad orientation plus precise local binding.

---

# 27. Placement Is Part of Density Policy

The same CBT count may behave differently depending on placement.

Therefore the density protocol should test:

```text
Global
Local
Hybrid
```

as separate conditions where relevant.

---

# 28. Canonical Placement Matrix

| ID | Global Context | Local CBT | Purpose     |
| -- | -------------: | --------: | ----------- |
| P0 |             No |        No | Baseline    |
| P1 |            Yes |        No | Global-only |
| P2 |             No |       Yes | Local-only  |
| P3 |            Yes |       Yes | Hybrid      |

Density can then be swept within P2 and P3.

---

# 29. Local Binding Hypothesis

A key hypothesis is:

> **Local CBTs may provide more precise structural evidence than equivalent global context when multiple objects play different roles in the same input.**

Example:

```text
graph@CallingGraph
node@Function
edge@CallRelation
delta@StructuralChange
```

A single global context header cannot express these bindings as precisely.

---

# 30. Context Reinforcement

Sometimes the same context should influence several related tokens.

Example:

```text
rollback@DatabaseTransaction
retry@DatabaseTransaction
failure@DatabaseTransaction
```

This is a form of context reinforcement.

It may be helpful when several lexical items belong to one structural region.

But excessive reinforcement may create anchoring.

---

# 31. Blind Repetition Should Be Avoided

A poor density strategy is:

```text
rollback@DatabaseTransaction
rollback@DatabaseTransaction
rollback@DatabaseTransaction
rollback@DatabaseTransaction
```

This changes sequence statistics without adding new structural evidence.

Therefore:

> **Repeated identical CBT strings should not be treated as the preferred mechanism for increasing context influence.**

---

# 32. Structural Reinforcement Is Preferred

Instead of repeated identical units:

```text
rollback@DatabaseTransaction
```

use complementary structural evidence:

```text
rollback@DatabaseTransaction
transaction@TransactionManager
retry@TransactionRecovery
```

This creates a richer context neighborhood.

---

# 33. Context Influence Without Model Modification

For existing LLMs and token-based systems, density provides one low-intrusion way to vary context evidence.

No direct internal attention or logit modification is required.

Conceptually:

```text
Baseline Evidence
+
Sparse Context Evidence
```

versus:

```text
Baseline Evidence
+
Dense Context Evidence
```

can be compared externally.

---

# 34. Density Is Not Guaranteed to Equal Influence

A critical caution:

> More CBTs do not guarantee proportionally greater model influence.

Existing Transformer systems determine contextual interactions through learned internal mechanisms.

Therefore:

```text
CID
```

is an input-level control variable.

It is not a direct measurement of:

```text
attention weight
```

or:

```text
internal model confidence
```

The actual influence must be measured through outcomes.

---

# 35. Outcome-Based Measurement

For each density condition measure:

```text
Task Score
Validation Result
Context Gain
Latency
Input Token Cost
Output Token Cost
Stability
Counter-Evidence Sensitivity
```

This avoids making unsupported assumptions about model internals.

---

# 36. Density Gain

Define:

```text
DensityGain(CID-x)
=
Score(CID-x)
-
Score(CID-0)
```

Examples:

```text
Gain(Low)

Gain(Medium)

Gain(High)
```

The objective is to find the density region with the best validated utility.

---

# 37. Marginal Density Gain

The additional benefit from increasing density is:

```text
MarginalDensityGain(L→M)
=
Score(CID-M)
-
Score(CID-L)
```

and:

```text
MarginalDensityGain(M→H)
=
Score(CID-H)
-
Score(CID-M)
```

This reveals saturation.

---

# 38. Density Saturation

Suppose:

```text
CID-0 = 0.60
CID-L = 0.80
CID-M = 0.89
CID-H = 0.90
```

Then:

```text
Low → Medium
produces useful gain
```

but:

```text
Medium → High
produces almost no gain
```

This suggests:

```text
Preferred Density = Medium
```

assuming cost and stability are comparable.

---

# 39. Density Dilution

Another pattern may be:

```text
CID-0 = 0.60
CID-L = 0.82
CID-M = 0.90
CID-H = 0.76
```

This indicates:

> **Context Density Dilution**

Additional structural evidence has degraded performance.

---

# 40. Density Reversal

A stronger failure is:

```text
CID-L > CID-0
```

but:

```text
CID-H < CID-0
```

The context itself is useful.

The excessive density is harmful.

This distinction is important for policy learning.

---

# 41. Density Utility Curve

A conceptual density curve may be:

```text
Utility
  ^
  |
  |            ●
  |         ●     ●
  |      ●           ●
  |   ●
  | ●
  +----------------------> CID
```

The operating target is near the useful peak, not at maximum density.

---

# 42. Minimum Effective Density

Define:

> **Minimum Effective Density (MED)**

as the lowest density that produces a predefined minimum validated Context Gain.

For example:

```text
Required Gain = +0.10

CID-L Gain = +0.14
```

Then:

```text
MED = CID-L
```

if validation passes.

---

# 43. Optimal Context Density

Define:

> **Optimal Context Density (OCD)**

as the density producing the best policy-defined tradeoff among:

```text
gain
validation
cost
latency
stability
risk
```

This is not necessarily the density with the highest raw score.

---

# 44. Minimum Sufficient Density

A stronger engineering concept is:

> **Minimum Sufficient Density (MSD)**

the lowest density whose utility falls within an accepted tolerance of the best validated density.

Example:

```text
CID-M Score = 0.91
CID-H Score = 0.92
Tolerance = 0.02
```

Then:

```text
MSD = CID-M
```

may be preferred.

---

# 45. Why Minimum Sufficient Density Is Important

Choosing MSD reduces:

```text
token cost
latency
context noise
specialization
prompt complexity
```

while preserving most or all measured benefit.

Thus:

> **The preferred density is usually the smallest density that captures the useful structural signal.**

---

# 46. Context Density Cost

Define:

```text
ContextDensityCost
```

using one or more measures:

```text
added input tokens
added bytes
serialization cost
latency
memory
query expansion
index growth
```

Different consumers require different cost metrics.

---

# 47. Density Efficiency

A simple conceptual measure is:

```text
DensityEfficiency
=
Validated Context Gain
/
Context Density Cost
```

This helps compare sparse and dense encoding.

Example:

```text
CID-L:
Gain = +0.18
Cost = 5 tokens

CID-H:
Gain = +0.20
Cost = 30 tokens
```

The dense condition has slightly higher absolute gain but much lower efficiency.

---

# 48. Context Gain per CBT

Another useful measure:

```text
GainPerCBT
=
Context Gain
/
Number of Injected CBTs
```

This identifies diminishing returns.

---

# 49. Token Cost per Gain

Conversely:

```text
TokenCostPerGain
=
Added Tokens
/
Context Gain
```

Lower values indicate greater encoding efficiency.

Care is required when Context Gain approaches zero.

---

# 50. Stability

Density should also be evaluated across repeated trials.

A high-density condition may have:

```text
higher average score
```

but also:

```text
higher variance
```

This may indicate unstable anchoring or sensitivity.

Therefore record:

```text
mean
median
standard deviation
pass rate
failure rate
```

where appropriate.

---

# 51. Density Stability

Define conceptually:

```text
DensityStability
=
consistency of validated outcome
across repeated runs
```

A good context policy should favor:

```text
useful gain
+
stable behavior
```

not merely occasional high performance.

---

# 52. Counter-Evidence Sensitivity

A dense context may make a model less responsive to contradictory evidence.

This must be tested.

For example:

```text
Injected:
rollback@DatabaseTransaction
```

but later evidence says:

```text
The operation is actually a deployment rollback.
```

Measure whether the system can recover.

---

# 53. Anchoring Stress Test

For each density level:

```text
CID-L
CID-M
CID-H
```

introduce counter-evidence after the context injection.

Measure:

```text
context correction rate
baseline recovery rate
wrong-context persistence
validation result
```

If higher density causes persistent incorrect commitment, the density is too aggressive.

---

# 54. Wrong-Context Density Test

A crucial adversarial experiment is to inject a deliberately incorrect context at increasing density.

Example:

```text
Actual Context:
DatabaseTransaction
```

but inject:

```text
CID-L:
rollback@GitRepository
```

then:

```text
CID-M:
rollback@GitRepository
commit@GitRepository
branch@GitRepository
```

then a denser condition.

Measure degradation.

---

# 55. Desired Wrong-Context Behavior

A robust policy should show:

```text
Low-confidence wrong context
→ limited influence
```

and:

```text
strong counter-evidence
→ correction or backoff
```

rather than:

```text
more injected context
→ irreversible false certainty
```

---

# 56. Context Confidence and Density

Density should depend on confidence.

A conceptual policy is:

```text
High Context Confidence
→ Medium density allowed

Medium Confidence
→ Sparse density

Low Confidence
→ Top-K / advisory / no injection
```

This prevents uncertain contexts from receiving excessive representational weight.

---

# 57. Confidence-Density Policy

Example:

| Context Confidence | Recommended Initial Density |
| -----------------: | --------------------------- |
|             ≥ 0.95 | Medium                      |
|          0.80–0.95 | Low                         |
|          0.60–0.80 | Very Low / Candidate        |
|             < 0.60 | Baseline / Top-K Search     |

These thresholds are illustrative hypotheses.

They must be experimentally determined.

---

# 58. High Confidence Does Not Justify Unlimited Density

Even a correct context can be over-injected.

Therefore:

```text
Confidence
```

controls whether context may be used.

It does not eliminate:

```text
density optimization
```

The two remain separate.

---

# 59. Task-Aware Density

Different task classes may require different density.

Example hypotheses:

| Task                           | Expected Density |
| ------------------------------ | ---------------- |
| Simple disambiguation          | Low              |
| Search query localization      | Low              |
| AI coding repair               | Low–Medium       |
| Complex multi-object reasoning | Medium           |
| Cache lookup                   | Very Low         |
| Brain-Unit dispatch            | Very Low         |
| Structural explanation         | Medium           |

These are experimental starting points, not fixed conclusions.

---

# 60. Consumer-Aware Density

The same full context may be projected differently.

Example:

```text
Search
→ 1–2 CBTs

Cache Key
→ compact structural ID

LLM
→ several contextual anchors

Brain Unit
→ one UTN type address

Delta Intelligence
→ richer structural metadata
```

Thus:

> **Context density should be consumer-specific.**

---

# 61. Search Density

Search often benefits from sparse structural constraints.

Too many CBTs may over-constrain retrieval.

Example:

```text
rollback@DatabaseTransaction
```

may be enough.

Adding:

```text
repository
version
function
policy
```

could reduce recall unnecessarily.

---

# 62. Search Density Measurements

Measure:

```text
precision
recall
candidate count
zero-result rate
query latency
```

A useful search policy may prefer the lowest density that materially improves precision without unacceptable recall loss.

---

# 63. Cache Density

Cache addressing usually prefers compact stable identity.

The relevant problem is not textual repetition but context-key granularity.

Too little context:

```text
wrong collisions
```

Too much context:

```text
fragmentation
low hit rate
```

Thus cache density is closely related to structural address specificity.

---

# 64. Cache Density Measurements

Measure:

```text
correct hit rate
wrong-hit rate
miss rate
fragmentation
entry count
invalidation rate
```

A higher-density context key must justify reduced reuse.

---

# 65. LLM Density

For an LLM, density determines how much explicit structural evidence appears in the sequence.

Potential benefits:

```text
localization
ambiguity reduction
role binding
```

Potential costs:

```text
input tokens
anchoring
repetition
distraction
```

This makes density testing particularly important.

---

# 66. Brain-Unit Density

Brain-Unit dispatch may require only:

```text
UTN Type
```

or:

```text
UTN Type + Task Type
```

Dense context injection into the dispatch layer may be unnecessary.

Additional context can instead be passed after dispatch.

This separation should be tested.

---

# 67. Delta Intelligence Density

Delta Intelligence may require rich context for safe reuse.

However, this does not mean all rich metadata should be injected into an LLM.

A useful distinction is:

```text
Rich Delta Storage Context
```

versus:

```text
Sparse Inference Context Projection
```

Again:

> **Preserve richly; inject selectively.**

---

# 68. Context Density Policy as Projection

The full context may contain:

```text
Domain
Space
Time
Role
State
Policy
History
CCC
UTN
```

Density Policy determines the projection:

```text
Full Context
     ↓
Consumer Policy
     ↓
Selected CBT Set
```

Therefore density control is part of Context Projection.

---

# 69. Context Set Selection

Given candidate CBTs:

```text
C = {c1, c2, c3, ..., cn}
```

the density policy chooses:

```text
C*
⊆
C
```

such that:

```text
Utility(C*)
```

is maximized under a context-cost budget.

Conceptually:

```text
maximize:
ValidatedUtility(C*)

subject to:
ContextCost(C*) ≤ Budget
```

No specific optimizer is required for v1.0.0.

---

# 70. Context Budget

A runtime may define:

```text
Maximum CBT Count
```

or:

```text
Maximum Added Token Budget
```

or:

```text
Maximum Context Cost
```

The policy then chooses the highest-value structural cues inside that budget.

---

# 71. Context Budget as a Runtime Control

Example:

```text
Budget:
10 added input tokens
```

Candidate contexts:

```text
rollback@DatabaseTransaction
function@TransactionManager
version@Version42
policy@SafeRetry
```

The policy may choose only:

```text
rollback@DatabaseTransaction
function@TransactionManager
```

if they provide the highest expected marginal gain.

---

# 72. Marginal Context Selection

Rather than injecting all CBTs at once:

```text
Start with baseline
      ↓
Add highest-value CBT
      ↓
Measure / predict marginal gain
      ↓
Add next CBT only if justified
```

This creates incremental density growth.

---

# 73. Greedy Context Density Strategy

A conceptual strategy:

```text
STEP 1
Rank candidate CBTs

STEP 2
Inject highest-value CBT

STEP 3
Estimate marginal benefit

STEP 4
Add next CBT

STEP 5
Stop when gain falls below threshold
```

This is analogous to controlled feature selection.

---

# 74. Density Stop Rule

A simple stop rule may be:

```text
Stop adding context when:

Marginal Gain < MinimumGain
```

or:

```text
Marginal Utility ≤ 0
```

or:

```text
Context Cost exceeds Budget
```

or:

```text
Validation Stability declines
```

---

# 75. Multi-Objective Stop Rule

A stronger rule:

```text
STOP IF

MarginalGain < Gmin

OR

MarginalGain / Cost < Emin

OR

Instability > Smax

OR

AnchoringRisk > Rmax
```

The exact values are policy-specific.

---

# 76. Context Priority

Candidate CBTs can be ranked using:

```text
Context Confidence
Structural Relevance
Expected Marginal Gain
Task Importance
Historical Success
Consumer Need
```

This prevents arbitrary dense injection.

---

# 77. Context Priority Score

A conceptual score may be:

```text
Priority(c)
=
f(
    confidence,
    relevance,
    historical gain,
    task fit,
    cost
)
```

Again, this is a policy abstraction rather than a fixed mathematical formula.

---

# 78. Historical Density Intelligence

Validated density experiments can become reusable experience.

For example:

```text
Task:
AI coding rollback repair

Context:
DatabaseTransaction

Best Density:
Medium

Useful CBTs:
rollback@DatabaseTransaction
function@TransactionManager

Dense Version:
No additional gain
```

This can guide future similar tasks.

---

# 79. Positive Density Delta

If increasing density:

```text
Low → Medium
```

produces validated improvement, record:

```text
Positive Density Delta
```

This is useful policy evidence.

---

# 80. Negative Density Delta

If:

```text
Medium → High
```

reduces validated performance, record:

```text
Negative Density Delta
```

This tells future runtime:

> Do not over-inject context in this structural neighborhood.

---

# 81. Density Cases as Delta Intelligence

A case can be represented as:

```text
Task
   ↓
Context Density Action
   ↓
Inference Delta
   ↓
Validation
   ↓
Positive / Negative Density Intelligence
```

This directly connects the protocol to TACG-SDIG.

---

# 82. ContextDensityCase Record

A conceptual record:

```text
ContextDensityCase
{
    caseId
    taskType

    baselineInput

    selectedContext
    contextSource
    contextConfidence

    candidateCBTs
    injectedCBTs

    densityLevel
    rawCID
    effectiveCID

    placementMode
    contextDepth
    contextBreadth

    baselineScore
    enhancedScore
    contextGain

    tokenCost
    latency

    validation
    stability
    counterEvidence

    finalDecision
    policyVersion
}
```

---

# 83. Canonical Density Experiment

For each case:

```text
D0
Baseline

D1
One high-value CBT

D2
Two complementary CBTs

D3
Three to five CBTs

D4
Dense stress condition
```

The exact CBT counts can be adjusted to the task.

The important factor is monotonic increase in injected structural evidence.

---

# 84. Example Density Sweep

Baseline:

```text
Fix retry after rollback.
```

### D0

```text
Fix retry after rollback.
```

### D1

```text
Fix retry after rollback.

rollback@DatabaseTransaction
```

### D2

```text
Fix retry after rollback.

rollback@DatabaseTransaction
retry@TransactionRecovery
```

### D3

```text
Fix retry after rollback.

rollback@DatabaseTransaction
retry@TransactionRecovery
function@TransactionManager
```

### D4

```text
Fix retry after rollback.

task@CodeRepair
rollback@DatabaseTransaction
retry@TransactionRecovery
function@TransactionManager
transaction@Database
version@Version42
policy@SafeRetry
```

All conditions reduce to the same baseline.

---

# 85. Example Result

| Density | Score |  Gain | Added Tokens | Validation | Stability |
| ------- | ----: | ----: | -----------: | ---------- | --------- |
| D0      |  0.62 |  0.00 |            0 | PASS       | High      |
| D1      |  0.79 | +0.17 |            5 | PASS       | High      |
| D2      |  0.89 | +0.27 |           10 | PASS       | High      |
| D3      |  0.90 | +0.28 |           16 | PASS       | High      |
| D4      |  0.84 | +0.22 |           34 | PASS       | Medium    |

The best raw score is:

```text
D3
```

but if policy tolerance is:

```text
0.02
```

then:

```text
D2
```

may be the Minimum Sufficient Density.

---

# 86. Density Decision

From the example:

```text
D0 → D1
large positive marginal gain

D1 → D2
large positive marginal gain

D2 → D3
minimal gain

D3 → D4
negative marginal gain
```

Therefore:

```text
Preferred Density = D2
```

This is the behavior the protocol is designed to detect.

---

# 87. Context Density Matrix

Density should eventually be evaluated across context selections.

For example:

| Context Set       | CID-L | CID-M | CID-H |
| ----------------- | ----: | ----: | ----: |
| Domain            |     ✓ |     ✓ |     ✓ |
| Space             |     ✓ |     ✓ |     ✓ |
| Time              |     ✓ |     ✓ |     ✓ |
| Domain+Space      |     ✓ |     ✓ |     ✓ |
| Domain+Space+Time |     ✓ |     ✓ |     ✓ |

This reveals interaction between:

```text
what context
```

and:

```text
how much context
```

---

# 88. Selection-Density Interaction

It is possible that:

```text
Domain Only
```

works best at high density, while:

```text
Domain + Space + Time
```

works best at low density.

Therefore:

```text
Optimal Density
```

cannot always be selected independently of:

```text
Context Selection
```

This creates a two-dimensional policy surface.

---

# 89. Context Policy Surface

Conceptually:

```text
                 Context Density
                 Low  Med  High

Domain            ●    ●    ○
Space             ○    ●    ○
Time              ○    ○    ×
Domain+Space      ●    ★    ○
D+S+T             ●    ○    ×
```

where:

```text
★ = preferred region
× = harmful region
```

The goal is to learn the useful policy surface.

---

# 90. Task-Density Interaction

Likewise:

```text
Task A
→ Low density

Task B
→ Medium density

Task C
→ High structural breadth but low repetition
```

Therefore density policies should be indexed by task type.

---

# 91. Model-Density Interaction

Different models may respond differently to the same CBT density.

For example:

```text
Model A
→ benefits from sparse CBTs

Model B
→ tolerates higher density

Model C
→ gains little because baseline contextual inference is already strong
```

Thus density results should record model/version.

---

# 92. Language-Density Interaction

CBTs may also behave differently across languages.

Example:

```text
rollback@DatabaseTransaction
```

embedded in English text versus:

```text
rollback@DatabaseTransaction
```

embedded in Chinese text.

Mixed-language contexts may provide useful structural anchors, but density should still be tested.

---

# 93. Cross-Language Structural Anchoring

A shared context identity may allow:

```text
折叠@StructuralIntelligence

folding@StructuralIntelligence
```

to point toward the same structural concept.

The density protocol can measure how many such anchors are useful before they become redundant.

---

# 94. Baseline Natural-Language Context

Density experiments should also include a natural-language baseline.

For example:

```text
B0
Raw prompt

B1
Raw prompt + concise NL context

D1
Raw prompt + sparse CBT

D2
Raw prompt + medium CBT

D3
Raw prompt + dense CBT
```

This prevents CBT density gains from being confused with ordinary prompt-context gains.

---

# 95. Fair Context-Information Comparison

An advanced experiment should approximately control for information content.

For example compare:

```text
Natural Language:
This task concerns database transaction rollback.
```

with:

```text
CBT:
rollback@DatabaseTransaction
```

The goal is to test whether structural form provides benefit beyond simply adding more information.

---

# 96. Prompt-Length Confound

Dense CBT conditions naturally increase input length.

Therefore results should report:

```text
added tokens
```

and, where possible, compare against length-matched non-structural controls.

Otherwise a result might reflect increased prompt attention or repetition rather than structural encoding.

---

# 97. Length-Matched Control

A stronger test may compare:

```text
CBT condition:
rollback@DatabaseTransaction
```

against a similar-length natural-language phrase:

```text
database transaction rollback context
```

This helps distinguish:

```text
structural-binding effect
```

from:

```text
mere additional-token effect
```

---

# 98. Random Extra-Token Control

For some experiments, an intentionally irrelevant augmentation can test whether any extra tokens improve or alter output.

Example:

```text
Control:
unrelated descriptive words
```

If CBT substantially outperforms irrelevant-token augmentation, that strengthens evidence that structural context matters.

---

# 99. Context Order Test

The same CBT set may be placed:

```text
before the prompt
after the prompt
near the relevant token
```

Order can affect sequence-based models.

Therefore location should be controlled or explicitly tested.

---

# 100. Context Position Conditions

Example:

```text
POS-A
CBT header

POS-B
Local CBT near raw token

POS-C
CBT footer

POS-D
Hybrid
```

Measure whether local proximity improves structural binding.

---

# 101. Context Distance

For sequence-based models, define conceptually:

```text
Context Distance
=
distance between raw token
and its explicit CBT evidence
```

A local CBT has low Context Distance.

A global header may have higher Context Distance.

This is another possible policy variable.

---

# 102. Locality Hypothesis

A testable hypothesis is:

> **For token-specific structural distinctions, lower Context Distance may produce more reliable context binding than distant global context.**

This should be tested rather than assumed.

---

# 103. Density and Context Distance

Dense context far from the target may still be less effective than one precise nearby CBT.

Thus:

```text
Density alone
```

is insufficient.

The protocol should record:

```text
placement
distance
binding
```

where meaningful.

---

# 104. Granularity Stress Test

Density should also be evaluated at different context depths.

Example:

```text
Low Depth:
rollback@Database
```

versus:

```text
High Depth:
rollback@DatabaseTransaction
```

Then combine with:

```text
Sparse
Medium
Dense
```

This produces a Depth × Density matrix.

---

# 105. Depth-Density Matrix

|                | Sparse | Medium | Dense |
| -------------- | -----: | -----: | ----: |
| Coarse Context |   Test |   Test |  Test |
| Medium Context |   Test |   Test |  Test |
| Fine Context   |   Test |   Test |  Test |

This can reveal whether:

```text
fine context requires lower density
```

or:

```text
coarse context benefits from multiple supporting cues
```

---

# 106. Confidence-Density Matrix

Similarly:

| Context Confidence | Sparse | Medium | Dense |
| ------------------ | -----: | -----: | ----: |
| High               |      ✓ |      ✓ |  Test |
| Medium             |      ✓ |   Test |  Risk |
| Low                |   Test |   Risk | Avoid |

This formalizes the intuition that uncertain context should not be densely injected.

---

# 107. Counter-Evidence-Density Matrix

Measure how effectively the system responds to contradiction at different densities.

| Density | Correct Context | Wrong Context | Recovery |
| ------- | --------------: | ------------: | -------: |
| Low     |         Measure |       Measure |  Measure |
| Medium  |         Measure |       Measure |  Measure |
| High    |         Measure |       Measure |  Measure |

An ideal policy seeks:

```text
high gain under correct context
+
high recovery under wrong context
```

---

# 108. Context Rigidity

Define conceptually:

> **Context Rigidity**

as resistance to revising an injected interpretation after new counter-evidence appears.

Excessively dense context may increase rigidity.

A robust structural encoding should maintain enough flexibility for correction.

---

# 109. Density Risk

A conceptual risk score may consider:

```text
Wrong-context persistence
Counter-evidence resistance
Validation failure
Output instability
Over-specialization
```

Then:

```text
DensityUtility
=
Gain
-
Risk
-
Cost
```

conceptually.

No fixed formula is prescribed.

---

# 110. Policy Regimes

A useful initial policy ladder is:

```text
Policy P0 — Disabled
No CBT

Policy P1 — Conservative
One high-confidence CBT

Policy P2 — Selective
Several complementary CBTs

Policy P3 — Dense
Broad explicit structural encoding

Policy P4 — Adaptive
Density selected from task/context/history
```

The long-term goal is P4.

---

# 111. Conservative Policy

A conservative policy may require:

```text
high context confidence
+
strong structural relevance
```

and inject only:

```text
one or two CBTs
```

This is a good initial deployment mode.

---

# 112. Selective Policy

A selective policy adds CBTs from complementary dimensions.

For example:

```text
Domain
+
Space
```

rather than multiple redundant Domain cues.

This is likely to be a useful default candidate for many experiments.

---

# 113. Dense Policy

Dense encoding is valuable primarily as:

```text
experimental condition
stress test
specialized high-structure mode
```

It should not become the default until validated.

---

# 114. Adaptive Density Policy

A mature system may choose density according to:

```text
task
context confidence
ambiguity
consumer
historical Context Gain
cost budget
risk
```

Conceptually:

```text
DensityPolicy(
    Task,
    Context,
    Consumer,
    Confidence,
    History,
    Budget
)
→
CBT Set
```

---

# 115. Density Escalation

A useful runtime strategy is:

```text
Baseline
   ↓
Sparse CBT
   ↓
Enough?
   ├── Yes → stop
   └── No
        ↓
     Medium CBT
        ↓
     Enough?
        ├── Yes → stop
        └── No
             ↓
           Dense / deeper reasoning
```

This avoids paying maximum context cost immediately.

---

# 116. Progressive Context Injection

This strategy can be called:

> **Progressive Context Injection**

Principle:

```text
Start sparse.
Increase context only when the current representation
fails to achieve sufficient localization or validation.
```

This is analogous to selective unfolding.

---

# 117. Density and Two-Phase Search

A natural integration is:

```text
Phase 1
Sparse structural context for localization

Phase 2
Additional context only within ambiguous region
```

Thus context density itself can be progressively unfolded.

---

# 118. Context Density as Unfolding

A low-density representation is a folded context summary.

When ambiguity remains:

```text
Unfold Context
```

by adding:

```text
more dimensions
more local bindings
greater depth
```

This connects Density Policy directly to Fold/Unfold.

---

# 119. Folded Context

Example:

```text
rollback@DatabaseTransaction
```

may summarize a much richer Starmap.

This is:

```text
Folded Context Representation
```

Only when required does the runtime expose more detail.

---

# 120. Context Unfolding

For a difficult case:

```text
rollback@DatabaseTransaction
```

may unfold into:

```text
rollback@DatabaseTransaction
function@TransactionManager
version@Version42
policy@SafeRetry
state@DeadlockRecovery
```

This is selective context unfolding.

---

# 121. Context Refolding

After determining that:

```text
Domain + Space
```

is sufficient, future similar cases need not inject:

```text
Time
Policy
State
```

The successful density policy is refolded into a compact representation.

---

# 122. Density Policy Learning Loop

```text
Full Context
    ↓
Candidate CBTs
    ↓
Sparse Injection
    ↓
Measure
    ↓
Add Context if Needed
    ↓
Validate
    ↓
Determine Minimum Sufficient Density
    ↓
Fold Policy
    ↓
Future Sparse Injection
```

This is a self-improving context-control loop.

---

# 123. Connection to MDT

MDT can assist density control by providing:

```text
parent context
child context
siblings
metric distance
local ambiguity
```

A highly isolated MDT leaf may require little extra context.

A dense ambiguous neighborhood may require more.

Thus structural geometry may predict useful context density.

---

# 124. Neighborhood Ambiguity

Conceptually:

```text
Low MDT Ambiguity
→ lower density

High MDT Ambiguity
→ more context evidence
```

This creates a possible future policy:

```text
CID
=
f(MDT Neighborhood Ambiguity)
```

---

# 125. Structural Separation and Density

If two candidate meanings are far apart in metric space, one Domain CBT may be sufficient.

If they are very close:

```text
more specific context
```

or:

```text
additional dimensions
```

may be required.

Thus density can adapt to structural separation.

---

# 126. Density and UTN Confidence

A validated UTN Type may allow compact encoding:

```text
token@UTN-8F32A
```

because substantial context has already been folded into the type identity.

This may reduce the need for many textual CBTs.

Therefore stronger UTN can potentially reduce context density.

---

# 127. Structural Type as Context Compression

This suggests:

```text
Many Context Features
        ↓
MDT / UTN Folding
        ↓
One Structural Type
        ↓
Compact CBT
```

For example:

```text
rollback@UTN-8F32A
```

may replace several surface context labels.

Thus MDT-UTN can act as a Context Compression layer.

---

# 128. Context Compression Ratio

A conceptual measure:

```text
ContextCompressionRatio
=
Raw Context Representation Cost
/
UTN-Bound Representation Cost
```

The compressed representation remains useful only if downstream performance is preserved.

---

# 129. Density and CCC

CCC may provide an even more specialized structural identity.

For example:

```text
retry@CCC-TransactionRecovery
```

may compactly encode accumulated experience.

Future validation can compare:

```text
multiple lexical CBTs
```

versus:

```text
one CCC-bound structural token
```

for equivalent or better performance.

---

# 130. Density and Brain Units

Once a task localizes to a Brain Unit, context density may be reduced at the global layer.

The specialist already carries:

```text
domain knowledge
local policy
CCC
historical cases
```

Therefore:

```text
Good Dispatch
→ Less Prompt Context Required
```

is another future hypothesis.

---

# 131. Density as a Systems-Level Cost

Excess context affects more than the LLM prompt.

It can increase:

```text
index size
cache-key fragmentation
network payload
storage
serialization
logging
trace complexity
```

Thus density policy is an infrastructure optimization problem as well as an inference problem.

---

# 132. Consumer-Specific Density Projection

A possible architecture:

```text
Full Structural Context
          │
          ├── LLM Projection
          ├── Search Projection
          ├── Cache Projection
          ├── Delta Projection
          └── Brain-Unit Projection
```

Each projection has its own density policy.

---

# 133. Canonical Experimental Measurements

For each density condition, record:

```text
Task Score
Validation Pass Rate
Context Gain
Marginal Density Gain
Added Input Tokens
Output Tokens
Latency
Stability
Counter-Evidence Recovery
Wrong-Context Failure Rate
```

Optionally:

```text
Search Candidate Count
Cache Hit Rate
LLM Fallback Rate
Tool Calls
```

depending on consumer.

---

# 134. Canonical Result Table

| Density | CBT Count |  Gain | Validation | Token Δ | Latency Δ | Stability | Wrong-Context Recovery |
| ------- | --------: | ----: | ---------- | ------: | --------: | --------- | ---------------------: |
| D0      |         0 |  0.00 | PASS       |       0 |         0 | High      |                      — |
| D1      |         1 | +0.18 | PASS       |      +5 |       +2% | High      |                    95% |
| D2      |         2 | +0.27 | PASS       |     +10 |       +4% | High      |                    92% |
| D3      |         4 | +0.28 | PASS       |     +21 |       +9% | Medium    |                    78% |
| D4      |         8 | +0.20 | PASS       |     +43 |      +18% | Medium    |                    55% |

This example strongly favors D2.

---

# 135. Density Summary Metrics

A validation campaign may report:

```text
Best Raw Density

Minimum Effective Density

Minimum Sufficient Density

Maximum Safe Density

Average Gain per CBT

Average Token Cost per Gain

Wrong-Context Recovery by Density

Stability by Density
```

These provide much richer policy information than one accuracy number.

---

# 136. Maximum Safe Density

Define:

> **Maximum Safe Density (MSafeD)**

as the highest tested density that does not exceed policy-defined limits for:

```text
wrong-context persistence
instability
cost
validation failure
```

This is distinct from optimal density.

---

# 137. Density Operating Window

A mature policy may define:

```text
Minimum Effective Density
        ≤
Operating Density
        ≤
Maximum Safe Density
```

Within this interval, choose the density maximizing utility.

---

# 138. Density Policy States

Recommended outputs:

```text
NO_CONTEXT

SPARSE_CONTEXT

SELECTIVE_CONTEXT

DENSE_CONTEXT

BACKOFF_DENSITY

INCREASE_DENSITY

ALTERNATIVE_CONTEXT

BASELINE_ONLY

ESCALATE
```

These states can later become runtime policy actions.

---

# 139. Density Backoff

When dense context fails:

```text
Dense
   ↓
Validation Failure
   ↓
Remove Low-Value CBTs
   ↓
Medium
   ↓
Revalidate
```

This is a natural reversible operation because the baseline remains intact.

---

# 140. Density Increase

Conversely:

```text
Sparse
   ↓
Insufficient Localization
   ↓
Add Next High-Value Context
   ↓
Re-evaluate
```

Thus density can move in both directions.

---

# 141. Context Density Should Be Reversible

Every injected CBT should retain provenance.

The runtime should know:

```text
which CBT was injected
why
by which policy
from which context source
```

This permits:

```text
remove one
remove several
back off entirely
```

without reconstructing the original input.

---

# 142. Ablation by CBT

For an enhanced set:

```text
C1
C2
C3
```

perform:

```text
All
All - C1
All - C2
All - C3
```

This reveals which CBT contributes actual value.

---

# 143. Leave-One-Out Context Test

Define:

```text
Contribution(Ci)
≈
Score(All)
-
Score(All - Ci)
```

This is a simple context attribution mechanism.

A CBT with near-zero or negative contribution may be removed.

---

# 144. Add-One Context Test

Starting from baseline:

```text
S0
```

test individually:

```text
S0 + C1
S0 + C2
S0 + C3
```

This identifies high-value anchors before constructing larger sets.

---

# 145. Interaction Still Matters

A CBT may provide little value alone but substantial value with another CBT.

Therefore:

```text
Add-One
```

and:

```text
Leave-One-Out
```

should be interpreted together.

This mirrors D/S/T interaction analysis.

---

# 146. Context Density and Explainability

Sparse context is easier to explain.

For example:

```text
The result changed because
rollback@DatabaseTransaction
was injected.
```

Dense context makes causal attribution harder.

Therefore explainability itself may be a policy cost.

---

# 147. Context Density and Auditability

Every validation report should preserve:

```text
baseline
injected CBT list
placement
density
context source
score
validation
decision
```

This makes context influence auditable.

---

# 148. Density Policy Record

A conceptual reusable policy record:

```text
ContextDensityPolicy
{
    taskType
    consumer

    contextType
    contextConfidenceRange

    minimumEffectiveDensity
    preferredDensity
    maximumSafeDensity

    preferredPlacement
    preferredDepth
    preferredBreadth

    tokenBudget

    gainThreshold
    stabilityThreshold
    riskThreshold

    supportingCases
    negativeCases

    version
}
```

---

# 149. Policy Extraction

After repeated experiments, a rule may emerge:

```text
IF
task = CodeRepair
AND
context = DatabaseTransaction
AND
UTN confidence > 0.90

THEN
inject:
    rollback@DatabaseTransaction
    function@TransactionManager

DO NOT inject:
    redundant domain CBTs

unless:
    baseline localization remains ambiguous
```

This is a concrete density policy.

---

# 150. Another Policy Example

```text
IF
consumer = Search
AND
Domain confidence is high

THEN
start with one Domain CBT

IF result set is too broad
    add Space CBT

IF result set becomes too narrow
    back off Space
```

This is progressive density control.

---

# 151. Cache Policy Example

```text
IF
consumer = Cache

USE
stable UTN context ID

ADD Time
only when result validity is version-dependent

DO NOT
include irrelevant lexical CBTs
```

This shows that density policy can be extremely sparse for address-based consumers.

---

# 152. Brain-Unit Policy Example

```text
IF
UTN Type maps confidently to a Brain Unit

THEN
dispatch using UTN Type

PASS richer D/S/T context
to the selected Brain Unit

rather than encoding all context
into the dispatch key
```

This separates routing density from reasoning density.

---

# 153. Validation Dataset Requirements

A useful validation set should include:

```text
low-ambiguity cases
high-ambiguity cases
correct-context cases
wrong-context cases
multi-object cases
context-already-obvious cases
D/S/T interaction cases
version-sensitive cases
```

Density should not be tested only on tasks known to benefit from context.

---

# 154. Density Benchmark Balance

Include cases where expected best density is:

```text
zero
low
medium
```

and some possible:

```text
high
```

Otherwise the benchmark cannot discover the true policy boundary.

---

# 155. Null Density Hypothesis

The protocol must preserve the possibility that:

> **For many tasks, the optimal explicit CBT density is zero.**

A strong baseline model may already infer context sufficiently.

This is a valid and important result.

---

# 156. Sparse Density Hypothesis

Another hypothesis is:

> **A small number of high-quality structural anchors may capture most available CBT benefit.**

If validated, this would be particularly attractive for engineering deployment.

---

# 157. Dense Context Hypothesis

In some highly structured tasks:

> **Multiple locally bound CBTs may outperform one global context description.**

This should be tested especially for:

```text
multi-object AI coding
CallingGraph reasoning
structured query tasks
```

---

# 158. Structural Compression Hypothesis

Another important future hypothesis is:

> **As MDT-UTN identities mature, one stable structural type may replace many surface CBTs without losing useful Context Gain.**

This would make structural encoding increasingly compact.

---

# 159. Canonical Experimental Procedure

```text
INPUT:
    Baseline S0
    Candidate Context Set C
    Task T
    Consumer R
    Context Policy P
    Validator V

STEP 1 — Freeze Baseline
    Preserve S0

STEP 2 — Identify Candidate CBTs
    From selected structural context

STEP 3 — Rank CBTs
    Relevance
    confidence
    expected gain

STEP 4 — Build Density Conditions
    D0
    D1
    D2
    D3
    D4

STEP 5 — Verify Recoverability
    Recover(Di) = S0

STEP 6 — Run Baseline

STEP 7 — Run Density Conditions

STEP 8 — Evaluate
    task score
    validation
    token cost
    latency
    stability

STEP 9 — Compute
    Context Gain
    Marginal Density Gain
    Gain per CBT

STEP 10 — Run Counter-Evidence Tests

STEP 11 — Run Wrong-Context Stress Test

STEP 12 — Determine
    Minimum Effective Density
    Minimum Sufficient Density
    Maximum Safe Density

STEP 13 — Select Preferred Density

STEP 14 — Archive
    positive density deltas
    negative density deltas

STEP 15 — Update Density Policy
```

---

# 160. Canonical Runtime Policy

```text
Start with Baseline
       │
       ▼
Is structural context useful?
       │
   ┌───┴───┐
   │       │
  No      Yes
   │       │
   ▼       ▼
Baseline Sparse CBT
           │
           ▼
       Sufficient?
       ┌───┴───┐
       │       │
      Yes      No
       │       │
       ▼       ▼
      Stop   Add Next
               │
               ▼
           Revalidate
               │
       ┌───────┼────────┐
       ▼       ▼        ▼
     Better   Same     Worse
       │       │        │
       ▼       ▼        ▼
     Keep     Stop     Backoff
```

---

# 161. Canonical Density-Governance Loop

```text
Full Context
     ↓
Candidate CBTs
     ↓
Sparse Projection
     ↓
Inference / Search / Dispatch
     ↓
Validation
     ↓
Marginal Gain?
     │
 ┌───┴──────────────┐
 │                  │
High              Low/Negative
 │                  │
 ▼                  ▼
Add Context        Stop / Backoff
 │                  │
 └────────┬─────────┘
          ▼
   Minimum Sufficient
        Density
          │
          ▼
     Fold Policy
          │
          ▼
   Future Context Use
```

---

# 162. Validation Invariants

## Invariant 1 — Baseline Preservation

> Every density condition must reduce to the same original baseline.

## Invariant 2 — Explicit Augmentation

> The system must know which units were injected.

## Invariant 3 — Density Is Measured

> Sparse, medium, and dense must not remain purely subjective labels.

## Invariant 4 — Density Is Separate from Context Selection

> Correct context does not imply maximum context.

## Invariant 5 — Density Is Separate from Depth

> More CBTs and more specific CBTs are distinct variables.

## Invariant 6 — Complementary Evidence Is Preferred

> Density should grow through structurally useful information rather than blind repetition.

## Invariant 7 — Marginal Gain Controls Growth

> Additional context should justify itself.

## Invariant 8 — Cost Is Explicit

> Context Gain must be considered together with encoding and runtime cost.

## Invariant 9 — Counter-Evidence Must Remain Effective

> Higher context density must not create uncontrolled rigidity.

## Invariant 10 — Wrong Context Is Stress-Tested

> A context policy is incomplete if it is evaluated only under correct context.

## Invariant 11 — Consumer Policies May Differ

> Search, LLM, Cache, Delta, and Brain Units need not use equal density.

## Invariant 12 — Sparse Is the Default Starting Point

> Increase density only when evidence supports doing so.

---

# 163. Failure Modes

## Failure Mode A — Maximum-Density Bias

Assuming more CBTs must be better.

## Failure Mode B — Blind Repetition

Repeating identical CBTs as a substitute for meaningful structural evidence.

## Failure Mode C — Density/Depth Confusion

Treating more specific context as equivalent to more context units.

## Failure Mode D — Redundant CBT Explosion

Injecting many tokens that express the same structural fact.

## Failure Mode E — Wrong-Context Amplification

Increasing the influence of an incorrect context through dense injection.

## Failure Mode F — Counter-Evidence Suppression

The enhanced representation becomes too rigid to recover from contradiction.

## Failure Mode G — Token-Cost Neglect

Tiny performance gains require large prompt expansion.

## Failure Mode H — No Natural-Language Control

Dense CBTs are compared only with raw input.

## Failure Mode I — No Length Control

Observed effects may come from extra tokens rather than structural content.

## Failure Mode J — Universal Density Policy

One density level is applied to every task and consumer.

## Failure Mode K — No Provenance

The runtime cannot identify which CBTs were injected.

## Failure Mode L — No Backoff

Once context is injected, it cannot be selectively removed.

---

# 164. Minimal Validation Report

```text
Case ID:

Task:

Consumer:

Baseline:

Selected Context:

Context Source:

Context Confidence:

Candidate CBTs:

D0 CBT Count:
D1 CBT Count:
D2 CBT Count:
D3 CBT Count:
D4 CBT Count:

Placement Mode:

Context Depth:

Context Breadth:

D0 Score:
D1 Score:
D2 Score:
D3 Score:
D4 Score:

Context Gain by Density:

Marginal Density Gain:

Added Token Cost:

Latency Delta:

Validation Result:

Stability:

Wrong-Context Recovery:

Counter-Evidence Result:

Minimum Effective Density:

Minimum Sufficient Density:

Maximum Safe Density:

Preferred Density:

Final Policy:
```

---

# 165. Summary Report

A campaign-level report should include:

```text
Total Cases

Cases Preferring CID-0

Cases Preferring Sparse Context

Cases Preferring Medium Context

Cases Preferring Dense Context

Average Gain — Sparse

Average Gain — Medium

Average Gain — Dense

Average Token Cost per Gain

Average Wrong-Context Recovery

Density Saturation Rate

Density Dilution Rate

Best Placement Mode

Best Density by Task

Best Density by Consumer
```

---

# 166. Canonical Result Matrix

| Task                    | Baseline | Sparse | Medium | Dense | MSD    | Max Safe |
| ----------------------- | -------: | -----: | -----: | ----: | ------ | -------- |
| Semantic Disambiguation |      .70 |    .91 |    .92 |   .90 | Sparse | Medium   |
| Code Localization       |      .61 |    .78 |    .90 |   .89 | Medium | Dense    |
| Search                  |      .68 |    .85 |    .84 |   .76 | Sparse | Medium   |
| Version Reasoning       |      .54 |    .70 |    .88 |   .88 | Medium | Dense    |

The purpose is to extract policy, not merely identify one global winner.

---

# 167. Connection to VALIDATION-001

`VALIDATION-001` establishes:

```text
Baseline
vs
Context-Enhanced Input
```

This document extends it to:

```text
Baseline
vs
Multiple Context Density Levels
```

Thus:

```text
VALIDATION-001
→ Does context help?

VALIDATION-003
→ How much context should be used?
```

---

# 168. Connection to VALIDATION-002

`VALIDATION-002` establishes:

```text
Which context dimensions?
```

This document establishes:

```text
How densely should those dimensions be expressed?
```

Together:

```text
Context Selection
+
Context Density
=
Context Injection Policy
```

---

# 169. The Complete Validation Triangle

The three validation documents now form:

```text
VALIDATION-001
Baseline-Preserved Injection
        ↓
Does explicit context add value?

VALIDATION-002
Domain-Space-Time Matrix
        ↓
Which context adds value?

VALIDATION-003
Context Density Policy
        ↓
How much context should be injected?
```

Together they answer:

```text
Whether?
Which?
How Much?
```

---

# 170. Context Policy Learning

The output of all three validations can be folded into:

```text
ContextPolicy
{
    whenToInject
    whichContext
    howDeep
    howDense
    whereToPlace
    whenToBackoff
}
```

This is substantially more powerful than a fixed prompt template.

---

# 171. From Prompt Engineering to Structural Context Policy

The progression is:

```text
Manual Prompt Context
        ↓
Explicit CBT
        ↓
Baseline Measurement
        ↓
Context Selection
        ↓
Density Optimization
        ↓
Validated Policy
        ↓
Reusable Structural Intelligence
```

This turns some aspects of prompt engineering into measurable structural policy.

---

# 172. Connection to Context-as-Address

Density control also matters for Context-as-Address.

An intelligence address should be:

```text
specific enough
to avoid collisions
```

but:

```text
general enough
to support reuse
```

This is structurally analogous to CBT density optimization.

---

# 173. Connection to Fold/Unfold

Context Density Policy has a natural Fold/Unfold interpretation.

```text
Rich Context
   ↓
Fold
   ↓
Sparse CBT
   ↓
Ambiguity?
   │
   ├── No → Use
   │
   └── Yes
        ↓
      Unfold More Context
        ↓
      Validate
        ↓
      Refold Policy
```

This provides a particularly clean SI interpretation of context control.

---

# 174. Core Principles

## Principle 1 — Start Sparse

> Use the smallest plausible context representation first.

## Principle 2 — Add Complementary Evidence

> Increase structural coverage rather than repeating equivalent context.

## Principle 3 — Measure Marginal Gain

> Every additional CBT should justify its cost.

## Principle 4 — Preserve Baseline

> Density changes must remain completely reversible.

## Principle 5 — Separate Selection from Density

> Knowing which context matters does not answer how much to inject.

## Principle 6 — Separate Density from Depth

> More contextual tokens and deeper structural identity are different controls.

## Principle 7 — Control by Confidence

> Low-confidence context should not receive high-density reinforcement.

## Principle 8 — Test Wrong Context

> Density policy must be robust to erroneous localization.

## Principle 9 — Preserve Counter-Evidence

> Dense context must not suppress legitimate contradiction.

## Principle 10 — Learn Consumer-Specific Policies

> Different intelligence components require different projections.

## Principle 11 — Fold Successful Density Decisions

> Historical density experiments should become future policy.

## Principle 12 — Stop When Context Stops Paying

> Maximum context is not the objective; sufficient context is.

---

# 175. Research Questions

### RQ-1

What Context Injection Density maximizes validated Context Gain?

### RQ-2

How quickly does marginal gain saturate as CBT count increases?

### RQ-3

When does density dilution begin?

### RQ-4

How does density interact with Domain, Space, and Time selection?

### RQ-5

How does density interact with context depth?

### RQ-6

Does local CBT placement outperform global context at equal information content?

### RQ-7

How does context confidence affect optimal density?

### RQ-8

How does density affect wrong-context anchoring?

### RQ-9

At what density does counter-evidence recovery begin to degrade?

### RQ-10

How much of observed density gain is due to additional tokens versus structural binding?

### RQ-11

Can length-matched natural-language controls distinguish CBT-specific gain?

### RQ-12

Do Search, LLM, Cache, Delta Intelligence, and Brain Units require different density policies?

### RQ-13

Can MDT neighborhood ambiguity predict useful CID?

### RQ-14

Can stable UTN identities compress several CBTs into one structural address?

### RQ-15

Can successful density policies be folded as TACG-SDIG structural experience?

### RQ-16

Can progressive context injection reduce average prompt cost without reducing quality?

---

# 176. Conclusion

Context-Bound Token Intelligence introduces a new control problem.

Once explicit structural context is available, the system must decide not only:

```text
what context to use
```

but also:

```text
how much context to expose
```

The naive solution is:

```text
More Context
→ Better Intelligence
```

The proposed framework rejects that assumption.

Instead:

```text
Context Density
        ↓
Measure Gain
        ↓
Measure Cost
        ↓
Measure Stability
        ↓
Test Counter-Evidence
        ↓
Find Minimum Sufficient Density
```

The preferred policy is not maximum injection.

It is:

> **Minimum sufficient structural evidence for maximum validated utility.**

The most important operational rule is:

> **Start sparse and unfold more context only when the current structural representation is insufficient.**

The most important safety rule is:

> **Never amplify uncertain or incorrect context merely by repeating it more densely.**

The most important engineering rule is:

> **Additional context must earn its cost through measurable marginal gain.**

And the most important evolutionary rule is:

> **Successful context-density decisions should themselves be folded into reusable Context Policy.**

---

## Canonical Summary

```text
                       FULL CONTEXT
                            │
                            ▼
                     MDT / UTN Identity
                            │
                            ▼
                    Candidate CBT Set
                            │
                            ▼
                      START SPARSE
                            │
                            ▼
                     Sparse Injection
                            │
                            ▼
                         Measure
                            │
              ┌─────────────┼─────────────┐
              ▼             ▼             ▼
            Gain           Cost       Stability
              │             │             │
              └─────────────┼─────────────┘
                            ▼
                     Sufficient?
                      /           \
                    Yes            No
                    │              │
                    ▼              ▼
                   STOP       Add Context
                    │              │
                    │              ▼
                    │          Revalidate
                    │              │
                    │      ┌───────┼────────┐
                    │      ▼       ▼        ▼
                    │    Better   Same     Worse
                    │      │       │        │
                    │      ▼       ▼        ▼
                    │    Keep     Stop    Backoff
                    │       \       |       /
                    └───────────────┼────────
                                    ▼
                         MINIMUM SUFFICIENT
                              DENSITY
                                    │
                                    ▼
                              FOLD POLICY
                                    │
                                    ▼
                           FUTURE CBT INJECTION
```

> **Select the right context.
> Inject it sparsely.
> Add only complementary evidence.
> Measure every marginal gain.
> Back off when density becomes harmful.
> Fold the successful density into future policy.**

