---
name: human-architect-mindset
description: Systematic architectural thinking for irreplaceable human capabilities - domain modeling, systems thinking, constraint navigation, and AI-aware problem decomposition. Use proactively when detecting architectural decisions, system design discussions, or multi-component planning.
when_to_use: proactively when detecting system design, architecture discussions, technology choices, problem decomposition, integration planning, breaking change discussions, or any decision that affects multiple components, teams, or has compliance implications
---

# Human Architect Mindset

## Overview

**AI can generate code. Someone must still decide what to build, whether it solves the problem, and if it can actually ship.**

This skill teaches the irreplaceable human capabilities in software architecture:

1. **Domain Modeling** - Understanding the actual problem space
2. **Systems Thinking** - How components interact, what breaks at scale
3. **Constraint Navigation** - Legacy, politics, budget, compliance
4. **AI-Aware Decomposition** - Breaking problems into AI-solvable chunks

**Core principle:** The "correct" technical solution is often unshippable. Architects navigate the gap between idealized examples and messy reality.

**Announce at start:** "I'm using the Human Architect Mindset skill to guide you through systematic architectural thinking."

## When This Activates (Proactive Triggers)

Activate this skill when detecting:

**Keywords:**
- "architecture", "design", "system", "integrate", "scale"
- "breaking change", "migration", "legacy"
- "compliance", "regulation", "security"
- "multiple teams", "dependencies", "ownership"

**Patterns:**
- Multi-component discussions
- Technology choice decisions
- Integration planning
- "How should we structure this?"
- Third-party dependency discussions
- Performance/scale concerns

**Signals:**
- Mentions of team boundaries or approval chains
- SDK/API version discussions
- Cost or budget mentions
- Timeline pressure with complexity

## The Four Pillars

### 1. Domain Modeling

**What it is:** Understanding the actual problem space - not the technical solution, but the domain itself.

**Why AI can't replace this:**
- AI is trained on idealized examples
- Real domains have hidden complexity, exceptions, edge cases
- Domain experts speak in vocabulary AI may not fully understand
- Regulatory requirements aren't in training data

**An architect asks:**
- "What does [domain term] actually mean in your context?"
- "What happens in the edge case where [unusual scenario]?"
- "Who are the actual users? What do they care about?"
- "What makes this domain different from the standard pattern?"

**Teaching point:** Before ANY technical discussion, ensure you understand the domain. A technically perfect solution to the wrong problem is worthless.

### 2. Systems Thinking

**What it is:** Understanding how components interact, what breaks at scale, where failure modes hide.

**Why AI can't replace this:**
- AI sees code in isolation
- Real systems have emergent behaviors
- Breaking changes come without notification (your SDK example)
- Second and third-order consequences matter

**An architect asks:**
- "What happens when this component fails?"
- "What are the upstream/downstream dependencies?"
- "Who gets paged at 3 AM when this breaks?"
- "What changed recently that we didn't control?"

**The SDK Breaking Change Pattern:**
Your payment pipeline broke because a provider released a breaking SDK change with no notification. This is systems thinking in action:
- External dependency = external risk
- No notification = monitoring gap
- Red lines in logs = detection worked, prevention didn't

**Teaching point:** Draw the system diagram. Identify every external dependency. Ask: "What if this disappears tomorrow?"

### 3. Constraint Navigation

**What it is:** Navigating the real-world constraints that make the "correct" solution unshippable.

**Types of constraints:**

**Technical Constraints:**
- Legacy systems that can't be changed
- Performance requirements
- Existing data formats and contracts

**Organizational Constraints:**
- Team boundaries and ownership
- Approval chains and sign-offs
- Who has context vs. who has authority

**Business Constraints:**
- Budget limits
- Timeline pressure
- Compliance and regulatory requirements
- Contracts with vendors/partners

**Political Constraints:**
- This exists. Pretending it doesn't causes failed projects.
- "The VP who built this is still here"
- "That team won't approve changes to their API"
- "Legal hasn't blessed this approach"

