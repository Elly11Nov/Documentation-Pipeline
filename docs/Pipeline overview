# Documentation Pipeline Overview

## Introduction

Technical documentation often begins with information that is incomplete, unstructured or written for a different purpose.

An API specification may describe endpoints and parameters but not explain how a developer should use them. A requirements document may contain important business and technical information without providing a documentation structure. Existing documentation may contain useful information but require restructuring for a new audience.

A documentation pipeline provides a repeatable way to move from this source material to documentation that is structured, usable and maintainable.

This project uses the following workflow:

```text
Source Material
       ↓
Content Intake
       ↓
Content Analysis
       ↓
Information Structure
       ↓
Documentation Development
       ↓
AI-Assisted Review
       ↓
Human Validation
       ↓
Quality Checks
       ↓
Publication & Maintenance
```

---

## 1. Source Material

The pipeline begins with one or more sources.

Examples include:

* API specifications
* Configuration files
* Existing documentation
* Requirements
* Product information
* Technical notes
* Subject-matter expert (SME) input

The source is treated as the authoritative starting point for the documentation work.

The first objective is **not to write**. It is to understand what information is available.

---

## 2. Content Intake

During intake, the source material is identified and assessed.

The intake stage establishes:

* What the source contains
* Where the information comes from
* What type of documentation may be required
* What information appears to be missing
* What information is ambiguous
* What questions may require clarification

This creates a clear boundary between **receiving information** and **interpreting information**.

See [`content-intake.md`](content-intake.md).

---

## 3. Content Analysis

The source is then analysed to identify the information needed for documentation.

For an API, this might include:

* API name and version
* Endpoint
* HTTP method
* Parameters
* Data types
* Required and optional values
* Default values
* Response structure
* Error conditions
* Examples

The information is separated into logical components so that gaps and inconsistencies can be identified before documentation is developed.

See [`content-analysis.md`](content-analysis.md).

---

## 4. Information Structure

The analysed information is organised into a structured representation.

This intermediate step is important because the source material and the final documentation do not necessarily have the same structure.

For example:

```text
API
├── Identity
├── Endpoint
├── Parameters
├── Request
├── Response
├── Errors
└── Examples
```

The structured information becomes the basis for developing different documentation outputs.

For example, the same underlying information can support both:

* Reference documentation
* A task-oriented tutorial

The extracted API information used in this project is provided as an example of this intermediate stage.

See [`../examples/extracted-api-information.md`](../examples/extracted-api-information.md).

---

## 5. Documentation Development

The structured information is transformed into documentation appropriate to the audience and purpose.

Different outputs may require different approaches.

### Reference documentation

Reference content focuses on providing accurate, structured information that users can consult when they need a specific detail.

For an API, this may include:

* Endpoint information
* Parameters
* Data types
* Defaults
* Responses
* Errors
* Examples

### Task-oriented documentation

A tutorial or how-to guide focuses on helping a user accomplish a task.

It may explain:

1. What is required
2. How to construct a request
3. How to submit the request
4. How to interpret the response
5. What to do when an error occurs

The documentation should therefore be designed around the **user's information need**, rather than simply reproducing the structure of the source material.

See [`api-documentation-workflow.md`](api-documentation-workflow.md).

---

## 6. AI-Assisted Review

AI can be introduced after the information has been structured and documentation has been drafted.

The purpose is to support review rather than replace technical judgement.

AI-assisted checks may identify:

* Missing parameters
* Inconsistent terminology
* Contradictory statements
* Missing defaults
* Incomplete examples
* Structural inconsistencies
* Potentially unclear descriptions

AI findings are treated as **review suggestions**, not as automatically correct conclusions.

See [`ai-assisted-review.md`](ai-assisted-review.md).

---

## 7. Human Validation

Human validation is a separate stage of the workflow.

The reviewer checks the documentation against the source material and the intended use.

Validation may include:

* Confirming technical accuracy
* Checking interpretation of the source
* Verifying examples
* Resolving ambiguities
* Confirming terminology
* Confirming that the documentation meets its intended purpose

This is especially important when source material is incomplete or ambiguous.

---

## 8. Quality Checks

After technical validation, the documentation can be checked against defined quality criteria.

Typical checks include:

### Completeness

Is the required information present?

### Accuracy

Does the documentation accurately represent the source?

### Consistency

Are terminology, parameter names, formatting and examples consistent?

### Clarity

Can the intended audience understand and use the information?

### Structure

Is information organised so that users can find what they need?

### Maintainability

Can the documentation be updated when the underlying product or API changes?

---

## 9. Publication and Maintenance

Once documentation has passed validation and quality checks, it can be published.

Publication is not the end of the workflow.

Changes to the underlying API, product, configuration or process may require corresponding documentation updates.

A maintainable documentation workflow therefore needs to preserve the relationship between:

```text
Source
  ↓
Structured information
  ↓
Documentation
```

When the source changes, the affected documentation can be identified and reviewed.

---

## AI and Human Responsibilities

The pipeline deliberately separates activities that can be assisted by AI from activities that require human judgement.

| Activity               | AI assistance                     | Human responsibility                              |
| ---------------------- | --------------------------------- | ------------------------------------------------- |
| Information extraction | Identify and organise information | Confirm interpretation                            |
| Gap identification     | Flag possible gaps                | Determine whether information is actually missing |
| Drafting               | Assist with structure and wording | Define appropriate content                        |
| Review                 | Identify potential issues         | Validate technical correctness                    |
| Quality checks         | Detect inconsistencies            | Decide whether corrections are required           |
| Final approval         | —                                 | Accept and publish the documentation              |

The objective is to create a workflow in which AI can accelerate documentation activities without making unsupported assumptions about the source.

---

## Core Principle

The pipeline separates **information extraction, interpretation, documentation development and validation** rather than treating documentation generation as a single AI task.

The resulting workflow is:

```text
Understand the source
        ↓
Structure the information
        ↓
Develop the documentation
        ↓
Use AI to assist review
        ↓
Validate with human judgement
        ↓
Publish and maintain
```

This approach provides a foundation for producing documentation that is accurate, useful and maintainable while making appropriate use of AI-assisted tools.
