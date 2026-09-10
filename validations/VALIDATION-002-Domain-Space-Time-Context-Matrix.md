# VALIDATION-002 — Domain-Space-Time Context Matrix

## A Factorized Validation Framework for Measuring Structural Context Dimensions

**Repository:** Metric-Differential-Tree UTN and Context-Bound Token Intelligence (MDT-UTN-CBT)  
**Validation Document:** VALIDATION-002  
**Status:** v1.0.0 Validation Methodology  
**Related Documents:**  
- MDT-UTN-CBT-004 — Context-Bound Tokens for Structural Encoding  
- MDT-UTN-CBT-005 — Baseline-Preserved Context Injection  
- VALIDATION-001 — Baseline-Preserved Context Injection  

---

## 1. Purpose

Context is potentially very large.

A target may be described by:

```text
domain
location
time
role
state
owner
version
policy
dependency
history
CallingGraph position
runtime condition
````

Blindly encoding every available dimension is neither necessary nor desirable.

For the first MDT-UTN-CBT validation stage, this document proposes three canonical context subspaces:

```text
Domain
Space
Time
```

abbreviated:

```text
D / S / T
```

These three dimensions provide a compact experimental basis for answering:

> **Which structural context dimensions actually improve downstream intelligence, individually and in combination?**

The central methodology is a factorized Context Matrix:

```text
Token Only
   ↓
+ Domain
+ Space
+ Time
+ Domain-Space
+ Domain-Time
+ Space-Time
+ Domain-Space-Time
```

Every condition remains paired with the same recoverable baseline.

---

# 2. Core Principle

The validation principle is:

> **Preserve rich context structurally, but inject only the context dimensions whose measured utility justifies their use.**

This separates:

```text
Context Preservation
```

from:

```text
Context Injection
```

The MDT-UTN system may preserve many dimensions.

The CBT Policy may expose only a selected subset.

---

# 3. Why Domain, Space, and Time?

These dimensions answer three fundamental localization questions.

```text
Domain
→ What kind of world are we in?

Space
→ Where in that world are we?

Time
→ Which state or version of that world applies?
```

Together:

```text
Domain
+
Space
+
Time
```

provide a minimal structural coordinate system.

---

# 4. Domain Context

Domain identifies the semantic, functional, or knowledge region in which a token should be interpreted.

Examples:

```text
commit@Git

commit@Database

node@CallingGraph

node@DistributedSystem

cache@LLMRuntime

cache@Database
```

Domain primarily answers:

> **What class of problem or system does this token belong to?**

---

# 5. Space Context

Space identifies structural location.

Examples:

```text
retry@TransactionManager

node@CallingGraph

function@PaymentService

policy@DeploymentPipeline
```

Space may represent:

```text
repository
module
class
function
CallingGraph node
subsystem
tree branch
MDT neighborhood
physical region
logical region
```

Space primarily answers:

> **Where is this object located structurally?**

---

# 6. Time Context

Time identifies temporal state, version, lifecycle stage, or historical period.

Examples:

```text
schema@Version3

policy@Release2026Q3

function@BeforeRefactor

function@AfterRefactor

configuration@CurrentDeployment
```

Time primarily answers:

> **Which temporal state of this object is relevant?**

---

# 7. Context as Coordinates

The three dimensions can be viewed as structural coordinates:

```text
Context
=
(Domain, Space, Time)
```

For example:

```text
Domain:
DatabaseTransaction

Space:
PaymentService.TransactionManager

Time:
Version42
```

Together they define a substantially narrower structural region than any one coordinate alone.

---

# 8. GenericContainerStarmap Representation

A target context may be represented conceptually as:

```text
GenericContainerStarmap
{
    Domain = DatabaseTransaction

    Space = {
        Repository = PaymentService
        Module = TransactionCore
        Class = TransactionManager
    }

    Time = {
        Version = 42
        State = Current
    }
}
```

MDT-UTN may preserve the complete Starmap.

CBT injection does not need to expose every stored field.

---

# 9. Storage vs Injection

This distinction is fundamental.

```text
Stored Context
=
Rich Structural Representation
```

while:

```text
Injected Context
=
Policy-Selected Structural Evidence
```

Therefore:

```text
Rich Context Storage
        ↓
Metric / Policy Selection
        ↓
