# AI-Assisted Review

## Purpose

AI-assisted review is a stage of the documentation pipeline where AI is used to help identify potential issues in technical documentation.

The purpose is not to replace technical review or automatically change documentation.

AI is used as a review assistant to help identify possible gaps, inconsistencies and areas that require human attention.

The workflow is:

    Source Material
           ↓
    Content Analysis
           ↓
    Documentation Development
           ↓
    AI-Assisted Review
           ↓
    Human Validation
           ↓
    Quality Checks
           ↓
    Publication

## Where AI Adds Value

AI can be useful for reviewing documentation against structured source information.

Potential uses include:

- Identifying missing information
- Comparing terminology
- Checking parameter names and descriptions
- Identifying inconsistent default values
- Reviewing examples for possible inconsistencies
- Identifying contradictory statements
- Checking whether documentation follows the intended structure
- Highlighting information that may require clarification

AI findings are treated as review suggestions rather than automatically correct conclusions.


## 1. Completeness Review

AI can compare the structured source information with the documentation and identify potential omissions.

For example:

    Source
    └── debug parameter

    Documentation
    └── debug parameter missing

The AI can flag the difference for review.

The reviewer then checks the source and determines whether the information should be added.


## 2. Consistency Review

AI can help identify differences in terminology, parameter names or documented values.

For example:

    Source:
    debug = false

    Documentation:
    debug = true

The AI can identify this as a potential inconsistency.

The human reviewer verifies the source and determines the correct value.


## 3. Contradiction Review

AI can compare different parts of a document and flag statements that appear to conflict.

For example:

    Parameter description:
    debug is optional.

    Later documentation:
    debug is required.

The AI can identify the apparent contradiction.

The reviewer then checks the source material and resolves the issue.


## 4. Example Review

AI can also review examples against the documented API structure.

Checks may include:

- Parameter names
- Parameter values
- Endpoint structure
- Response structure
- Terminology

The purpose is to identify examples that may require verification.

AI does not establish whether an example is technically valid.

That decision remains with the reviewer.


## 5. Identifying Missing Information

AI can help identify information that appears to be missing from the documentation.

For example, if the source contains information about:

- Endpoint
- Parameters
- Response
- Errors

but the documentation does not contain an errors section, AI can flag the omission.

The reviewer then determines whether the missing information is relevant to the intended documentation.

## 6. What AI Should Not Do

AI should not automatically:

- Invent technical information
- Invent API behaviour
- Invent authentication requirements
- Invent parameter values
- Invent error conditions
- Assume undocumented information is supported
- Change technical content without review
- Treat its own interpretation as the source of truth

If information is missing from the source, it should be identified as missing rather than filled with an assumption.

This is especially important when working with technical documentation, where plausible-sounding information may still be incorrect.


## 7. Human Validation

AI-assisted review is followed by human validation.

The reviewer checks potential findings against the source material and determines what action is required.

The responsibilities can be divided as follows:

| Activity | AI assistance | Human responsibility |
|---|---|---|
| Completeness | Identify possible omissions | Verify against source |
| Terminology | Flag inconsistencies | Confirm correct terminology |
| Parameters | Compare documented values | Confirm technical accuracy |
| Examples | Identify possible inconsistencies | Validate examples |
| Errors | Flag possible gaps or conflicts | Confirm documented behaviour |
| Missing information | Highlight potential gaps | Decide whether clarification is required |
| Final documentation | Support review | Approve final content |



## Example: Gateways API

The Gateways API provides a practical example of how AI-assisted review can be used.

### Source information

The source defines:

    debug
    Type: boolean
    Required: No
    Default: false

### Documentation

Suppose the draft documentation contains:

    debug
    Type: boolean
    Required: No
    Default: true

### AI review finding

The AI can flag:

    Potential inconsistency:
    The source specifies a default value of false,
    while the documentation specifies true.

### Human action

The reviewer checks the original source.

If the source confirms `false`, the documentation is corrected.

The important point is that AI **identified the issue**, while the source and human reviewer determined the correct result.


## Review Checklist

    [ ] Documentation compared with source information
    [ ] Missing information identified
    [ ] Parameter names checked
    [ ] Default values checked
    [ ] Terminology checked
    [ ] Examples reviewed
    [ ] Potential contradictions identified
    [ ] Undocumented information flagged
    [ ] AI findings verified against the source
    [ ] Unsupported AI-generated information rejected
    [ ] Final documentation reviewed by a human


## Key Principle

AI is used as an assistant within the documentation workflow, not as the authority on technical accuracy.

The principle is:

> **AI can identify what needs to be checked; the source and human judgement determine what is correct.**
