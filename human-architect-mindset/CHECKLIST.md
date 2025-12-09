# Human Architect Mindset - Checklists

Practical audit checklists for each phase of architectural thinking.

## Phase 1: Domain Discovery Checklist

Use before ANY technical discussion.

### Problem Understanding
- [ ] Can I explain the problem in domain terms, not technical terms?
- [ ] Do I know who the actual users are?
- [ ] Do I understand what "success" looks like to users?
- [ ] Have I identified domain-specific vocabulary?

### Domain Complexity
- [ ] What are the edge cases in this domain?
- [ ] What happens when the "happy path" doesn't apply?
- [ ] What domain rules seem simple but have hidden complexity?
- [ ] What domain knowledge am I missing?

### Stakeholder Understanding
- [ ] Who cares if this works?
- [ ] Who cares if this fails?
- [ ] Who has domain expertise I should consult?
- [ ] What competing interests exist between stakeholders?

### Domain Constraints
- [ ] What regulatory requirements apply?
- [ ] What industry standards must be followed?
- [ ] What domain-specific compliance exists?
- [ ] What domain assumptions should I challenge?

**Exit criteria:** I can explain the problem to a domain expert and they would nod, not correct me.

---

## Phase 2: Systems Thinking Checklist

Use when mapping dependencies and failure modes.

### Dependency Mapping
- [ ] What internal systems does this depend on?
- [ ] What external systems does this depend on?
- [ ] What depends on THIS system?
- [ ] Have I drawn the dependency diagram?

### External Dependency Audit
For each external dependency:
- [ ] What version are we using?
- [ ] When was it last updated?
- [ ] What's their breaking change policy?
- [ ] Do we have monitoring for their failures?
- [ ] What's our fallback if they disappear?

### Failure Mode Analysis
- [ ] What happens when [component A] fails?
- [ ] What happens when [external API] is slow?
- [ ] What happens when [database] is unavailable?
- [ ] What cascading failures are possible?
- [ ] What silent failures are possible?

### Monitoring & Alerting
- [ ] How do we know if this is working?
- [ ] How do we know if this is broken?
- [ ] Who gets alerted when it fails?
- [ ] What's the time-to-detection?
- [ ] What's the time-to-recovery?

### Scale Considerations
- [ ] What's the current scale?
- [ ] What scale do we need in 12 months?
- [ ] What breaks at 10x scale?
- [ ] What breaks at 100x scale?

**Exit criteria:** I can trace any failure to its impact and know who gets paged.

---

## Phase 3: Constraint Mapping Checklist

Use before proposing solutions.

### Technical Constraints
- [ ] What existing systems can't be changed?
- [ ] What data formats are locked in?
- [ ] What APIs must we maintain?
- [ ] What performance requirements exist?
- [ ] What security requirements exist?

### Organizational Constraints
- [ ] Which teams own which components?
- [ ] What approval chains exist?
- [ ] Who has authority to approve this?
- [ ] Who has context but not authority?
- [ ] Who has authority but not context?

### Business Constraints
- [ ] What's the budget?
- [ ] What's the timeline?
- [ ] What compliance requirements apply?
- [ ] What contracts constrain us?
- [ ] What vendor relationships affect this?

### Political Constraints
(These exist. Ignoring them causes failed projects.)
- [ ] Whose system would this change affect?
- [ ] Who built the current system? Are they still here?
- [ ] Which teams have historically resisted changes?
- [ ] What past decisions are politically sensitive?
- [ ] Who needs to be consulted even if not required?

### The Shippability Test
- [ ] Can this actually ship given our constraints?
- [ ] What would prevent this from shipping?
- [ ] Who could block this and why?
- [ ] What's the minimum viable version that ships?

**Exit criteria:** I know what's fixed vs. flexible and what could block shipping.

---

## Phase 4: AI Decomposition Checklist

Use when breaking work into AI-solvable chunks.

### Task Boundary Quality
For each AI task:
- [ ] Is the input clearly defined?
- [ ] Is the expected output clearly defined?
- [ ] Can success be objectively verified?
- [ ] Does the task have bounded scope?

### Context Completeness
For each AI task:
- [ ] Does the AI have all needed information?
- [ ] Are there hidden assumptions the AI would need to know?
- [ ] Is the context self-contained?
- [ ] Can the task be understood without external knowledge?