Sparse Context Injection
```

is preferred over blindly flattening the entire context into the prompt.

---

# 10. The Full D/S/T Experimental Matrix

Three binary context dimensions produce eight primary conditions.

| ID | Domain | Space | Time | Representation          |
| -- | -----: | ----: | ---: | ----------------------- |
| A0 |      0 |     0 |    0 | Token Only              |
| A1 |      1 |     0 |    0 | Token@Domain            |
| A2 |      0 |     1 |    0 | Token@Space             |
| A3 |      0 |     0 |    1 | Token@Time              |
| A4 |      1 |     1 |    0 | Token@Domain@Space      |
| A5 |      1 |     0 |    1 | Token@Domain@Time       |
| A6 |      0 |     1 |    1 | Token@Space@Time        |
| A7 |      1 |     1 |    1 | Token@Domain@Space@Time |

This is the canonical **Domain-Space-Time Context Matrix**.

---

# 11. A0 — Token-Only Baseline

Example:

```text
rollback
```

No explicit structural context is injected.

This condition establishes:

```text
Score(A0)
```

which becomes the primary baseline for all D/S/T comparisons.

---

# 12. A1 — Domain Only

Example:

```text
rollback@DatabaseTransaction
```

This tests whether semantic or functional localization alone provides measurable gain.

Define:

```text
Gain(D)
=
Score(A1) - Score(A0)
```

---

# 13. A2 — Space Only

Example:

```text
rollback@TransactionManager
```

This tests whether structural location alone provides measurable gain.

Define:

```text
Gain(S)
=
Score(A2) - Score(A0)
```

---

# 14. A3 — Time Only

Example:

```text
rollback@Version42
```

This tests whether temporal localization alone provides measurable gain.

Define:

```text
Gain(T)
=
Score(A3) - Score(A0)
```

---

# 15. A4 — Domain + Space

Example:

```text
rollback@DatabaseTransaction@TransactionManager
```

This tests whether semantic and structural localization reinforce one another.

Define:

```text
Gain(D,S)
=
Score(A4) - Score(A0)
```

---

# 16. A5 — Domain + Time

Example:

```text
rollback@DatabaseTransaction@Version42
```

This condition is particularly relevant when behavior changes across versions within the same domain.

Define:

```text
Gain(D,T)
=
Score(A5) - Score(A0)
```

---

# 17. A6 — Space + Time

Example:

```text
rollback@TransactionManager@Version42
```

This tests whether location plus version is sufficient without explicitly stating the broader domain.

Define:

```text
Gain(S,T)
=
Score(A6) - Score(A0)
```

---

# 18. A7 — Domain + Space + Time

Example:

```text
rollback@DatabaseTransaction@TransactionManager@Version42
```

This is the maximum D/S/T condition.

Define:

```text
Gain(D,S,T)
=
Score(A7) - Score(A0)
```

A7 should not automatically be assumed to be the best condition.

That is an experimental question.

---

# 19. The Main Research Question

The important question is not:

> Does more context improve performance?

It is:

> **Which minimum context subset produces the largest validated utility for this task?**

The desired result may be:

```text
A1
```

rather than:

```text
A7
```

if Domain alone already resolves the relevant ambiguity.

---

# 20. Minimum Sufficient Context

Define:

> **Minimum Sufficient Context (MSC)**

as the smallest context subset whose performance is statistically or operationally indistinguishable from the best validated context condition within a defined tolerance.

For example:

```text
A1 = 0.91
A4 = 0.92
A7 = 0.92
```

If the acceptance tolerance is:

```text
0.02
```

then:

```text
MSC = Domain
```

may be preferable.

---

# 21. Why Minimum Sufficient Context Matters

Using unnecessary context can increase:

```text
token cost
latency
feature noise
anchoring
over-specialization
cache fragmentation
context-management complexity
```

Therefore:

> **The objective is not Maximum Context. It is Maximum Useful Structural Information at Minimum Context Cost.**

---

# 22. Marginal Context Gain

The Context Matrix allows measurement of marginal contribution.

For Domain:

```text
MarginalGain(D)
=
Score(A1) - Score(A0)
```

For Space:

```text
MarginalGain(S)
=
Score(A2) - Score(A0)
```

For Time:

```text
MarginalGain(T)
=
Score(A3) - Score(A0)
```

These are first-order gains.

---

# 23. Conditional Marginal Gain

A dimension may be useful only after another dimension is present.

For example:

```text
MarginalGain(S | D)
=
Score(A4) - Score(A1)
```

Similarly:

```text
MarginalGain(T | D)
=
Score(A5) - Score(A1)
```

and:

```text
MarginalGain(T | D,S)
=
Score(A7) - Score(A4)
```

This is more informative than measuring only absolute gain from A0.

---

# 24. Context Interaction

Suppose:

```text
Gain(D) = +0.10
Gain(S) = +0.08
```

but:

```text
Gain(D,S) = +0.30
```

Then Domain and Space exhibit strong positive interaction.

Conversely:

```text
Gain(D,S) = +0.11
```

may indicate substantial redundancy.

Thus context dimensions may be:

```text
complementary
redundant
independent
conflicting
```

---

# 25. Context Interaction Gain

A conceptual interaction measure is:

```text
Interaction(D,S)
=
Gain(D,S)
-
Gain(D)
-
Gain(S)
```

Interpretation:

```text
> 0
Positive interaction

≈ 0
Approximately additive

< 0
Redundancy or interference
```

The same idea applies to:

```text
D × T
S × T
D × S × T
```

---

# 26. Context Matrix as an Ablation Study

The D/S/T Matrix is essentially a structural-context ablation experiment.

Instead of asking only:

```text
Does context help?
```

it asks:

```text
Which context helps?

