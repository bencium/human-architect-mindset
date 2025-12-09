# Human Architect Mindset Skill

A Claude Code skill that teaches systematic architectural thinking - the irreplaceable human capabilities that AI cannot replace.

## The Problem This Solves

AI can generate code. But someone must still:
- **Decide what to build** (product vision, strategy)
- **Understand whether it solves the problem** (domain expertise)
- **Navigate corporate reality** (politics, approvals, constraints)
- **Prevent system collapse** (systems thinking)

This skill teaches the architectural mindset needed to guide AI effectively.

## The Four Pillars

### 1. Domain Modeling
Understanding the actual problem space - not the technical solution, but the domain itself. Healthcare, finance, logistics - each has hidden complexity AI doesn't see.

### 2. Systems Thinking
How components interact, what breaks at scale, where failure modes hide. Example: Your payment pipeline broke because a backend provider released a breaking SDK change with no notification.

### 3. Constraint Navigation
The real world has:
- Legacy systems you can't change
- Political boundaries between teams
- Budget limits and compliance requirements
- The "correct" solution that's completely unshippable

### 4. AI-Aware Problem Decomposition
A new architectural skill: knowing how to decompose problems into chunks AI can reliably solve, then composing solutions back together. This isn't "prompting" - it's architecture at a different abstraction level.

## Skill Behavior

- **Proactive** - Activates automatically when detecting architectural decisions
- **Teaching mode** - Guides you through architect thinking step-by-step
- **Always asks** about constraints before proposing solutions
- **Tool-agnostic** - AI decomposition patterns work with any AI assistant

## Files

| File | Purpose |
|------|---------|
| SKILL.md | Core teaching framework - the main skill |
| CHECKLIST.md | Practical audit checklists for each pillar |
| EXAMPLES.md | Real-world scenarios with walkthroughs |
| REFERENCE.md | Deep technical reference material |
| README.md | This file - overview and session outputs |

## Session Outputs (2024-12-09)

### Design Decisions Made

1. **Activation Mode**: Proactive
   - Auto-activate when detecting architectural decisions
   - Keywords: "architecture", "design", "system", "integrate", "scale"
   - Signals: Team boundaries, breaking changes, compliance mentions

2. **Persona**: Teaching Mode
   - Guide through architect thinking step-by-step
   - Explain WHY each question matters
   - "An architect would now ask..." framing
   - Not silent application - visible reasoning

3. **Constraint Handling**: Always Ask
   - Proactively ask about political boundaries
   - Ask about legacy systems before proposing
   - Ask about budget and compliance
   - Surface constraints BEFORE solutions

4. **AI Decomposition**: Tool-Agnostic
   - General principles for any AI assistant
   - Not Claude-specific patterns
   - Focus on: clear contracts, verification points, failure isolation

### Questions to Always Ask (Captured)

**Domain:**
1. What problem are we actually solving?
2. Who are the real users?
3. What domain-specific constraints exist?

**Systems:**
4. What external dependencies exist?
5. How does this fail?
6. Who gets paged?

**Constraints:**
7. What legacy systems must we integrate with?
8. Who needs to approve this?
9. What's the budget constraint?
10. What compliance requirements apply?
11. What can't we change, even if it's wrong?

**AI Decomposition:**
12. What are the discrete, bounded tasks?
13. How do we verify each chunk?
14. Where do humans make judgment calls?

### Good vs Bad AI Task Boundaries

**Bad:**
- "Make it better" (no clear output)
- "Fix the bugs" (unbounded scope)
- "Refactor the system" (too large)

**Good:**
- "Convert this function from callbacks to async/await"
- "Add error handling for network failures to these 3 API calls"
- "Write unit tests for this pure function given these examples"

### Key Patterns Identified

**AI Task Boundary Criteria:**
- Clear input/output contracts
- Bounded context (all info provided)
- Verifiable results
- Failure isolation
- Independence for parallelization
- Human checkpoints between chunks

**The Composition Problem:**
After AI solves chunks, humans must:
- Verify each chunk works
- Integrate chunks together
- Handle gaps between chunks
- Ensure overall coherence

## Origin

Created from a conversation about what makes architectural thinking irreplaceable by AI:

> "A new skill is emerging: knowing how to decompose problems into chunks that AI can reliably solve, and then composing those solutions back together. This isn't 'prompting' - it's architecture at a different abstraction level."

The skill captures:
- Domain modeling requirements
- Systems thinking (failure modes, cascading effects)
- Constraint navigation (the messy reality of humans)
- AI-aware decomposition (the new architectural layer)

## Usage

This skill activates proactively. When Claude detects architectural discussions, it will announce:

> "I'm using the Human Architect Mindset skill to guide you through systematic architectural thinking."

Then it guides through:
1. **Phase 1**: Domain Discovery
2. **Phase 2**: Systems Analysis
3. **Phase 3**: Constraint Mapping
4. **Phase 4**: AI Decomposition Planning
5. **Phase 5**: Solution Synthesis

## Related Skills

- `superpowers:brainstorming` - Before implementation
- `superpowers:writing-plans` - Detailed plans
- `relationship-design` - AI-first interfaces
- `scientific-critical-thinking` - Evaluating claims