### Failure Handling
For each AI task:
- [ ] What happens if this task fails?
- [ ] Can we retry safely?
- [ ] Does failure cascade to other tasks?
- [ ] Is there a fallback strategy?

### Independence Assessment
- [ ] Can tasks run in parallel?
- [ ] What sequential dependencies exist?
- [ ] What shared state would cause conflicts?
- [ ] What's the critical path?

### Verification Points
- [ ] Where do humans verify AI output?
- [ ] What verification criteria exist?
- [ ] How long does verification take?
- [ ] What happens if verification fails?

### Composition Planning
- [ ] How do AI outputs integrate?
- [ ] What gaps exist between tasks?
- [ ] Who handles the integration?
- [ ] How do we ensure overall coherence?

**Exit criteria:** Each task has clear boundaries, and I know how to verify and compose results.

---

## Phase 5: Solution Validation Checklist

Use before finalizing recommendations.

### Domain Fit
- [ ] Does this actually solve the domain problem?
- [ ] Would a domain expert agree this solves their problem?
- [ ] Have I validated with stakeholders?
- [ ] Does the solution match user needs?

### Systems Fit
- [ ] Does this work with existing dependencies?
- [ ] Have I addressed failure modes?
- [ ] Is monitoring and alerting planned?
- [ ] Does this fit within scale requirements?

### Constraint Fit
- [ ] Does this fit technical constraints?
- [ ] Does this fit organizational constraints?
- [ ] Does this fit budget and timeline?
- [ ] Can this actually ship?

### Tradeoff Transparency
- [ ] Have I made tradeoffs explicit?
- [ ] Do stakeholders understand what we're giving up?
- [ ] Are there options with different tradeoff profiles?
- [ ] Is the recommended tradeoff justified?

### Implementation Readiness
- [ ] Is the approach detailed enough to implement?
- [ ] Are AI task boundaries defined?
- [ ] Are verification points established?
- [ ] Is the critical path identified?

**Exit criteria:** Solution addresses domain needs, fits constraints, and can ship.

---

## Quick Pre-Meeting Checklist

Before architectural discussions:

### Before I propose anything:
- [ ] Have I asked about the domain?
- [ ] Have I mapped dependencies?
- [ ] Have I asked about constraints?
- [ ] Do I know what can't change?

### Before I agree to anything:
- [ ] Can this actually ship?
- [ ] Who needs to approve?
- [ ] What's the timeline?
- [ ] What could block this?

### Before I decompose for AI:
- [ ] Are tasks bounded?
- [ ] Can outputs be verified?
- [ ] Where do humans checkpoint?
- [ ] How do pieces integrate?

---

## Red Flags Checklist

Warning signs that architectural thinking is missing:

### Domain Red Flags
- [ ] Solution discussed before problem understood
- [ ] Technical terms used, domain terms missing
- [ ] "Users" mentioned generically without specifics
- [ ] Edge cases dismissed as "rare"

### Systems Red Flags
- [ ] No dependency diagram exists
- [ ] External APIs treated as always available
- [ ] "We'll add monitoring later"
- [ ] Single points of failure not identified

### Constraint Red Flags
- [ ] "In an ideal world..." framing
- [ ] Legacy systems dismissed as "bad"
- [ ] Political constraints ignored
- [ ] Budget/timeline not discussed

### AI Decomposition Red Flags
- [ ] "AI can just figure it out"
- [ ] Tasks like "make it better"
- [ ] No verification points planned
- [ ] Integration assumed to be easy

**If any red flags are checked:** Stop and address before proceeding.

---

## Post-Mortem Checklist

After failures or surprises:

### What broke?
- [ ] What was the direct cause?
- [ ] What was the root cause?
- [ ] Was this a known failure mode?
- [ ] Was monitoring in place?

### Why didn't we see it coming?
- [ ] Did we miss a dependency?
- [ ] Did we miss a constraint?
- [ ] Did we ignore a warning sign?
- [ ] Did external factors change?

### Domain Learning
- [ ] What domain knowledge were we missing?
- [ ] Who should we have consulted?
- [ ] What assumption was wrong?

### Systems Learning
- [ ] What dependency failed?
- [ ] What cascade occurred?
- [ ] What monitoring was missing?

### Process Improvement
- [ ] What checklist item would have caught this?
- [ ] What question should we have asked?
- [ ] What constraint did we miss?
- [ ] How do we prevent this class of failure?
