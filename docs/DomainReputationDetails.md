# DomainReputationDetails

Detailed infrastructure and individual IP scores

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**domain_ips** | **List[str]** | Domain&#39;s A record IP addresses | [optional] 
**domain_ip_scores** | **Dict[str, float]** | Individual scores for each domain IP | [optional] 
**nameserver_domains** | **List[str]** | Nameserver domain names | [optional] 
**nameserver_ips** | **List[str]** | IP addresses of nameservers | [optional] 
**nameserver_ip_scores** | **Dict[str, float]** | Individual scores for each nameserver IP | [optional] 
**mailserver_domains** | **List[str]** | Mail server domain names | [optional] 
**mailserver_ips** | **List[str]** | IP addresses of mail servers | [optional] 
**mailserver_ip_scores** | **Dict[str, float]** | Individual scores for each mail server IP | [optional] 

## Example

```python
from whisper_api_sdk.models.domain_reputation_details import DomainReputationDetails

# TODO update the JSON string below
json = "{}"
# create an instance of DomainReputationDetails from a JSON string
domain_reputation_details_instance = DomainReputationDetails.from_json(json)
# print the JSON string representation of the object
print(DomainReputationDetails.to_json())

# convert the object into a dict
domain_reputation_details_dict = domain_reputation_details_instance.to_dict()
# create an instance of DomainReputationDetails from a dict
domain_reputation_details_from_dict = DomainReputationDetails.from_dict(domain_reputation_details_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


