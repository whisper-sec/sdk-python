# AttributeRequest

Request for threat actor attribution and campaign clustering

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**indicators** | **List[str]** | List of indicators (IPs, domains, hashes, URLs) for attribution analysis. Maximum 500 indicators per request. | 
**context** | [**AttributionContext**](AttributionContext.md) | Optional context object to enhance attribution accuracy. NOT a string - must be an object with fields like observedTTPs, targetedSector, etc. | [optional] 

## Example

```python
from whisper_api_sdk.models.attribute_request import AttributeRequest

# TODO update the JSON string below
json = "{}"
# create an instance of AttributeRequest from a JSON string
attribute_request_instance = AttributeRequest.from_json(json)
# print the JSON string representation of the object
print(AttributeRequest.to_json())

# convert the object into a dict
attribute_request_dict = attribute_request_instance.to_dict()
# create an instance of AttributeRequest from a dict
attribute_request_from_dict = AttributeRequest.from_dict(attribute_request_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


