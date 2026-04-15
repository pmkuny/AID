# For Developers

The AI Disclosure (AID) standard provides a structured way to report AI usage in software projects.


---

##  Nomenclature

- **Disclosure Versioning**: We're starting this at v1.0. As AI gets more pervasive, we'll probably need to update these definitions. Using a version number ensures that if you say your project is "ZAID v1.0," people know exactly what rules you were following at the time.

- **Predictable Tools vs. Creative Models**:
  - **Deterministic (Not AI)**: These are the "traditional" tools that follow strict rules. If you give a compiler, formatter, or standard linter the same input, you get the same output. Even IntelliSense fits here. These don't trigger our AI threshold.
  - **Non-Deterministic (AI)**: These are the models that make "decisions" or creative leaps—like Copilot or an LLM. Because they're probabilistic and don't just follow a static script, they count as AI usage.

- **AI System or Tooling**: Includes direct engagement of an AI Tool, Assistant, LLM, or third-party source that provides the former. Includes iteration, "spot checking", "tweaking" or formatting-only type tools. 

- **Content**: The actual content of a repository, interpreted widely. This could be images, source code, documentation, tests, or other core content that provides both primary and auxiliary functionality to the program or media in question. This takes a "no threshold" approach, where any engagement with AI in content creation counts as a usage of AI in general. Levels of content generation are then clarified in the type of disclosure used. **Note that this relates to content creation only, not any external process such as brainstorming or ideation.**

- **Documentation**: Auxiliary material (READMEs, wikis, inline comments, API docs) that explains or supports the Content.

- **Verification**: Human review of AI-generated output for correctness, safety, or style. This is a critical component of FAID and MAID-C levels.

- **Provenance**: The lineage of content creation, from initial prompt to final output. This includes identifying which AI systems were used and at what stage of the lifecycle.

- **Derivative Work**: Content modified by AI from a human-created source, or vice-versa. This includes AI-based refactoring or human "polishing" of AI drafts.


---

## Direct vs. Inherited Disclosure

Modern software is like an onion—it has layers. Sometimes you might not use AI at all, but one of your dependencies did. We should probably distinguish between those:

- **Direct Disclosure (D)**: This is about what *you* did in this specific repository.
- **Inherited Disclosure (I)**: This is about the AI used by the libraries, vendors, or services your project relies on.

**How to write it**: 
- `ZAID(D) / SAID(I)`: This means your code is 100% human-written, but you're using an AI-assisted library. 
- `MAID(D)`: If you don't specify an `(I)`, we'll just assume you're talking about the direct content of the repo.


---

## Levels of Involvement

- **FAID (Full AI Disclosure)** - This content was written entirely by AI tooling or systems, and contains only human-in-the-loop interactions, or verification for functionality and security. All content should be considered AI-generated.

- **MAID (Moderate AI Disclosure)** - This content was written by a human, with moderate usage of AI tooling or systems to generate the content contained within.
  - **MAID-A (Augmented)** - Human-led; AI provides boilerplate, refactoring, or minor logic blocks. The core architecture and complex logic remain human-originated.
  - **MAID-C (Collaborative)** - Significant shared effort; AI generates core logic or major components, which are then integrated, reviewed, and refined by a human. Authorship is effectively split.

- **SAID (Small AI Disclosure)** - This content was written by a human, with small adjustments by AI tooling or systems to ensure accuracy, best practices, or bug-fixing (e.g., using AI for linting, formatting, or "spot checking" logic). 

- **ZAID (Zero AI Disclosure)** - This content was created by a human, with zero AI involvement. No AI tools were used in the IDE, CLI, or any part of the creative pipeline.


---

##  Deep Dive - Scenarios


---

## 
# Scenario 1: The AI-Assisted Developer (MAID-A)
A developer uses GitHub Copilot while writing a new feature. They design the architecture, define the interfaces, and write the core business logic. They use Copilot to generate boilerplate getters/setters, simple utility functions, and unit test skeletons.
**Disclosure: MAID-A**


---

## 
# Scenario 2: The Documentation Generator (DAID)
A project's source code is 100% human-written. However, the developer uses an LLM to scan the code and generate a comprehensive `README.md`, `API.md`, and inline JSDoc comments.
**Disclosure: DAID (at the project level)**


---

## 
# Scenario 3: The AI-Bootstrapped Infrastructure (IAID)
A developer manually writes a Python application but uses an AI tool to generate the complex `Terraform` modules and `GitHub Actions` YAML files needed for deployment.
**Disclosure: IAID**


---

## 
# Scenario 4: The Zero-AI Purist (ZAID)
An open-source contributor disables all AI-based completion tools (like Copilot or Cursor's AI features) and writes all code, documentation, and tests manually, using only traditional IDE features (like IntelliSense) and static analysis tools.
**Disclosure: ZAID**


---

## Lowering the Burden

Tracking AI usage across complex dependency trees can be challenging. To make this standard practical, we suggest the following approaches to minimize the maintenance burden for developers:



### 1. Presumption of Human Creation
We follow a simple rule: **if a library does not disclose AI usage, it is treated as ZAID (Zero AI).** 
You are not expected to audit all dependencies. Disclosure is only required if a library explicitly discloses AI usage or is marketed as an AI-focused tool.


### 2. The `disclosure.yaml` Manifest
To support automation, we propose a standard [disclosure.yaml](disclosures/disclosure.yaml) file in the repository root.
 This machine-readable format allows future tooling to aggregate disclosure data across dependency chains, automating the calculation of a project's total disclosure level.


### 3. The Modifier
We do not expect an audit of the entire dependency history. If you have reviewed top-level documentation and manifests, your disclosure should reflect the information available for your primary dependencies.

### 4. Top-Level Only Rule
For most projects, disclosure responsibilities are limited to **Direct Dependencies**. If your project depends on `Library A`, and `Library A` depends on `Library B`, your disclosure should reflect `Library A`'s status. It is the responsibility of each maintainer to disclose the usage within their own project, preventing recursive disclosure overhead.


---

## Implementation


---

## 
# 1. Badge Integration
Use standard [shields.io](https://shields.io) badges in the `README.md` to provide an immediate visual indicator of the project's AI disclosure level.
```markdown
[![MAID-A](https://img.shields.io/badge/AID-MAID--A-blue)](https://github.com/path/to/ai-disclosure)
```


---

## 
# 2. CI/CD Validation
Incorporate checks into CI/CD pipelines (e.g., GitHub Actions) that look for AI-generated patterns or metadata. If a project is labeled ZAID but shows signs of AI-generated boilerplate, the build could fail or trigger a manual review.


---

## 
# 3. Pre-commit Hooks
A pre-commit hook could remind developers to update their AI disclosure if significant changes are made using AI tooling.


---

## Compliance and Verification

To ensure the integrity of the AI Disclosure standard, we recommend a three-tier compliance model:

1. **Self-Disclosure (Standard)**: The project maintainer provides the AID level based on their own assessment. This is the baseline for all projects.
2. **Third-Party Review (Optional)**: A trusted third-party (e.g., an open-source security firm or a specialized audit tool) verifies the disclosure level through code analysis and provenance tracking.
3. **Automated Attestation (Advanced)**: CI/CD systems generate a cryptographic attestation of the AID level, linking it to specific commits and the tools used during those commits.
