# MDT-UTN-CBT-002 — Metric-Differential Tree and Per-Node UTN Intelligence

## From Metric Localization to Local Typing-and-Naming Decisions

**Repository:** Metric-Differential-Tree UTN and Context-Bound Token Intelligence (MDT-UTN-CBT)  
**Document:** MDT-UTN-CBT-002  
**Status:** Algorithmic Foundation  
**Version:** v1.0.0

---

## Abstract

MDT-UTN begins from a simple structural observation:

> Universal Typing and Naming does not need to be solved as one global all-in-one intelligence problem.

If target contexts can be represented in a metric-compatible form, then each new or existing context can be localized into a nearby region of a **Metric-Differential Tree (MDT)**.

The typing-and-naming problem can then be reduced from a global search over all known structures to a small set of local decisions around:

- the candidate leaf;
- sibling leaves;
- the direct parent;
- nearby parent nodes;
- explicit leftover branches.

This document defines the core algorithmic role of **Per-Node UTN Intelligence**.

Per-Node UTN Intelligence determines whether contextual structures should:

- remain separate;
- share a structural parent;
- be split into accepted core and leftover;
- create a new parent type;
- reuse an existing type;
- receive a canonical name;
- preserve local aliases;
- defer judgment;
- escalate to LLM or human review.

The framework is governed by several principles:

- original leaf context is preserved by default;
- metric similarity proposes candidates but does not prove equivalence;
- typing precedes naming;
- counter-evidence is searched explicitly;
- leftovers remain visible;
- context richness is preserved while metric granularity is policy-controlled;
- every important merge is auditable and testable;
- successful structural decisions can later become reusable Delta Intelligence.

The central algorithmic thesis is:

> **MDT localizes the search space; Per-Node Intelligence performs the structural decision.**

---

# 1. From Global UTN to Local Structural Decisions

A naive Universal Typing and Naming system appears to require something like:

```text
New Context
    ↓
Compare against everything
    ↓
Infer all possible meanings
    ↓
Choose global type
    ↓
Assign name
````

This approach is expensive and difficult to explain.

It also mixes several different problems:

* similarity search;
* type formation;
* ambiguity handling;
* counter-evidence;
* naming;
* versioning;
* human review;
* validation.

MDT-UTN separates these concerns.

The alternative is:

```text
New Context
    ↓
Metric Representation
    ↓
MDT Localization
    ↓
Small Candidate Neighborhood
    ↓
Per-Node UTN Intelligence
    ↓
Local Structural Decision
```

The key transformation is:

> **Global universality is approached through local structural localization and composable decisions.**

---

# 2. The Role of the Metric-Differential Tree

A Metric-Differential Tree organizes contextual structures according to measured structural similarity and difference.

Conceptually:

```text
                           Root
                            │
               ┌────────────┴────────────┐
               │                         │
          Structural A              Structural B
             │                         │
        ┌────┴────┐               ┌────┴────┐
        │         │               │         │
       A1        A2              B1        B2
      /  \      /  \            /  \
    L1   L2   L3   L4         L5   L6
```

The purpose is not merely classification.

Each node represents accumulated structural information.

Each branch represents some meaningful differential.

Each parent represents commonality.

Each leaf preserves a specific contextual individual or unresolved residual structure.

The MDT therefore provides:

```text
Structural Neighborhood
Structural Distance
Candidate Parents
Candidate Siblings
Alternative Branches
Leftover Regions
```

These become the local evidence space for UTN.

---

# 3. Why the Direct Parent Matters

The leaf and its direct parent are especially important.

A leaf carries a concrete structural individual.

Its direct parent is the smallest existing structural abstraction that may already explain it.

Therefore much of UTN can be localized to:

```text
Leaf
  +
Direct Parent
  +
Sibling Leaves
  +
