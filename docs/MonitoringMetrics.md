# MonitoringMetrics

Monitoring metrics and statistics for the target

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**uptime_percentage** | **float** | Uptime percentage over the last 30 days | [optional] 
**avg_response_time** | **int** | Average response time in milliseconds | [optional] 
**ssl_expires_in_days** | **int** | Days until SSL certificate expires | [optional] 
**dns_change_count** | **int** | Number of DNS change events detected | [optional] 
**whois_change_count** | **int** | Number of WHOIS change events detected | [optional] 
**last_check_at** | **str** | Timestamp of last successful check | [optional] 
**current_status** | **str** | Current check status | [optional] 

## Example

```python
from whisper_api_sdk.models.monitoring_metrics import MonitoringMetrics

# TODO update the JSON string below
json = "{}"
# create an instance of MonitoringMetrics from a JSON string
monitoring_metrics_instance = MonitoringMetrics.from_json(json)
# print the JSON string representation of the object
print(MonitoringMetrics.to_json())

# convert the object into a dict
monitoring_metrics_dict = monitoring_metrics_instance.to_dict()
# create an instance of MonitoringMetrics from a dict
monitoring_metrics_from_dict = MonitoringMetrics.from_dict(monitoring_metrics_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


