# InfraScanRequest

Configuration for performing infrastructure discovery and security scanning

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**target** | **str** | The target to scan (IP, CIDR, domain, or ASN) | 
**target_type** | **str** | Type of target being scanned | 
**scan_types** | **List[str]** | Types of scans to perform | [optional] 
**scan_depth** | **str** | Scan depth level | [optional] [default to 'medium']
**timeout** | **int** | Maximum scan duration in seconds | [optional] [default to 300]
**options** | [**ScanOptions**](ScanOptions.md) |  | [optional] 

## Example

```python
from whisper_api_sdk.models.infra_scan_request import InfraScanRequest

# TODO update the JSON string below
json = "{}"
# create an instance of InfraScanRequest from a JSON string
infra_scan_request_instance = InfraScanRequest.from_json(json)
# print the JSON string representation of the object
print(InfraScanRequest.to_json())

# convert the object into a dict
infra_scan_request_dict = infra_scan_request_instance.to_dict()
# create an instance of InfraScanRequest from a dict
infra_scan_request_from_dict = InfraScanRequest.from_dict(infra_scan_request_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