Nearby Candidate Parents
```

This is a major isolation advantage.

Instead of asking:

> Which universal type in the entire system should this structure belong to?

the runtime asks:

> Does this leaf fit its local parent?
> Does it belong with its siblings?
> Should the parent be split?
> Should a new parent be created?
> Should the leaf remain leftover?

This is a much smaller reasoning problem.

---

# 4. Per-Node UTN Intelligence

A relevant MDT node can host **Per-Node UTN Intelligence**.

Conceptually:

```text
MDT Node
│
├── structural context
├── metric neighborhood
├── local children
├── candidate siblings
├── parent relationship
├── metric policy
├── merge history
├── counter-evidence
├── leftover policy
├── naming policy
├── QA status
└── version / provenance
```

Per-Node UTN Intelligence is not necessarily one algorithm.

It is a local decision framework.

Its responsibilities may include:

```text
Should this node merge?
Should this node remain separate?
Should a new parent type be created?
Should an existing parent be reused?
Should one or more leaves be excluded?
Should the decision be deferred?
Should naming occur now?
Should LLM reasoning be requested?
Should human review be required?
```

This is the core of MDT-UTN.

---

# 5. Leaf Preservation as the Default Rule

The first operational rule is:

> **Do not destroy or casually rename original leaves.**

A leaf may contain:

```text
Leaf
├── original context
├── original name
├── original source
├── repository
├── version
├── provenance
├── evidence
└── local metadata
```

The default behavior should be:

```text
Leaf remains intact
```

while new abstractions are created above it.

For example:

```text
retryOnTimeout
retryOnDeadlock
```

may remain unchanged while a new parent is created:

```text
          RetryableTransactionalAction
               /                \
      retryOnTimeout        retryOnDeadlock
```

The original names are preserved.

This enables:

* full traceability;
* rollback;
* alternative future typing;
* version comparison;
* local naming compatibility;
* counter-evidence analysis.

This principle can be summarized as:

> **Fold upward; do not erase downward.**

---

# 6. UTN Should Operate on Mergeable Groups

UTN should not rename every leaf merely because naming logic exists.

The more important operation is to identify structural commonality among two or more leaves.

The candidate operation is therefore:

```text
{Leaf A, Leaf B, ...}
        ↓
Candidate Commonality
        ↓
Possible Parent Type
```

This is different from:

```text
Leaf A
  ↓
Rename
```

The core UTN question is:

> **Do multiple contextual individuals justify a shared structural abstraction?**

Only after that question is answered should canonical naming become relevant.

---

# 7. Metric Similarity as the Candidate Generator

Metric similarity is the primary localization mechanism.

Suppose each context is represented through `GenericContainerStarmap`.

Then a structural distance function can conceptually be written as:

```text
D(A, B)
```

or as a composite function:

```text
D(A, B)
=
PolicyWeighted(
    structural dimensions
)
```

The exact formula may vary.

What matters is that the system can identify:

```text
near
far
similar
different
candidate sibling
candidate parent
```

This produces a candidate neighborhood.

For example:

```text
New Leaf
   ↓
Metric Search
   ↓
Nearest MDT Region
   ↓
Candidate Siblings
```

But similarity is only the beginning.

---

# 8. Similarity Does Not Authorize Merge

A central MDT-UTN principle is:

> **Similarity creates a candidate, not a final type.**

Two structures may be highly similar while differing on one critical dimension.

For example:

```text
Function A
├── same input
├── same output
├── same call pattern
└── read-only

Function B
├── same input
├── same output
├── same call pattern
└── destructive write
```

A purely similarity-based algorithm might merge them.

A structural intelligence system should not.

Therefore:

```text
Metric Similarity
       ↓
