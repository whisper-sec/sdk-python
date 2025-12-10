# AnalysisMetadata

Metadata about the similarity search that was performed

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**techniques_used** | **str** | Comma-separated list of backend similarity types that were used | 
**base_domain** | **str** | The base domain that was searched | 
**search_limit** | **int** | The limit that was applied to the search | 

## Example

```python
from whisper_api_sdk.models.analysis_metadata import AnalysisMetadata

# TODO update the JSON string below
json = "{}"
# create an instance of AnalysisMetadata from a JSON string
analysis_metadata_instance = AnalysisMetadata.from_json(json)
# print the JSON string representation of the object
print(AnalysisMetadata.to_json())

# convert the object into a dict
analysis_metadata_dict = analysis_metadata_instance.to_dict()
# create an instance of AnalysisMetadata from a dict
analysis_metadata_from_dict = AnalysisMetadata.from_dict(analysis_metadata_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


