# HomoglyphConfig

Configuration for homoglyph (look-alike character) variations

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**cyrillic** | **bool** | Include Cyrillic character substitutions | [optional] [default to True]
**greek** | **bool** | Include Greek character substitutions | [optional] [default to True]
**latin** | **bool** | Include Latin character substitutions | [optional] [default to True]
**max_substitutions** | **int** | Maximum number of character substitutions per domain | [optional] [default to 2]

## Example

```python
from whisper_api_sdk.models.homoglyph_config import HomoglyphConfig

# TODO update the JSON string below
json = "{}"
# create an instance of HomoglyphConfig from a JSON string
homoglyph_config_instance = HomoglyphConfig.from_json(json)
# print the JSON string representation of the object
print(HomoglyphConfig.to_json())

# convert the object into a dict
homoglyph_config_dict = homoglyph_config_instance.to_dict()
# create an instance of HomoglyphConfig from a dict
homoglyph_config_from_dict = HomoglyphConfig.from_dict(homoglyph_config_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