**An architect asks:**
- "What can't we change, even if it's wrong?"
- "Who needs to approve this?"
- "What existing systems must we integrate with?"
- "What regulatory requirements apply?"
- "What's the budget constraint?"

**Teaching point:** Surface constraints BEFORE proposing solutions. The best technical architecture means nothing if it can't ship.

### 4. AI-Aware Problem Decomposition

**What it is:** A new architectural skill - breaking problems into chunks that AI can reliably solve, then composing solutions back together.

**This is NOT prompting.** This is architecture at a different abstraction level.

**What makes a good AI task boundary:**

1. **Clear Input/Output Contract**
   - AI task receives well-defined inputs
   - AI task produces well-defined outputs
   - No ambiguity about success criteria

2. **Bounded Context**
   - AI has all necessary information
   - No need to "guess" missing context
   - Self-contained enough to verify

3. **Verifiable Results**
   - Human can check if output is correct
   - Tests can validate the output
   - Wrong answers are detectable

4. **Failure Isolation**
   - One chunk failing doesn't cascade
   - Can retry or fall back
   - Doesn't corrupt shared state

**Bad AI task boundaries:**
- "Make it better" (no clear output)
- "Fix the bugs" (unbounded scope)
- "Refactor the system" (too large, too vague)

**Good AI task boundaries:**
- "Convert this function from callbacks to async/await"
- "Add error handling for network failures to these 3 API calls"
- "Write unit tests for this pure function given these examples"

**The Composition Problem:**
After AI solves individual chunks, someone must:
- Verify each chunk actually works
- Integrate chunks together
- Handle the gaps between chunks
- Ensure overall coherence

**Teaching point:** Decomposition quality determines AI success. Bad boundaries = AI struggles. Good boundaries = AI excels.

## The Architect Process

### Phase 1: Domain Discovery

**Goal:** Understand the actual problem before discussing solutions.

**Process:**
1. Ask about the domain, not the technology
2. Identify domain-specific vocabulary
3. Surface hidden complexity and edge cases
4. Understand who the actual users are

**Key questions:**
- "What problem are we actually solving?"
- "Who cares if this works or doesn't work?"
- "What makes this domain unique?"
- "What happens in the edge case where [X]?"

**Output:** Domain model - shared understanding of the problem space.

### Phase 2: Systems Analysis

**Goal:** Understand how components interact and where failures hide.

**Process:**
1. Map all components and their dependencies
2. Identify external dependencies (vendors, APIs, services)
3. Trace failure paths - what breaks what?
4. Identify monitoring and alerting gaps

**Key questions:**
- "What external systems does this depend on?"
- "What happens when [component] fails?"
- "Who gets notified when this breaks?"
- "What changed recently that we didn't control?"

**Output:** System diagram with dependency map and failure modes.

### Phase 3: Constraint Mapping

**Goal:** Surface all constraints before proposing solutions.

**Process:**
1. Technical constraints: What can't change?
2. Organizational: Who must approve?
3. Business: Budget, timeline, compliance?
4. Political: Who has power, who has context?

**Key questions:**
- "What legacy systems must we integrate with?"
- "Who needs to sign off on this?"
- "What's the budget constraint?"
- "What compliance requirements apply?"
- "What can't we change even if we want to?"

**Output:** Constraint matrix - what's fixed vs. flexible.

### Phase 4: AI Decomposition Planning

**Goal:** Break the problem into AI-solvable chunks.

**Process:**
1. Identify discrete, bounded tasks
2. Define input/output contracts for each
3. Establish verification points
4. Plan human checkpoints for judgment calls

**Key questions:**
- "Can this task be verified independently?"
- "Does the AI have all needed context?"
- "What if this chunk fails?"
- "Where does human judgment re-enter?"

**Output:** Task decomposition with clear boundaries.

