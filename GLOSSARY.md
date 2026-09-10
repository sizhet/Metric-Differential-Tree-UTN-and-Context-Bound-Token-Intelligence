# GLOSSARY — MDT-UTN-CBT

## Metric-Differential-Tree UTN and Context-Bound Token Intelligence

This glossary defines the canonical terminology used throughout the MDT-UTN-CBT repository.

The terms are organized around the main progression:

```text
Context
   ↓
Structural Representation
   ↓
Metric Localization
   ↓
MDT
   ↓
UTN
   ↓
Structural Identity
   ↓
Context-Bound Token
   ↓
Context Address
   ↓
Reusable Intelligence
   ↓
Structural Growth
````

---

# 1. Context

## Definition

**Context** is the set of structural conditions that determine how a target should be interpreted, localized, typed, named, searched, reused, or acted upon.

Context may include:

```text
Domain
Space
Time
Role
State
Policy
Version
Dependencies
CallingGraph Position
History
Runtime Conditions
```

## Principle

> **Context is primary; naming is secondary.**

A name is a symbolic interface.

Context provides the structural evidence behind that interface.

---

# 2. Target

## Definition

A **Target** is the object, token, function, node, event, query, behavior, task, state, or other entity whose structural context is being analyzed.

Examples:

```text
rollback

Function X

CallingGraph Node A

Transaction Failure

Search Query Q
```

A Target becomes meaningful for UTN only when considered together with its context.

---

# 3. Context Starmap

## Definition

A **Context Starmap** is a structured representation of a target's context.

It contains multiple named dimensions or features that can participate in structural comparison.

Conceptually:

```text
Context Starmap
{
    Domain
    Space
    Time
    Role
    State
    Policy
    ...
}
```

The Context Starmap provides the input representation for metric localization.

---

# 4. GenericContainerStarmap

## Definition

**GenericContainerStarmap** is the general structural container used to represent heterogeneous context information.

It may contain:

```text
named scalar values
named string values
named numeric sequences
named symbolic sequences
other structured attributes
```

Its purpose is not to impose one domain-specific schema.

Its purpose is to provide a common structural representation suitable for metric comparison.

## Role

```text
Raw Context
   ↓
GenericContainerStarmap
   ↓
Metric Similarity / Distance
```

---

# 5. Metric Similarity

## Definition

**Metric Similarity** measures how structurally close two Context Starmaps are under a selected metric policy.

Higher similarity indicates stronger structural resemblance.

Similarity is used primarily for:

```text
candidate localization
candidate clustering
candidate parent formation
candidate reuse
```

## Important Rule

> **Similarity creates candidates, not truth.**

A high similarity score does not automatically justify typing or merging.

---

# 6. Metric Distance

## Definition

**Metric Distance** measures structural difference between two Context Starmaps.

Lower distance generally indicates greater structural proximity.

Conceptually:

```text
Distance(A, B)
```

may combine multiple dimensions:

```text
Domain Distance
Space Distance
Time Distance
Behavior Distance
Sequence Distance
Policy Distance
```

under a Metric Policy.

---

# 7. Metric Policy

## Definition

A **Metric Policy** determines which context dimensions participate in comparison and how strongly they are weighted.

Conceptually:

```text
Distance
=
wD × DomainDistance
+
wS × SpaceDistance
+
wT × TimeDistance
+
...
```

The exact formula is application-specific.

## Principle

> **Preserve context richly; govern effective dimensions through policy.**

---

# 8. Metric-Differential Tree

## Abbreviation

**MDT**

## Definition

A **Metric-Differential Tree** is a hierarchical structural organization in which Context Starmaps are progressively grouped and differentiated according to metric similarity, distance, and policy-governed structural boundaries.

Conceptually:

```text
                     Root
                      │
              ┌───────┴───────┐
              │               │
           Region A         Region B
              │
         ┌────┴────┐
         │         │
      Type A1   Type A2
         │
      Leaves
```

## Purpose

MDT converts a global structural classification problem into localized neighborhood decisions.

---

# 9. Metric-Differential Localization

## Definition

**Metric-Differential Localization** is the process of finding the structural neighborhood in the MDT that best corresponds to a target Context Starmap.

The result may be:

```text
exact leaf neighborhood
existing parent type
candidate sibling region
ambiguous region
leftover region
```

Localization precedes typing.

---

# 10. Structural Neighborhood

## Definition

A **Structural Neighborhood** is a local MDT region containing structurally related leaves, parent nodes, siblings, and nearby alternatives.

Per-Node Intelligence operates primarily within such neighborhoods.

## Principle

> **Localize first; compare locally.**

---

# 11. Leaf

## Definition

A **Leaf** is a structural individual preserved at the lower level of the MDT.

A leaf may retain:

```text
original context
original name
source
version
provenance
evidence
history
```

Leaves represent individual evidence, not merely labels.

---

# 12. Leaf Immutability Principle

## Definition

The **Leaf Immutability Principle** states that structural folding should not erase or overwrite the original individual evidence represented by leaves.

Canonical rule:

> **Fold upward; do not erase downward.**

Parent structure may evolve while original leaf provenance remains preserved.

---

# 13. Parent Type

## Definition

A **Parent Type** represents structural commonality shared by two or more descendant nodes.

A parent may exist before receiving a final human-friendly name.

Therefore:

> **Typing does not have to wait for Naming.**

---

# 14. Structural Type

## Definition

A **Structural Type** is a validated structural grouping defined by context similarity, compatibility, counter-evidence analysis, policy, and validation.

A Structural Type is deeper than a lexical name.

It represents shared structural identity.

---

# 15. Universal Typing

## Definition

**Universal Typing** is the process of determining whether structural individuals or subtrees can legitimately share a structural type.

Typical evidence includes:

```text
metric similarity
context compatibility
positive evidence
counter-evidence
historical cases
policy
validation
```

Possible outcomes include:

```text
reuse existing type
create new type
merge
split
defer
leftover
```

---

# 16. Universal Naming

## Definition

**Universal Naming** is the process of assigning a stable symbolic name or alias to an already justified structural type.

Naming may use:

```text
existing terminology
domain vocabulary
repository vocabulary
LLM suggestions
historical naming
human policy
```

Naming follows typing.

---

# 17. UTN

## Full Name

**Universal Typing and Naming**

## Definition

UTN is the combined process of:

```text
Structural Localization
      ↓
Typing
      ↓
Naming
```

Within this repository:

> **UTN is Typing-first, Naming-second.**

UTN is evolutionary rather than one-time.

---

# 18. MDT-UTN

## Definition

**MDT-UTN** is the use of a Metric-Differential Tree as the structural substrate for Universal Typing and Naming.

The canonical pipeline is:

```text
Context
   ↓
GenericContainerStarmap
   ↓
Metric Similarity / Distance
   ↓
MDT
   ↓
Per-Node UTN
   ↓
Structural Type
   ↓
Name / Alias
```

---

# 19. Per-Node Intelligence

## Definition

**Per-Node Intelligence** is localized intelligence attached to an MDT node or structural neighborhood.

It may perform:

```text
candidate comparison
merge decisions
split decisions
counter-evidence search
leftover handling
typing
naming
validation
policy application
historical-case lookup
```

Its main advantage is structural isolation.

---

# 20. Per-Node UTN Intelligence

## Definition

**Per-Node UTN Intelligence** is the specialized Per-Node Intelligence responsible for local typing-and-naming decisions.

Canonical sequence:

```text
Preserve Context
      ↓
