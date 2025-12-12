# MonitorAssertions

Assertions to validate check results

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**headers** | **Dict[str, str]** | Expected response headers | [optional] 
**status_code** | **int** | Expected HTTP status code | [optional] 
**max_response_time** | **int** | Maximum response time in milliseconds | [optional] 
**contains_text** | **str** | Text that must be present in response body | [optional] 
**not_contains_text** | **str** | Text that must NOT be present in response body | [optional] 
**ssl_days_until_expiry** | **int** | Minimum SSL certificate days until expiry (for ssl checks) | [optional] 
**dns_record_value** | **str** | Expected DNS record value (for dns checks) | [optional] 
**dns_record_type** | **str** | DNS record type (for dns checks) | [optional] 

## Example

```python
from whisper_api_sdk.models.monitor_assertions import MonitorAssertions

# TODO update the JSON string below
json = "{}"
# create an instance of MonitorAssertions from a JSON string
monitor_assertions_instance = MonitorAssertions.from_json(json)
# print the JSON string representation of the object
print(MonitorAssertions.to_json())

# convert the object into a dict
monitor_assertions_dict = monitor_assertions_instance.to_dict()
# create an instance of MonitorAssertions from a dict
monitor_assertions_from_dict = MonitorAssertions.from_dict(monitor_assertions_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