Which combination helps?

Which context is unnecessary?

Which context causes interference?
```

This makes the algorithm experimentally decomposable.

---

# 27. Recommended Baseline Extension

Each D/S/T condition should ideally also be compared against an ordinary natural-language context condition.

For example:

```text
B0:
Fix the rollback behavior.
```

```text
B1:
This task concerns rollback behavior in the database
transaction manager at version 42.
Fix the rollback behavior.
```

```text
A7:
Fix the rollback behavior.

rollback@DatabaseTransaction@TransactionManager@Version42
```

This asks whether structured context provides value beyond ordinary prompt engineering.

---

# 28. Factorized vs Natural-Language Context

Natural-language context often combines multiple dimensions implicitly.

For example:

```text
In version 42 of the PaymentService transaction manager,
fix the database rollback behavior.
```

contains:

```text
Domain
Space
Time
```

but not in explicitly factorized form.

CBT makes the dimensions structurally visible:

```text
rollback
+
rollback@DatabaseTransaction
+
rollback@TransactionManager
+
rollback@Version42
```

or:

```text
rollback@DatabaseTransaction@TransactionManager@Version42
```

The experiment should determine whether this explicit factorization matters.

---

# 29. Separate CBTs vs Composite CBT

Two representation styles should be distinguished.

## Style A — Separate Dimension CBTs

```text
rollback
rollback@DatabaseTransaction
rollback@TransactionManager
rollback@Version42
```

## Style B — Composite CBT

```text
rollback
rollback@DatabaseTransaction@TransactionManager@Version42
```

Both preserve the baseline token.

They may behave differently.

---

# 30. Why Separate CBTs May Help

Separate CBTs expose independent evidence:

```text
Domain Evidence
Space Evidence
Time Evidence
```

This may make ablation and policy control easier.

For example:

```text
remove Time
```

without changing Domain or Space.

---

# 31. Why Composite CBTs May Help

A composite CBT expresses a joint structural coordinate:

```text
token@(D,S,T)
```

This may provide stronger local binding when the combination itself is important.

However, it may also increase specialization.

Both forms should eventually be tested.

---

# 32. Canonical v1.0.0 Representation

For validation clarity, the recommended initial representation is:

```text
raw token
+
separate CBT dimensions
```

Example:

```text
rollback
rollback@DatabaseTransaction
rollback@TransactionManager
rollback@Version42
```

This makes the contribution of each dimension easier to isolate.

---

# 33. Domain Test Family

Domain cases should include tokens whose meaning changes substantially across domains.

Examples:

```text
commit@Git
commit@Database

branch@Git
branch@ControlFlow

node@CallingGraph
node@DistributedSystem

cache@LLMRuntime
cache@Database
```

These cases test semantic disambiguation.

---

# 34. Space Test Family

Space cases should hold domain relatively stable while changing structural location.

Example:

```text
retry@TransactionManager

retry@PaymentGateway

retry@MessageConsumer
```

All may belong to the same broad software domain, but require different behavior.

These cases test local structural binding.

---

# 35. Time Test Family

Time cases should involve real state or version differences.

Example:

```text
API@Version1

API@Version2
```

or:

```text
policy@BeforeMigration

policy@AfterMigration
```

The correct answer should depend materially on the time dimension.

---

# 36. Domain-Space Test Family

Example:

```text
node@CallingGraph@PaymentService

node@CallingGraph@OrderService
```

The domain identifies the object type.

The space identifies its local role.

This tests hierarchical localization.

---

# 37. Domain-Time Test Family

Example:

```text
schema@Database@Version3

schema@Database@Version4
```

This is useful for:

```text
migration
compatibility
historical reasoning
version-aware cache
```

---

# 38. Space-Time Test Family

Example:

```text
policy@DeploymentPipeline@Release42

policy@DeploymentPipeline@Release43
```

This tests whether local structure plus temporal state is sufficient.

---

# 39. Full Domain-Space-Time Test Family

Example:

```text
retry
retry@DatabaseTransaction
retry@TransactionManager
retry@Version42
```

or composite:

```text
retry@DatabaseTransaction@TransactionManager@Version42
```

The expected behavior should require all three dimensions in at least some test cases.

Otherwise A7 cannot be meaningfully validated.

---

# 40. Context Necessity Cases

Some cases should be deliberately constructed so that:

```text
Domain is necessary
Space is irrelevant
Time is irrelevant
```

Others:

```text
Space is necessary
Domain alone is insufficient
```

Others:

```text
Time is decisive
```

And some:

```text
D + S + T are all necessary
```

This prevents the benchmark from accidentally favoring one dimension.

---

# 41. Redundant Context Cases

Include cases where one dimension is already implied.

Example:

```text
The PaymentService TransactionManager...
```

may already strongly imply Space.

Adding:

```text
TransactionManager
```

again may produce little gain.

These cases test whether policy can avoid redundant context injection.

---

# 42. Misleading Domain Test

Inject the wrong domain:

```text
commit@Database
```

when the actual task concerns:

```text
Git
```

Measure:

```text
performance loss
anchoring
baseline recovery
counter-evidence sensitivity
```

---

# 43. Misleading Space Test

Inject:

```text
retry@PaymentGateway
```

when the relevant component is:

```text
TransactionManager
```

This tests wrong-locality effects.

---

# 44. Stale Time Test

Inject:

```text
API@Version1
```

when the task requires:

```text
Version2
```

This is especially important for cache and historical intelligence.

Time errors may cause correct historical knowledge to become incorrect current guidance.

---

# 45. Conflicting Context Test

A useful adversarial case is:

```text
Domain:
DatabaseTransaction