Metric Localization
      ↓
Candidate Formation
      ↓
Positive Evidence Search
      ↓
Counter-Evidence Search
      ↓
Leftover Separation
      ↓
Policy Evaluation
      ↓
Type Decision
      ↓
Naming
      ↓
Validation
      ↓
Commit
      ↓
Learn
```

---

# 21. Positive Evidence

## Definition

**Positive Evidence** is evidence supporting a proposed structural relationship, merge, type, context interpretation, or reuse decision.

Examples:

```text
metric proximity
shared behavior
shared role
shared structural constraints
historical successful merges
validated similar cases
```

Positive evidence alone is not sufficient.

---

# 22. Counter-Evidence

## Definition

**Counter-Evidence** is evidence that challenges a proposed structural relationship or interpretation.

Examples:

```text
behavioral conflict
different runtime state
different policy
version mismatch
semantic contradiction
failed historical cases
unit-test failure
```

Counter-Evidence is a first-class input to UTN and runtime reuse.

---

# 23. Two-Way Structural Search

## Definition

**Two-Way Structural Search** means searching both:

```text
FOR a candidate structural decision
```

and:

```text
AGAINST the candidate structural decision
```

Conceptually:

```text
Candidate
   │
   ├── Supporting Evidence
   │
   └── Counter-Evidence
```

This reduces forced or overconfident structural merges.

---

# 24. Leftover

## Definition

A **Leftover** is a target or structural region that cannot yet be safely assigned to an existing type.

Reasons may include:

```text
novel structure
insufficient evidence
high noise
policy uncertainty
semantic conflict
metric ambiguity
```

## Principle

> **Leftover is an explicit structural state, not an error state.**

---

# 25. Explicit Leftover

## Definition

**Explicit Leftover** means that unresolved cases remain represented directly in the structure rather than being forced into the nearest available class.

Possible evolution:

```text
Leftover
   ↓
Repeated Similar Cases
   ↓
Metric Cluster
   ↓
New MDT Branch
   ↓
New Type
```

---

# 26. Structural Identity

## Definition

**Structural Identity** is the persistent identity of a target or type derived from structural context rather than merely from its lexical name.

Canonical identity layers:

```text
Structural Identity
        ↓
Universal Type ID
        ↓
Canonical Name
        ↓
Local Aliases
```

## Important Rule

```text
Rename ≠ Identity Change
```

---

# 27. Universal Type ID

## Definition

A **Universal Type ID** is a stable machine-oriented identifier for a Structural Type.

Conceptually:

```text
UTN-8F32A
```

or:

```text
utn://database/transaction/8F32A
```

The exact syntax is not fixed by v1.0.0.

Its role is to separate stable structural identity from mutable human-readable names.

---

# 28. Canonical Name

## Definition

A **Canonical Name** is the preferred human-readable label associated with a Structural Type.

Example:

```text
RetryableTransactionBehavior
```

A Canonical Name may change over time without destroying structural identity.

---

# 29. Alias

## Definition

An **Alias** is an alternative local or historical name mapped to the same Structural Type.

Aliases support:

```text
local vocabulary
cross-repository compatibility
cross-language naming
legacy terminology
```

Universal identity does not require lexical uniformity.

---

# 30. Universal Structural Addressability

## Definition

**Universal Structural Addressability** means that structurally equivalent entities can be resolved to shared or compatible structural identities even when their local names differ.

This is preferred over:

> universal lexical uniformity.

---

# 31. Evolutionary Identity

## Definition

**Evolutionary Identity** is structural identity that remains traceable while its:

```text
name
parent
aliases
metric policy
scope
version
```

may evolve.

Evolution should use explicit versioned mappings rather than silent replacement.

---

# 32. UTNMergeRecord

## Definition

A **UTNMergeRecord** is a conceptual audit record for a local typing or merge decision.

It may preserve:

```text
child nodes
parent type
metric policy
distance evidence
positive evidence
counter-evidence
leftovers
naming evidence
LLM suggestions
human decision
validation results
timestamp
version
```

Its purpose is full structural traceability.

---

# 33. Composable UTN

## Definition

**Composable UTN** is the principle that larger UTN structures should emerge through the composition of locally folded UTN trees.

Canonical progression:

```text
Local
   ↓
Subsystem
   ↓
Repository
   ↓
Organization
   ↓
Domain
   ↓
Universal
```

---

# 34. Folded UTN Merge

## Definition

**Folded UTN Merge** means merging mature UTN trees using their existing folded structure rather than flattening all trees back into raw leaves.

Principle:

> **Fold locally; merge folded structures globally; unfold only ambiguous regions.**

---

# 35. Hierarchical MDT Merge

## Definition

**Hierarchical MDT Merge** is tree-to-tree integration performed progressively:

```text
root alignment
   ↓
high-level branch comparison
   ↓
candidate subtree localization
   ↓
selective unfolding
   ↓
Per-Node UTN
```

This reduces unnecessary recomputation.

---

# 36. Selective Unfolding

## Definition

**Selective Unfolding** means expanding only those folded structural regions whose current representation is insufficient for a reliable decision.

Examples:

```text
ambiguous tree region
insufficient context
conflicting cache result
uncertain Brain-Unit dispatch
```

Selective Unfolding is central to computational efficiency.

---

# 37. CBT

## Full Name

**Context-Bound Token**

## Definition

A **Context-Bound Token** is a lexical-symbolic unit that binds a token or symbol to an explicit structural context identity.

Canonical notation:

```text
token@context
```

Examples:

```text
open@FileIO

open@NetworkSocket

commit@GitRepository

rollback@DatabaseTransaction

node@CallingGraph
```

---

# 38. `token@context`

## Definition

`token@context` is the canonical human-readable notation for a Context-Bound Token.

It represents:

```text
Lexical Symbol
+
Structural Context Identity
```

It should not automatically be interpreted as one atomic tokenizer vocabulary token.

---

# 39. Structured Bigram

## Definition

A **Structured Bigram** is an informal analogy for CBT.

Unlike a conventional adjacent lexical bigram:

```text
word1 word2
```

CBT expresses a structural conjunction:

```text
token@context
```

The relationship is semantic and structural rather than necessarily positional.

---

# 40. Dual-Track Encoding

## Definition

**Dual-Track Encoding** preserves both:

```text
raw token
```

and:

```text
context-bound token
```

Example:

```text
open
open@FileIO
```

Raw token supports:

```text
broad recall
compatibility
baseline semantics
```

CBT supports:

```text
structural precision
localization
routing
```

---

# 41. Structural Encoding

## Definition

**Structural Encoding** means exposing explicit structural identity in a representation that downstream intelligence systems can consume.

CBT is one low-intrusion form of Structural Encoding.

---

# 42. Structural Encoding Layer

## Definition

The **Structural Encoding Layer** is a conceptual layer between raw lexical input and downstream intelligence components.

Canonical flow:

```text
Raw Input
   ↓
