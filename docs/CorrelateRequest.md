# CorrelateRequest

Request for cross-customer indicator correlation analysis

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**indicators** | **List[str]** | List of indicators (IPs, domains, hashes) to correlate across global threat intelligence. Maximum 100 indicators per request. | 
**options** | [**CorrelateOptions**](CorrelateOptions.md) | Optional configuration object for correlation analysis. NOT a string - must be an object with fields like timeWindow, minConfidence, etc. | [optional] 

## Example

```python
from whisper_api_sdk.models.correlate_request import CorrelateRequest

# TODO update the JSON string below
json = "{}"
# create an instance of CorrelateRequest from a JSON string
correlate_request_instance = CorrelateRequest.from_json(json)
# print the JSON string representation of the object
print(CorrelateRequest.to_json())

# convert the object into a dict
correlate_request_dict = correlate_request_instance.to_dict()
# create an instance of CorrelateRequest from a dict
correlate_request_from_dict = CorrelateRequest.from_dict(correlate_request_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


