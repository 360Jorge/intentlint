# IntentLint

IntentLint is a specification oversight tool for AI-assisted software development.

Current AI coding systems often assume that natural-language specifications are complete, precise, and aligned with user intent. In practice, many software failures originate earlier: from ambiguous requirements, hidden assumptions, contradictory constraints, or underspecified behavior.

IntentLint analyzes natural-language software specifications *before* code generation and attempts to identify:

- Ambiguities
- Missing constraints
- Hidden assumptions
- Contradictory requirements
- Edge cases
- Clarifying questions

The goal is not formal verification itself, but improving specification quality and intent traceability before implementation begins.

---

## Motivation

As AI systems become increasingly capable of generating code, the bottleneck shifts toward specification oversight:

- Did the user fully specify intent?
- Are important edge cases missing?
- Are requirements internally consistent?
- Could multiple incompatible implementations satisfy the same specification?

IntentLint explores whether language models can help detect underspecified or potentially unsafe requirements before implementation.

---

## Example

### Input Specification

> "Build a secure login system for a web application."

### Example Output

```json
{
  "ambiguities": [
    "The term 'secure' is undefined."
  ],
  "missing_constraints": [
    "Password reset behavior unspecified",
    "Session expiration unspecified",
    "Multi-factor authentication unspecified"
  ],
  "clarifying_questions": [
    "Should MFA be required?",
    "How long should sessions remain active?"
  ],
  "edge_cases": [
    "Repeated failed login attempts",
    "Concurrent sessions across devices"
  ]
}
```

---

## Current MVP

The current prototype focuses on:

1. Ambiguity detection
2. Missing constraint identification
3. Clarifying question generation
4. Edge-case extraction
5. Structured JSON outputs

---

## Project Structure

```text
specs/      # Example specifications
prompts/    # Prompt templates
outputs/    # Model outputs
src/        # Core analysis pipeline
```

---

## Research Questions

Some questions we are exploring:

- Can LLMs reliably identify underspecified requirements?
- Can specification ambiguity be measured systematically?
- Which prompting strategies improve specification oversight?
- Can structured outputs improve intent traceability?

---

## Status

Hackathon prototype for the Apart Research / Theorem Secure Program Synthesis Hackathon.