Context Representation
   ↓
MDT / UTN
   ↓
Structural Encoding
   ↓
LLM / Search / Cache / Brain Unit
```

Its role is to provide reusable structural context without requiring immediate model-architecture modification.

---

# 43. Domain Context

## Definition

**Domain Context** identifies the semantic or functional world in which a target belongs.

Examples:

```text
commit@GitRepository

commit@DatabaseTransaction
```

Domain answers:

> **What kind of structural world are we in?**

---

# 44. Space Context

## Definition

**Space Context** identifies structural location.

Examples:

```text
function@TransactionManager

node@CallingGraph

policy@DeploymentPipeline
```

Space may include:

```text
repository
module
class
function
graph node
subsystem
tree branch
```

Space answers:

> **Where are we inside the structural world?**

---

# 45. Time Context

## Definition

**Time Context** identifies the relevant temporal state, version, lifecycle phase, or historical period.

Examples:

```text
schema@Version3

policy@CurrentRelease

function@BeforeRefactor
```

Time answers:

> **Which state of the structural world applies?**

---

# 46. D/S/T

## Full Name

**Domain / Space / Time**

## Definition

D/S/T is the first canonical factorization of context in this repository.

Conceptually:

```text
Context
=
(Domain, Space, Time)
```

It provides a compact initial structural coordinate system for validation.

---

# 47. Context Matrix

## Definition

A **Context Matrix** is a controlled experiment that evaluates different combinations of context dimensions.

For D/S/T:

```text
A0 = none
A1 = D
A2 = S
A3 = T
A4 = D + S
A5 = D + T
A6 = S + T
A7 = D + S + T
```

It is used to determine which structural dimensions provide measurable value.

---

# 48. Context Projection

## Definition

**Context Projection** selects a consumer-specific subset of a richer stored context.

Conceptually:

```text
Full Context
    ↓
Projection Policy
    ↓
Selected Context
```

Example:

```text
LLM    → Domain + Space
Search → Domain
Cache  → Domain + Space + Time
```

---

# 49. Context Projection Policy

## Definition

A **Context Projection Policy** decides which stored context dimensions should be exposed to a particular:

```text
task
consumer
runtime
model
search system
cache
Brain Unit
```

It separates rich context preservation from selective context consumption.

---

# 50. BPCI

## Full Name

**Baseline-Preserved Context Injection**

## Definition

BPCI is a controlled context-augmentation method in which the context-enhanced input preserves a mechanically recoverable context-free baseline.

Canonical relation:

```text
S1 = S0 + C
```

and:

```text
Recover(S1) = S0
```

where:

```text
S0 = baseline input
S1 = context-enhanced input
C  = injected context
```

---

# 51. Recoverable Baseline

## Definition

A **Recoverable Baseline** is the exact original input that can be reconstructed by removing explicitly injected structural context.

The recovery should be mechanical rather than manually rewritten.

---

# 52. Baseline Fidelity

## Definition

**Baseline Fidelity** measures whether removal of injected context produces the exact intended baseline.

Canonical check:

```text
Recover(S1) == S0
```

If this fails, the experiment does not satisfy strict BPCI methodology.

---

# 53. Paired-Control Inference

## Definition

**Paired-Control Inference** compares:

```text
Baseline Input
```

with:

```text
Context-Enhanced Input
```

under otherwise equivalent runtime conditions.

This creates a natural control group for measuring context effects.

---

# 54. Context Gain

## Definition

**Context Gain** is the measured performance difference caused by explicit context augmentation.

Conceptually:

```text
Context Gain
=
Score(Context-Enhanced)
-
Score(Baseline)
```

Possible outcomes:

```text
Positive Gain
Neutral Gain
Negative Gain
```

The Score must be task-specific.

---

# 55. Positive Context Gain

## Definition

**Positive Context Gain** occurs when context-enhanced performance exceeds baseline performance under the selected metric and validation criteria.

It may become Positive Delta Intelligence.

---

# 56. Negative Context Gain

## Definition

**Negative Context Gain** occurs when explicit context degrades performance relative to the baseline.

Possible causes:

```text
wrong context
context overload
anchoring
excessive specificity
conflicting evidence
dense repetition
```

Negative Context Gain should be preserved, not discarded.

---

# 57. Context Differential Test

## Definition

A **Context Differential Test** holds the raw token constant while changing the explicit context.

Example:

```text
commit@GitRepository

commit@DatabaseTransaction
```

The test verifies whether context produces the expected behavioral or semantic difference.

---

# 58. Context Injection

## Definition

**Context Injection** is the act of adding explicit structural context to an existing input while preserving the original baseline.

CBT is one form of Context Injection.

---

# 59. Context Injection Density

## Abbreviation

**CID**

## Definition

**Context Injection Density** measures how much explicit context-bound evidence is added relative to a defined baseline.

Conceptually:

```text
CID
=
Injected Context-Bound Units
/
Relevant Baseline Units
```

The exact denominator is implementation-specific but must remain consistent within an experiment.

---

# 60. Sparse Context Injection

## Definition

**Sparse Context Injection** introduces only a small number of high-value CBTs.

Example:

```text
rollback@DatabaseTransaction
```

Sparse injection is the preferred starting point.

---

# 61. Selective Context Injection

## Definition

**Selective Context Injection** introduces several complementary CBTs chosen for structural relevance.

Example:

```text
rollback@DatabaseTransaction
function@TransactionManager
version@Version42
```

The goal is complementary coverage rather than repetition.

---

# 62. Dense Context Injection

## Definition

**Dense Context Injection** introduces explicit context for many tokens or structural dimensions.

It is useful primarily for:

```text
experimental comparison
stress testing
high-structure tasks
```

Dense context should not automatically be the default.

---

# 63. Effective Context Density

## Definition

**Effective Context Density** estimates the amount of non-redundant structural information represented by injected context.

Three repeated CBTs may have high raw density but low effective density.

---

# 64. Context Redundancy

## Definition

**Context Redundancy** is repeated or overlapping context information that adds little new structural discrimination.

Example:

```text
rollback@Database
transaction@Database
database@Database
```

A good policy prefers complementary evidence over redundant repetition.

---

# 65. Context Depth

## Definition

**Context Depth** measures how specific a context identity is within a hierarchy.

Example:

```text
Database
   ↓
Transaction
   ↓
DatabaseTransaction
```

Higher depth means finer structural specialization.

---

# 66. Context Breadth

## Definition

**Context Breadth** measures how many distinct context dimensions, roles, or structural objects are explicitly represented.

Example:

```text
Domain
+
Space
+
Time
+
Policy
```

has broader structural coverage than Domain alone.

---

# 67. Context Depth-Density-Breadth Policy

## Definition

The **Context Depth-Density-Breadth Policy** controls three independent context dimensions:

```text
Depth
→ How specific?

Density
→ How much?