Candidate
```

must be followed by further analysis.

---

# 9. Positive Evidence Search

The first local reasoning direction asks:

> Why should these nodes belong together?

Possible evidence includes:

```text
Shared task role
Shared CallingGraph position
Shared parameter structure
Shared return behavior
Shared exception pattern
Shared data dependencies
Shared runtime outcome
Shared domain context
Shared temporal context
Shared historical evolution
```

Positive evidence can be represented conceptually as:

```text
EvidenceForMerge
```

and may itself be structured.

The runtime should be able to explain:

```text
These nodes were considered similar because:
1. ...
2. ...
3. ...
```

This evidence should be retained in the eventual merge record.

---

# 10. Two-Way Counter-Evidence Search

Positive similarity is not enough.

MDT-UTN should explicitly search for evidence against the merge.

The second reasoning direction asks:

> Why should these nodes NOT belong together?

Possible counter-evidence includes:

```text
Different side effects
Different safety requirements
Different transaction semantics
Different lifecycle
Different ownership
Different calling constraints
Different temporal validity
Different version contracts
Different policy requirements
Different failure semantics
```

This creates a two-way structure:

```text
Candidate Merge
      │
      ├── Evidence For
      │
      └── Evidence Against
```

The final decision depends on both.

This is stronger than ordinary nearest-neighbor classification.

---

# 11. Explicit Leftover Separation

Counter-evidence may reveal that only part of a candidate group should merge.

For example:

```text
Candidate Set
├── A
├── B
├── C
└── D
```

After analysis:

```text
Accepted Core
├── A
├── B
└── C

Leftover
└── D
```

The result becomes:

```text
             New Parent Type
              /    |    \
             A     B     C

Leftover:
D
```

This is not a failed merge.

It is a more precise structural result.

The leftover may represent:

* noise;
* insufficient evidence;
* true structural novelty;
* hidden substructure;
* a future branch;
* a different policy regime.

Therefore:

> **Leftover is first-class structural information.**

---

# 12. Leftover Preservation Prevents Forced Classification

A dangerous failure mode in typing systems is forced classification.

Conceptually:

```text
Unknown Context
      ↓
Nearest Known Type
      ↓
Forced Assignment
```

MDT-UTN should instead allow:

```text
Unknown Context
      ↓
Candidate Search
      ↓
Insufficient Evidence
      ↓
Explicit Leftover
```

Possible states include:

```text
Known
Likely
Ambiguous
Conflicting
Novel
Deferred
Leftover
```

This gives the runtime room to learn later.

A universal system should be able to say:

> **I do not yet have sufficient structural evidence to merge this context.**

---

# 13. Typing Before Naming

Once the structural merge has survived positive and negative analysis, the runtime can create a type.

For example:

```text
A
B
C
 ↓
Validated Commonality
 ↓
UTN-TYPE-8F32A
```

Only after the type is structurally justified should the runtime ask:

> What should this type be called?

This ordering is essential:

```text
Structural Evidence
       ↓
Validated Type
       ↓
Canonical Name
```

not:

```text
Convenient Name
       ↓
Assumed Type
```

Therefore:

> **Typing is structural. Naming is symbolic.**

---

# 14. Parent Type Formation

A new parent type may be created when:

```text
Multiple Leaves
      +
Sufficient Commonality
      +
Acceptable Counter-Evidence
      +
Policy Approval
      +
Validation
```

justify a higher abstraction.

Conceptually:

```text
CreateParentType(
    acceptedChildren,
    structuralCommonality,
    metricPolicy,
    evidence,
    provenance
)
```

The new parent should preserve:

```text
Parent
├── child references
├── structural summary
├── metric profile
├── evidence
├── counter-evidence
├── leftover references
├── type ID
├── naming state
├── version
└── provenance
```

The parent itself becomes a future searchable structural object.

---

# 15. Reuse Existing Parent or Create New Parent

Not every candidate needs a new type.

The runtime must decide between:

```text
Reuse Existing Parent
```

and:

```text
Create New Parent
```

A candidate may already fit:

```text
Existing Type
```

sufficiently well.

The decision may consider:

```text
distance to existing parent
distance to siblings
policy threshold
counter-evidence
type granularity
historical stability
```

This prevents uncontrolled type proliferation.

---

# 16. Metric Granularity Is Policy-Governed

Different applications require different levels of structural distinction.

A coarse policy may merge:

```text
openFile
openSocket
openStream
```

under:

```text
OpenResource
```

A finer policy may separate them into:

```text
FileIO
NetworkIO
StreamIO
```

Therefore:

```text
Same Context Set
      +
