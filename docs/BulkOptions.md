# BulkOptions

Advanced configuration options for bulk processing behavior

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**parallel_processing** | **bool** | Enable parallel processing of indicators for faster results | [optional] [default to True]
**batch_size** | **int** | Number of indicators to process in each batch. Smaller batches &#x3D; more frequent progress updates | [optional] [default to 10]
**timeout_per_indicator** | **int** | Maximum time in milliseconds to wait for each indicator before timing out. Domain enrichment and ip_intelligence require longer timeouts. | [optional] [default to 30000]
**continue_on_error** | **bool** | Continue processing remaining indicators if one fails. Recommended for large batches. | [optional] [default to True]
**include_failed** | **bool** | Include failed indicators in the response with error details | [optional] [default to False]

## Example

```python
from whisper_api_sdk.models.bulk_options import BulkOptions

# TODO update the JSON string below
json = "{}"
# create an instance of BulkOptions from a JSON string
bulk_options_instance = BulkOptions.from_json(json)
# print the JSON string representation of the object
print(BulkOptions.to_json())

# convert the object into a dict
bulk_options_dict = bulk_options_instance.to_dict()
# create an instance of BulkOptions from a dict
bulk_options_from_dict = BulkOptions.from_dict(bulk_options_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


