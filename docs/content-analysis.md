# Content Analysis

## Purpose

Content analysis is the second stage of the documentation pipeline.

The purpose is to examine the source material in detail and identify the information that will be needed to develop the documentation.

At this stage, the source is broken into logical information components and relationships.

The objective is to create a structured understanding of the content before documentation is developed.

The workflow is:

```text
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


Then I would **not immediately launch into lots of theory**.

The next section should be your actual Gateways example:

```markdown
## Example: Gateways API

The Gateways API source is analysed by identifying and structuring the information required to document the API.

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

The resulting structured information is captured in [`../examples/extracted-api-information.md`](../examples/extracted-api-information.md).