Different Metric Policy
      ↓
Different Valid Structural Trees
```

This is not necessarily inconsistency.

It may reflect different perspectives or operational needs.

The governing rule is:

> **Preserve rich context; let policy determine effective structural granularity.**

---

# 17. Rich Context Is Better Than Premature Context Reduction

The stored context should usually contain more dimensions than one current merge decision requires.

Possible dimensions include:

```text
Domain
Space
Time
CallingGraph
Task
Action
Behavior
Runtime
Version
Repository
Ownership
Policy
Tests
History
```

The runtime should not prematurely destroy them.

Instead:

```text
Rich Context
     ↓
Metric Policy
     ↓
Selected Effective Dimensions
     ↓
Decision
```

This preserves future reinterpretation.

A context ignored today may become decisive tomorrow.

---

# 18. LLM as a Local Reasoning Assistant

LLM reasoning can assist Per-Node Intelligence.

Possible roles include:

```text
Summarize commonality
Identify semantic differences
Propose candidate parent type
Suggest canonical name
Generate counter-evidence
Explain ambiguous cases
Compare historical examples
```

But LLM output should generally be treated as:

```text
Suggestion
Evidence
Candidate
```

rather than:

```text
Authority
```

A useful conceptual pattern is:

```text
Metric Candidate
      ↓
LLM Structural Review
      ↓
Policy
      ↓
Validation
```

The MDT remains the structural substrate.

---

# 19. Historical Merge Cases as Delta Intelligence

Successful historical UTN operations can themselves become reusable structural experience.

A successful merge contains:

```text
Context Situation
      ↓
Candidate Set
      ↓
Reasoning
      ↓
Merge Action
      ↓
Validation
      ↓
Structural Delta
```

This naturally maps to:

```text
Task
  ↓
Action
  ↓
Structural Delta
```

Therefore previous UTN decisions can become a form of localized Delta Intelligence.

Future Per-Node Intelligence may ask:

```text
Have we seen a structurally similar merge before?
```

and retrieve:

```text
Historical Successful Cases
```

This provides a second reasoning source beyond raw metric similarity.

---

# 20. Human Review Remains Necessary

Some cases should remain explicitly reviewable by humans.

Examples include:

```text
Insufficient initial context
Novel domain terminology
New naming policy
Conflicting aliases
Regulatory constraints
Safety-critical semantics
Repository migration
Cross-organization type merge
```

Human review is not a failure of automation.

It is part of a hybrid structural intelligence system.

A local escalation model may be:

```text
Automatic
   ↓
LLM-Assisted
   ↓
Policy Review
   ↓
Human Review
```

depending on confidence and risk.

---

# 21. Unit-Test and QA Validation

A merge should not be considered complete merely because the structure appears plausible.

Important merges should support QA.

Possible checks include:

```text
Type invariants
Child compatibility
Counter-example tests
Regression tests
CallingGraph consistency
Name uniqueness
Alias consistency
Version compatibility
Policy compliance
```

Conceptually:

```text
Candidate Parent
      ↓
QA
      │
      ├── Pass → Commit
      │
      └── Fail → Reconsider / Leftover / Split
```

This is especially important in AI coding contexts.

---

# 22. Canonical Per-Node UTN Algorithm

The MDT-UTN Per-Node algorithm can now be summarized.

```text
INPUT:
    Candidate contextual nodes C
    Local MDT neighborhood N
    Metric policy P
    Existing UTN structures U
    Historical cases H

STEP 1 — Preserve Original Context
    Preserve leaf names
    Preserve leaf contexts
    Preserve provenance

