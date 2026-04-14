# Contributing

Thanks for your interest in improving the AI disclosure framework.

This repository functions as a **reference specification expressed through examples**, not a traditional schema-only project. Contributions should improve the **clarity, consistency, and usability** of these examples as a standard for others to follow.

---

## Repository Role

This project is:

- A **reference standard for AI disclosure**
- An **example-driven specification** (`disclosure-examples/`)
- A **documentation source** (`README.md`)
- A **guide for agents** (`AGENTS.md`)

It is **not**:
- An application codebase
- A schema-enforced system (no single canonical file)
- A fast-moving experimental project

---

## Key Structure

### `disclosure-examples/`

This directory contains all disclosure examples and templates.

- `disclosure.yaml` → **baseline reference example**
- Other YAML files → **scenario-specific templates**, such as:
  - creative works
  - legal documentation
  - other specialized use cases

These files collectively define the **practical standard**.

---

### `README.md`

Explains:
- The purpose of AI disclosure
- How to interpret and use the examples
- Key concepts and patterns

---

### `AGENTS.md`

Defines:
- How agents should interpret and reuse these examples
- How to adapt them into other repositories

---

## Contribution Philosophy

Because this is an example-driven spec:

- Consistency across examples is critical
- Patterns matter more than any single file
- Changes should improve **general usability**, not just one scenario

---

## What You Can Contribute

### Improve Philsophy and Guidance

- Suggest improvements around philosophy of disclosure
- Suggest improvemnts on how these disclosures should be consumed or interprted.
- Suggest improvements on how disclosures are cataloged and standardized.

### Improve Core Example

- Refine `disclosure-examples/disclosure.yaml`
- Improve clarity, naming, or structure
- Ensure it serves as a strong “default” model

### Improve Scenario Templates

- Enhance placeholder YAML files (e.g., creative, legal)
- Add realistic, useful variations
- Ensure they remain aligned with the core structure

### Add New Examples

- Introduce new scenario templates when broadly useful
- Keep them generalizable (avoid niche edge cases)

### Improve Documentation

- Clarify README explanations
- Add examples showing how to adapt templates

### Improve Agent Guidance

- Refine `AGENTS.md` for clearer interpretation and reuse

---

## What to Avoid

Avoid contributions that:

- Diverge structure significantly between example files
- Introduce incompatible field naming across templates
- Overfit templates to niche or domain-specific cases
- Treat one example as fundamentally different from the rest without explanation

---

## Making Changes to Examples

When modifying any YAML in `disclosure-examples/`:

### 1. Maintain Structural Consistency

- Core concepts (AI usage, tools, contributions, oversight) should remain recognizable across all files
- Field names should remain consistent unless intentionally evolving the standard

---

### 2. Propagate Important Changes

If you change structure in `disclosure.yaml`, you should:

- Review other example files
- Update them if the change is broadly applicable
- Or explicitly justify why they differ

---

### 3. Document the Change

If the change affects how users interpret the format:

- Update `README.md`
- Ensure examples reflect the updated pattern

---

### 4. Evolve Carefully

There is no strict schema enforcement, so:

- Changes must be deliberate
- Avoid silent breaking changes
- Prefer additive evolution over removal

---

## Pull Request Guidelines

- Keep PRs focused and minimal
- Clearly explain:
  - What changed
  - Why it improves the standard

For structural changes:
- Show before/after YAML snippets
- Indicate whether changes should propagate to other examples

---

## Review Criteria

Contributions are evaluated based on:

- Clarity
- Consistency across examples
- General applicability
- Alignment with repository purpose
- Impact on downstream users (humans and agents)

---

## Role of Agents

AI agents may read this repository, but:

- They are **consumers of examples**
- They should not contribute directly without human intent
- Their behavior is guided by `AGENTS.md`

---

## When to Open an Issue First

Open an issue before submitting a PR if:

- You are proposing a structural change across examples
- You are introducing a new template type
- You are unsure whether a variation fits the standard

---

## Design Philosophy

This project prioritizes:

- Examples over rigid schemas
- Consistency over completeness
- Clarity over flexibility
- Practical usability over theoretical coverage

A strong contribution makes the examples:

- Easier to understand
- Easier to reuse
- More consistent across contexts

---

## Summary

- This is an **example-driven specification**
- `disclosure-examples/` defines the standard in practice
- Keep examples **aligned, consistent, and general-purpose**
- Optimize for both **human understanding and agent reuse**