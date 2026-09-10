# Gateways API

## Overview

The Gateways API returns a list of paths between potential gateway persons and a prospect company.

This documentation is based on the [Gateways API Reference PDF]([(https://github.com/Elly11Nov/Configuration-Documentation/blob/main/docs/samples/Gateways%20API%20Reference.pdf)]).

## API Information

| Attribute | Value |
|---|---|
| API name | Gateways |
| Type | REST |
| Version | 1.0 |
| Method | GET |

## Endpoint

`GET /gateways`

## Request Parameters

| Parameter | Type | Required | Default | Description |
|---|---|---|---|---|
| `prospect_id` | string | Yes | — | Prospect company ID |
| `potential_gateways` | string | Yes | — | Comma-separated list of potential gateway person IDs |
| `number_of_path_per_gw_person` | integer | No | 10 | Maximum number of paths per gateway person |
| `number_of_gw_person_per_prospect_person` | integer | No | 10 | Maximum number of gateway persons per prospect person |
| `number_of_prospect_person` | integer | No | — | Maximum number of prospect persons |
| `debug` | boolean | No | false | Enables debug information |

## Request Example

`GET /gateways?prospect_id={prospectID}&potential_gateways={gatewayID}&number_of_path_per_gw_person={numberOfpathPerGWPerson}&number_of_prospect_person={numberOfGWPersonsPerProspectPerson}&number_of_prospect_person={numberOfProspectPersons}&debug=true`

The example uses placeholder identifiers.

## Response

### 200 OK

Content type: `application/json`

A successful response returns a list of paths between potential gateway persons and the prospect company.

### Response Structure

The response contains a list of prospects, gateway persons and paths.

    list_of_prospects
    ├── link
    ├── score
    ├── paths_string
    └── gateways_persons
        ├── link
        ├── score
        └── paths
            └── path_time_in_ms

`paths_string` and `path_time_in_ms` are associated with debug information.

## Errors

### 400 Bad Request

The source documents the following causes:

- No company for the supplied prospect ID
- Invalid parameter value

No additional error behaviour is documented in the source.

## Debug Mode

The `debug` parameter is optional.

| Parameter | Type | Default |
|---|---|---|
| `debug` | boolean | false |

When debug information is enabled, the response can contain additional debug-related information identified in the source.

## Documentation Notes

This documentation is a portfolio-safe representation of the source material.

Example identifiers are treated as placeholders because the source notes that the IDs have not been stabilised.

Only information supported by the source has been included. Undocumented API behaviour has not been added or inferred.

## Related Documentation

- [Extracted API Information](extracted-api-information.md)
- [API Documentation Workflow](../docs/api-documentation-workflow.md)
- [AI-Assisted Review](../docs/ai-assisted-review.md)