STEP 2 — Metric Localization
    Locate nearest structural neighborhood
    Select candidate siblings / parents

STEP 3 — Candidate Formation
    Form possible merge group

STEP 4 — Positive Evidence Search
    Search for structural commonality

STEP 5 — Counter-Evidence Search
    Search for reasons against the merge

STEP 6 — Leftover Separation
    Remove incompatible or uncertain nodes

STEP 7 — Policy Evaluation
    Apply granularity, domain, safety,
    naming, version, and merge policies

STEP 8 — Type Decision
    Reuse existing parent
    OR create new parent
    OR keep separate
    OR defer

STEP 9 — Naming
    Assign canonical name if appropriate
    Preserve aliases and original names

STEP 10 — QA
    Execute structural checks and tests

STEP 11 — Commit
    Write merge record
    Preserve version and provenance

STEP 12 — Learn
    Archive successful or failed case
    for future Delta Intelligence
```

This is the core algorithmic skeleton of MDT-UTN v1.0.0.

---

# 23. Decision Outcomes

Per-Node UTN Intelligence should support several explicit outcomes.

```text
OUTCOME A
Keep Leaf Unchanged

OUTCOME B
Attach Leaf to Existing Parent

OUTCOME C
Create New Parent Type

OUTCOME D
Merge Multiple Leaves

OUTCOME E
Split Candidate Set

OUTCOME F
Create Explicit Leftover

OUTCOME G
Create Alias Only

OUTCOME H
Defer Decision

OUTCOME I
Escalate to LLM / Human

OUTCOME J
Reject Proposed Merge
```

This avoids reducing UTN to a binary merge/no-merge system.

---

# 24. A Minimal Decision Tree

A simplified local decision flow is:

```text
Candidate Context
      ↓
Metric Neighbor Found?
   ┌──┴──┐
   │     │
  No    Yes
   │     │
Leftover │
         ↓
Sufficient Similarity?
   ┌─────┴─────┐
   │           │
  No          Yes
   │           │
Keep Separate  ↓
        Counter-Evidence?
           ┌────┴────┐
           │         │
          High      Low
           │         │
     Split/Leftover  ↓
                 Existing Parent Fits?
                    ┌────┴────┐
                    │         │
                   Yes       No
                    │         │
                 Reuse      Create Parent
                    │         │
                    └────┬────┘
                         ↓
                       Naming
                         ↓
                         QA
                         ↓
                       Commit
```

This is intentionally local and inspectable.

---

# 25. Per-Node Intelligence as Isolation

One of the strongest engineering properties of MDT-UTN is isolation.

Instead of creating one global intelligence engine that must understand every type and every naming rule, intelligence is attached to structural localities.

Conceptually:

```text
MDT
├── Node A
│   └── Per-Node Intelligence A
├── Node B
│   └── Per-Node Intelligence B
└── Node C
    └── Per-Node Intelligence C
```

Different nodes may use different:

```text
Metric Policies
Naming Policies
Validation Rules
Historical Cases
LLM Prompts
Human Review Requirements
```

This enables specialization without losing a common framework.

---

# 26. Per-Node Intelligence Can Evolve

A Per-Node Intelligence module should not be static.

It may accumulate:

```text
Successful merges
Failed merges
Counter-examples
Aliases
Policy changes
QA history
Delta Intelligence
Version transitions
```

Therefore:

```text
Per-Node Intelligence(t)
        ↓
New Cases
        ↓
Per-Node Intelligence(t+1)
```

This allows local structural intelligence to mature over time.

A mature branch may become increasingly cheap to classify.

A novel branch may remain exploratory.

---

# 27. Why This Can Reduce Computation

Suppose a system contains:

```text
N = very large number of contexts
```

A flat global comparison may require large search effort.

MDT instead enables:

```text
New Context
    ↓
Locate Coarse Region
    ↓
Search Local Neighborhood
    ↓
