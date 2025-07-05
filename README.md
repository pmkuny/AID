## TODO
- [ ] Further clarification of AI usage levels
- [ ] Deep dive into specific examples of AI usage levels
- [ ] Overview
- [ ] Additional levels of Special Usage
- [ ] Continued breakdown of Nomenclature

# AID
Standardization for AI Disclosures as it relates to Code and Media Content

## Overview and Intention

### No Threshold
One of the concepts encapsulated here is the "no threshold" approach, which simply means that for the purposes of this disclosure, ANY usage of AI, including AI tooling or a vendor that provides AI tooling (or an output that is AI-generated or influenced) **passes the threshold for AI usage**. While different levels of engagement with AI are later specified, it's important to keep the bar for what actually constitutes AI usage low, in my opinion. This makes it easy to immediately differentiate those projects that incorporate a zero-tolerance rule for AI usage.

### Vendors and AI Tools
A note on vendors: With the rise of AI tooling in businesses, organizations, and third-parties, we hope to incorporate this disclosure as one that is at the lowest level, or as far-right in the chain as possible. That is, the same metrics that are used here on a per-project basis are applied to anything vendor-related higher in the chain. If this project had a section of content created by an AI tool that a vendor provides, then we believe that that disclosure should "propagate down" to this project. Therefore, keeping the "no threshold" rule in mind, any usage of an AI tool to bootstrap or otherwise create initial content for this project, passes that no threshold mark and counts as a usage of AI.
- Example: I use a tool that builds a skeleton of my project based on what an AI recommends. That skeleton is the baseline for a new programming project I'm working on. Because the skeleton was AI-generated, the final project's README should include an AI disclosure statement, at the very least SAID-level, because an AI-tool was used to generate at least part of the content.

## Nomenclature

- **AI System or Tooling**: Includes direct engagement of an AI Tool, Assistant, LLM, or third-party source that provides the former. Includes iteration, "spot checking", "tweaking" or formatting-only type tools. 

- **Content**: The actual content of a repository, interpreted widely. This could be images, source code, documentation, tests, or other core content that provides both primary and auxiliary functionality to the program or media in question. This takes a "no threshold" approach, where any engagement with AI in content creation counts as a usage of AI in general. Levels of content generation are then clarified in the type of disclosure used. **Note that this relates to content creation only, not any external process such as brainstorming or ideation.**

- **Documentation**: 

## Example Disclosures

### General Usage - Level of AI Involvement

- **FAID** - This content was written entirely by AI tooling or systems, and contains only human-in-the-loop interactions, or verification for functionality and security. All content should be considered AI-generated.
  
- **MAID** - This content was written by a human, with moderate usage of AI tooling or systems to generate the content contained within. Clarification on AI-generated content may be present, or will require further clarification
  - **MAID-A** - 
  - **MAID-C** - 

- **SAID** - This content was written by a human, with small adjustments by AI tooling or systems to ensure accuracy, best practices, or bug-fixing.
  
- **ZAID** - This content was created by a human, with zero AI involvement.
  

### Special Usage - Content-Specific AI Involvement

**DAID** - This content was **primarily** written by a human, with AI-generated documentation, including the documentation tools being configured in question by AI. All documentation and documentation systems presented in this repository should be considered AI-generated.

## Thoughts - Systemic and Automated Inclusion

## FAQ
