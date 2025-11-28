# SubdomainInfo

Detailed information about a discovered subdomain

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**subdomain** | **str** | The full subdomain name | 
**ip_addresses** | **List[str]** | IP addresses associated with the subdomain | [optional] 
**first_seen** | **datetime** | First time this subdomain was observed | [optional] 
**last_seen** | **datetime** | Last time this subdomain was observed | [optional] 
**record_type** | **str** | Type of subdomain record | [optional] 
**status** | **str** | Current status of the subdomain | [optional] 
**technologies** | **List[str]** | Technology stack detected on this subdomain | [optional] 
**risk_score** | **int** | Risk score for this subdomain (0-100) | [optional] 

## Example

```python
from whisper_api_sdk.models.subdomain_info import SubdomainInfo

# TODO update the JSON string below
json = "{}"
# create an instance of SubdomainInfo from a JSON string
subdomain_info_instance = SubdomainInfo.from_json(json)
# print the JSON string representation of the object
print(SubdomainInfo.to_json())

# convert the object into a dict
subdomain_info_dict = subdomain_info_instance.to_dict()
# create an instance of SubdomainInfo from a dict
subdomain_info_from_dict = SubdomainInfo.from_dict(subdomain_info_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