Perform Expensive Reasoning Only Locally
```

The exact complexity depends on implementation.

But the structural principle is clear:

> **Folded localization reduces the candidate space before expensive intelligence is invoked.**

This matters especially when the expensive component is:

```text
LLM reasoning
Human review
Deep semantic comparison
Cross-repository analysis
```

---

# 28. MDT as a Structural Search Plane

MDT can be interpreted as part of a broader Structural Search Plane.

Conceptually:

```text
Raw Context
     ↓
GenericContainerStarmap
     ↓
Metric Representation
     ↓
MDT Localization
     ↓
Per-Node Intelligence
     ↓
Type / Name / Leftover
```

This means UTN is not merely taxonomy maintenance.

It is a runtime structural localization process.

This distinction is important for dynamic AI systems.

---

# 29. Relationship to Context-Bound Tokens

Once Per-Node Intelligence validates a structural type, the result can become available to downstream token-based systems.

For example:

```text
rollback
```

may become:

```text
rollback@DatabaseTransaction
```

The CBT does not invent the context.

It exposes the context identity already established or suggested by UTN.

Therefore:

```text
MDT
  ↓
UTN Type
  ↓
Context-Bound Token
```

creates a bridge from structural folding to token-based computation.

This relationship is developed further in later documents.

---

# 30. Algorithmic Invariants

The following invariants should guide future implementation.

## Invariant 1 — Original Leaf Preservation

A parent merge does not silently destroy original contextual identities.

## Invariant 2 — Explicit Evidence

Important merges retain supporting evidence.

## Invariant 3 — Explicit Counter-Evidence

Important merges retain reasons that were considered against the merge.

## Invariant 4 — Explicit Leftover

Rejected or unresolved nodes remain structurally visible.

## Invariant 5 — Typing Before Naming

Names do not substitute for structural validation.

## Invariant 6 — Policy Visibility

Metric and merge policies should be inspectable.

## Invariant 7 — Version Traceability

Structural evolution should be reconstructable.

## Invariant 8 — QA Before Stable Commit

Important parent types should support validation.

## Invariant 9 — Local Decision Scope

Per-Node Intelligence should reason primarily over a bounded structural neighborhood.

## Invariant 10 — Reusability

Successful decisions should be eligible for future structural reuse.

---

# 31. Failure Modes

Several failure modes should be explicitly avoided.

## Failure Mode A — Similarity Equals Identity

High metric similarity is treated as proof of equivalence.

## Failure Mode B — Forced Merge

Every candidate must be assigned somewhere.

## Failure Mode C — Leaf Destruction

Original names or contexts are overwritten.

## Failure Mode D — Name-Driven Typing

Lexical convenience drives structural identity.

## Failure Mode E — Global Reasoning Everywhere

Every new context triggers full-system analysis.

## Failure Mode F — Hidden Policy

Merge granularity changes without traceability.

## Failure Mode G — No Counter-Evidence

The system searches only for reasons to merge.

## Failure Mode H — No QA

Structurally important merges are committed without validation.

## Failure Mode I — No Version History

Later users cannot reconstruct why a type exists.

## Failure Mode J — All-in-One Intelligence

Metric, LLM, human, policy, naming, and validation are collapsed into one opaque step.

---

# 32. Canonical Architecture

The core architecture can be summarized as:

```text
                    Contexts
                       │
                       ▼
            GenericContainerStarmap
                       │
                       ▼
              Metric Representation
                       │
                       ▼
          Metric-Differential Tree
                       │
                       ▼
            Candidate Neighborhood
                       │
                       ▼
          Per-Node UTN Intelligence
                       │
        ┌──────────────┼──────────────┐
        ▼              ▼              ▼
 Positive Search   Counter Search   Policy
        │              │              │
        └──────────┬───┴──────┬───────┘
                   ▼          ▼
             Accepted Core   Leftover
                   │
                   ▼
              Type Decision
                   │
        ┌──────────┴──────────┐
        ▼                     ▼
 Existing Parent          New Parent
        │                     │
        └──────────┬──────────┘
                   ▼
                 Naming
                   │
                   ▼
                  QA
                   │
                   ▼
                Commit
                   │
                   ▼
            Version / Provenance
                   │
                   ▼
            Delta Intelligence
