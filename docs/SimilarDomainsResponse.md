# SimilarDomainsResponse

Result returned when a similar domains job completes. Access this via GET /v1/ops/jobs/{jobId} after the job status becomes COMPLETED.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**domain** | **str** | The input domain that was analyzed | 
**status** | **str** | Job completion status | 
**similar_domains** | [**List[SimilarDomainEntry]**](SimilarDomainEntry.md) | List of similar domains found | 
**total_count** | **int** | Total number of similar domains found | 
**analysis** | [**AnalysisMetadata**](AnalysisMetadata.md) | Analysis metadata about the search | 
**error** | **bool** | Error flag, present only when status is &#39;failed&#39; | [optional] 
**message** | **str** | Error message, present only when status is &#39;failed&#39; | [optional] 

## Example

```python
from whisper_api_sdk.models.similar_domains_response import SimilarDomainsResponse

# TODO update the JSON string below
json = "{}"
# create an instance of SimilarDomainsResponse from a JSON string
similar_domains_response_instance = SimilarDomainsResponse.from_json(json)
# print the JSON string representation of the object
print(SimilarDomainsResponse.to_json())

# convert the object into a dict
similar_domains_response_dict = similar_domains_response_instance.to_dict()
# create an instance of SimilarDomainsResponse from a dict
similar_domains_response_from_dict = SimilarDomainsResponse.from_dict(similar_domains_response_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