Breadth
→ How many structural dimensions?
```

These should not be conflated.

---

# 68. Minimum Sufficient Context

## Abbreviation

**MSC**

## Definition

**Minimum Sufficient Context** is the smallest context subset that achieves performance within an accepted tolerance of the best validated context condition.

Principle:

> **Use no more structural context than is needed for reliable performance.**

---

# 69. Minimum Effective Density

## Abbreviation

**MED**

## Definition

The **Minimum Effective Density** is the lowest tested context density that produces a predefined useful validated Context Gain.

---

# 70. Minimum Sufficient Density

## Abbreviation

**MSD**

## Definition

The **Minimum Sufficient Density** is the lowest context density whose validated utility is within an accepted tolerance of the best tested density.

It is often more useful operationally than maximum raw performance.

---

# 71. Maximum Safe Density

## Definition

**Maximum Safe Density** is the highest tested context density that remains within policy limits for:

```text
wrong-context persistence
instability
validation failure
cost
anchoring
```

---

# 72. Progressive Context Injection

## Definition

**Progressive Context Injection** begins with sparse context and adds more only when needed.

Canonical flow:

```text
Baseline
   ↓
Sparse Context
   ↓
Enough?
   ├── Yes → Stop
   └── No
        ↓
      Add Context
        ↓
      Revalidate
```

This is the context equivalent of selective unfolding.

---

# 73. Context Backoff

## Definition

**Context Backoff** removes, broadens, or reduces explicit context when the current context is:

```text
too specific
low confidence
harmful
conflicting
stale
```

Example:

```text
rollback@DatabaseTransaction
        ↓
rollback@Transaction
        ↓
rollback@Database
        ↓
rollback
```

---

# 74. Parent Backoff

## Definition

**Parent Backoff** moves from a specific MDT/UTN context toward a broader parent context.

It can be used for:

```text
search
cache
inference
Brain-Unit routing
```

when an exact context is unavailable or unreliable.

---

# 75. Child Expansion

## Definition

**Child Expansion** explores more specific descendants of a structural context.

Example:

```text
retry@Transaction
   ↓
retry@DatabaseTransaction
retry@DistributedTransaction
```

It is useful when broader context remains ambiguous.

---

# 76. Sibling Search

## Definition

**Sibling Search** explores structurally adjacent alternative contexts.

Example:

```text
rollback@DatabaseTransaction
rollback@Deployment
rollback@GitRepository
```

Sibling Search is particularly useful for counter-evidence and ambiguity resolution.

---

# 77. Top-K Context

## Definition

**Top-K Context** preserves multiple plausible context candidates rather than forcing one premature interpretation.

Example:

```text
rollback@DatabaseTransaction   0.55
rollback@Deployment            0.30
rollback@GitRepository         0.15
```

Top-K Context supports uncertainty preservation.

---

# 78. Context Confidence

## Definition

**Context Confidence** indicates how strongly the system supports a proposed context interpretation.

Sources may include:

```text
user input
API
MDT localization
CCC
historical evidence
LLM inference
```

Confidence should affect context influence and density policy.

---

# 79. Context Consistency

## Definition

**Context Consistency** measures whether multiple context dimensions are structurally compatible.

Example checks:

```text
Domain ↔ Space
Domain ↔ Time
Space ↔ Time
```

Conflicting context combinations should not be silently accepted.

---

# 80. Context Policy

## Definition

A **Context Policy** governs:

```text
when to inject
which context to inject
how deep
how dense
where to place
when to back off
when to preserve ambiguity
```

Conceptually:

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

---

# 81. Context Density Policy

## Definition

A **Context Density Policy** determines how much explicit structural evidence should be injected for a given:

```text
task
context
consumer
confidence
budget
risk profile
```

It is distinct from Context Selection Policy.

---

# 82. Context Selection Policy

## Definition

A **Context Selection Policy** determines which context dimensions or candidate identities are relevant.

Example:

```text
Domain + Space
```

may be selected while Time is omitted.

Selection answers:

> Which context?

Density answers:

> How much?

---

# 83. Context Budget

## Definition

A **Context Budget** limits context cost.

Possible forms include:

```text
maximum CBT count
maximum additional tokens
maximum latency
maximum context cost
```

A policy selects the highest-value context within this budget.

---

# 84. Context Efficiency

## Definition

**Context Efficiency** measures validated Context Gain relative to context cost.

Conceptually:

```text
Context Efficiency
=
Validated Context Gain
/
Context Cost
```

It helps distinguish maximum score from best engineering choice.

---

# 85. Context Compression

## Definition

**Context Compression** is the process of folding many contextual features into a compact structural identity.

Example:

```text
Domain
Space
Time
State
Policy
   ↓
UTN Type
   ↓
token@UTN-Type
```

This reduces surface context density while preserving useful structural identity.

---

# 86. Context Compression Ratio

## Definition

Conceptually:

```text
Context Compression Ratio
=
Raw Context Representation Cost
/
Compressed Structural Representation Cost
```

A useful compression must preserve downstream utility.

---

# 87. Context Address

## Definition

A **Context Address** is a stable structural identity used to localize computation, memory, or intelligence resources.

Conceptually:

```text
Context
   ↓
MDT
   ↓
UTN Type
   ↓
Context Address
```

A human-readable form may be:

```text
rollback@DatabaseTransaction
```

while a machine-stable form may use a UTN Type ID.

---

# 88. Structural Address

## Definition

A **Structural Address** is a machine-resolvable location in the structural intelligence space.

A Context Address is one form of Structural Address.

It may resolve to:

```text
Search Region
Cache
Delta Cases
CCC
Brain Unit
Policy
Validator
```

---

# 89. Context-as-Address

## Definition

**Context-as-Address** is the principle that explicit structural context can become more than descriptive evidence.

It can become a reusable address for:

```text
computation
retrieval
caching
experience
specialists
learning
```

Canonical thesis:

> **Context is not merely additional information for a query; it can become an address for computation, caching, intelligence reuse, and structural growth.**

---

# 90. Structural Search

## Definition

**Structural Search** is retrieval guided by explicit structural context and MDT relationships rather than flat lexical matching alone.

Typical progression:

```text
Exact Context
   ↓
Parent
   ↓
Sibling
   ↓
Broader Region
   ↓
Raw Query
```

---

# 91. Structural Search Plane

## Definition

The **Structural Search Plane** is the runtime layer that uses structural identity to locate:

```text
information
computation
historical experience
policies
specialists
```

It extends search from:

```text
search for data
```

toward:

```text
search for intelligence
```

---

# 92. Two-Phase Search

## Definition

**Two-Phase Search** separates:

```text
Phase 1
Structural Localization
```

from:

```text
Phase 2
Detailed Search / Reasoning
```

The goal is to narrow the relevant structural region before expensive processing.

---

# 93. Context Search Reduction Ratio

## Definition

A conceptual metric:

```text
Context Search Reduction Ratio
=
Candidate Count Before Context
/
Candidate Count After Context
```

It estimates how much structural context reduces the candidate search space.

---

# 94. Context Cache

## Definition

A **Context Cache** stores results under context-aware keys rather than raw queries alone.

Example:

```text
rollback@DatabaseTransaction → Result A

rollback@Deployment → Result B
```

This reduces semantic cache collisions.

---

# 95. Structural Query Cache

## Definition

A **Structural Query Cache** uses a canonical structural identity or Context Address as part of the cache key.

Conceptual pipeline:

```text
Query
   ↓
Context Localization
   ↓
UTN Address
   ↓
