# SimilarCasesRequest

Request for ML-based similar case matching

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**indicators** | **List[str]** | List of indicators for the current case | 
**behavior_description** | **str** | Description of observed behavior | [optional] 
**observed_ttps** | **List[str]** | Observed MITRE ATT&amp;CK TTPs | [optional] 
**min_similarity** | **float** | Confidence threshold for matches (0-1) | [optional] 
**limit** | **int** | Maximum number of similar cases to return | [optional] 

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


