# DomainIntelligenceResponse

Comprehensive domain intelligence response containing registration, DNS, relationships, and IP data

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**query** | [**DomainIntelligenceResponseQuery**](DomainIntelligenceResponseQuery.md) |  | [optional] 
**summary** | [**DomainIntelligenceResponseSummary**](DomainIntelligenceResponseSummary.md) |  | [optional] 
**registration** | **object** | WHOIS registration details | [optional] 
**dns** | **object** | DNS records (A, AAAA, MX, NS, TXT, etc.) | [optional] 
**relationships** | **object** | Related domains and infrastructure | [optional] 
**trademark** | **object** | Trademark information | [optional] 
**ip_intelligence** | **object** | Intelligence for resolved IP addresses | [optional] 
**metadata** | **object** | Response metadata and data sources | [optional] 

## Example

```python
from noctis_frontgraph_sdk.models.domain_intelligence_response import DomainIntelligenceResponse

# TODO update the JSON string below
json = "{}"
# create an instance of DomainIntelligenceResponse from a JSON string
domain_intelligence_response_instance = DomainIntelligenceResponse.from_json(json)
# print the JSON string representation of the object
print(DomainIntelligenceResponse.to_json())

# convert the object into a dict
domain_intelligence_response_dict = domain_intelligence_response_instance.to_dict()
# create an instance of DomainIntelligenceResponse from a dict
domain_intelligence_response_from_dict = DomainIntelligenceResponse.from_dict(domain_intelligence_response_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


