# ThreatProfile

Industry threat landscape

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**top_threats** | **List[str]** | Top threat types | [optional] 
**common_vectors** | **List[str]** | Common attack vectors | [optional] 
**attack_frequency** | **str** | Average attack frequency per month | [optional] 
**targeted_assets** | **List[str]** | Most targeted assets | [optional] 

## Example

```python
from whisper_api_sdk.models.threat_profile import ThreatProfile

# TODO update the JSON string below
json = "{}"
# create an instance of ThreatProfile from a JSON string
threat_profile_instance = ThreatProfile.from_json(json)
# print the JSON string representation of the object
print(ThreatProfile.to_json())

# convert the object into a dict
threat_profile_dict = threat_profile_instance.to_dict()
# create an instance of ThreatProfile from a dict
threat_profile_from_dict = ThreatProfile.from_dict(threat_profile_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