Space:
GitRepository
```

The dimensions conflict.

The system should not blindly accept the composite context.

Expected outcomes may include:

```text
AMBIGUOUS
REJECT_CONTEXT
BACKOFF_CONTEXT
REQUEST_RELOCALIZATION
```

---

# 46. Context Consistency

Before injection, a Context Consistency check may ask:

```text
Is Domain compatible with Space?

Is Space compatible with Time?

Is Domain compatible with Time?

Does the full D/S/T combination exist
in the MDT neighborhood?
```

This provides structural counter-evidence before inference.

---

# 47. Context Consistency Matrix

Conceptually:

| Pair           | Compatibility       |
| -------------- | ------------------- |
| Domain ↔ Space | High / Medium / Low |
| Domain ↔ Time  | High / Medium / Low |
| Space ↔ Time   | High / Medium / Low |

The full context can then receive:

```text
ContextConsistencyScore
```

The exact formula remains policy-specific.

---

# 48. Context Confidence by Dimension

Confidence should be factorized where possible.

Example:

```text
DomainConfidence = 0.98

SpaceConfidence = 0.92

TimeConfidence = 0.61
```

This is more useful than assigning only one confidence to the whole context.

---

# 49. Confidence-Governed Injection

A policy may use:

```text
DomainConfidence > 0.90
→ Inject Domain

SpaceConfidence > 0.85
→ Inject Space

TimeConfidence = 0.61
→ Do not inject Time
```

Thus the resulting CBT may be:

```text
token@Domain@Space
```

rather than blindly using all three dimensions.

---

# 50. Top-K Context by Dimension

If Domain is ambiguous:

```text
DomainCandidate1 = Database
DomainCandidate2 = Git
```

while Space and Time are known, the system may preserve:

```text
Top-K Domain Candidates
```

instead of forcing one D/S/T coordinate.

This supports uncertainty-preserving localization.

---

# 51. Context Backoff

Suppose:

```text
D + S + T
```

produces poor validation.

Backoff can test:

```text
D + S
D + T
S + T
D
S
T
Baseline
```

This is not random removal.

It is structured context ablation.

---

# 52. Context Backoff Tree

```text
                     D + S + T
                  /      |      \
               D+S      D+T      S+T
              /  \      / \      / \
             D    S    D   T    S   T
              \   |     \  |    /  /
                    Baseline
```

The system can search for the smallest validated context.

---

# 53. Metric Policy and D/S/T

MDT distance may itself depend on D/S/T weighting.

Conceptually:

```text
Distance
=
wD × DomainDistance
+
wS × SpaceDistance
+
wT × TimeDistance
```

where:

```text
wD
wS
wT
```

are policy-controlled weights.

The exact metric is application-specific.

---

# 54. Storage-Rich, Decision-Sparse Principle

A key principle is:

> **Preserve many potentially useful context dimensions in the Starmap; use a sparse, task-specific subset for localization and injection.**

Thus:

```text
Storage:
D + S + T + Role + State + Policy + History + ...

Decision:
D + S
```

may be perfectly valid.

---

# 55. Task-Dependent Context Weight

Different tasks may prioritize different dimensions.

For semantic explanation:

```text
Domain
```

may dominate.

For AI coding localization:

```text
Space
```

may dominate.

For version compatibility:

```text
Time
```

may dominate.

For production debugging:

```text
Domain + Space + Time
```

may all matter.

Therefore there is no universal fixed D/S/T weighting.

---

# 56. Context Policy by Task

A conceptual policy table:

| Task Type               | Domain |  Space |   Time |
| ----------------------- | -----: | -----: | -----: |
| Semantic Disambiguation |   High |    Low |    Low |
| Code Localization       | Medium |   High | Medium |
| Version Compatibility   | Medium | Medium |   High |
| Historical Analysis     | Medium |    Low |   High |
| Runtime Debugging       |   High |   High |   High |
| Search                  |   High | Medium | Medium |
| Cache Lookup            |   High |   High |   High |

These are hypotheses to validate, not fixed rules.

---

# 57. Primary Measurements

For every matrix cell, record:

```text
Task Score

Validation Result

Context Gain

Token Cost

Latency

Stability

Context Confidence

Counter-Evidence