Context Cache Key
   ↓
Cached Result
```

---

# 96. Raw Cache

## Definition

A **Raw Cache** stores:

```text
Query
→ Result
```

without explicit structural context.

This is the L0 cache level in the repository's maturity model.

---

# 97. Structural Intelligence Cache

## Definition

A **Structural Intelligence Cache** stores not only results but validated structural experience.

Conceptually:

```text
UTN / CCC Type
   ↓
Query Pattern
   ↓
Validated Result
   ↓
Evidence
   ↓
Delta
   ↓
Policy
```

It is closer to structural memory than conventional caching.

---

# 98. Computational Folding

## Definition

**Computational Folding** is the conversion of expensive validated computation into reusable structural memory.

Canonical progression:

```text
Expensive Computation
        ↓
Validated Result
        ↓
Context Localization
        ↓
Folded Structural Memory
```

This allows later queries to reuse prior intelligence.

---

# 99. Folded Structural Memory

## Definition

**Folded Structural Memory** is validated experience stored under structural identity for future retrieval and reuse.

It may include:

```text
query patterns
results
positive deltas
negative deltas
CCC
policy
validation
provenance
```

---

# 100. Delta

## Definition

A **Delta** is a meaningful change between two structural states.

Conceptually:

```text
Before State
    ↓
Action
    ↓
After State
```

The difference is the Structural Delta.

---

# 101. Structural Delta

## Definition

A **Structural Delta** is a change in:

```text
CallingGraph
MDT
UTN
policy
code
state
behavior
cache
dispatch
```

that can be associated with a task, action, context, and validation outcome.

---

# 102. Delta Intelligence

## Definition

**Delta Intelligence** is validated experience about structural change.

Canonical form:

```text
Context
   ↓
Task
   ↓
Action
   ↓
Structural Delta
   ↓
Validation
```

It records not merely what was known, but what changed and whether the change worked.

---

# 103. Positive Delta Intelligence

## Definition

**Positive Delta Intelligence** is a validated structural change that produced a successful outcome.

It can be searched and reused in structurally similar situations.

---

# 104. Negative Delta Intelligence

## Definition

**Negative Delta Intelligence** is a failed or harmful structural change preserved as reusable counter-evidence.

Examples include:

```text
failed code repair
harmful retry policy
wrong context injection
bad UTN merge
invalid cache reuse
```

Negative experience is a first-class form of intelligence.

---

# 105. Context-Localized Delta Intelligence

## Definition

**Context-Localized Delta Intelligence** stores a structural delta under the context in which it occurred.

This prevents overgeneralizing actions across incompatible contexts.

Example:

```text
IncreaseRetryCount@DatabaseTransaction
```

should not automatically transfer to unrelated contexts.

---

# 106. TACG-SDIG

## Full Name

**Task-Action CallingGraph Structural Delta Intelligence and Growth**

## Definition

TACG-SDIG represents successful and failed Task-Action-Delta histories as reusable structural experience.

Within MDT-UTN-CBT, it can provide historical evidence for:

```text
UTN merge
context selection
context density
action choice
structural growth
```

---

# 107. CCC

## Definition

**CCC** is a compact reusable structural experience or control representation used throughout the broader Structural Intelligence framework.

Within MDT-UTN-CBT:

```text
UTN
→ identifies what something is structurally

CCC
→ identifies what known structural experience belongs there
```

A Context Address may resolve to one or more CCCs.

---

# 108. CCC Identity

## Definition

A **CCC Identity** is the structural identity of reusable CCC experience associated with a UTN type or structural context.

Conceptually:

```text
UTN Type
   ↓
CCC Identity
```

This can support reasoning, reuse, and Brain-Unit dispatch.

---

# 109. Brain Unit

## Definition

A **Brain Unit** is a specialized intelligence component associated with a structural domain, task family, or context region.

A Brain Unit may contain:

```text
specialized reasoning
specialized prompt
specialized model
specialized tools
CCC
cache
policy
validation
```

---

# 110. Brain-Unit Dispatch

## Definition

**Brain-Unit Dispatch** is the routing of a localized task to the most relevant specialized Brain Unit.

Canonical path:

```text
Context
   ↓
UTN Type
   ↓
CCC Identity
   ↓
Brain Unit
```

---

# 111. Brain-Unit Address

## Definition

A **Brain-Unit Address** is a structural routing identity that maps a context or UTN type to a specialized Brain Unit.

If no exact Brain Unit exists, hierarchical backoff may occur.

---

# 112. Structural Intelligence Dispatch Node

## Definition

A **Structural Intelligence Dispatch Node** is a mature MDT node capable of referencing:

```text
UTN Type
Aliases
Metric Policy
Search
Cache
Delta Intelligence
CCC
Brain Unit
Validation
Policy
Version
Provenance
```

It combines structural localization with runtime intelligence routing.

---

# 113. Intelligence Neighborhood

## Definition

An **Intelligence Neighborhood** is a structural MDT region that has accumulated reusable local intelligence such as:

```text
queries
cache entries
positive cases
negative cases
CCC
Brain Units
tests
policies
```

A mature structural neighborhood becomes more than a classification region.

It becomes a local intelligence resource.

---

# 114. Structural Intelligence Runtime

## Definition

A **Structural Intelligence Runtime** is a runtime architecture combining:

```text
MDT
UTN
CBT
Search
Cache
Delta Intelligence
CCC
Brain Units
Policy
Validation
```

to support localized reasoning, reuse, and continual growth.

---

# 115. Structural Memory

## Definition

**Structural Memory** is memory organized by structural identity rather than flat lexical or temporal indexing alone.

It supports:

```text
hierarchical retrieval
context-aware reuse
counter-evidence
versioning
local growth
```

---

# 116. Read/Write Symmetry

## Definition

**Read/Write Symmetry** is the principle that the same structural address should support both:

```text
READ
Context Address
→ Retrieve Intelligence
```

and:

```text
WRITE
Validated Intelligence
→ Context Address
```

This turns context into a memory location as well as a retrieval key.

---

# 117. Structural Growth

## Definition

**Structural Growth** is the incremental evolution of MDT, UTN, policy, CCC, cache, Delta Intelligence, or Brain Units through validated new evidence.

Canonical loop:

```text
Context
   ↓
Reason / Act
   ↓
Validation
   ↓
Structural Delta
   ↓
Fold
   ↓
