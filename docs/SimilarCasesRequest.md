# SimilarCasesRequest

Request for ML-based similar case matching. Finds historical incidents similar to the current case based on indicators, behaviors, and TTPs.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**indicators** | **List[str]** | List of indicators (IPs, domains, hashes, URLs) associated with the current case. This is the primary matching criteria. | 
**behavior_description** | **str** | Free-text description of observed malicious behavior or incident details. Improves matching accuracy by considering behavioral patterns. | [optional] 
**observed_ttps** | **List[str]** | Observed MITRE ATT&amp;CK technique IDs. Helps find cases with similar attack techniques. See https://attack.mitre.org for reference. | [optional] 
**min_similarity** | **float** | Minimum similarity score threshold (0.0 to 1.0). Higher values return fewer but more precise matches. Default: 0.5 | [optional] [default to 0.5]
**limit** | **int** | Maximum number of similar cases to return. Higher limits may increase processing time. | [optional] [default to 10]

## Example

```python
from whisper_api_sdk.models.similar_cases_request import SimilarCasesRequest

# TODO update the JSON string below
json = "{}"
# create an instance of SimilarCasesRequest from a JSON string
similar_cases_request_instance = SimilarCasesRequest.from_json(json)
# print the JSON string representation of the object
print(SimilarCasesRequest.to_json())

# convert the object into a dict
similar_cases_request_dict = similar_cases_request_instance.to_dict()
# create an instance of SimilarCasesRequest from a dict
similar_cases_request_from_dict = SimilarCasesRequest.from_dict(similar_cases_request_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


