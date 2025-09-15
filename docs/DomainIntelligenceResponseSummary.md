# DomainIntelligenceResponseSummary


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**domain_name** | **str** | Domain name | [optional] 
**registrar** | **str** | Domain registrar | [optional] 
**registration_date** | **str** | Registration date | [optional] 
**expiration_date** | **str** | Expiration date | [optional] 
**status** | **str** | Domain status | [optional] 
**has_trademark** | **bool** | Trademark status | [optional] 
**dns_provider** | **str** | Primary DNS provider | [optional] 
**total_links_in** | **int** | Incoming links | [optional] 
**total_links_out** | **int** | Outgoing links | [optional] 

## Example

```python
from noctis_frontgraph_sdk.models.domain_intelligence_response_summary import DomainIntelligenceResponseSummary

# TODO update the JSON string below
json = "{}"
# create an instance of DomainIntelligenceResponseSummary from a JSON string
domain_intelligence_response_summary_instance = DomainIntelligenceResponseSummary.from_json(json)
# print the JSON string representation of the object
print(DomainIntelligenceResponseSummary.to_json())

# convert the object into a dict
domain_intelligence_response_summary_dict = domain_intelligence_response_summary_instance.to_dict()
# create an instance of DomainIntelligenceResponseSummary from a dict
domain_intelligence_response_summary_from_dict = DomainIntelligenceResponseSummary.from_dict(domain_intelligence_response_summary_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


