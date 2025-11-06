# TldVariationConfig

Configuration for top-level domain variations

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**common_tlds** | **bool** | Include common TLD variations (.com, .net, .org, etc.) | [optional] [default to True]
**country_tlds** | **bool** | Include country-code TLDs | [optional] [default to False]
**new_gtlds** | **bool** | Include new generic TLDs (.app, .dev, .cloud, etc.) | [optional] [default to True]
**custom_tlds** | **List[str]** | Custom TLDs to check | [optional] 

## Example

```python
from whisper_api_sdk.models.tld_variation_config import TldVariationConfig

# TODO update the JSON string below
json = "{}"
# create an instance of TldVariationConfig from a JSON string
tld_variation_config_instance = TldVariationConfig.from_json(json)
# print the JSON string representation of the object
print(TldVariationConfig.to_json())

# convert the object into a dict
tld_variation_config_dict = tld_variation_config_instance.to_dict()
# create an instance of TldVariationConfig from a dict
tld_variation_config_from_dict = TldVariationConfig.from_dict(tld_variation_config_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


