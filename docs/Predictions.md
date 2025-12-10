# Predictions

Future risk predictions

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**day7** | [**PredictionPoint**](PredictionPoint.md) | 7-day risk prediction | [optional] 
**day30** | [**PredictionPoint**](PredictionPoint.md) | 30-day risk prediction | [optional] 

## Example

```python
from whisper_api_sdk.models.predictions import Predictions

# TODO update the JSON string below
json = "{}"
# create an instance of Predictions from a JSON string
predictions_instance = Predictions.from_json(json)
# print the JSON string representation of the object
print(Predictions.to_json())

# convert the object into a dict
predictions_dict = predictions_instance.to_dict()
# create an instance of Predictions from a dict
predictions_from_dict = Predictions.from_dict(predictions_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


