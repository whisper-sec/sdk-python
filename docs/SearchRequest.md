# SearchRequest

Search query for finding domains matching WHOIS registration criteria.  **Query Modes:** 1. **Field-based (recommended):** Specify individual fields like `registrantCompany`, `tld`, etc. 2. **Query string:** Use `query` field with `field:value` syntax for compatibility.  Multiple criteria are combined with AND logic. Results are paginated with a maximum of 100 results per page.  **Use Cases:** - Threat hunting: Find domains registered by known malicious actors - Brand protection: Monitor for domains similar to your brand - Infrastructure discovery: Map domains sharing registrants or nameservers - Investigation: Track domains created on specific dates 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**effective_page** | **int** |  | [optional] 
**query** | **str** | Search query using field:value syntax (alternative to individual field parameters). If individual field parameters are provided, they take precedence.  **Supported Syntax:** - Single field: &#x60;registrantCompany:Google&#x60; - Multiple fields: &#x60;registrantCompany:Google registrantCountry:US&#x60;  **Note:** For new integrations, prefer using individual field parameters instead of query syntax.  | [optional] 
**var_field** | **str** | Field to search in when using simple query mode. Use with &#x60;query&#x60; parameter. | [optional] 
**tld** | **str** | Top-Level Domain to filter by (exact match). Examples: com, org, net, io | [optional] 
**registrar_name** | **str** | Domain registrar name to filter by (exact match) | [optional] 
**registrar_iana_id** | **str** | IANA registrar ID to filter by (exact match) | [optional] 
**registrant_name** | **str** | Registrant name to search for (text search, partial match) | [optional] 
**registrant_company** | **str** | Registrant company/organization to search for (text search, partial match) | [optional] 
**registrant_email** | **str** | Registrant email to search for (text search). Supports wildcards like *@example.com | [optional] 
**registrant_phone** | **str** | Registrant phone number to search for (text search) | [optional] 
**registrant_country** | **str** | Registrant country code to filter by (2-letter ISO code) | [optional] 
**registrant_city** | **str** | Registrant city to search for (text search) | [optional] 
**name_server** | **str** | Name server hostname to search for (text search) | [optional] 
**domain_status** | **str** | Domain status flag to search for (text search). E.g., clientTransferProhibited | [optional] 
**created_date** | **str** | Domain creation date to filter by (exact match, format: YYYY-MM-DD) | [optional] 
**updated_date** | **str** | Domain last update date to filter by (exact match, format: YYYY-MM-DD) | [optional] 
**expiry_date** | **str** | Domain expiry date to filter by (exact match, format: YYYY-MM-DD) | [optional] 
**limit** | **int** | Maximum number of results to return per page (max 100 for WHOIS searches) | [optional] [default to 100]
**page** | **int** | Page number for pagination (0-indexed). Alternative to offset. | [optional] [default to 0]
**offset** | **int** | Number of results to skip for pagination. Converted to page internally. | [optional] [default to 0]

## Example

```python
from whisper_api_sdk.models.search_request import SearchRequest

# TODO update the JSON string below
json = "{}"
# create an instance of SearchRequest from a JSON string
search_request_instance = SearchRequest.from_json(json)
# print the JSON string representation of the object
print(SearchRequest.to_json())

# convert the object into a dict
search_request_dict = search_request_instance.to_dict()
# create an instance of SearchRequest from a dict
search_request_from_dict = SearchRequest.from_dict(search_request_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


