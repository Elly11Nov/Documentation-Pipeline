# Content Analysis

Content analysis is the second stage of the documentation pipeline.

The purpose is to examine the source material in detail and identify the information needed to develop the documentation.

At this stage, the source is broken into logical information components and relationships.

The objective is to create a structured understanding of the content before documentation is developed.

The workflow is:

    Source Material
           ↓
    Identify Information Components
           ↓
    Classify and Structure Information
           ↓
    Identify Relationships and Dependencies
           ↓
    Identify Gaps and Inconsistencies
           ↓
    Create Structured Information
           ↓
    Ready for Documentation Development

## Example: Gateways API

The Gateways API is used as a practical example of the content analysis process.

The analysis identifies:

- API identity
- Endpoint
- HTTP method
- Request parameters
- Parameter types
- Required and optional parameters
- Default values
- Response
- Response schema
- Error conditions
- Examples

## 1. Identify Information Components

    Gateways API
    ├── API identity
    ├── Endpoint
    ├── Request
    │   └── Parameters
    ├── Response
    │   └── Response schema
    ├── Errors
    └── Examples

This creates an initial information model before documentation is developed.

## 2. Classify the Information

| Information | Category |
|---|---|
| Gateways | API identity |
| REST | API type |
| 1.0 | API version |
| `GET` | HTTP method |
| `/gateways` | Endpoint |
| `prospect_id` | Request parameter |
| `potential_gateways` | Request parameter |
| `debug` | Request parameter |
| `200` | Response status |
| `application/json` | Response content type |
| `400 Bad Request` | Error |

## 3. Analyse Parameters

| Parameter | Type | Required | Default |
|---|---|---:|---|
| `prospect_id` | string | Yes | — |
| `potential_gateways` | string | Yes | — |
| `number_of_path_per_gw_person` | integer | No | 10 |
| `number_of_gw_person_per_prospect_person` | integer | No | 10 |
| `number_of_prospect_person` | integer | No | — |
| `debug` | boolean | No | false |

The full extracted information is captured in [`../examples/extracted-api-information.md`](../examples/extracted-api-information.md).

## 4. Analyse the Response

The source documents a successful response with:

    Status: 200
    Content type: application/json

The response contains information about prospects, gateway persons and paths.

    Response
    └── list_of_prospects
        ├── link
        ├── score
        ├── paths_string
        └── gateways_persons
            ├── link
            ├── score
            └── paths
                └── path_time_in_ms

Some fields are associated with debug information.

## 5. Analyse Errors

The source documents an HTTP `400 Bad Request` response.

The documented causes include:

- No company for the supplied prospect ID
- Invalid parameter value

No additional error behaviour is assumed where it is not documented by the source.

## 6. Analyse Relationships and Dependencies

Content analysis considers how individual pieces of information relate to each other.

    Endpoint
        ↓
    Request parameters
        ↓
    API request
        ↓
    Response
        ↓
    Response structure

For example, `debug` is an optional parameter with a default value of `false`, and the response contains additional information associated with debug mode.

Understanding these relationships helps determine how the information should be explained in the documentation.

## 7. Identify Gaps and Inconsistencies

The analysis identifies information that is missing, unclear or inconsistent.

If the source does not document items such as:

- Authentication
- Base URL
- Request headers

they are treated as **undocumented information**.

They are not replaced with assumptions or invented technical details.

Other issues that may require review include:

- Inconsistent terminology
- Unclear descriptions
- Missing parameter information
- Examples that require clarification
- Information referenced in one section but not explained elsewhere

## 8. Create Structured Information

The result of content analysis is a structured representation of the source.

    API
    ├── Identity
    │   ├── Name
    │   ├── Type
    │   ├── Version
    │   └── Method
    ├── Endpoint
    ├── Parameters
    │   ├── Required
    │   └── Optional
    ├── Response
    │   ├── Status
    │   ├── Content type
    │   └── Schema
    ├── Errors
    └── Examples

This structured information becomes an intermediate layer between the original source and the final documentation.

## 9. From Analysis to Documentation
    Structured Information
             ↓
    ┌────────┴────────┐
    ↓                 ↓
API Reference     API Tutorial
    ↓                 ↓
Lookup information   Task-oriented guidance

The API reference provides detailed technical information.

The tutorial uses the same underlying information to guide users through a task.

## Analysis Checklist

    [ ] Main information components identified
    [ ] API identity identified
    [ ] Endpoint and HTTP method identified
    [ ] Parameters extracted
    [ ] Data types recorded
    [ ] Required and optional parameters identified
    [ ] Default values recorded where provided
    [ ] Response structure identified
    [ ] Error conditions identified
    [ ] Examples reviewed
    [ ] Relationships and dependencies considered
    [ ] Missing information recorded
    [ ] Unclear information identified
    [ ] Unsupported assumptions avoided
    [ ] Information structured for documentation

## Output

The output of content analysis is a structured understanding of the source material.

For this project, the extracted API information is captured in [`../examples/extracted-api-information.md`](../examples/extracted-api-information.md).

This information is then used to develop the API reference and tutorial described in [`api-documentation-workflow.md`](api-documentation-workflow.md).

## Key Principle

Content analysis transforms source material into structured information that can be used consistently across documentation outputs.

> **Understand and structure the information before turning it into documentation.**
