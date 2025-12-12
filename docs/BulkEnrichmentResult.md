# BulkEnrichmentResult

Result of a bulk indicator enrichment job. Contains enriched data for all successfully processed indicators.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**status** | **str** | Status of the bulk enrichment | [optional] 
**results** | **List[object]** | Array of successfully enriched indicator results. Each item contains: - &#x60;indicator&#x60;: The original indicator value (e.g., \&quot;8.8.8.8\&quot; or \&quot;google.com\&quot;) - &#x60;type&#x60;: \&quot;ip\&quot; or \&quot;domain\&quot; - &#x60;query&#x60;: Request metadata with type, value, timestamp, and response_time_ms - &#x60;summary&#x60;: Key information summary (organization, location, ASN, risk_score, etc.)  For IP indicators: - &#x60;geolocation&#x60;: Country, city, coordinates, ISP details - &#x60;network&#x60;: BGP routing data if requested (visibility, origins, prefix info) - &#x60;isp&#x60;: ISP name, organization, ASN - &#x60;reputation&#x60;: Risk score and blacklist scores - &#x60;relationships&#x60;: Related domains and shared infrastructure  For domain indicators: - &#x60;registration&#x60;: WHOIS data (registrar, dates, nameservers, status, registrant info) - &#x60;dns&#x60;: DNS records (A, AAAA, MX, NS, TXT, CNAME) - &#x60;reputation&#x60;: Domain reputation with infrastructure scores - &#x60;relationships&#x60;: Related domains, incoming/outgoing links  | [optional] 
**errors** | **List[object]** | Array of failed enrichment attempts. Each item contains: - &#x60;indicator&#x60;: The indicator that failed enrichment - &#x60;type&#x60;: \&quot;ip\&quot; or \&quot;domain\&quot; - &#x60;error&#x60;: true (boolean flag indicating this is an error entry) - &#x60;message&#x60;: Human-readable error description (e.g., \&quot;Timeout or error during enrichment\&quot;)  | [optional] 
**total_processed** | **int** | Total number of indicators processed | [optional] 
**total_failed** | **int** | Total number of failed enrichments | [optional] 
**total_indicators** | **int** | Total number of indicators in the request | [optional] 
**success_rate** | **float** | Percentage of successful enrichments | [optional] 
**message** | **str** | Error message if the entire job failed | [optional] 

## Example

```python
from whisper_api_sdk.models.bulk_enrichment_result import BulkEnrichmentResult

# TODO update the JSON string below
json = "{}"
# create an instance of BulkEnrichmentResult from a JSON string
bulk_enrichment_result_instance = BulkEnrichmentResult.from_json(json)
# print the JSON string representation of the object
print(BulkEnrichmentResult.to_json())

# convert the object into a dict
bulk_enrichment_result_dict = bulk_enrichment_result_instance.to_dict()
# create an instance of BulkEnrichmentResult from a dict
bulk_enrichment_result_from_dict = BulkEnrichmentResult.from_dict(bulk_enrichment_result_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