```

---

# 33. Research Questions

This algorithmic structure raises several important research questions.

### RQ-1

How large should the local MDT neighborhood be for Per-Node Intelligence?

### RQ-2

How should metric distance interact with semantic or behavioral evidence?

### RQ-3

How should counter-evidence be weighted relative to positive similarity?

### RQ-4

When should one leftover trigger creation of a new branch?

### RQ-5

How should parent types summarize descendants without losing important distinctions?

### RQ-6

How should different domain policies alter merge granularity?

### RQ-7

How should historical successful merges become reusable Delta Intelligence?

### RQ-8

When should LLM reasoning be invoked, and when should metric rules be sufficient?

### RQ-9

How should human decisions be recorded so that future automation can learn from them?

### RQ-10

How should QA be designed for structural types that do not yet have executable tests?

---

# 34. Relationship to the Repository

This document defines the core local runtime logic of MDT-UTN.

The sequence is:

```text
MDT-UTN-CBT-001
Context Primacy and UTN Foundation
        ↓
MDT-UTN-CBT-002
MDT + Per-Node UTN Intelligence
        ↓
MDT-UTN-CBT-003
Composable Tree Merge and Evolutionary Identity
        ↓
MDT-UTN-CBT-004
Context-Bound Tokens
        ↓
MDT-UTN-CBT-005
Baseline-Preserved Context Injection
        ↓
MDT-UTN-CBT-006
Context-Addressed Intelligence Runtime
```

Document 001 establishes why context precedes naming.

Document 002 defines how local structural typing-and-naming decisions are made.

Document 003 will then explain how many local MDT structures can be progressively merged into larger evolutionary UTN structures.

---

# 35. Conclusion

The central problem of Universal Typing and Naming becomes manageable once it is structurally localized.

A Metric-Differential Tree provides the localization substrate.

Per-Node Intelligence provides the local decision mechanism.

The core sequence is:

```text
Context
  ↓
Metric Localization
  ↓
Candidate Neighborhood
  ↓
Positive Evidence
  ↓
Counter-Evidence
  ↓
Leftover Separation
  ↓
Type Decision
  ↓
Naming
  ↓
QA
  ↓
Commit
```

The system does not need to force every context into an existing class.

It does not need to erase original names.

It does not need to ask an LLM to solve a universal naming problem from scratch.

Instead:

> **MDT narrows the structural search space.**

and:

> **Per-Node Intelligence resolves the remaining local typing-and-naming decision.**

This produces a UTN system that is:

```text
context-preserving
metric-localized
counter-evidence-aware
leftover-preserving
policy-governed
auditable
testable
evolutionary
composable
```

The key algorithmic idea can therefore be summarized as:

> **Localize first.
> Compare locally.
> Search both for and against the merge.
> Preserve leftovers.
> Type before naming.
> Validate before commit.
> Learn from every structural delta.**

---

## Canonical Summary

```text
Context
  ↓
GenericContainerStarmap
  ↓
Metric-Differential Tree
  ↓
Candidate Local Neighborhood
  ↓
Per-Node UTN Intelligence
  ↓
┌───────────────┬───────────────┐
│               │               │
Positive      Counter        Policy
Evidence      Evidence
│               │               │
└───────────────┴───────┬───────┘
                        ↓
                 Core + Leftover
                        ↓
                  Type Decision
                        ↓
                      Naming
                        ↓
                       QA
                        ↓
                     Commit
                        ↓
               Version / Learning
```

> **MDT localizes the problem.
> Per-Node Intelligence makes the decision.
> Structural history preserves the explanation.**