Structural Growth
```

---

# 118. Local Structural Growth

## Definition

**Local Structural Growth** updates only the relevant structural neighborhood rather than requiring global model retraining or global structure reconstruction.

Benefits include:

```text
isolation
traceability
lower interference
incremental evolution
```

---

# 119. Structural Continual Learning

## Definition

**Structural Continual Learning** is continual intelligence growth achieved through explicit updates to structural memory and local intelligence organization.

Examples:

```text
new MDT branch
new UTN type
new Delta case
new CCC
new Brain Unit
updated Context Policy
```

It complements rather than necessarily replaces model-weight learning.

---

# 120. Model Intelligence

## Definition

**Model Intelligence** is intelligence primarily encoded in learned model parameters.

Examples include learned representations and behavior within an LLM.

---

# 121. Structural Intelligence

## Definition

**Structural Intelligence** is intelligence represented explicitly through structural organization, identity, memory, policy, routing, and reusable experience.

Within this repository it includes:

```text
MDT
UTN
CBT
Cache
Delta
CCC
Brain Units
Policy
Validation
```

Model Intelligence and Structural Intelligence are complementary.

---

# 122. Fold

## Definition

**Fold** means compressing, organizing, or converting repeated or detailed structural experience into a reusable structural representation.

Examples:

```text
raw contexts → MDT type
repeated computation → structural cache
successful cases → Delta Intelligence
context features → UTN identity
```

---

# 123. Unfold

## Definition

**Unfold** means expanding a folded structural representation when more detail is needed for:

```text
ambiguity resolution
reasoning
adaptation
validation
execution
```

The system should unfold selectively rather than globally.

---

# 124. Fold/Unfold

## Definition

**Fold/Unfold** is the recurring Structural Intelligence cycle:

```text
Experience
   ↓
Fold
   ↓
Structural Memory
   ↓
Unfold
   ↓
Reason / Act
   ↓
Validation
   ↓
Refold
```

MDT-UTN-CBT applies this cycle to context itself.

---

# 125. Context Folding

## Definition

**Context Folding** compresses a rich Context Starmap into a smaller structural identity or CBT representation.

Example:

```text
Domain
Space
Time
State
Policy
   ↓
UTN Type
   ↓
token@UTN-Type
```

---

# 126. Context Unfolding

## Definition

**Context Unfolding** exposes additional context dimensions when a compact representation is insufficient.

Example:

```text
rollback@DatabaseTransaction
        ↓
rollback@DatabaseTransaction
function@TransactionManager
version@Version42
policy@SafeRetry
```

---

# 127. Context Refolding

## Definition

**Context Refolding** converts validated richer context use into a simpler future context policy.

Example:

```text
D + S + T tested
        ↓
D + S sufficient
        ↓
future policy uses D + S
```

---

# 128. Structural Prior

## Definition

A **Structural Prior** is explicit structural information supplied before general inference to narrow or organize the reasoning space.

CBT can provide a Structural Prior.

Important rule:

> A Structural Prior should bias inference, not dictate it blindly.

---

# 129. Attention Evidence Injection

## Definition

**Attention Evidence Injection** is an informal description of adding explicit context-bound evidence to an input sequence consumed by a Transformer.

It does not imply direct control over internal attention weights.

The measurable object is the downstream behavioral effect.

---

# 130. Policy-Controlled Structural Evidence Injection

## Definition

**Policy-Controlled Structural Evidence Injection** is the controlled addition of CBTs according to:

```text
context confidence
task
consumer
density
cost
risk
counter-evidence
```

It is a more precise description than uncontrolled repetition of `token@context`.

---

# 131. Context Rigidity

## Definition

**Context Rigidity** is the tendency of a context-enhanced system to resist revising an interpretation after contradictory evidence appears.

Excessive context density may increase rigidity.

A robust system should preserve correction capability.

---

# 132. Anchoring

## Definition

**Anchoring** occurs when explicit context overly biases later reasoning toward an incorrect interpretation.

Wrong-context tests and baseline backoff are intended to detect and mitigate anchoring.

---

# 133. Context Dilution

## Definition

**Context Dilution** occurs when additional context reduces performance because relevant structural signals are weakened by:

```text
noise
redundancy
over-specialization
conflicting context
prompt complexity
```

More context is therefore not assumed to be better.

---

# 134. Context Saturation

## Definition

**Context Saturation** occurs when additional context produces negligible marginal gain.

Example:

```text
Sparse → large gain
Medium → useful gain
Dense → almost no additional gain
```

A policy should normally stop near saturation.

---

# 135. Context Reversal

## Definition

**Context Reversal** occurs when adding an additional context dimension or increasing density turns a previously positive Context Gain into a negative result.

Such cases should be preserved as Negative Delta Intelligence.

---

# 136. Marginal Context Gain

## Definition

**Marginal Context Gain** measures the incremental value of adding one context dimension or CBT to an existing context set.

Example:

```text
MarginalGain(S | D)
=
Score(D + S)
-
Score(D)
```

---

# 137. Context Interaction

## Definition

**Context Interaction** occurs when two or more context dimensions have a combined effect that differs from the sum of their individual effects.

Interactions may be:

```text
positive
redundant
negative
conflicting
```

---

# 138. Context Utility

## Definition

**Context Utility** is a policy-level measure combining multiple objectives.

Conceptually:

```text
Context Utility
=
f(
    Gain,
    Validation,
    Cost,
    Latency,
    Stability,
    Confidence,
    Risk
)
```

No universal formula is prescribed.

---

# 139. Density Efficiency

## Definition

**Density Efficiency** measures useful Context Gain relative to the cost of injected context.

Conceptually:

```text
Density Efficiency
=
Validated Context Gain
/
Context Density Cost
```

---

# 140. Gain per CBT

## Definition

A simple efficiency metric:

```text
Gain per CBT
=
Context Gain
/
Number of Injected CBTs
```

It helps identify diminishing returns.

---

# 141. Context Removal Rule

## Definition

A **Context Removal Rule** specifies how explicitly injected structural augmentation is removed to recover the baseline.

The rule should be deterministic and auditable.

---

# 142. Context Provenance

## Definition

**Context Provenance** records where a context interpretation came from.

Possible sources:

```text
USER
API
UPPER_LAYER
MDT_UTN
CCC
LLM_ESTIMATE
HISTORICAL_CASE
MANUAL_FIXTURE
```

Provenance affects confidence and reuse policy.

---

# 143. Structural Provenance

## Definition

**Structural Provenance** records how a structural identity, type, address, cache entry, delta, or policy was produced.

It may include:

```text
source
version
evidence
model
human decision
policy
validation
timestamp
```

---

# 144. Versioned Structural Address

## Definition

A **Versioned Structural Address** links a structural identity to a particular version or temporal interpretation.

Conceptually:

```text
UTN-8F32A@v3
```

or:

```text
UTN-8F32A@current
```

This supports historical reproducibility and cache validity.

---

# 145. Address Migration

## Definition

**Address Migration** is the explicit remapping of structural resources after UTN merge, split, rename, or reorganization.

Example merge:

```text
UTN-A ─┐
       ├→ UTN-C
UTN-B ─┘
```

Historical references remain preserved.

---

# 146. Structural Conflict

## Definition

A **Structural Conflict** occurs when candidate contexts, trees, policies, or identities cannot be safely unified.

Examples:

```text
semantic conflict
policy conflict
temporal conflict
parent conflict
metric conflict
```

Conflict should remain explicit.

---

# 147. Ambiguous Context

## Definition

An **Ambiguous Context** has multiple plausible structural interpretations without sufficient evidence for a unique choice.

The preferred response may be:

```text
Top-K Context
Backoff
Additional Search
Human Review
```

rather than forced classification.

---

# 148. Unknown Context

## Definition

**Unknown Context** means that the system lacks enough evidence to form a reliable structural interpretation.

Unknown is a valid runtime state.

The baseline path should remain available.

---

# 149. Structural Isolation

## Definition

**Structural Isolation** is the engineering advantage gained by restricting reasoning or updates to the relevant MDT neighborhood.

Benefits include:

```text
smaller search region
easier debugging
local policy
lower interference
traceability
```

---

# 150. Intelligence Localization

## Definition

**Intelligence Localization** is the process of using structural identity to find the most relevant:

```text
memory
policy
historical cases
CCC
Brain Unit
search region
```

before invoking broad computation.

---

# 151. Reuse Before Recompute

## Definition

**Reuse Before Recompute** is the runtime principle of checking validated folded intelligence before performing expensive computation again.

This does not permit blind reuse.

Reuse remains subject to:

```text
context compatibility
version
policy
confidence
counter-evidence
validation
```

---

# 152. Structural Backoff

## Definition

**Structural Backoff** broadens the structural scope when an exact context or resource is unavailable.

Example:

```text
Exact Type
   ↓
