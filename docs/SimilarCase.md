# SimilarCase

Similar historical case

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**similarity** | **float** | Similarity score (0-1) | [optional] 
**outcome** | **str** | Case outcome | [optional] 
**case_id** | **str** | Case ID | [optional] 

## Example

```python
from whisper_api_sdk.models.similar_case import SimilarCase

# TODO update the JSON string below
json = "{}"
# create an instance of SimilarCase from a JSON string
similar_case_instance = SimilarCase.from_json(json)
# print the JSON string representation of the object
print(SimilarCase.to_json())

# convert the object into a dict
similar_case_dict = similar_case_instance.to_dict()
# create an instance of SimilarCase from a dict
similar_case_from_dict = SimilarCase.from_dict(similar_case_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


