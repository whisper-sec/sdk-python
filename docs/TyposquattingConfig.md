# TyposquattingConfig

Configuration for typosquatting variations

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**character_omission** | **bool** | Include character omission variations | [optional] [default to True]
**character_swap** | **bool** | Include character swap variations | [optional] [default to True]
**double_character** | **bool** | Include double character variations | [optional] [default to True]
**keyboard_proximity** | **bool** | Include keyboard proximity variations | [optional] [default to True]

## Example

```python
from whisper_api_sdk.models.typosquatting_config import TyposquattingConfig

# TODO update the JSON string below
json = "{}"
# create an instance of TyposquattingConfig from a JSON string
typosquatting_config_instance = TyposquattingConfig.from_json(json)
# print the JSON string representation of the object
print(TyposquattingConfig.to_json())

# convert the object into a dict
typosquatting_config_dict = typosquatting_config_instance.to_dict()
# create an instance of TyposquattingConfig from a dict
typosquatting_config_from_dict = TyposquattingConfig.from_dict(typosquatting_config_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