Parent Type
   ↓
Domain
   ↓
Raw Baseline
```

This can apply to Search, Cache, and Brain Units.

---

# 153. Structural Reuse

## Definition

**Structural Reuse** means retrieving and adapting validated intelligence associated with a structurally similar context.

Reuse may involve:

```text
direct reuse
adaptation
unfolding
revalidation
```

It is not equivalent to copying blindly.

---

# 154. Validation

## Definition

**Validation** determines whether a typing decision, context injection, cached result, structural delta, or action is acceptable.

Possible validators include:

```text
Unit Tests
Compiler
Schema Checks
Known Answer Sets
External Verifiers
Human Review
Structural Consistency Checks
```

Validation should be separated from model self-confidence.

---

# 155. Unit-Test QA

## Definition

**Unit-Test QA** uses deterministic executable tests to validate structural decisions or code changes when applicable.

In AI Coding, it can act as a high-value external validator.

---

# 156. Validation Success

## Definition

**Validation Success** means that the result satisfies predefined correctness or acceptance criteria.

Important distinction:

```text
Positive Context Gain
≠
Validation Success
```

An enhanced result may improve relative to baseline yet still remain incorrect.

---

# 157. Policy

## Definition

A **Policy** is an explicit rule set governing structural decisions.

Policies may control:

```text
metric weighting
merge threshold
context selection
context density
cache reuse
Brain-Unit dispatch
validation
human escalation
```

---

# 158. Policy-Governed Runtime

## Definition

A **Policy-Governed Runtime** applies explicit policies to structural localization, context injection, reuse, and action decisions.

Policy makes structural behavior configurable rather than hard-coded.

---

# 159. Structural Delta Policy

## Definition

A **Structural Delta Policy** governs when a validated change should be:

```text
accepted
rejected
stored
promoted
merged
decayed
revalidated
```

---

# 160. Human Escalation

## Definition

**Human Escalation** occurs when structural evidence remains insufficient or high-risk decisions require external judgment.

Common triggers include:

```text
new policy
novel context
low confidence
strong conflict
high-impact action
missing initial conditions
```

---

# 161. LLM-Assisted UTN

## Definition

**LLM-Assisted UTN** uses an LLM as one reasoning source for:

```text
semantic comparison
candidate naming
counter-evidence generation
merge explanation
context estimation
```

The LLM does not replace metric structure, validation, or policy.

---

# 162. Top-Down Context Injection

## Definition

**Top-Down Context Injection** occurs when context is explicitly supplied by:

```text
user
API
upper-layer application
runtime system
```

before downstream reasoning.

---

# 163. Bottom-Up Context Estimation

## Definition

**Bottom-Up Context Estimation** occurs when the system infers candidate contexts from raw input.

Possible sources include:

```text
LLM
retrieval
MDT search
historical cases
```

The result may remain Top-K.

---

# 164. Structural Prompt Encoding

## Definition

**Structural Prompt Encoding** uses compact explicit structural context in or alongside a natural-language prompt.

Example:

```text
rollback@DatabaseTransaction
```

instead of repeatedly expressing the same structural context through verbose prose.

It complements rather than replaces natural language.

---

# 165. Baseline Runtime

## Definition

A **Baseline Runtime** is the original system path without explicit MDT-UTN-CBT enhancement.

It is preserved for comparison and fallback.

---

# 166. Context-Addressed Runtime

## Definition

A **Context-Addressed Runtime** first localizes a query structurally, then uses the resulting Context Address to locate reusable intelligence.

Canonical flow:

```text
Query
   ↓
Context
   ↓
MDT / UTN
   ↓
Context Address
   ↓
Search / Cache / Delta / CCC / Brain Unit
```

---

# 167. LLM Fallback

## Definition

**LLM Fallback** is the use of general LLM reasoning when structural memory, cache, CCC, or Brain Units do not provide a sufficiently reliable result.

A mature Structural Intelligence runtime should preserve this path for novelty and uncertainty.

---

# 168. Structural Maturity

## Definition

**Structural Maturity** describes how much validated reusable intelligence has accumulated in a structural neighborhood.

A mature region may contain:

```text
stable UTN
validated cache
positive and negative deltas
CCC
Brain Unit
policy
tests
```

Higher maturity may reduce repeated general reasoning.

---

# 169. Collective Learning

## Definition

**Collective Learning** is the progressive sharing and composition of validated structural intelligence across local systems.

Possible progression:

```text
Local Experience
   ↓
Repository Structure
   ↓
Shared Type
   ↓
Shared Structural Address
   ↓
Cross-System Intelligence Reuse
```

Composable UTN provides one structural basis for this process.

---

# 170. Local-to-Universal Evolution

## Definition

**Local-to-Universal Evolution** is the process through which local structural identities become progressively composable into wider scopes.

Canonical hierarchy:

```text
Local
Subsystem
Repository
Organization
Domain
Universal
```

Universality emerges rather than being imposed from the beginning.

---

# 171. Context Scope

## Definition

**Context Scope** indicates the structural range within which a context identity is valid.

Possible scopes:

```text
Local
Subsystem
Repository
Organization
Domain
Universal
```

Scope should remain explicit during tree merge and reuse.

---

# 172. Structural Alias Resolution

## Definition

**Structural Alias Resolution** maps different human-readable names to the same Structural Type.

Example:

```text
transaction-retry
retryable-tx
事务重试
```

may all resolve to the same stable UTN identity.

---

# 173. Cross-Language Structural Identity

## Definition

**Cross-Language Structural Identity** allows surface forms in different languages to share the same structural type.

Example:

```text
folding@StructuralIntelligence

折叠@StructuralIntelligence
```

The lexical representation differs.

The context identity may remain the same.

---

# 174. Structural Coordinate

## Definition

A **Structural Coordinate** is a context tuple used to localize a target.

The simplest canonical example is:

```text
(Domain, Space, Time)
```

A Structural Coordinate may later include additional dimensions.

---

# 175. Structural Feature Conjunction

## Definition

A **Structural Feature Conjunction** is an explicit binding of multiple structural features into one representation.

CBT is a simple example:

```text
token
+
context
```

Composite CBTs may combine:

```text
token@Domain@Space@Time
```

---

# 176. Consumer

## Definition

A **Consumer** is a downstream system that uses structural context.

Examples:

```text
LLM
Search Engine
Cache
RAG Runtime
Agent
Brain Unit
Delta Intelligence Store
```

Different consumers may require different Context Projection Policies.

---

# 177. Context Consumer Policy

## Definition

A **Context Consumer Policy** determines the context representation used by a specific consumer.

Example:

```text
Search
→ Domain

