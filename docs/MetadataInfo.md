# MetadataInfo

Response metadata including data sources and any errors encountered

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**data_sources** | **List[str]** | List of data sources used to build this response | [optional] 
**errors** | **List[str]** | Any non-fatal errors encountered during data collection. Empty if all sources succeeded. | [optional] 

## Example

```python
from whisper_api_sdk.models.metadata_info import MetadataInfo

# TODO update the JSON string below
json = "{}"
# create an instance of MetadataInfo from a JSON string
metadata_info_instance = MetadataInfo.from_json(json)
# print the JSON string representation of the object
print(MetadataInfo.to_json())

# convert the object into a dict
metadata_info_dict = metadata_info_instance.to_dict()
# create an instance of MetadataInfo from a dict
metadata_info_from_dict = MetadataInfo.from_dict(metadata_info_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


