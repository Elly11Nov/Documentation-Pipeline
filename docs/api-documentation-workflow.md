# API Documentation Workflow

## Purpose

This workflow demonstrates how source material for a REST API can be transformed into structured, user-focused API documentation.

The example uses the **Gateways API** as the source material.

The workflow separates information extraction and analysis from documentation development and review.


## Workflow

```text
Gateways API Source
        ↓
Identify API Structure
        ↓
Extract API Information
        ↓
Structure the Information
        ↓
Create API Reference
        ↓
Create API Tutorial
        ↓
Review
        ↓
Human Validation
```


## 1. Start with the Source

The starting point is an existing API reference describing the Gateways REST API.

The source contains information about:

* API name and type
* Version
* HTTP method
* Endpoint
* Parameters
* Response
* Response schema
* Errors
* Example request and response

The source identifies the API as a REST API using the `GET` method and the `/gateways` endpoint.



## 2. Identify the API Structure

The first step is to identify the main components of the API.

```text
Gateways API
├── API identity
├── Endpoint
├── Method
├── Parameters
├── Response
├── Response schema
├── Errors
└── Example
```

This creates a high-level map of the information available in the source.



## 3. Extract the API Information

The next step is to extract the individual pieces of information.

For example, the source identifies six parameters:

* `prospect_id`
* `potential_gateways`
* `number_of_path_per_gw_person`
* `number_of_gw_person_per_prospect_person`
* `number_of_prospect_person`
* `debug`

The source also identifies which parameters are required, optional and have default values.

The extracted information is recorded separately before documentation is written.

See [`../examples/extracted-api-information.md`](../examples/extracted-api-information.md).



## 4. Structure the Information

The extracted information is organised into a consistent structure.

For example:

```text
API
├── Identity
│   ├── Name
│   ├── Type
│   ├── Version
│   └── Method
├── Endpoint
├── Parameters
├── Response
├── Errors
└── Examples
```

This intermediate structure makes it easier to identify missing information and maintain consistency between different documentation outputs.


## 5. Create the API Reference

The structured information is then used to create reference documentation.

The reference documentation focuses on answering questions such as:

* What does the API do?
* What endpoint should I use?
* Which parameters are required?
* What values can the parameters contain?
* What is the default value?
* What does the response contain?
* What errors can occur?

The resulting API reference is maintained as a separate documentation sample in the **Configuration-Documentation** portfolio repository.


## 6. Create the API Tutorial

Reference documentation and tutorials serve different purposes.

The reference explains **what the API contains**.

The tutorial explains **how to use it**.

For the Gateways API, the tutorial provides a task-oriented path through:

1. Identifying the required information
2. Constructing the request
3. Adding optional parameters where appropriate
4. Sending the request
5. Interpreting the response
6. Using debug information
7. Troubleshooting a `400 Bad Request` response

The tutorial is based on the information available in the source rather than inventing additional API behaviour.


## 7. Review the Documentation

Before publication, the documentation is reviewed against the source material.

The review checks for:

### Completeness

Are all documented API parameters and response elements represented?

### Consistency

Are parameter names, terminology and values used consistently?

### Accuracy

Does the documentation accurately reflect the source?

### Clarity

Can the intended reader understand how to use the API?

### Examples

Do examples correspond to the documented request and response structure?


## 8. Human Validation

Automated or AI-assisted review can identify potential problems, but it does not establish technical truth.

Human validation is used to confirm:

* Technical accuracy
* Interpretation of ambiguous source material
* Correct terminology
* Correct examples
* Appropriate handling of undocumented information

Information that cannot be confirmed from the source should not be presented as fact.



## 9. Final Outputs

The workflow produces two main documentation outputs:

```text
                    Gateways API Source
                            ↓
                 Extracted API Information
                       ↙          ↘
              API Reference      API Tutorial
```

The **API Reference** provides structured reference information.

The **API Tutorial** provides task-oriented guidance.

Both are derived from the same underlying information.


## Why Separate the Workflow from the Documentation?

Keeping the workflow separate from the final documentation makes the process easier to understand and maintain.

The documentation repository demonstrates the **finished documentation**.

This repository demonstrates **how the information was analysed, structured and transformed into documentation**.

The workflow can also be reused for other APIs and technical documentation projects.



## Key Principle

API documentation should not be treated as a simple conversion from source material to prose.

A more reliable approach is:

```text
Understand
    ↓
Extract
    ↓
Structure
    ↓
Document
    ↓
Review
    ↓
Validate


AI can assist with some of these activities, but human judgement remains part of the documentation process.
