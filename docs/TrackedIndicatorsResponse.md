# TrackedIndicatorsResponse

Response containing a list of indicators being tracked for changes

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**count** | **int** | Total number of tracked indicators | [optional] 
**max_tracked** | **int** | Maximum number of indicators that can be tracked per API key | [optional] 
**indicators** | [**List[TrackedIndicator]**](TrackedIndicator.md) | List of tracked indicators | [optional] 

## Example

```python
from whisper_api_sdk.models.tracked_indicators_response import TrackedIndicatorsResponse

# TODO update the JSON string below
json = "{}"
# create an instance of TrackedIndicatorsResponse from a JSON string
tracked_indicators_response_instance = TrackedIndicatorsResponse.from_json(json)
# print the JSON string representation of the object
print(TrackedIndicatorsResponse.to_json())

# convert the object into a dict
tracked_indicators_response_dict = tracked_indicators_response_instance.to_dict()
# create an instance of TrackedIndicatorsResponse from a dict
tracked_indicators_response_from_dict = TrackedIndicatorsResponse.from_dict(tracked_indicators_response_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


