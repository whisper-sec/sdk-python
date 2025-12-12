# SimilarCasesResult

Result of ML-based similar case matching

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**indicators** | **List[str]** | List of indicators that were analyzed | [optional] 
**status** | **str** | Status of the similar cases search | [optional] 
**error** | **bool** | Whether an error occurred | [optional] 
**message** | **str** | Error message if the search failed | [optional] 
**similar_cases** | **object** |  | [optional] 

## Example

```python
from whisper_api_sdk.models.similar_cases_result import SimilarCasesResult

# TODO update the JSON string below
json = "{}"
# create an instance of SimilarCasesResult from a JSON string
similar_cases_result_instance = SimilarCasesResult.from_json(json)
# print the JSON string representation of the object
print(SimilarCasesResult.to_json())

# convert the object into a dict
similar_cases_result_dict = similar_cases_result_instance.to_dict()
# create an instance of SimilarCasesResult from a dict
similar_cases_result_from_dict = SimilarCasesResult.from_dict(similar_cases_result_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


