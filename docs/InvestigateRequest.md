# InvestigateRequest

Request for comprehensive AI threat investigation

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**indicator** | **str** | The indicator to investigate | 
**indicator_type** | **str** | Type of indicator | 
**depth** | **str** | Investigation depth level | [optional] 
**context** | [**InvestigateContext**](InvestigateContext.md) |  | [optional] 

## Example

```python
from whisper_api_sdk.models.investigate_request import InvestigateRequest

# TODO update the JSON string below
json = "{}"
# create an instance of InvestigateRequest from a JSON string
investigate_request_instance = InvestigateRequest.from_json(json)
# print the JSON string representation of the object
print(InvestigateRequest.to_json())

# convert the object into a dict
investigate_request_dict = investigate_request_instance.to_dict()
# create an instance of InvestigateRequest from a dict
investigate_request_from_dict = InvestigateRequest.from_dict(investigate_request_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