Final Decision
```

This creates a multidimensional evaluation rather than a single-score benchmark.

---

# 58. Matrix Score Table

A basic result table:

| Condition | Score | Gain vs A0 | Validation | Token Δ |
| --------- | ----: | ---------: | ---------- | ------: |
| A0        |  0.60 |       0.00 | PASS       |       0 |
| A1 D      |  0.82 |      +0.22 | PASS       |      +5 |
| A2 S      |  0.70 |      +0.10 | PASS       |      +6 |
| A3 T      |  0.61 |      +0.01 | PASS       |      +4 |
| A4 D+S    |  0.91 |      +0.31 | PASS       |     +11 |
| A5 D+T    |  0.81 |      +0.21 | PASS       |      +9 |
| A6 S+T    |  0.72 |      +0.12 | PASS       |     +10 |
| A7 D+S+T  |  0.91 |      +0.31 | PASS       |     +15 |

In this example:

```text
A4
```

would likely be preferred over A7.

Time adds cost without measurable gain.

---

# 59. Context Efficiency

Define conceptually:

```text
ContextEfficiency
=
Validated Context Gain
/
Context Cost
```

where Context Cost may be:

```text
added tokens
latency
encoding complexity
```

This helps distinguish:

```text
highest score
```

from:

```text
best engineering choice
```

---

# 60. Dimension Efficiency

Similarly:

```text
DomainEfficiency
=
MarginalGain(D)
/
Cost(D)
```

and:

```text
SpaceEfficiency
TimeEfficiency
```

can be compared.

This may guide default context policy.

---

# 61. Saturation

Context gain may follow:

```text
A0 < A1 < A4 ≈ A7
```

This indicates saturation.

Once sufficient context has been provided, additional dimensions contribute little.

The Context Policy should detect this region.

---

# 62. Context Dilution

Another possible pattern is:

```text
A0 < A1 < A4 > A7
```

Here full context reduces performance.

Possible causes include:

```text
noise
irrelevant time information
over-specialization
conflicting evidence
prompt complexity
```

This is Context Dilution.

---

# 63. Context Reversal

A dangerous pattern is:

```text
A1 > A0
```

but:

```text
A4 < A0
```

This suggests that adding Space reversed the benefit of Domain.

Such interaction should be preserved as Negative Delta Intelligence.

---

# 64. Context Gain Curve

For a selected case, plot conceptually:

```text
Performance
   ^
   |
   |            ●
   |        ●       ●
   |     ●
   |  ●
   +-------------------->
       Context Amount
```

The expected optimum may occur before maximum context.

Therefore:

> **Context has a utility curve, not an unlimited monotonic benefit.**

---

# 65. Per-Case Best Context

Each test case should identify:

```text
BestValidatedContext
```

Example:

```text
Case C-001
Best = D

Case C-002
Best = D+S

Case C-003
Best = T

Case C-004
Best = D+S+T
```

These results can later be folded into Context Policy.

---

# 66. Per-Task Best Context

Aggregate cases by task:

```text
AI Coding
Search
Cache
Routing
Reasoning
Version Analysis
```

Then determine:

```text
PreferredContext(TaskType)
```

This converts experimental results into reusable structural policy.

---

# 67. Per-Token Best Context

Some tokens may repeatedly benefit from particular context dimensions.

Example:

```text
commit
→ Domain is highly valuable

node
→ Domain + Space

version
→ Time

retry
→ Domain + Space + Time
```

These patterns may eventually become CBT-generation knowledge.

---

# 68. Context Policy Learning

Validated cases can produce:

```text
Task
+
Token Type
+
Context Dimensions
+
Observed Gain
```

which can be folded as:

```text
Context Injection Policy Experience
```

This creates a path from manual validation toward learned structural policy.

---

# 69. Positive Context Pattern

Example:

```text
Task:
AI Coding

Token:
rollback

Domain:
DatabaseTransaction

Space:
TransactionManager

Observed:
D+S consistently improves localization
```

This can become positive policy evidence.

---

# 70. Negative Context Pattern

Example:

```text
Task:
Semantic Explanation

Time:
Build Version

Observed:
No gain, increased token cost
```

This becomes negative policy evidence.

Future injection can omit Time for similar tasks.

---

# 71. Connection to TACG-SDIG

A successful context policy case can be represented as:

```text
Task
   ↓
Context Selection
   ↓
CBT Injection
   ↓
Inference
   ↓
Validated Gain
```

This is itself a Task-Action-Delta pattern.

Therefore successful and failed D/S/T selections can become TACG-SDIG experience.

---

# 72. Connection to MDT

The D/S/T matrix also informs MDT metric policy.

If experiments repeatedly show:

```text
Domain highly discriminative
Space moderately discriminative
Time weak
```

for a task family, MDT localization may use corresponding weighting.

Thus downstream validation can feed back into upstream structural organization.

---

# 73. Bidirectional Learning

The loop becomes:

```text
MDT
 ↓
UTN Context
 ↓
D/S/T CBT
 ↓
