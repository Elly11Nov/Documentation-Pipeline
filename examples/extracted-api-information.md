# Extracted API Information

## Source

This structured information was extracted from the **Gateways API Reference**, an existing REST API reference used as the source for this documentation pipeline.

[View the Gateways API Reference PDF](LINK_TO_GATEWAYS_PDF)

The information below reflects the content provided by the source document.

## API Identity

| Attribute | Value |
|---|---|
| API name | Gateways |
| Type | REST |
| Version | 1.0 |
| Method | GET |

## Endpoint

`/gateways`

The endpoint accepts parameters that identify the prospect company, potential gateway persons and the number of results to return.

## Request Parameters

| Parameter | Type | Required | Default | Description |
|---|---|---|---|---|
| `prospect_id` | string | Yes | — | Prospect company ID |
| `potential_gateways` | string | Yes | — | Comma-separated list of potential gateway person IDs |
| `number_of_path_per_gw_person` | integer | No | 10 | Maximum number of paths per gateway person |
| `number_of_gw_person_per_prospect_person` | integer | No | 10 | Maximum number of gateway persons per prospect person |
| `number_of_prospect_person` | integer | No | — | Maximum number of prospect persons |
| `debug` | boolean | No | false | Debug mode |

## Request Structure

The source defines the request using the following endpoint structure:

`/gateways?prospect_id={prospectID}&potential_gateways={gatewayID}&number_of_path_per_gw_person={numberOfpathPerGWPerson}&number_of_prospect_person={numberOfGWPersonsPerProspectPerson}&number_of_prospect_person={numberOfProspectPersons}&debug=true`

The source identifies `prospect_id` and `potential_gateways` as required parameters. The remaining parameters are optional.

## Response

### Successful Response

| Attribute | Value |
|---|---|
| Status | 200 |
| Content type | `application/json` |

The response returns a list of paths between potential gateway persons and the prospect company.

### Response Structure

The source defines a response containing a list of prospects, gateway persons and paths.

- `list_of_prospects`
  - `link`
  - `score`
  - `paths_string`
  - `gateways_persons`
    - `link`
    - `score`
    - `paths`
      - `path_time_in_ms`

The source identifies `paths_string` and `path_time_in_ms` as debug-related information.

## Errors

### 400 Bad Request

The source documents a `400 Bad Request` response.

The documented causes include:

- No company for the supplied prospect ID
- Invalid parameter value

No additional error behaviour is inferred from the source.

## Examples

The source includes example request and response information.

Example identifiers are treated as placeholders because the source notes that the IDs have not been stabilised.

When preparing portfolio documentation, example values should therefore be treated as illustrative rather than as production identifiers.

## Information Model

The extracted information can be represented as:

- Gateways API
  - Identity
    - Name: Gateways
    - Type: REST
    - Version: 1.0
    - Method: GET
  - Endpoint
    - `/gateways`
  - Parameters
    - Required
      - `prospect_id`
      - `potential_gateways`
    - Optional
      - `number_of_path_per_gw_person`
      - `number_of_gw_person_per_prospect_person`
      - `number_of_prospect_person`
      - `debug`
  - Response
    - Status: 200
    - Content type: `application/json`
    - `list_of_prospects`
  - Errors
    - 400 Bad Request
  - Examples

## Documentation Outputs

This structured information provides the basis for different documentation outputs:

- **API Reference** — structured technical information for lookup
- **API Tutorial** — task-oriented guidance for using the API

The same underlying information can therefore support different documentation needs.

## Traceability

The information in this file is derived from the Gateways API source document.

The purpose of this intermediate representation is to make the source information explicit and structured before it is transformed into user-facing documentation.

No undocumented API behaviour has been added.
