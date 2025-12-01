# SubdomainResponse

Response containing discovered subdomains and related metadata

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**domain** | **str** | The root domain that was queried | 
**total_count** | **int** | Total number of subdomains discovered | 
**subdomains** | [**List[SubdomainInfo]**](SubdomainInfo.md) | List of discovered subdomains | 
**timestamp** | **datetime** | Timestamp of when the data was retrieved | 
**sources** | **List[str]** | Data sources used for subdomain discovery | [optional] 

## Example

```python
from whisper_api_sdk.models.subdomain_response import SubdomainResponse

# TODO update the JSON string below
json = "{}"
# create an instance of SubdomainResponse from a JSON string
subdomain_response_instance = SubdomainResponse.from_json(json)
# print the JSON string representation of the object
print(SubdomainResponse.to_json())

# convert the object into a dict
subdomain_response_dict = subdomain_response_instance.to_dict()
# create an instance of SubdomainResponse from a dict
subdomain_response_from_dict = SubdomainResponse.from_dict(subdomain_response_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


