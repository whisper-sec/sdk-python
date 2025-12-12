# IndicatorResponse

Comprehensive intelligence response for an IP address or domain indicator

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**query** | [**QueryInfo**](QueryInfo.md) | Query metadata including the indicator type, value, and response timing | [optional] 
**summary** | [**SummaryInfo**](SummaryInfo.md) | Executive summary with key facts about the indicator for quick decision-making | [optional] 
**geolocation** | **object** |  | [optional] 
**network** | **object** |  | [optional] 
**routing** | **object** |  | [optional] 
**isp** | **object** |  | [optional] 
**registration** | **object** |  | [optional] 
**dns** | [**DnsInfo**](DnsInfo.md) | DNS records and resolution data | [optional] 
**relationships** | [**RelationshipInfo**](RelationshipInfo.md) | Relationship data showing connections to other infrastructure | [optional] 
**reputation** | [**ReputationInfo**](ReputationInfo.md) | Reputation and risk scoring information | [optional] 
**security** | **object** |  | [optional] 
**rpki** | **object** |  | [optional] 
**ip_intelligence** | **Dict[str, object]** | When domain is queried with include&#x3D;ip_intelligence, contains full intelligence for each resolved IP | [optional] 
**metadata** | [**MetadataInfo**](MetadataInfo.md) | Response metadata including data sources, errors, and processing information | [optional] 

## Example

```python
from whisper_api_sdk.models.indicator_response import IndicatorResponse

# TODO update the JSON string below
json = "{}"
# create an instance of IndicatorResponse from a JSON string
indicator_response_instance = IndicatorResponse.from_json(json)
# print the JSON string representation of the object
print(IndicatorResponse.to_json())

# convert the object into a dict
indicator_response_dict = indicator_response_instance.to_dict()
# create an instance of IndicatorResponse from a dict
indicator_response_from_dict = IndicatorResponse.from_dict(indicator_response_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