Inference
 ↓
Validation
 ↓
Observed Context Gain
 ↓
Metric / Injection Policy Update
 ↓
MDT / UTN
```

This is a closed structural learning loop.

---

# 74. Connection to Search

Search can use the same matrix.

Compare:

```text
query
query@Domain
query@Space
query@Time
query@Domain@Space
...
```

Measure:

```text
precision
recall
candidate count
latency
```

The best context for LLM inference may differ from the best context for search.

---

# 75. Connection to Cache

Cache keys can also be evaluated using D/S/T.

Too broad:

```text
query
```

Too narrow:

```text
query@D@S@T
```

may reduce reuse.

The matrix can determine which dimensions are necessary for safe cache separation.

---

# 76. Cache Context Matrix

For cache experiments, measure:

```text
hit rate
wrong-hit rate
reuse rate
invalidation rate
storage growth
```

Example:

```text
D only
→ high hit rate, some collisions

D+S
→ lower hit rate, fewer collisions

D+S+T
→ very precise, poor reuse
```

The optimum becomes a policy decision.

---

# 77. Connection to Delta Intelligence

A Delta may require more context than an ordinary query.

For example:

```text
IncreaseRetryCount
```

may only be reusable under:

```text
Domain
+
Space
+
Runtime State
+
Time
```

Therefore Delta Intelligence may use stricter context granularity than search.

---

# 78. Connection to Brain Units

Brain-Unit dispatch may often depend primarily on:

```text
Domain
+
Space
```

while Time is handled inside the Brain Unit.

For example:

```text
DatabaseTransaction
+
TransactionManager
→ Transaction Recovery Brain Unit
```

Then:

```text
Version42
```

is passed as local task context.

This is another experimentally testable architecture.

---

# 79. Different Consumers, Different Context Policies

The same stored context can support different projections.

```text
Full Context
      │
      ├── Search → D
      ├── Cache → D + S + T
      ├── LLM → D + S
      ├── Delta → D + S + T
      └── Brain Unit → D + S
```

This illustrates why context storage and context consumption should remain separate.

---

# 80. Context Projection

Define:

> **Context Projection**

as selecting a consumer-specific subset of the full structural context.

Conceptually:

```text
Full Starmap Context
        ↓
Projection Policy
        ↓
Consumer Context
```

This may become a core future runtime abstraction.

---

# 81. Context Projection Function

Conceptually:

```text
Project(
    FullContext,
    Consumer,
    Task,
    Policy
)
→
SelectedContext
```

Examples:

```text
Project(C, LLM, CodingTask)
→ D + S

Project(C, Cache, QueryTask)
→ D + S + T

Project(C, Search, DiscoveryTask)
→ D
```

The v1.0.0 matrix provides the experimental foundation for learning such projections.

---

# 82. Baseline Preservation Across the Matrix

Every matrix condition must still satisfy:

```text
Recover(A1) = A0
Recover(A2) = A0
Recover(A3) = A0
...
Recover(A7) = A0
```

This preserves the BPCI principle.

All D/S/T experiments therefore share one canonical control.

---

# 83. Paired Experimental Control

For each case:

```text
A0
vs
A1

A0
vs
A2

A0
vs
A3

...

A0
vs
A7
```

Additional pairwise comparisons can then measure marginal contribution:

```text
A1 vs A4
A1 vs A5
A4 vs A7
```

---

# 84. Experimental Record

A conceptual record:

```text
DstValidationRecord
{
    caseId
    taskType

    baselineInput

    domain
    space
    time

    domainConfidence
    spaceConfidence
    timeConfidence

    contextConsistency

    scores {
        A0
        A1
        A2
        A3
        A4
        A5
        A6
        A7
    }

    costs {
        A0
        A1
        A2
        A3
        A4
        A5
        A6
        A7
    }

    bestValidatedContext
    minimumSufficientContext

    counterEvidence
    finalPolicy
}
```

---

# 85. Minimal Case Report

```text
Case ID:

Task:

Baseline Input:

Domain:

Space:

Time:

Domain Confidence:

Space Confidence:

Time Confidence:

Context Consistency:

A0 Score:

A1 D Score:

A2 S Score:

A3 T Score:

A4 D+S Score:

A5 D+T Score:

A6 S+T Score:

A7 D+S+T Score:

Best Validated Context:

Minimum Sufficient Context:

Cost Difference:

Counter-Evidence:

Final Policy:
```

---

# 86. Summary Matrix

A repository-level summary may use:

| Case |  A0 |   D |   S |   T | D+S | D+T | S+T | D+S+T | MSC |
| ---- | --: | --: | --: | --: | --: | --: | --: | ----: | --- |
| C01  | .60 | .82 | .70 | .61 | .91 | .81 | .72 |   .91 | D+S |
| C02  | .75 | .76 | .90 | .74 | .91 | .75 | .89 |   .90 | S   |
| C03  | .55 | .60 | .58 | .88 | .61 | .90 | .89 |   .90 | T   |

This makes context specialization visible immediately.

---

# 87. Aggregate Dimension Report

Across all cases, report:

```text
Average Gain(D)

