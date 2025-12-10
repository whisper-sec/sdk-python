# InvestigateRequest

Request for comprehensive AI-powered threat investigation. Analyzes indicators and returns verdict, timeline, and recommendations.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**indicator** | **str** | The indicator to investigate (IP address, domain name, or file hash) | 
**indicator_type** | **str** | Type of indicator being investigated | 
**depth** | **str** | Investigation depth level. &#39;quick&#39; (30-60s) for basic checks, &#39;standard&#39; (60-120s) for typical investigations, &#39;comprehensive&#39; (120-300s) for deep analysis. | [optional] [default to 'standard']
**context** | [**InvestigateContext**](InvestigateContext.md) | Optional context object to guide the investigation. NOT a string - must be an object with fields like hypothesis, relatedIndicators, timeRange. | [optional] 

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