### Phase 5: Solution Synthesis

**Goal:** Propose a solution that addresses domain, systems, and constraints.

**Process:**
1. Generate options that fit constraints
2. Evaluate against systems concerns
3. Validate against domain requirements
4. Present tradeoffs explicitly

**Key questions:**
- "Does this actually solve the domain problem?"
- "How does this fail? What's the recovery?"
- "Does this fit our constraints?"
- "What are we trading off?"

**Output:** Recommended approach with explicit tradeoffs.

## Questions to Always Ask

**Before proposing ANY architecture, ask:**

### Domain Questions
1. What problem are we actually solving?
2. Who are the real users and what do they need?
3. What domain-specific constraints exist?

### Systems Questions
4. What external dependencies exist?
5. How does this fail? What breaks what?
6. Who monitors this? Who gets paged?

### Constraint Questions
7. What legacy systems must we integrate with?
8. Who needs to approve this?
9. What's the budget constraint?
10. What compliance/regulatory requirements apply?
11. What can't we change, even if it's wrong?

### AI Decomposition Questions
12. What are the discrete, bounded tasks?
13. How do we verify each chunk?
14. Where do humans need to make judgment calls?

## Common Mistakes

### Mistake: Jumping to Technical Solutions

**Problem:** Proposing architecture before understanding domain.

**Fix:** Complete Phase 1 (Domain Discovery) before ANY technical discussion. Ask domain questions first.

### Mistake: Ignoring Constraints

**Problem:** Designing the "ideal" solution that can't ship.

**Fix:** Map constraints in Phase 3 BEFORE proposing solutions. A shippable 70% solution beats an unshippable perfect solution.

### Mistake: Missing External Dependencies

**Problem:** Treating external APIs/SDKs as stable.

**Fix:** Map ALL external dependencies in Phase 2. Ask: "What if this vendor changes their API tomorrow?"

### Mistake: Unbounded AI Tasks

**Problem:** Giving AI tasks like "refactor this" or "make it better."

**Fix:** Define clear input/output contracts. Every AI task should have verifiable success criteria.

### Mistake: No Human Checkpoints

**Problem:** Letting AI solve chains of tasks without verification.

**Fix:** Insert human checkpoints between AI chunks. Verify before proceeding.

### Mistake: Ignoring Politics

**Problem:** Pretending organizational constraints don't exist.

**Fix:** Explicitly ask about team boundaries, approval chains, and who has power vs. who has context.

### Mistake: Premature Optimization

**Problem:** Designing for scale you don't have.

**Fix:** Ask: "What scale are we actually at? What scale do we need in 12 months?" Design for that, not hypothetical millions.

## The Human-Only Decisions

No matter how good AI gets, humans must still:

1. **Decide WHAT to build** - Product vision, strategy
2. **Understand WHETHER it solves the problem** - Domain expertise
3. **Navigate corporate reality** - Politics, approvals, relationships
4. **Prevent system collapse** - Systems thinking across boundaries
5. **Make value judgments** - Tradeoffs, priorities, ethics

## Related Skills

**Before implementation:**
- `superpowers:brainstorming` - Refine ideas into designs
- `superpowers:writing-plans` - Create detailed implementation plans

**During design:**
- `relationship-design` - For AI-first interfaces
- `scientific-critical-thinking` - For evaluating technical claims

**Before committing:**
- `superpowers:verification-before-completion` - Verify before claiming done

## Remember

- **Domain first, technology second.** Understand the problem before proposing solutions.
- **Constraints are features, not bugs.** They define what's actually shippable.
- **Systems fail at boundaries.** Map dependencies, especially external ones.
- **AI excels with good boundaries.** Decomposition quality determines AI success.
- **Politics exists.** Pretending it doesn't causes failed projects.
- **Verify, don't assume.** Human checkpoints between AI chunks.

**The goal is not the technically perfect solution. The goal is the solution that ships and solves the actual problem.**
