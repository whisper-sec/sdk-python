# ScanRequest

Request for initiating a domain infrastructure scan

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**domain** | **str** | The target domain to scan | 
**type** | **str** | Type of scan to perform. Determines which scanning module to use. | [optional] [default to 'comprehensive']

## Example

```python
from whisper_api_sdk.models.scan_request import ScanRequest

# TODO update the JSON string below
json = "{}"
# create an instance of ScanRequest from a JSON string
scan_request_instance = ScanRequest.from_json(json)
# print the JSON string representation of the object
print(ScanRequest.to_json())

# convert the object into a dict
scan_request_dict = scan_request_instance.to_dict()
# create an instance of ScanRequest from a dict
scan_request_from_dict = ScanRequest.from_dict(scan_request_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