Cache
→ Domain + Space + Time

LLM
→ Domain + Space

Brain Unit
→ UTN Type
```

---

# 178. Structural Resource

## Definition

A **Structural Resource** is any reusable resource indexed by structural identity.

Examples:

```text
SearchResult
CacheEntry
DeltaCase
CCC
BrainUnit
Policy
Validator
```

---

# 179. Structural Resource Lookup

## Definition

**Structural Resource Lookup** resolves a Context Address and resource type to relevant reusable assets.

Conceptually:

```text
lookup(ContextAddress, ResourceType)
```

This is an architectural abstraction, not a required v1.0.0 API.

---

# 180. Intelligence Address

## Definition

An **Intelligence Address** is a structural address used specifically to locate reusable intelligence.

It may point toward:

```text
historical reasoning
validated answers
Delta Intelligence
CCC
Brain Units
policies
```

---

# 181. Read-Compute-Validate-Fold

## Definition

**Read-Compute-Validate-Fold** is a canonical Structural Intelligence lifecycle.

```text
READ
Retrieve existing intelligence

COMPUTE
Generate missing intelligence

VALIDATE
Check correctness

FOLD
Store validated experience
```

---

# 182. Unfold-Act-Refold

## Definition

**Unfold-Act-Refold** describes runtime reuse of folded structural memory.

```text
Folded Memory
   ↓
Unfold
   ↓
Act
   ↓
Validate
   ↓
Refold
```

---

# 183. Algorithmic Foundation Release

## Definition

The v1.0.0 release is an **Algorithmic Foundation Release**.

Its goal is to define:

```text
algorithms
structural principles
invariants
validation protocols
runtime architecture
```

without requiring a full executable implementation.

---

# 184. Validation 001

## Full Name

**Baseline-Preserved Context Injection**

## Core Question

> Does explicit context help?

It establishes:

```text
Baseline
vs
Context-Enhanced Input
```

and measures Context Gain.

---

# 185. Validation 002

## Full Name

**Domain-Space-Time Context Matrix**

## Core Question

> Which context helps?

It evaluates all major D/S/T combinations and identifies Minimum Sufficient Context.

---

# 186. Validation 003

## Full Name

**Context Density Policy Protocol**

## Core Question

> How much context should be injected?

It evaluates sparse, selective, dense, and stress-test context regimes.

---

# 187. Validation Triangle

## Definition

The three validation protocols form the canonical MDT-UTN-CBT validation sequence:

```text
VALIDATION-001
Does Context Help?
        ↓
VALIDATION-002
Which Context Helps?
        ↓
VALIDATION-003
How Much Context?
```

Or:

```text
Whether?
   ↓
Which?
   ↓
How Much?
```

---

# 188. Canonical MDT-UTN-CBT Pipeline

```text
Target
   ↓
Context
   ↓
GenericContainerStarmap
   ↓
Metric Similarity / Distance
   ↓
Metric-Differential Tree
   ↓
Per-Node UTN Intelligence
   ↓
Structural Type
   ↓
Universal Type ID
   ↓
Canonical Name / Alias
   ↓
Context-Bound Token
   ↓
Baseline-Preserved Context Injection
   ↓
Context Policy
   ↓
Context Address
   ↓
Search / LLM / Cache / Delta / CCC / Brain Unit
   ↓
Validation
   ↓
Structural Delta
   ↓
Fold
   ↓
Structural Growth
```

---

# 189. Canonical Short Definitions

For quick reference:

```text
Context
→ Structural conditions that determine interpretation.

Starmap
→ Structured carrier of context.

Metric
→ Structural similarity/difference measure.

MDT
→ Hierarchical organization of metric differences.

UTN
→ Typing-first, Naming-second structural identity process.

Per-Node Intelligence
→ Local intelligence operating in an MDT neighborhood.

Leftover
→ Explicit unresolved structural case.

CBT
→ token@context structural encoding unit.

BPCI
→ Context injection with recoverable baseline.

Context Gain
→ Performance change caused by explicit context.

CID
→ Context Injection Density.

Context Projection
→ Consumer-specific context selection.

Context Address
→ Structural identity used as a computational address.

Computational Folding
→ Turn validated computation into reusable structural memory.

Delta Intelligence
→ Validated intelligence about structural change.

CCC
→ Reusable compact structural experience.

Brain Unit
→ Specialized intelligence addressed by structural context.

Structural Growth
→ Validated local evolution of intelligence structure.
```

---

# 190. Canonical Principles

## Context Principle

> **Context is primary; naming is secondary.**

## Typing Principle

> **Type before name.**

## Leaf Principle

> **Fold upward; do not erase downward.**

## Metric Principle

> **Similarity creates candidates, not truth.**

## Counter-Evidence Principle

> **Search both for and against a structural decision.**

## Leftover Principle

> **Unknown structure should remain explicit.**

## Composition Principle

> **Fold locally; merge folded structures globally.**

## CBT Principle

> **Keep the token; bind the context.**

## Baseline Principle

> **Every context-enhanced input should preserve a recoverable baseline.**

## Density Principle

> **Start sparse and add only useful structural evidence.**

## Runtime Principle

> **Localize first; reuse what is known; recompute only when necessary.**

## Evolution Principle

> **Every validated structural delta is a candidate for future intelligence.**

---

# 191. Final Glossary Map

```text
                            CONTEXT
                               │
                               ▼
                  GenericContainerStarmap
                               │
                               ▼
                   Metric Similarity / Distance
                               │
                               ▼
                 METRIC-DIFFERENTIAL TREE
                               │
                               ▼
                      PER-NODE UTN
                               │
                   ┌───────────┼───────────┐
                   ▼           ▼           ▼
                 TYPE        NAME       LEFTOVER
                   │
                   ▼
                    STRUCTURAL IDENTITY
                               │
                               ▼
                     CONTEXT-BOUND TOKEN
                         token@context
                               │
                               ▼
              BASELINE-PRESERVED INJECTION
                               │
                               ▼
                        CONTEXT POLICY
                               │
                               ▼
                        CONTEXT ADDRESS
                               │
        ┌──────────────┬───────┼───────┬──────────────┐
        ▼              ▼       ▼       ▼              ▼
      SEARCH          LLM    CACHE   DELTA         BRAIN UNIT
                               │
                               ▼
                           VALIDATION
                               │
                               ▼
                       STRUCTURAL DELTA
                               │
                               ▼
                              FOLD
                               │
                               ▼
                      STRUCTURAL GROWTH
```

---

## Canonical Repository Statement

> **Context identifies what a target means structurally.
> MDT organizes its neighborhood.
> UTN gives it structural identity.
> CBT exposes that identity.
> BPCI measures its influence.
> Context Policy controls its use.
> Context Address localizes reusable intelligence.
> Validation determines what may be folded.
> Structural Delta drives future growth.**

---

**MDT-UTN-CBT — Metric-Differential-Tree UTN and Context-Bound Token Intelligence**