Average Gain(S)

Average Gain(T)

Average Gain(D,S)

Average Gain(D,T)

Average Gain(S,T)

Average Gain(D,S,T)
```

and:

```text
Average Marginal Gain

Average Cost

Validation Pass Rate

Negative Gain Rate
```

for each context subset.

---

# 88. Dimension Importance

A simple empirical ranking may emerge:

```text
Domain > Space > Time
```

for one task family.

Another may produce:

```text
Space > Time > Domain
```

These rankings should remain task-specific.

The framework should resist premature universalization.

---

# 89. Cross-Model Validation

The same D/S/T matrix can be tested across different models.

The question becomes:

```text
Does the same context policy generalize?
```

Possible outcomes:

```text
Model A prefers D
Model B prefers D+S
Model C reconstructs context well and gains little
```

This is useful evidence about model dependence.

---

# 90. Cross-Language Validation

CBT can also test multilingual structural identity.

Example:

```text
folding@StructuralIntelligence

折叠@StructuralIntelligence
```

Both share:

```text
Domain = StructuralIntelligence
```

The D/S/T matrix can test whether explicit structural context improves cross-language consistency.

---

# 91. Cross-Repository Validation

The same token may occur in multiple repositories.

Example:

```text
node@RepositoryA

node@RepositoryB
```

Here repository identity can be treated as Space.

This tests whether CBT reduces cross-repository structural confusion.

---

# 92. AI Coding Canonical Example

Baseline:

```text
Fix the retry logic after rollback.
```

Context:

```text
D:
DatabaseTransaction

S:
PaymentService.TransactionManager

T:
Version42
```

Matrix:

```text
A0
retry

A1
retry@DatabaseTransaction

A2
retry@TransactionManager

A3
retry@Version42

A4
retry@DatabaseTransaction
retry@TransactionManager

A5
retry@DatabaseTransaction
retry@Version42

A6
retry@TransactionManager
retry@Version42

A7
retry@DatabaseTransaction
retry@TransactionManager
retry@Version42
```

The original sentence remains unchanged in every condition.

Only the explicit structural evidence varies.

---

# 93. Search Canonical Example

Query:

```text
rollback failure
```

D:

```text
DatabaseTransaction
```

S:

```text
TransactionManager
```

T:

```text
Version42
```

Measure:

```text
candidate count
precision
recall
top-k relevance
latency
```

The matrix reveals how much structural narrowing each dimension provides.

---

# 94. Cache Canonical Example

Raw key:

```text
rollback-failure
```

Candidate context keys:

```text
rollback-failure@DatabaseTransaction

rollback-failure@TransactionManager

rollback-failure@Version42

rollback-failure@DatabaseTransaction@TransactionManager

...
```

Measure the tradeoff between:

```text
reuse
collision
fragmentation
staleness
```

---

# 95. Brain-Unit Canonical Example

Task:

```text
Repair retry behavior.
```

Potential dispatch:

```text
D only
→ Database Brain Unit

S only
→ TransactionManager Specialist

D + S
→ Transaction Recovery Brain Unit

D + S + T
→ Same Brain Unit + Version-Specific Context
```

This helps determine which dimensions should control dispatch and which should remain task-local evidence.

---

# 96. Validation Decision Logic

```text
FOR each test case:

    Freeze A0

    Identify D, S, T

    Verify confidence and consistency

    Generate A1 ... A7

    Verify:
        Recover(Ai) = A0

    Run all conditions

    Validate outputs

    Measure:
        score
        gain
        cost
        stability

    Determine:
        best validated context

    Determine:
        minimum sufficient context

    Search:
        counter-evidence
        wrong-context sensitivity

    Record:
        positive context deltas
        negative context deltas

    Derive:
        context policy
```

---

# 97. Context Selection Decision Logic

```text
IF no dimension produces validated gain
    use baseline

ELSE

    find highest validated utility

    find smallest context subset
    within accepted tolerance

    IF context confidence is insufficient
        backoff

    IF context dimensions conflict
        preserve ambiguity

    ELSE
        use Minimum Sufficient Context
