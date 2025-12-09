# BulkIpLocationRequest

Request for bulk IP geolocation lookup

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**ips** | **List[str]** | List of IP addresses to lookup | 

## Example

```python
from whisper_api_sdk.models.bulk_ip_location_request import BulkIpLocationRequest

# TODO update the JSON string below
json = "{}"
# create an instance of BulkIpLocationRequest from a JSON string
bulk_ip_location_request_instance = BulkIpLocationRequest.from_json(json)
# print the JSON string representation of the object
print(BulkIpLocationRequest.to_json())

# convert the object into a dict
bulk_ip_location_request_dict = bulk_ip_location_request_instance.to_dict()
# create an instance of BulkIpLocationRequest from a dict
bulk_ip_location_request_from_dict = BulkIpLocationRequest.from_dict(bulk_ip_location_request_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


