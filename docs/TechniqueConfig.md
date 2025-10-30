# TechniqueConfig

Detailed configuration for each domain variation technique

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**typosquatting** | [**TyposquattingConfig**](TyposquattingConfig.md) |  | [optional] 
**homoglyph** | [**HomoglyphConfig**](HomoglyphConfig.md) |  | [optional] 
**bitsquatting** | [**BitsquattingConfig**](BitsquattingConfig.md) |  | [optional] 
**tld_variation** | [**TldVariationConfig**](TldVariationConfig.md) |  | [optional] 

## Example

```python
from whisper_api_sdk.models.technique_config import TechniqueConfig

# TODO update the JSON string below
json = "{}"
# create an instance of TechniqueConfig from a JSON string
technique_config_instance = TechniqueConfig.from_json(json)
# print the JSON string representation of the object
print(TechniqueConfig.to_json())

# convert the object into a dict
technique_config_dict = technique_config_instance.to_dict()
# create an instance of TechniqueConfig from a dict
technique_config_from_dict = TechniqueConfig.from_dict(technique_config_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


