# AttributeResult

Result of threat actor attribution analysis

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**indicators** | **List[str]** | List of indicators that were analyzed | [optional] 
**status** | **str** | Status of the attribution analysis | [optional] 
**error** | **bool** | Whether an error occurred | [optional] 
**message** | **str** | Error message if the attribution failed | [optional] 
**attribution** | **object** |  | [optional] 

## Example

```python
from whisper_api_sdk.models.attribute_result import AttributeResult

# TODO update the JSON string below
json = "{}"
# create an instance of AttributeResult from a JSON string
attribute_result_instance = AttributeResult.from_json(json)
# print the JSON string representation of the object
print(AttributeResult.to_json())

# convert the object into a dict
attribute_result_dict = attribute_result_instance.to_dict()
# create an instance of AttributeResult from a dict
attribute_result_from_dict = AttributeResult.from_dict(attribute_result_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


