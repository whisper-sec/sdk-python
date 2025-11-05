# BitsquattingConfig

Configuration for bitsquatting (bit-flip) variations

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**max_bit_flips** | **int** | Maximum bit flips per character | [optional] [default to 1]

## Example

```python
from whisper_api_sdk.models.bitsquatting_config import BitsquattingConfig

# TODO update the JSON string below
json = "{}"
# create an instance of BitsquattingConfig from a JSON string
bitsquatting_config_instance = BitsquattingConfig.from_json(json)
# print the JSON string representation of the object
print(BitsquattingConfig.to_json())

# convert the object into a dict
bitsquatting_config_dict = bitsquatting_config_instance.to_dict()
# create an instance of BitsquattingConfig from a dict
bitsquatting_config_from_dict = BitsquattingConfig.from_dict(bitsquatting_config_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