```

---

# 98. Validation Invariants

## Invariant 1 — Same Baseline

All D/S/T conditions derive from the same original input.

## Invariant 2 — Recoverability

Every enhanced condition can return to A0.

## Invariant 3 — Factorized Dimensions

Domain, Space, and Time remain independently removable.

## Invariant 4 — Rich Storage, Sparse Injection

Stored context does not imply full context injection.

## Invariant 5 — Maximum Context Is Not Automatically Preferred

A7 must earn its additional complexity.

## Invariant 6 — Context Confidence Is Dimension-Specific

D, S, and T may have different confidence levels.

## Invariant 7 — Context Conflict Is Explicit

Incompatible D/S/T combinations should not be silently merged.

## Invariant 8 — Unknown Is Valid

Missing Domain, Space, or Time should remain missing when evidence is insufficient.

## Invariant 9 — Negative Gain Is Preserved

Harmful context combinations become policy evidence.

## Invariant 10 — Consumer Policy May Differ

LLM, Search, Cache, Delta, and Brain Units may require different context projections.

---

# 99. Failure Modes

## Failure Mode A — Maximum-Context Bias

Always assuming D+S+T is superior.

## Failure Mode B — Dimension Entanglement

Encoding D/S/T so tightly that individual contribution cannot be tested.

## Failure Mode C — Context Leakage

Changing the baseline while constructing a context condition.

## Failure Mode D — Stale Time

Using an obsolete temporal context.

## Failure Mode E — Wrong Space

Localizing to the wrong subsystem.

## Failure Mode F — Wrong Domain

Injecting semantically misleading domain evidence.

## Failure Mode G — Context Conflict

Combining mutually incompatible dimensions.

## Failure Mode H — Context Dilution

Adding weak dimensions reduces performance.

## Failure Mode I — Ignoring Cost

Selecting A7 for negligible gain over A4.

## Failure Mode J — Universal Policy Assumption

Assuming one D/S/T combination is optimal for every consumer and task.

---

# 100. Research Questions

### RQ-1

Which of Domain, Space, and Time provides the highest standalone Context Gain?

### RQ-2

Which pairwise context combinations provide positive interaction?

### RQ-3

When is D+S+T necessary?

### RQ-4

When does additional context become redundant?

### RQ-5

When does context dilution occur?

### RQ-6

What is the Minimum Sufficient Context for each task class?

### RQ-7

How should context confidence affect dimension selection?

### RQ-8

How should conflicting D/S/T coordinates be handled?

### RQ-9

Does structured D/S/T encoding outperform equivalent natural-language context?

### RQ-10

Do separate CBT dimensions outperform composite CBTs?

### RQ-11

How do optimal context projections differ across LLM, Search, Cache, Delta Intelligence, and Brain Units?

### RQ-12

Can D/S/T validation results improve MDT metric weighting?

### RQ-13

Can successful context-selection policies be folded into TACG-SDIG experience?

### RQ-14

How stable are D/S/T policies across models, languages, repositories, and versions?

### RQ-15

Can context projection reduce computation while preserving or improving task quality?

---

# 101. Canonical Experimental Summary

```text
                         FULL CONTEXT
                              │
                              ▼
                    GenericContainerStarmap
                              │
             ┌────────────────┼────────────────┐
             ▼                ▼                ▼
           DOMAIN           SPACE             TIME
             │                │                │
             └────────────────┼────────────────┘
                              ▼
                     CONTEXT MATRIX

                 ┌────────────┼────────────┐
                 │            │            │
                 ▼            ▼            ▼
                 D            S            T
                 │            │            │
                 ├─────┐      │      ┌─────┤
                 ▼     ▼      ▼      ▼     ▼
                D+S   D+T          S+T
                  \     \          /     /
                   \     \        /     /
                    └─────D+S+T───┘
                              │
                              ▼
                      Paired Validation
                              │
                              ▼
                         Context Gain
                              │
             ┌────────────────┼────────────────┐
             ▼                ▼                ▼
            Cost          Stability      Counter-Evidence
             │                │                │
             └────────────────┼────────────────┘
                              ▼
                    BEST VALIDATED CONTEXT
                              │
                              ▼
                  MINIMUM SUFFICIENT CONTEXT
                              │
                              ▼
                       CONTEXT POLICY
```

---

# 102. Conclusion

Domain, Space, and Time provide a compact first decomposition of structural context.

They answer:

```text
Domain
→ What kind of structural world?

Space
→ Where inside that world?

Time
→ Which state of that world?
```

The MDT-UTN system may preserve all three dimensions and many more.

But Context-Bound Token Intelligence should not blindly expose everything.

Instead:

```text
Rich Structural Context
        ↓
Factorization
        ↓
D / S / T Validation
        ↓
Marginal Context Gain
        ↓
Context Interaction
        ↓
Minimum Sufficient Context
        ↓
Policy-Controlled Injection
```

The central experimental question is therefore not:

> **How much context can we add?**

It is:

> **What is the smallest structural context that produces the largest validated intelligence gain for the current task?**

This leads to the primary design principle:

> **Preserve context richly; project context selectively.**

And the primary engineering principle:

> **Context should earn its place through measured marginal gain.**

---

## Canonical Principle

```text
FULL CONTEXT
     ↓
Domain / Space / Time
     ↓
Measure Each Dimension
     ↓
Measure Their Interactions
     ↓
Reject Redundant or Harmful Context
     ↓
Select Minimum Sufficient Context
     ↓
Inject
     ↓
Validate
     ↓
Fold the Result into Context Policy
```

> **Domain tells us what structural world we are in.
> Space tells us where we are inside it.
> Time tells us which state of that world applies.
> The Context Matrix tells us which of those coordinates are actually worth using.**
