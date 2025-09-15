# IpIntelligenceResponse

Comprehensive IP intelligence response containing geolocation, network, security, and relationship data

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**query** | [**IpIntelligenceResponseQuery**](IpIntelligenceResponseQuery.md) |  | [optional] 
**summary** | [**IpIntelligenceResponseSummary**](IpIntelligenceResponseSummary.md) |  | [optional] 
**geolocation** | [**IpIntelligenceResponseGeolocation**](IpIntelligenceResponseGeolocation.md) |  | [optional] 
**network** | **object** | Network and routing information | [optional] 
**isp** | **object** | ISP and organization details | [optional] 
**relationships** | **object** | DNS and infrastructure relationships | [optional] 
**reputation** | **object** | Reputation and threat intelligence | [optional] 
**security** | **object** | Security assessment and RPKI status | [optional] 
**validation** | **object** | IP validation details | [optional] 
**history** | **object** | Historical routing data | [optional] 
**asn_details** | **object** | ASN ownership and prefix details | [optional] 
**metadata** | **object** | Response metadata and data sources | [optional] 

## Example

```python
from noctis_frontgraph_sdk.models.ip_intelligence_response import IpIntelligenceResponse

# TODO update the JSON string below
json = "{}"
# create an instance of IpIntelligenceResponse from a JSON string
ip_intelligence_response_instance = IpIntelligenceResponse.from_json(json)
# print the JSON string representation of the object
print(IpIntelligenceResponse.to_json())

# convert the object into a dict
ip_intelligence_response_dict = ip_intelligence_response_instance.to_dict()
# create an instance of IpIntelligenceResponse from a dict
ip_intelligence_response_from_dict = IpIntelligenceResponse.from_dict(ip_intelligence_response_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


