# IpIntelligenceResponseSummary

Executive summary of IP intelligence

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**organization** | **str** | Organization name | [optional] 
**location** | **str** | Geographic location | [optional] 
**network** | **str** | Network prefix | [optional] 
**asn_primary** | **str** | Primary ASN | [optional] 
**risk_score** | **float** | Risk score (0-1) | [optional] 
**ip_type** | **str** | IP type classification | [optional] 
**total_domains** | **int** | Number of associated domains | [optional] 
**total_dns_records** | **int** | Number of DNS records | [optional] 

## Example

```python
from noctis_frontgraph_sdk.models.ip_intelligence_response_summary import IpIntelligenceResponseSummary

# TODO update the JSON string below
json = "{}"
# create an instance of IpIntelligenceResponseSummary from a JSON string
ip_intelligence_response_summary_instance = IpIntelligenceResponseSummary.from_json(json)
# print the JSON string representation of the object
print(IpIntelligenceResponseSummary.to_json())

# convert the object into a dict
ip_intelligence_response_summary_dict = ip_intelligence_response_summary_instance.to_dict()
# create an instance of IpIntelligenceResponseSummary from a dict
ip_intelligence_response_summary_from_dict = IpIntelligenceResponseSummary.from_dict(ip_intelligence_response_summary_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


