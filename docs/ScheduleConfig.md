# ScheduleConfig

Configuration for scheduling recurring screenshot captures

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**cron** | **str** | Cron expression for scheduling | [optional] 
**frequency** | **str** | Frequency of captures | [optional] 
**timezone** | **str** | Timezone for scheduled captures | [optional] [default to 'UTC']
**retention_count** | **int** | Maximum number of captures to retain | [optional] [default to 30]
**enabled** | **bool** | Enable/disable the schedule | [optional] [default to True]

## Example

```python
from whisper_api_sdk.models.schedule_config import ScheduleConfig

# TODO update the JSON string below
json = "{}"
# create an instance of ScheduleConfig from a JSON string
schedule_config_instance = ScheduleConfig.from_json(json)
# print the JSON string representation of the object
print(ScheduleConfig.to_json())

# convert the object into a dict
schedule_config_dict = schedule_config_instance.to_dict()
# create an instance of ScheduleConfig from a dict
schedule_config_from_dict = ScheduleConfig.from_dict(schedule_config_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


