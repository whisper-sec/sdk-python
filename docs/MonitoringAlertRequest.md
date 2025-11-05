# MonitoringAlertRequest

Configuration for creating monitoring alert rules with notification channels

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**type** | **str** | Type of alert condition to monitor | 
**threshold_days** | **int** | Threshold in days (for ssl_expiring alerts). Alert triggers when SSL cert expires within this many days. | [optional] 
**channels** | **List[str]** | Notification channels to use for alerts | [optional] 
**email** | **str** | Email address for alert notifications | [optional] 
**slack_webhook** | **str** | Slack webhook URL for notifications | [optional] 
**webhook_url** | **str** | Custom webhook URL for notifications (will receive POST with alert data) | [optional] 
**pagerduty_key** | **str** | PagerDuty integration key for incident creation | [optional] 

## Example

```python
from whisper_api_sdk.models.monitoring_alert_request import MonitoringAlertRequest

# TODO update the JSON string below
json = "{}"
# create an instance of MonitoringAlertRequest from a JSON string
monitoring_alert_request_instance = MonitoringAlertRequest.from_json(json)
# print the JSON string representation of the object
print(MonitoringAlertRequest.to_json())

# convert the object into a dict
monitoring_alert_request_dict = monitoring_alert_request_instance.to_dict()
# create an instance of MonitoringAlertRequest from a dict
monitoring_alert_request_from_dict = MonitoringAlertRequest.from_dict(monitoring_alert_request_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


