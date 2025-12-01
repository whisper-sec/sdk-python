# BulkRequest

Request payload for bulk enrichment of multiple IP addresses and domains

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**indicators** | **List[str]** | List of indicators (IP addresses or domains) to enrich. Mix of IPs and domains is supported. | 
**include** | **List[str]** | Additional data modules to include for each indicator. Same options as single indicator endpoint. | [optional] 
**options** | [**BulkOptions**](BulkOptions.md) |  | [optional] 

## Example

```python
from whisper_api_sdk.models.bulk_request import BulkRequest

# TODO update the JSON string below
json = "{}"
# create an instance of BulkRequest from a JSON string
bulk_request_instance = BulkRequest.from_json(json)
# print the JSON string representation of the object
print(BulkRequest.to_json())

# convert the object into a dict
bulk_request_dict = bulk_request_instance.to_dict()
# create an instance of BulkRequest from a dict
bulk_request_from_dict = BulkRequest.from_dict(bulk_request_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


