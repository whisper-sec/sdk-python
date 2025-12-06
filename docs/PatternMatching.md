# PatternMatching

Pattern matching insights

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**confidence** | **float** | Pattern confidence score | [optional] 
**matched_patterns** | **List[str]** | Matched pattern types | [optional] 

## Example

```python
from whisper_api_sdk.models.pattern_matching import PatternMatching

# TODO update the JSON string below
json = "{}"
# create an instance of PatternMatching from a JSON string
pattern_matching_instance = PatternMatching.from_json(json)
# print the JSON string representation of the object
print(PatternMatching.to_json())

# convert the object into a dict
pattern_matching_dict = pattern_matching_instance.to_dict()
# create an instance of PatternMatching from a dict
pattern_matching_from_dict = PatternMatching.from_dict(pattern_matching_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


