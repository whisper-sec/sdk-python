# SummaryInfo

Executive summary with the most important facts for quick decision-making

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**organization** | **str** | Primary organization name | [optional] 
**location** | **str** | Primary location | [optional] 
**network** | **str** | Network range or CIDR | [optional] 
**registrar** | **str** | Domain registrar | [optional] 
**status** | **str** | Domain status | [optional] 
**asn_primary** | **str** | Primary ASN | [optional] 
**risk_score** | **float** | Composite risk score (0-10, higher is riskier) | [optional] 
**ip_type** | **str** | IP classification | [optional] 
**total_domains** | **int** | Total number of domains resolving to this IP | [optional] 
**domain_name** | **str** | The domain name | [optional] 
**registration_date** | **str** | Domain registration date | [optional] 
**expiration_date** | **str** | Domain expiration date | [optional] 
**dns_provider** | **str** | Primary DNS provider | [optional] 
**total_links_in** | **int** | Number of incoming links/backlinks | [optional] 
**total_links_out** | **int** | Number of outgoing links | [optional] 

## Example

```python
from whisper_api_sdk.models.summary_info import SummaryInfo

# TODO update the JSON string below
json = "{}"
# create an instance of SummaryInfo from a JSON string
summary_info_instance = SummaryInfo.from_json(json)
# print the JSON string representation of the object
print(SummaryInfo.to_json())

# convert the object into a dict
summary_info_dict = summary_info_instance.to_dict()
# create an instance of SummaryInfo from a dict
summary_info_from_dict = SummaryInfo.from_dict(summary_info_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


